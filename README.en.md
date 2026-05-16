<div align="center">

# ✦ ClearQC

**Quantum chemistry, right on your own computer**

[📥 Download](https://github.com/SigmaAdrich/ClearQC/releases/latest) · [🐛 Report Issues](https://github.com/SigmaAdrich/ClearQC/issues)

**[中文](README.md) · English · [Deutsch](README.de.md) · [日本語](README.ja.md)**

</div>

---

## What is this?

Have you ever wondered — **what does a molecule actually look like? How are its electrons distributed? Why does one bond break, but another doesn't?**

In theory, these questions can be answered by quantum mechanics — that's exactly what "quantum chemistry" or "computational chemistry" does.

But traditionally, running quantum chemistry calculations requires:

- Setting up Linux on a remote server
- Learning to write cryptic input files from the command line
- Waiting in long job queues
- Copying output files manually and plotting graphs yourself

This workflow has a very steep learning curve, and many students give up before they even start.

**ClearQC's goal is to remove all of those barriers.**

Just tell the software which molecule you want to compute — type "caffeine" or "benzene" — click a button, and within a few minutes you'll see:

- The molecule's 3D structure
- Total energy and atomic charge distribution
- Visualization of frontier orbitals (HOMO / LUMO)
- IR or UV-Vis absorption spectra (if you selected those tasks)

**Everything runs locally on your Windows PC. No internet required for computing, no account needed, no Python knowledge necessary.**

---

## What can quantum chemistry actually calculate?

If "quantum chemistry" sounds intimidating, here are some concrete examples of what it means in practice:

**🔬 Geometry Optimization**
Given a rough starting structure, the computer finds the most stable 3D shape of the molecule — the configuration with the lowest energy. Think of it like letting a stretched spring snap back to its natural resting position.

**⚡ Frontier Orbitals (HOMO / LUMO)**
HOMO stands for "Highest Occupied Molecular Orbital," and LUMO for "Lowest Unoccupied Molecular Orbital." These two orbitals determine where a molecule donates or accepts electrons in a reaction — in other words, its chemical reactivity. ClearQC renders them as beautiful 3D isosurfaces.

**🌈 UV-Vis Absorption Spectrum (TD-DFT)**
Why does benzene absorb in the UV region? Why do dyes have color? Excited-state calculations (TD-DFT) predict which wavelengths of light a molecule absorbs, directly comparable to experimental UV-Vis spectroscopy data.

**📳 Infrared Spectrum (IR)**
Chemical bonds vibrate like springs at specific frequencies. A frequency calculation predicts where IR absorption peaks appear — directly comparable to what an IR spectrometer measures in the lab.

**🧪 Mulliken Charges**
Shows how much excess charge each atom carries, helping you understand polarity, hydrogen-bond donors/acceptors, and nucleophilic/electrophilic sites.

---

## Screenshots

![ClearQC screenshot](docs/screenshot.png)

---

## Features

| Feature | Description |
|---------|-------------|
| Molecule library | Type a name (English, Chinese, or IUPAC) to auto-complete and start a calculation |
| File import | Drag and drop XYZ, PDB, MOL/SDF, or Gaussian GJF files |
| Methods | HF · 21 DFT functionals (B3LYP, PBE0, M06-2X, ωB97X-V, CAM-B3LYP …) · post-HF (MP2, CCSD, CCSD(T)) |
| Basis sets | 28 basis sets across Pople, Dunning, Karlsruhe, pcseg, and ECP families |
| Single-point energy | Calculate the electronic energy for a given geometry |
| Geometry optimization | Find the most stable molecular structure automatically |
| Frequency analysis | Compute vibrational frequencies and generate an IR spectrum |
| Excited states (TD-DFT) | Compute light absorption and generate a UV-Vis spectrum |
| Solvent effects | 8 implicit solvents (ddCOSMO): water, DMSO, methanol, ethanol, acetonitrile, THF, DCM, toluene |
| 3D visualization | Ball-and-stick model + HOMO/LUMO/density isosurfaces |
| AI Assistant | Remote OpenAI-compatible API, auto-explains results and diagnoses failures |
| Export | Results as JSON / CSV / IR / UV-Vis data |
| Languages | 中文 / English / Deutsch / 日本語 |
| Theme & font size | Dark / Light theme, 4-step font size scaling |

---

## System Requirements

ClearQC currently supports **Windows 10 / 11 (64-bit) only**.

You also need **WSL 2** (Windows Subsystem for Linux 2) enabled. WSL 2 is a built-in Windows feature that lets Windows run Linux programs — ClearQC's calculation engine (PySCF) runs inside this Linux environment. **You don't need to know Linux at all**; ClearQC handles everything automatically.

### How to enable WSL 2

1. Open PowerShell **as Administrator** (search "PowerShell" in the Start menu → right-click → Run as administrator)
2. Run the following command:
   ```
   wsl --install
   ```
3. Wait for installation to finish, then **restart your computer**

After the restart, WSL 2 is ready. If you run into issues, see the [official Microsoft documentation](https://learn.microsoft.com/en-us/windows/wsl/install).

### Hardware recommendations

| | Minimum | Recommended |
|--|---------|-------------|
| RAM | 4 GB | 8 GB or more |
| Disk space | 600 MB | 1 GB+ (for temp calculation files) |
| CPU | Any x64 | More cores = faster calculations |

---

## Download & Install

Go to the [Releases page](https://github.com/SigmaAdrich/ClearQC/releases/latest) to download the latest version.

The `.exe` installer is ~135 MB. The calculation engine is bundled inside, so **no internet is required** for installation or use.

### Installation steps

1. Download the `.exe` installer
2. Double-click to run. Windows may show a security warning ("Windows protected your PC"). Click **More info → Run anyway**
3. Follow the installation wizard
4. Launch **ClearQC** from the Start menu or desktop shortcut
5. **On first launch**, the app will automatically import the WSL calculation environment — this takes about 30–60 seconds. Please be patient
6. Once the main interface appears, you're ready to go!

---

## 5-Minute Quickstart

**Step 1: Enter a molecule name**

In the chat input box at the bottom left, type `/compute caffeine` and press Enter.

The app will look up caffeine in the built-in molecule library and show a **calculation card** in the chat panel.

**Step 2: Configure calculation parameters**

The card defaults to a recommended method and basis set (B3LYP / def2-SVP — a good balance of speed and accuracy). Click **Adjust** to expand more options:

- **Method**: HF, 21 DFT functionals (B3LYP, PBE0, M06-2X, ωB97X-V, CAM-B3LYP, …), or post-HF (MP2 / CCSD / CCSD(T))
- **Basis**: 28 basis sets grouped by family (Pople, Dunning, Karlsruhe, pcseg, ECP); default def2-SVP
- **Task**: Single Point (SP) / Optimization (Opt) / Frequency (Freq) / Excited States
- **Solvent**: Pick one of 8 solvents to simulate solution-phase conditions

For your first try, leave everything at the defaults.

**Step 3: Click Compute**

Click the green **Compute** button. The right-side status bar shows calculation progress.

A small molecule like caffeine takes about 1–3 minutes at the default settings (B3LYP / def2-SVP).

**Step 4: View results**

When the calculation finishes, a result card appears showing:

- Total energy (in Hartree)
- Convergence status
- Mulliken atomic charges
- Calculation time

The right panel simultaneously updates with the 3D structure. Use the dropdown menu to switch between **HOMO, LUMO, and electron density** isosurfaces.

**Step 5 (optional): Let AI explain the results**

ClearQC does not ship any AI model — you bring your own OpenAI-compatible API. Once configured, the **AI Explain** (interpret results) and **AI Diagnose** (debug failures) buttons on the result card become active.

**Configuration steps:**

1. Top menu **Settings → AI Configuration…** opens the configuration dialog
2. Fill in the three fields:

   | Field | What to put | Example |
   |---|---|---|
   | **API Base URL** | The API endpoint (without trailing `/chat/completions`) | OpenAI: `https://api.openai.com/v1`<br>DeepSeek: `https://api.deepseek.com/v1`<br>Moonshot: `https://api.moonshot.cn/v1` |
   | **API Key** | Your key, usually starts with `sk-`. Copy it from the provider's "API Keys" page | `sk-xxxxxxxxxxxxx` |
   | **Model** | Model name. Pick something cheap and fast | `gpt-4o-mini` / `deepseek-chat` / `moonshot-v1-8k` |

3. Click **Save**

Now go back to the result card and click **AI Explain** — the AI will describe in plain language what was computed, what the energy means, whether the charge distribution looks reasonable, and what to look out for. If a calculation fails, the result card shows **AI Diagnose** instead, which analyzes the error (most often an incorrect charge/spin setting or an inappropriate method).

> **Don't have a paid API?** Most LLM providers offer free credits on signup (OpenAI trial, DeepSeek welcome credit, Moonshot monthly free tier). Just register, create an API key on the provider's "API Keys" page, and paste it in.

---

## FAQ

**Q: The app won't open, or says WSL is not found?**
A: Make sure WSL 2 is enabled by following the steps above, then restart your PC.

**Q: Stuck at "Importing calculation environment" for a long time?**
A: This is normal — WSL import can take 30–60+ seconds depending on your disk speed. Please wait; don't close the window.

**Q: Calculation failed with an error?**
A: The most common cause is incorrect charge or spin settings (e.g., computing a cation without setting charge to +1). Click **AI Diagnose** on the result card for an automated diagnosis.

**Q: Which file formats are supported for import?**
A: XYZ, PDB, MOL/SDF, and Gaussian GJF/COM files can be dragged directly into the window.

**Q: Calculations are slow?**
A: Quantum chemistry calculations are inherently compute-intensive. Larger molecules, larger basis sets, and more accurate methods all take longer. Start with the default settings (B3LYP / def2-SVP) and a Single Point (SP) calculation to get familiar with the workflow, then move up to more accurate methods (MP2, CCSD(T)) or larger basis sets (cc-pVTZ, def2-TZVP) when needed.

**Q: Is Mac or Linux supported?**
A: Not currently. Windows 10/11 only. Mac/Linux support is not planned at this time.

---

## Feedback & Support

Found a bug, have a feature request, or want to chat about quantum chemistry workflows? Reach out via any of the following:

- **GitHub Issues**: [report bugs or request features](https://github.com/SigmaAdrich/ClearQC/issues)
- **Email**: 540059610@qq.com
- **Discord server**: <https://discord.gg/gNkRV2xkC3>

---

## License

© 2025 SigmaAdrich. All rights reserved.