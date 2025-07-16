# Tools for Multiple Sequence Alignment Visualization



## 🔧 Tool 1: Clustal Omega + ESPript3

### Step 1: Perform Alignment with Clustal Omega

[Clustal Omega](https://www.ebi.ac.uk/jdispatcher/msa/clustalo) is a fast and scalable MSA tool developed by EMBL-EBI. It can handle large datasets and outputs high-quality alignments in several formats (Clustal, FASTA, PHYLIP, etc.).

**How to use:**
1. Go to [Clustal Omega webserver](https://www.ebi.ac.uk/jdispatcher/msa/clustalo).
2. Paste your protein sequences in FASTA format.
3. Choose the output format as **Clustal (.aln)**.
4. Click *Submit* to run the alignment.
5. Download the resulting `.aln` file.

### Step 2: Visualize with ESPript3

Once you have the `.aln` file, use [ESPript3](https://espript.ibcp.fr/ESPript/ESPript/) to generate a clean and customizable graphical output of your alignment.

**Key Features of ESPript3:**
- Color-coding of conserved residues
- Secondary structure annotation
- Logo-style conservation bars
- Supports both sequence-only and structure-based alignments

**How to use:**
1. Go to the ESPript3 server.
2. Upload your `.aln` file under the “MSA file” section.
3. Customize visualization options (color schemes, numbering, secondary structure overlay, etc.).
4. Click *Submit* to generate a PDF or PostScript output of the alignment.

> 🔍 *Tip: ESPript3 works best with Clustal or aligned FASTA files. You can also upload a PDB file to overlay secondary structure.*

---

## 🔧 Tool 2: JalView

[JalView](https://www.jalview.org) is a powerful desktop application for alignment visualization, editing, and analysis.

**Key Features:**
- Interactive GUI for manual adjustment of alignments
- Real-time coloring by conservation, hydrophobicity, charge, etc.
- Integrated phylogenetic tree generation
- Secondary structure prediction and RNA structure support
- Export to various formats including PNG, HTML, or EPS

**How to use:**
1. Download and install JalView from [https://www.jalview.org](https://www.jalview.org).
2. Open JalView and import your sequences (FASTA or Clustal).
3. Use the *Calculate* menu to align sequences (via Clustal or MAFFT).
4. Customize colors and layout from the *Colour* and *Format* menus.
5. Export figures or save project files for sharing and future edits.


---



---
