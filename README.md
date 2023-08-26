# Generating OOD Datasets by Filtering CLIP Pretraining Captions

## Description
| ![CLIP](https://raw.githubusercontent.com/mlfoundations/open_clip/main/docs/CLIP.png) |
|:--:|
| Image Credit: https://github.com/openai/CLIP |
This project generates out-of-distribution (OOD) datasets for evaluating CLIP models.

It analyzes the text prompts used to train CLIP and filters out any that match the CLIP pretraining captions. The remaining unseen prompts are used to construct an OOD evaluation dataset.

This helps create test sets that evaluate CLIP's ability to generalize to new textual concepts not present in its training data. 

## Approach  

- Load the list of textual prompts we want to use for evaluating CLIP
- Load the dataframe containing captions from CLIP's pretraining dataset (e.g. LAION-400M) 
- Search through the captions and filter out any of our prompts that have matching captions
- The prompts remaining after filtering form the OOD dataset

## Prompts

We use a variety of procedural prompts like:

- Adjective-noun combinations
- Noun-noun combinations
- Novel compositions not in CLIP training data

## CLIP Pretraining Data 

We analyze datasets like LAION-400M used to train CLIP. The captions are loaded as a dataframe for filtering.

## OOD Dataset  

The prompts remaining after the filtering process are used to construct a text-image dataset for OOD evaluation of CLIP.

Images are scraped from the web for each prompt. 

## Usage

The code performs the filtering and text-image dataset generation process. 

It can be used to quickly generate OOD sets for evaluating CLIP models.

## References

- [LAION-400M Dataset](https://laion.ai/blog/laion-400-open-dataset/)
