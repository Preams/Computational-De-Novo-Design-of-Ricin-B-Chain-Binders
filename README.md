# 👋 # _In Silico_ Evaluation of _De Novo_ Binders Targeting the Ricin B-Chain
This repository contains the code, workflow, and results for designing _de novo_ protein binders against the Ricin B-chain (PDB: 2AAI). The goal was to design miniprotein binders for three sugar-binding sites: Y248, W37, and Y78, to block the toxin from entering cells. I used AlphaFold3 to check the predicted structures and find promising binders. The Y248 site gave the best result, with an ipTM score of 0.84. However, W37 and Y78 were much harder to target because their surfaces were shallow. I tried different design methods, including beta-sheet models, guiding potentials, and partial diffusion, but the binders for these two sites reached ipTM scores of only around 0.4. By comparing deep pockets with shallow surfaces, this project explores how the shape of a binding site affects the binder design. The results show what worked, what did not, and what could be improved in future binder design projects.
## Intro
Castor oil is one of the world’s most important plant-based industrial oils. The global market is worth around $1.4–1.5 billion, and the oil is widely used as a renewable alternative to petroleum in many heavy industries.
Castor oil comes from the seeds of Ricinus communis, commonly called the castor bean plant. India is the largest producer, supplying roughly 80–92% of the world’s castor oil. Although castor is also grown in other tropical and semi-arid regions, India dominates the global trade and exports a large share of its production to China, the United States, and countries across the European Union. Castor seeds contain ricin, one of the most toxic naturally occurring proteins known.
##What is ricin?
Ricin is a water-soluble protein found in castor seeds. It belongs to a group called Type 2 Ribosome-Inactivating Proteins (RIPs) and is made of two protein chains connected by a disulfide bond.
•	Ricin A-chain (RTA): This is the active part of the toxin. Its job is to damage ribosomes, the structures cells use to make proteins.
•	Ricin B-chain (RTB): This part helps the toxin attach to cells by recognizing certain sugar molecules on their surface.
The two chains work together: the B-chain helps the toxin enter the cell, while the A-chain causes the damage.
Chain B contains 2 major globular domains:
o	Domain 1 (RTB-D1): Located at the N-terminal half of the chain.
o	Domain 2 (RTB-D2): Located at the C-terminal half of the chain
Each of the 2 main domains is further subdivided into 4 subdomains:
•	Domain 1 consists of subdomains 1λ, 1α, 1β, and 1γ.
•	Domain 2 consists of subdomains 2λ, 2α, 2β and 2γ
