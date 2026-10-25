# _In Silico_ Evaluation of _De Novo_ Binders Targeting the Ricin B-Chain
This repository contains the code, workflow, and results for designing _de novo_ protein binders against the Ricin B-chain (PDB: 2AAI). The goal was to design miniprotein binders for three sugar-binding sites: Y248, W37, and Y78, to block the toxin from entering cells. I used AlphaFold3 to check the predicted structures and find promising binders. The Y248 site gave the best result, with an ipTM score of 0.84. However, W37 and Y78 were much harder to target because their surfaces were shallow. I tried different design methods, including beta-sheet models, guiding potentials, and partial diffusion, but the binders for these two sites reached ipTM scores of only around 0.4. By comparing deep pockets with shallow surfaces, this project explores how the shape of a binding site affects the binder design. The results show what worked, what did not, and what could be improved in future binder design projects.
## Intro
Castor oil is one of the world’s most important plant-based industrial oils. The global market is worth around $1.4–1.5 billion, and the oil is widely used as a renewable alternative to petroleum in many heavy industries.
Castor oil comes from the seeds of Ricinus communis, commonly called the castor bean plant. India is the largest producer, supplying roughly 80–92% of the world’s castor oil. Although castor is also grown in other tropical and semi-arid regions, India dominates the global trade and exports a large share of its production to China, the United States, and countries across the European Union. Castor seeds contain ricin, one of the most toxic naturally occurring proteins known.
## What is ricin?
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
## How does ricin enter a cell?
The B-chain attaches to specific sugar-containing molecules on the surface of a cell.
The cell then takes the toxin inside through a process called endocytosis. From there, ricin can move through several parts of the cell, including the Golgi apparatus and the endoplasmic reticulum.
Inside the endoplasmic reticulum, the connection between the two chains can be broken. The A-chain can then reach the cell’s cytosol, where it becomes active.
The A-chain targets a specific part of the 28S ribosomal RNA within the cell’s 60S ribosomal subunit. By removing a single adenine residue, it permanently disrupts the ribosome. Hence, cell can no longer make proteins properly. As protein production stops, essential cellular functions fail and the affected cell can eventually die.
## How can exposure happen?
Ricin toxicity depends heavily on the route of exposure. Inhalation, injection, and ingestion can all be dangerous, but they affect the body differently.
Simply having castor seeds does not mean that ricin is automatically absorbed into the body. The risk depends on how the seeds or ricin-containing material are processed and how exposure occurs.
## Is there an antidote?
At present, there is no widely approved antidote or vaccine for ricin poisoning. Treatment mainly focuses on rapid medical care and supporting the affected organs while the body deals with the toxin.
Researchers have been studying neutralizing monoclonal antibodies as a possible treatment. Some experimental antibodies, including antibodies such as SylH3 and 24B11, have shown protective effects in laboratory and animal studies.
The idea is straightforward: if an antibody can stop ricin from attaching to cells or interfere with its movement inside the cell, the toxin may be prevented from causing its full effect.
However, these antibody treatments remain experimental and are not currently available as routine civilian treatment.
## Computational biology:
Out of these eight domains I discussed earlier, three domains contain key amino acid residue that are responsible for mammalian cell entry. Trp-37 in subdomain 1α, Tyr-78 in subdomain 1β, and Tyr-248 in subdomain 2γ. 
The Ricin B-chain has several sites that bind to sugars. These sites have shallow grooves and aromatic rings that help the toxin attach to sugars, which is important for its ability to bind to cells. I focused on Tyr248 (Y248) in Subdomain 2γ. Tyrosine 248 (Y248) plays an important role in helping ricin bind to host cells. Its aromatic side chain interacts with sugars such as galactose and GalNAc, helping the toxin attach to the surface of cells. This binding site is a shallow pocket on the Ricin B-chain. Once ricin attaches to the cell, it can enter through a process called receptor-mediated endocytosis. It then travels through the cell, passing through the Golgi apparatus before reaching the endoplasmic reticulum (ER). There, the A-chain separates and moves into the cytosol, where it blocks protein production. Studies have also shown that modifying Tyr248 with a chemical called N-acetylimidazole disrupts the B-chain's ability to bind sugars. 
Apart from Y248, I also focused on two other regions, W37 and Y78, which are involved in sugar binding but have lower binding affinity. In subdomain 1α, Tryptophan 37 (W37) helps the Ricin B-chain bind to sugars by interacting with the sugar ring. It works together with other residues, including Asp22, Gln35, and Asn46, which help stabilize the binding through hydrogen bonds. In subdomain 1β, Tyrosine 78 (Y78) also plays a role in sugar binding. Studies have shown that changes to this residue can affect how well ricin binds to sugars. Changes to Y78, especially when combined with changes to W37 and Y248, can greatly reduce sugar binding and the toxin's ability to harm cells.
