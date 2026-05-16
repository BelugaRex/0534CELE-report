# Survey Paper Optimization Guidelines (AI-NoC)

## 1. Structural Overhaul & Real Estate Allocation
To achieve depth in 8 pages, eliminate "Definitions" and focus on "Analyses."

| Section | Page Target | AI/Team Strategy |
| :--- | :--- | :--- |
| **I. Introduction** | 1.0 | **Depth Move:** Define the "Communication Wall." Contrast TFLOPS compute growth vs. interconnect bandwidth lag. Establish the 2022–2026 scope. |
| **II. AI Dataflow Analysis** | 1.5 | **Depth Move:** Replaces "Fundamentals." Group by **Traffic Archetypes**: All-Reduce (LLM Training), KV-Cache (Inference), and Systolic flows (CNNs). |
| **III. Microarch Synthesis** | 2.5 | **Depth Move:** Group by **Mechanism**, not paper. Contrast Multicast Routers vs. Sparsity-Gating vs. In-Network Computation. |
| **IV. Multi-Die & NoP** | 2.0 | **Depth Move:** Analyze the physical vs. logical hierarchy. Compare UCIe/BoW protocols and 2.5D/3D thermal vs. latency trade-offs. |
| **V. Conclusion/Trends** | 1.0 | **Depth Move:** Predict the 5-year roadmap. Use this space for brief mentions of Photonics and Security as "Long-term Challenges." |

---

## 2. Requirement: "Synthesis" over "Summarization"
**Rule:** No paragraph should ever describe only one paper. 
*   **Instruction to AI:** "Compare and contrast. Use phrases like 'While [12] optimizes for energy via sparsity, it lacks the deterministic latency required for the systolic arrays described in [18].'"
*   **Design Insight:** Every sub-section must conclude with a "Design Insight" sentence that summarizes the consensus or the major trade-off discovered across the cited works.

---

## 3. Quantitative Rigor & Data Tables
Prose is for analysis; tables are for data. The AI must be prompted to extract specific metrics.
*   **Metric Checklist:** Every architecture discussed should ideally have data for:
    1.  **Energy Efficiency:** (pJ/bit)
    2.  **Bandwidth Density:** (Gbps/mm or Gbps/mm²)
    3.  **Area Overhead:** (% of total die)
    4.  **Workload Speedup:** (Relative to standard 2D Mesh)
*   **Mandatory Tables:** At least two deep-dive tables:
    *   *Table A:* Microarchitecture comparison (Logic/Mechanism focused).
    *   *Table B:* Chiplet/Interconnect comparison (Physical/Protocol focused).

---

## 4. Scaling the Bibliography (Target: 40-60 Sources)
*   **Instruction:** Aim for **6-8 citations per page**. 
*   **Quality Control:** 80% of sources must be from **2022–2026**. 
*   **Team Instruction:** Use the AI to find "connected papers." (e.g., "Find papers that cite the NVIDIA Simba architecture and propose a microarchitectural improvement on its NoC.")

---

## 5. Technical Visuals & Deep-Dives
Avoid generic "Router" or "Mesh" diagrams. 
*   **Visualization Goal:** Create **"Workload Mapping Diagrams."** 
    *   *Example:* Show a Transformer block being mapped onto a NoC. Use arrows to show where "hot spots" occur during the All-Reduce phase.
*   **AI Prompting for Visuals:** If using AI image generators or Mermaid/TikZ code generators, ensure the prompts specify "Architectural Block Diagram" with clear labels for "Input Buffer," "Crossbar," and "Control Logic."

---

## 6. AI Guardrails: Preventing "Hallucinated" Specs
When using AI to compile quantitative data:
1.  **Direct Source Check:** Every number extracted by the AI (e.g., "0.5 pJ/bit") **must** be manually verified by a team member against the PDF's Table or Abstract.
2.  **No "Filler" Adjectives:** Instruct the AI to delete words like "revolutionary," "unprecedented," or "groundbreaking." Use "efficient," "low-latency," or "area-optimized" supported by data.
3.  **Conflict Resolution:** If the AI finds two papers with conflicting results, do not ignore it. This is a **Design Insight**. Write about *why* they differ (e.g., different process nodes, 7nm vs 5nm).

---

## 7. New Section: "Sub-Topic Depth" Checklist
Before finalizing a section, ensure it answers:
*   **Section II:** How does the NoC handle **Sparsity** (zeros) in AI weights?
*   **Section III:** Is the **Multicast** implementation done in the router logic or via a separate network layer?
*   **Section IV:** How much **latency** is added at the Die-to-Die (D2D) interface compared to a local hop?