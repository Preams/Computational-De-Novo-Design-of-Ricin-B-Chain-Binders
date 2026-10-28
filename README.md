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
The cell then takes the toxin inside through a process called endocytosis. From there, ricin can move through several parts of the cell, including the Golgi apparatus and the endoplasmic 

<figure>
<img width="1640" height="1258" alt="Picture1" src="https://github.com/user-attachments/assets/ad865df1-359e-4f0b-b62d-448f6578edf1" />
<figcaption><em>Fig.1: Overview of Ricin and Ricin chain B interaction with different Carbohydrate Recognition Domain (CRD) </em></figcaption>
</figure>


## How can exposure happen?
Ricin toxicity depends heavily on the route of exposure. Inhalation, injection, and ingestion can all be dangerous, but they affect the body differently.
Simply having castor seeds does not mean that ricin is automatically absorbed into the body. The risk depends on how the seeds or ricin-containing material are processed and how exposure occurs.
## Is there an antidote?
At present, there is no widely approved antidote or vaccine for ricin poisoning. Treatment mainly focuses on rapid medical care and supporting the affected organs while the body deals with the toxin.
Researchers have been studying neutralizing monoclonal antibodies as a possible treatment. Some experimental antibodies, including antibodies such as SylH3 and 24B11, have shown protective effects in laboratory and animal studies.
The idea is straightforward: if an antibody can stop ricin from attaching to cells or interfere with its movement inside the cell, the toxin may be prevented from causing its full effect.
However, these antibody treatments remain experimental and are not currently available as routine civilian treatment.
## How Do Three Key Amino Acids Help Ricin Bind to Cells?
Out of these eight domains I discussed earlier, three domains contain key amino acid residue that are responsible for mammalian cell entry. Trp-37 in subdomain 1α, Tyr-78 in subdomain 1β, and Tyr-248 in subdomain 2γ. 
The Ricin B-chain has several sites that bind to sugars. These sites have shallow grooves and aromatic rings that help the toxin attach to sugars, which is important for its ability to bind to cells. I focused on Tyr248 (Y248) in Subdomain 2γ. Tyrosine 248 (Y248) plays an important role in helping ricin bind to host cells. Its aromatic side chain interacts with sugars such as galactose and GalNAc, helping the toxin attach to the surface of cells. This binding site is a shallow pocket on the Ricin B-chain. Once ricin attaches to the cell, it can enter through a process called receptor-mediated endocytosis. It then travels through the cell, passing through the Golgi apparatus before reaching the endoplasmic reticulum (ER). There, the A-chain separates and moves into the cytosol, where it blocks protein production. Studies have also shown that modifying Tyr248 with a chemical called N-acetylimidazole disrupts the B-chain's ability to bind sugars. 
Apart from Y248, I also focused on two other regions, W37 and Y78, which are involved in sugar binding but have lower binding affinity. In subdomain 1α, Tryptophan 37 (W37) helps the Ricin B-chain bind to sugars by interacting with the sugar ring. It works together with other residues, including Asp22, Gln35, and Asn46, which help stabilize the binding through hydrogen bonds. In subdomain 1β, Tyrosine 78 (Y78) also plays a role in sugar binding. Studies have shown that changes to this residue can affect how well ricin binds to sugars. Changes to Y78, especially when combined with changes to W37 and Y248, can greatly reduce sugar binding and the toxin's ability to harm cells.


<figure>
<img width="1200" height="800" alt="ricin_shallow_surfaces" src="https://github.com/user-attachments/assets/ecc7d892-b4f2-4696-a31e-374e9baca30a" />
<figcaption><em>Fig.2: Three important key residues (W-37, Y-78, and Y-248) are highlighted. </em></figcaption>
</figure>


| Sub domain | Role | Key residue | Other important residue |
| :--- | :---: | :---: | ---: |
| 1α | Low-affinity Gal binding | Trp (37th residue) | Asp22, Arg24, Asp25, Gly26, Ala45 |
| 1β | Gal binding site | Try (78th residue) | Tyr67, Tyr69, Ala83, Ala84 |
| 2γ | High-affinity Gal/GalNAc binding | Try (248th residue) | Val235, Ala237, Ile246, Leu247, Pro249 |

Based on my goal to target Trp37 (subdomain 1α), Tyr78 (subdomain 1β), and Tyr248 (subdomain 2γ), I used the pdb structure 2AAI. With 2.5Å, containing native ricin holotoxin; complexed with a carbohydrate ligand (mannose-rich N-glycan), this structure provides the complete RTB fold, showing the pseudo-threefold symmetry of the subdomains.
## How I did this?
All computational work was carried out using open-source protein design and structure prediction tools, mainly through the Neurosnap web interface and AlphaFold Server.
The crystal structure of the Ricin B-chain (PDB ID: 2AAI) was used as the starting structure. Three sugar-binding regions were selected for binder design: Y248 in subdomain 2γ, W37 in subdomain 1α, and Y78 in subdomain 1β. PyMOL was used to examine the structure and select surface regions around these residues.
RFdiffusion was used to generate binder backbones ranging from 60 to 80 amino acids. The target residues were specified as hotspots using contig settings, such as B37, B78, and B248. Since these regions have shallow surfaces, the Complex_beta model and guiding potentials, including monomer_ROG and Binder & Interface Contacts, were used to explore suitable binder shapes and improve contact with the target. For designs with steric clashes, partial diffusion with a partial_T value of 10–15 was used to adjust the structures while keeping the overall binding pose.
The generated backbones were then used with ProteinMPNN to design amino acid sequences. The target chain and selected interface residues were kept fixed while the models generated sequences for the remaining positions. The top five to ten sequences, based on their MPNN scores, were selected for further testing.
The predicted binder–target complexes were then checked using AlphaFold3 Server. AlphaFold3 was used to predict the structures of the complexes, and the results were assessed using the interface predicted TM-score (ipTM) and predicted aligned error (PAE). Designs with an ipTM above 0.6 and low predicted error at the interface were selected for further analysis.
Finally, PyMOL was used to align the selected binders onto the Ricin B-chain to examine how they could fit together in a three-binder arrangement. The distances between the C-terminus of one binder and the N-terminus of the next were measured to estimate suitable flexible linker lengths. The Interface Analysis tool in Neurosnap was also used to examine atom contacts, buried surface area, hydrogen bonds, salt bridges, and steric clashes in the predicted complexes.
## Results:
The Ricin B-chain (RTB) is difficult to design binders for because its carbohydrate-binding sites (W37, Y78, and Y248) are shallow surface depressions rather than deep pockets. This makes it harder to design a binder that fits the target and forms strong interactions. 
Despite this challenge, I successfully designed a high-affinity binder for the Y248 site. I used the Beta-Sheet RFdiffusion model to generate binders with flat interfaces that could fit the target surface. I also used guiding potentials, including radius of gyration and interface contacts, to encourage close contact between the binder and the target. AlphaFold3 co-folding supported the design, with an ipTM score of around 0.80. The PAE plot also showed dark green regions at the interface, suggesting that the predicted binding pose was consistent [Click here to view the Y248 Binder folder](Y248%20binder). 
I then applied the same approach to the W37 site in subdomain 1α and the Y78 site in subdomain 1β. However, these sites were harder to target. Although the models generated flat binders and the guiding potentials brought them into contact with the target, the resulting interactions were not specific enough. The initial designs had several problems, including 92 atomic clashes, no salt bridges, and very few hydrogen bonds. I tried low-noise partial diffusion to reduce the clashes. This improved the physical fit, but it did not lead to stronger interactions. The ipTM scores remained around 0.4, and the PAE plots showed white regions at the interface, stating that AlphaFold3 could not confidently predict the binding poses. 
Overall, the results show that the approach worked for Y248 but did not produce reliable binders for W37 or Y78. While guiding potentials helped improve the fit between the binder and target, they were not enough to create the specific interactions needed for stable binding.
## What I conclude?
The aim of this project was to design small proteins that could bind to the Ricin B-chain (RTB) and block its interaction with sugars on host cells. The work also helped us understand how the shape of a target region affects protein design and how well tools such as RFdiffusion and AlphaFold3 can predict these interactions.
### Effect of the Target Surface on Binder Design
The Ricin B-chain has several sugar-binding sites with shallow grooves on its surface. The results showed that the shape of these sites made a big difference to the success of binder design.
### Y248 (Subdomain 2γ): Among the three target regions, Y248 gave the best result. This residue helps ricin bind to sugars through interactions with its aromatic side chain. The designed binder had an ipTM score of 0.84, suggesting that the predicted binding position was reliable. The PAE heatmap (Figure X) also showed strong confidence at the interface. Other results, including a ranking score of 0.88, a clash score of 0.0, and a disorder fraction of 0.06, suggested that the predicted structure was stable and had no major atomic clashes. However, these results are based on computer predictions and still need to be confirmed experimentally.
### W37 and Y78 (Subdomains 1α and 1β): The results for these two regions were less successful. Both are located on relatively flat parts of the protein surface, which makes it harder to design a binder that fits closely. The predicted binders had ipTM scores below 0.2, suggesting that their binding positions were not reliable.
### Attempts to Improve the W37 and Y78 Designs
Several approaches were tested to improve the binders targeting W37 and Y78. First, the Complex_beta model in RFdiffusion was used to generate beta-sheet structures that might fit better against the flatter surfaces. Guiding potentials, including monomer_ROG and interface contact settings, were also used to encourage closer contact between the binder and the target.
Although these settings brought the structures closer together, some designs developed serious atomic clashes and lacked important stabilising interactions, such as salt bridges. Partial diffusion was then used to adjust the structures and reduce these clashes. While this helped improve the physical fit, it did not produce the interactions needed for a stable interface. The ipTM scores remained around 0.4, and the PAE plots continued to show low confidence at the binding sites.
### What We can Learn from the Results
This project showed that generating a protein structure that fits a target is not enough to ensure successful binding. The binder must also form the right chemical interactions with the target. RFdiffusion helped generate possible structures, while AlphaFold3 and Chai-1 helped assess how the binders might interact with the Ricin B-chain. However, these tools could not produce reliable designs for every target region.
Partial diffusion helped correct some structural clashes, but it could not fix every problem with the predicted binding positions. The results suggest that designing binders from scratch may be more difficult for shallow surfaces like those around W37 and Y78.
One possible next step is to test scaffold-based approaches using stable protein frameworks, such as DARPins or Affibodies, with selected binding regions redesigned to interact with the target. Experimental methods could also help identify better candidates.
## Conclusion and Future Work
The most promising result from this project was the predicted binder targeting Y248. Its structural scores suggest that it is worth further investigation, but its ability to bind RTB and reduce ricin activity has not yet been confirmed. The next step would be to produce the binder and test it in the laboratory using methods such as microscale thermophoresis (MST) or ELISA, followed by suitable functional tests to assess whether it can reduce ricin activity.
The designs targeting W37 and Y78 need further improvement. Scaffold-based design or laboratory methods such as directed evolution may be useful alternatives for these regions.
Overall, this project showed how protein design and structure prediction tools can help identify possible binders and study their interactions with a target protein. It also showed that the shape of the target surface and the interactions formed at the binding site remain important challenges in computational protein design.
