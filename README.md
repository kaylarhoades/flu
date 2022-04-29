# flu for this project we are picking 12 influenza A strains from 2019 and 12 from 2020 and then constructing a phylogenetic tree.

# H5N1 (avian influenza A) is out group
# https://pubmed.ncbi.nlm.nih.gov/9360372/ info about hemogglutinin and its role in influenza virus transmission
# we are using conda.sh as our sequencing platform
# https://docs.google.com/presentation/d/1CGOebLC6FZPsCn3Bwy2tyHOOIDTQDSpUzrj0ClJlti4/edit#slide=id.p link to R's GEN725 project to use as a model for our analysis 

# Background: Influenza A is an orthomyxovirus with 8 segments of (-)ssRNA in its genome
# Influenza A contains two major envelope proteins that are surface antigens: hemagglutinin (HA) and neuraminidase (NA).
# Hemagglutinin is used for attachment and composes 80% of surface proteins
# HA is responsible for bidning of the virus to cell surface receptors, and it mediatese liberation of the viral genome into the cytoplasm through membrane fusion https://pubmed.ncbi.nlm.nih.gov/9360372/#:~:text=The%20hemagglutinin(HA)%20of%20influenza,the%20cytoplasm%20through%20membrane%20fusion. 
# http://assets.geneious.com/manual/8.0/GeneiousManualsu64.html how to align in clustlw
# sequences are being put on a google doc so they can be uploaded all at once: https://docs.google.com/document/d/1puxg5FQv2mZlGy4V6Lnj8Xv2-zC8BJUws7JdhahDVek/edit# 
# presentation link https://docs.google.com/presentation/d/1UPxW0D_jq9qnWfWj21y9nlx0BLGnr1kqd5Tsy6zpaTw/edit?usp=sharing
# 2019 HA H1N1:
## Influenza A virus (A/Alabama/03/2019(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MK630770.1?report=fasta 
## Influenza A virus (A/Alabama/06/2019(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MK630778.1?report=fasta 
## Influenza A virus (A/Alabama/09/2019(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MK772909.1?report=fasta 
## Influenza A virus (A/Alabama/12/2019(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MK772917.1?report=fasta 
## Influenza A virus (A/Alabama/17/2019(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MK855605.1?report=fasta 
## Influenza A virus (A/Alabama/19/2019(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MK999442.1?report=fasta 
## Influenza A virus (A/Alabama/25/2019(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT034585.1?report=fasta 
## Influenza A virus (A/Alabama/26/2019(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT034599.1?report=fasta 
## Influenza A virus (A/Alabama/27/2019(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT167169.1?report=fasta 
## Influenza A virus (A/Alabama/28/2019(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT167193.1?report=fasta 
### Influenza A virus (A/Alaska/02/2019(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MK630786.1?report=fasta 
## Influenza A virus (A/Alaska/03/2019(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MK630794.1?report=fasta 
# 2020 HA H1N1:
## Influenza A virus (A/Alabama/01/2020(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT244087.1?report=fasta 
## Influenza A virus (A/Alabama/02/2020(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT244098.1?report=fasta 
## Influenza A virus (A/Alabama/03/2020(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT244105.1?report=fasta 
## Influenza A virus (A/Alabama/04/2020(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT244111.1?report=fasta 
## Influenza A virus (A/Alabama/05/2020(H1N1)) segment 4 hemagglutinin  (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT303191.1?report=fasta 
## Influenza A virus (A/Alabama/06/2020(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT303224.1?report=fasta 
## Influenza A virus (A/Alabama/07/2020(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT330562.1?report=fasta 
## Influenza A virus (A/Alabama/08/2020(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT330567.1?report=fasta 
## Influenza A virus (A/Alabama/09/2020(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT466096.1?report=fasta 
## Influenza A virus (A/Alabama/10/2020(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT466104.1?report=fasta 
## Influenza A virus (A/Alaska/01/2020(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT330576.1?report=fasta 
## Influenza A virus (A/Alaska/02/2020(H1N1)) segment 4 hemagglutinin (HA) gene, complete cds: https://www.ncbi.nlm.nih.gov/nuccore/MT330584.1?report=fasta 

### clustalw resources: https://www.genome.jp/tools/clustalw/clustalw_help.html#input_sequence

## Background
## Methods
### ![clustalw](<img width="696" alt="Clustalw" src="https://user-images.githubusercontent.com/103778823/166059778-93969574-4280-446a-a8cc-f9696a74c96a.png">)



## Findings

# https://www.genome.jp/tools-bin/clustalw this is what we used to align our sequences above

