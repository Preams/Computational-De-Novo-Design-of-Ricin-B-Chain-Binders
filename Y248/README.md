# Highaffinity binder
The most successful outcome of this project was the _de novo_ design of a miniprotein binder [[View](Binder.cif%20binder/Binder%20designing)] targeting the Y248 residue (Subdomain 2γ) of the Ricin B-chain. Despite the target being a shallow surface cleft, the integration of advanced generative strategies yielded a highly stable and confident interaction.

The final design was analysed using AlphaFold3

|Metric|Score|Interpretation|
|:---:|:---:|:---:|
|ipTM|0.84|High confidence in the predicted interface|
|pTM|0.9|High confidence of the overall structure|
|PAE Interface|< 5.0 Å|High certainty of the binding orientation|
|Clash|0.0|Viable structure (Relaxed using partial diffusion)|
|Ranking score|0.88|The model is structurally sound and the interaction between your binder and Ricin B is highly probable|
|Fraction disordered|0.06|The N- and C-termini is disordered|

Design Statergies:
A standard _de novo_ design approach was not enough to achieve the desired interaction, so three additional strategies were used: 
1. Beta-sheet model: The `Complex_beta` RFdiffusion model was used to generate flat beta-sheet backbones that fit the shallow shape of the Y248 cleft.
2. Guiding potentials: The `monomer_ROG` and interface contact potentials were used to help the binder fit closely against the target and increase the buried surface area.
3. Partial diffusion: Low-noise partial diffusion was used to refine the final interface, remove atomic clashes, and preserve key hydrogen bonds and the salt bridge.


<figure>
<img width="1086" height="408" alt="Interacting sites" src="https://github.com/user-attachments/assets/0c4899da-3c6b-4874-832b-989a9084f6fe" />
<figcaption>Fig.1: PyMOL surface representation of the Ricin B-chain (red) bound to the designed Y248 miniprotein binder (Cyan)</figcaption>
</figure>


The final sequence of binder for Y248 region is given below:

>Y248 binder
EEEKKKREEYYKEHAEEIKEQNKKDTEEALKRLKERLKTEETSYSPSIKKVLELIDSGEKTLEEIWEEQLAKLKALVVLP
