---
tags: [magnific-ai, ki-tools, ebay, produktfotografie, workflow]
status: aktiv
date: 2026-08-07
---

# eBay Produktfoto-Workflow in Magnific AI Spaces

Workflow-Projekt "Product Enhancer": Beliebige Produktfotos (z.B. gebrauchte Monitore) werden automatisiert in professionell wirkende, aber ehrliche eBay-Produktbilder verwandelt. Entwickelt über mehrere Sessions mit Gemini, dokumentiert hier als Referenz für dich selbst.

## Ziel des Workflows

- Beliebig viele Ausgangsbilder eines Produkts hochladen können
- Für jedes einzelne Bild (nicht nur ein Gesamtbild) eine aufgewertete Version erzeugen
- Pro Bild zusätzlich 2 leichte Blickwinkel-Varianten
- Wichtig: Das Produkt darf nicht verfälscht werden. Kratzer, Gebrauchsspuren, Logos, Anschlüsse müssen exakt erhalten bleiben, da es sich um einen echten Verkaufsartikel handelt (keine Fake-Bilder, rechtlich und ethisch heikel bei eBay)
- Zwei Varianten je nach Bildtyp:
  - Kontext-Aufnahme (Produkt im Raum, z.B. Monitor auf Schreibtisch): bekommt festen, wiederkehrenden Hintergrund für Wiedererkennungswert
  - Makro-/Detailaufnahme (z.B. Typenschild, Anschlüsse): wird nur aufpoliert, kein Hintergrund-Ersatz

## Node-Bibliothek (Pro-Abo, Stand August 2026)

Magnific Spaces hat keine generischen Nodes wie "Vision" oder "Iterator", sondern direkte Nodes für konkrete Modelle/Tools. Wichtig für den Workflow:

- **KI-Assistent** – universeller LLM-Node (Modelle: Claude Sonnet 5, Claude Opus 4.8, Claude Fable 5, GPT-5.6 Terra/Sol/Luna, GPT-5 Mini, Gemini 3.1 Pro, Gemini 3.5 Flash, u.a.). Kann Bilder über Media-Eingang analysieren und Text ausgeben. Ersetzt einen separaten "Vision"-Node, den es nicht gibt.
- **Bildgeneratoren**: Google Nano Banana / Nano Banana Pro / Nano Banana 2, Google Imagen 3/4/4 Fast/4 Ultra, Flux.1 Realism, Qwen Image 3.0, Ideogram, MAI Image 2.5 u.a.
- **Bild-Hochskalierer**: Modi u.a. Precision (Clarity) – originalgetreu, erfindet keine Details; Creative – kann Details erfinden/glätten (für eBay ungeeignet, da Kratzer wegretuschiert würden)
- **Variationen** / **Kamerawinkel ändern** – erzeugt leichte Perspektivwechsel eines Bildes
- **Relight** – Beleuchtung eines Bildes verändern
- **Hintergrundentferner**, **Manuelle Auswahl**, **List** (Batch-/Stapelverarbeitung), **Text**, **Gruppe**
- Es gibt **keinen** "Medien-Kombinierer" und **keinen** "Iterator"/"For Each"-Node (ChatGPT hatte das fälschlich vorgeschlagen). Mehrere Bild-Nodes können aber direkt in den Media-Eingang eines KI-Assistenten gezogen werden.

## Finale Workflow-Architektur

```
Text-Input (Produktname/Modell, manuell)
        │
Referenzbild (fixer, immer gleicher Hintergrund/Setting)
        │
List #1 (Produktfotos, "Elemente Beibehalten")
        │
        ├──► KI-Assistent 1 (Claude Sonnet 5) – Produkt-Analyse
        │            │
Referenzbild ──► Referenz-Assistent – Setting-Analyse (separat, einmalig)
        │            │
        └────► KI-Assistent 2 (GPT-5.6 Sol) – kombiniert beide Analysen zu finalem Bild-Prompt
                     │ (List #2, "Elemente Ersetzen")
                     ▼
        Bild-Hochskalierer / Bildgenerator (Precision-Modus, direkt mit List #1 verbunden)
                     │
              Variationen (2 Stück, ähnliche Perspektive)
                     │
              Output-Liste (fertige Bilder, "Elemente Beibehalten")
```

Drei getrennte KI-Assistenten statt einem: einer analysiert nur das Produktfoto, einer nur das Referenz-Setting, der dritte kombiniert beides zum finalen Prompt. Das trennt Analyse und Prompterstellung sauber und macht das System modular.

## Die drei finalen Prompts

### Referenz-Assistent (Input: nur das feste Setting-Referenzbild)
```
Analyze ONLY the attached reference image.
TASK:
Provide a detailed photographic breakdown of the background environment and setup.
Describe:
1. Surface & Background: Textures, materials, background elements, colors, and spatial setting.
2. Lighting & Perspective: Light angle, shadow intensity/softness, camera elevation, and framing distance.
Goal: Provide a structured raw text description of this exact room/background setting so another AI can replicate the scene seamlessly.
```

### KI-Assistent 1 (Input: Produktbild aus der Liste + Text-Input Modellname)
```
Analyze ONLY the attached image of the item.
INPUT DATA:
- Image: Attached photo of the item.
- User-provided Product Name/Model: Read the incoming text input. If specific details are given, use them as fact. If empty or unclear, analyze the image to identify the item.
TASK:
1. Identify exact product/item based on provided text + visual features.
2. Photographic Context Decision: Determine if this is a photographic contextual shot (item seen as a whole in an environment/background) OR a macro/detail shot (close-up of text, labels, textures, or a component, with minimal to no visible background).
3. Describe the item's details, framing, and specific photographic flaws (underexposed, weak contrast, glare over text, motion blur, etc.).
Goal: Provide structured raw text analysis, explicitly stating if it's a context shot or a macro/detail shot.
```

### KI-Assistent 2 (Input: Text von Assistent 1 + Text vom Referenz-Assistenten)
```
Create a detailed, high-realism photo-enhancement prompt in English.
INPUTS RECEIVED:
- Product/Item Analysis (from Assistant 1)
- Reference Background Analysis (from Reference Assistant)
LOGIC & COMPOSITION DECISION:
1. First, check Assistant 1's analysis: Is the product image a context shot or a macro/detail shot?
2. Context Shot: IF it's a context shot, seamlessly place the product from Assistant 1 onto the background from the Reference Assistant, strictly maintaining the scene description (lighting, perspective, framing) of the Reference.
3. Macro/Detail Shot: IF it's a macro/detail shot, DO NOT use the Reference Background. Focus 100% on enhancing the original detail image from Assistant 1.
STRICT REQUIREMENTS FOR REALISM & E-COMMERCE TRUST:
- AUTHENTIC ENHANCEMENT: Improve exposure, fix white balance, sharpen details (especially text), enhance contrast, and remove distracting glare or blur.
- PRESERVE REALITY: Maintain the original physical state.
- NO CGI LOOK: Must look like a high-end photo from a professional DSLR.
Output the plain text prompt ONLY.
```

Bewusst produktunabhängig formuliert (kein "wooden desk" o.ä. fest im Prompt), damit derselbe Workflow später auch für T-Shirts, Schuhe usw. mit anderem Referenzbild funktioniert.

### Negative Prompt (falls Feld vorhanden)
```
cgi, 3d render, white background, stock photo, fake reflections, artificial look, smooth plastic texture, altered object geometry, removed details, cartoon, watermark, text, cropped, people, hands
```

## Wichtige technische Erkenntnisse

**Upload-Node:** Es gibt keinen leeren "Input"-Node. Beim Erstellen öffnet sich sofort der Datei-Explorer, man muss direkt eine Datei wählen. Workflow einmal mit Testbild bauen, später Bilder im Upload-Node austauschen.

**List-Node Einstellung "Elemente Ersetzen" vs. "Elemente Beibehalten"** – das war der Kernfehler, der lange gesucht wurde:
- Input-Bild-Liste (Originalfotos): **Elemente Beibehalten** – hält den ganzen Stapel als Basis für die Batch-Verarbeitung
- Zwischen-Listen mit Text-Prompts (Ausgabe der KI-Assistenten): **Elemente Ersetzen** – sonst sammeln sich alte Prompts an und der Bildgenerator bekommt am Ende alle Prompts gleichzeitig statt nacheinander
- Output-Bild-Listen (fertige Ergebnisse): **Elemente Beibehalten** – sammelt alle fertigen Bilder

**Das Referenzbild-Akkumulations-Problem:** Wenn eine Liste mit mehreren Bildern direkt an den Bild-/Referenz-Eingang eines Bildgenerators gehängt wird, lädt Magnific alle Bilder gleichzeitig als Multi-Referenz in die Referenzbild-Slots – auch wenn man die Verbindung neu herstellt, sammeln sich die Slots wieder automatisch auf. Ergebnis: Der Generator vermischt alle Ansichten und erzeugt bei jedem Durchlauf fast dasselbe (meist die dominante Frontalansicht), statt jedes Bild einzeln zu verarbeiten.

Es gibt **keinen Iterator-Node** in Magnific Spaces, um das sauber zu lösen (anders als in Make/n8n/ComfyUI). Getestete Lösungsansätze:
1. Bild-Kabel zum Generator komplett kappen, nur über die individuellen Text-Prompts (aus KI-Assistent 2) je Bild steuern lassen – funktioniert zuverlässig, aber ohne visuelle Referenz besteht Halluzinationsrisiko (z.B. falsche Anschlüsse), was für eBay riskant ist.
2. Alternative: Image-to-Image-/Restyle-Modus des Bildgenerators nutzen (bzw. Relight-Node) statt reinem Text-zu-Bild-Generator – nimmt ein Eingangsbild als harte visuelle Vorlage und verarbeitet die Liste dadurch Frame für Frame synchron zum Prompt, statt alle Referenzen zu vermischen. **Das war der letzte offene Lösungsansatz, noch nicht abschließend getestet.**
3. Per Prompt steuern ("nutze nur Referenzbild 2") funktioniert **nicht** – der Bildgenerator kann Referenzbilder nicht per Text indizieren, er sieht sie immer als einen gemeinsamen Pool.

**Precision statt Creative beim Hochskalieren:** Creative-Modus kann Kratzer/Gebrauchsspuren wegretuschieren oder Details erfinden – für eBay (Käuferschutz, Ehrlichkeit) ungeeignet. Immer Precision (Clarity) verwenden.

**Genereller Realismus-Fix:** Erste Workflow-Version hat einen zu "gekünstelten" Studio-Look mit weißem CGI-Hintergrund erzeugt, der nicht dem echten Produktzustand entsprach. Umgestellt auf: echten Hintergrund/echtes Setting beibehalten (bzw. festes Referenzbild verwenden), nur Belichtung/Schärfe/Kontrast/Weißabgleich verbessern, explizit keine CGI-/Stockfoto-Optik.

## Offener Punkt / nächster Schritt

Testen, ob der Image-to-Image- bzw. Relight-Ansatz (Lösungsansatz 2 oben) das Referenzbild-Akkumulations-Problem tatsächlich behebt, ohne die visuelle Bildreferenz zu verlieren. Falls nicht: Workaround über Duplizieren einzelner Stränge pro Bild (ein kompletter Node-Strang je Produktfoto statt Batch über List-Node).
