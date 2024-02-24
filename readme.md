---
annotations_creators:
- crowdsourced
language_creators:
- crowdsourced
language:
- en
license:
- unknown
multilinguality:
- monolingual
size_categories:
- 10K<n<100K
source_datasets:
- extended|other-foodspotting
task_categories:
- image-classification
task_ids:
- multi-class-image-classification
paperswithcode_id: food-101
pretty_name: Food-101
dataset_info:
  features:
  - name: image
    dtype: image
  - name: label
    dtype:
      class_label:
        names:
          '0': apple_pie
          '1': baby_back_ribs
          '2': baklava
          '3': beef_carpaccio
          '4': beef_tartare
          '5': beet_salad
          '6': beignets
          '7': bibimbap
          '8': bread_pudding
          '9': breakfast_burrito
          '10': bruschetta
          '11': caesar_salad
          '12': cannoli
          '13': caprese_salad
          '14': carrot_cake
          '15': ceviche
          '16': cheesecake
          '17': cheese_plate
          '18': chicken_curry
          '19': chicken_quesadilla
          '20': chicken_wings
          '21': chocolate_cake
          '22': chocolate_mousse
          '23': churros
          '24': clam_chowder
          '25': club_sandwich
          '26': crab_cakes
          '27': creme_brulee
          '28': croque_madame
          '29': cup_cakes
          '30': deviled_eggs
          '31': donuts
          '32': dumplings
          '33': edamame
          '34': eggs_benedict
          '35': escargots
          '36': falafel
          '37': filet_mignon
          '38': fish_and_chips
          '39': foie_gras
          '40': french_fries
          '41': french_onion_soup
          '42': french_toast
          '43': fried_calamari
          '44': fried_rice
          '45': frozen_yogurt
          '46': garlic_bread
          '47': gnocchi
          '48': greek_salad
          '49': grilled_cheese_sandwich
          '50': grilled_salmon
          '51': guacamole
          '52': gyoza
          '53': hamburger
          '54': hot_and_sour_soup
          '55': hot_dog
          '56': huevos_rancheros
          '57': hummus
          '58': ice_cream
          '59': lasagna
          '60': lobster_bisque
          '61': lobster_roll_sandwich
          '62': macaroni_and_cheese
          '63': macarons
          '64': miso_soup
          '65': mussels
          '66': nachos
          '67': omelette
          '68': onion_rings
          '69': oysters
          '70': pad_thai
          '71': paella
          '72': pancakes
          '73': panna_cotta
          '74': peking_duck
          '75': pho
          '76': pizza
          '77': pork_chop
          '78': poutine
          '79': prime_rib
          '80': pulled_pork_sandwich
          '81': ramen
          '82': ravioli
          '83': red_velvet_cake
          '84': risotto
          '85': samosa
          '86': sashimi
          '87': scallops
          '88': seaweed_salad
          '89': shrimp_and_grits
          '90': spaghetti_bolognese
          '91': spaghetti_carbonara
          '92': spring_rolls
          '93': steak
          '94': strawberry_shortcake
          '95': sushi
          '96': tacos
          '97': takoyaki
          '98': tiramisu
          '99': tuna_tartare
          '100': waffles
  splits:
  - name: train
    num_bytes: 3845865322
    num_examples: 75750
  - name: validation
    num_bytes: 1276249954
    num_examples: 25250
  download_size: 4998236572
  dataset_size: 5122115276
---

# Dataset Card for Food-101

## Table of Contents
- [Table of Contents](#table-of-contents)
- [Dataset Description](#dataset-description)
  - [Dataset Summary](#dataset-summary)
  - [Supported Tasks and Leaderboards](#supported-tasks-and-leaderboards)
  - [Languages](#languages)
- [Dataset Structure](#dataset-structure)
  - [Data Instances](#data-instances)
  - [Data Fields](#data-fields)
  - [Data Splits](#data-splits)
- [Dataset Creation](#dataset-creation)
  - [Curation Rationale](#curation-rationale)
  - [Source Data](#source-data)
  - [Annotations](#annotations)
  - [Personal and Sensitive Information](#personal-and-sensitive-information)
- [Considerations for Using the Data](#considerations-for-using-the-data)
  - [Social Impact of Dataset](#social-impact-of-dataset)
  - [Discussion of Biases](#discussion-of-biases)
  - [Other Known Limitations](#other-known-limitations)
- [Additional Information](#additional-information)
  - [Dataset Curators](#dataset-curators)
  - [Licensing Information](#licensing-information)
  - [Citation Information](#citation-information)
  - [Contributions](#contributions)

## Dataset Description

- **Homepage:** [Food-101 Dataset](https://data.vision.ee.ethz.ch/cvl/datasets_extra/food-101/)
- **Repository:**
- **Paper:** [Paper](https://data.vision.ee.ethz.ch/cvl/datasets_extra/food-101/static/bossard_eccv14_food-101.pdf)
- **Leaderboard:**
- **Point of Contact:**

### Dataset Summary

This dataset consists of 101 food categories, with 101'000 images. For each class, 250 manually reviewed test images are provided as well as 750 training images. On purpose, the training images were not cleaned, and thus still contain some amount of noise. This comes mostly in the form of intense colors and sometimes wrong labels. All images were rescaled to have a maximum side length of 512 pixels.

### Supported Tasks and Leaderboards

- `image-classification`: The goal of this task is to classify a given image of a dish into one of 101 classes. The leaderboard is available [here](https://paperswithcode.com/sota/fine-grained-image-classification-on-food-101).

### Languages

English

## Dataset Structure

### Data Instances

A sample from the training set is provided below:

```
{
  'image': <PIL.JpegImagePlugin.JpegImageFile image mode=RGB size=384x512 at 0x276021C5EB8>,
  'label': 23
}
```

### Data Fields

The data instances have the following fields:

- `image`: A `PIL.Image.Image` object containing the image. Note that when accessing the image column: `dataset[0]["image"]` the image file is automatically decoded. Decoding of a large number of image files might take a significant amount of time. Thus it is important to first query the sample index before the `"image"` column, *i.e.* `dataset[0]["image"]` should **always** be preferred over `dataset["image"][0]`.
- `label`: an `int` classification label.

<details>
  <summary>Class Label Mappings</summary>

  ```json
  {
    "apple_pie": 0,
    "baby_back_ribs": 1,
    "baklava": 2,
    "beef_carpaccio": 3,
    "beef_tartare": 4,
    "beet_salad": 5,
    "beignets": 6,
    "bibimbap": 7,
    "bread_pudding": 8,
    "breakfast_burrito": 9,
    "bruschetta": 10,
    "caesar_salad": 11,
    "cannoli": 12,
    "caprese_salad": 13,
    "carrot_cake": 14,
    "ceviche": 15,
    "cheesecake": 16,
    "cheese_plate": 17,
    "chicken_curry": 18,
    "chicken_quesadilla": 19,
    "chicken_wings": 20,
    "chocolate_cake": 21,
    "chocolate_mousse": 22,
    "churros": 23,
    "clam_chowder": 24,
    "club_sandwich": 25,
    "crab_cakes": 26,
    "creme_brulee": 27,
    "croque_madame": 28,
    "cup_cakes": 29,
    "deviled_eggs": 30,
    "donuts": 31,
    "dumplings": 32,
    "edamame": 33,
    "eggs_benedict": 34,
    "escargots": 35,
    "falafel": 36,
    "filet_mignon": 37,
    "fish_and_chips": 38,
    "foie_gras": 39,
    "french_fries": 40,
    "french_onion_soup": 41,
    "french_toast": 42,
    "fried_calamari": 43,
    "fried_rice": 44,
    "frozen_yogurt": 45,
    "garlic_bread": 46,
    "gnocchi": 47,
    "greek_salad": 48,
    "grilled_cheese_sandwich": 49,
    "grilled_salmon": 50,
    "guacamole": 51,
    "gyoza": 52,
    "hamburger": 53,
    "hot_and_sour_soup": 54,
    "hot_dog": 55,
    "huevos_rancheros": 56,
    "hummus": 57,
    "ice_cream": 58,
    "lasagna": 59,
    "lobster_bisque": 60,
    "lobster_roll_sandwich": 61,
    "macaroni_and_cheese": 62,
    "macarons": 63,
    "miso_soup": 64,
    "mussels": 65,
    "nachos": 66,
    "omelette": 67,
    "onion_rings": 68,
    "oysters": 69,
    "pad_thai": 70,
    "paella": 71,
    "pancakes": 72,
    "panna_cotta": 73,
    "peking_duck": 74,
    "pho": 75,
    "pizza": 76,
    "pork_chop": 77,
    "poutine": 78,
    "prime_rib": 79,
    "pulled_pork_sandwich": 80,
    "ramen": 81,
    "ravioli": 82,
    "red_velvet_cake": 83,
    "risotto": 84,
    "samosa": 85,
    "sashimi": 86,
    "scallops": 87,
    "seaweed_salad": 88,
    "shrimp_and_grits": 89,
    "spaghetti_bolognese": 90,
    "spaghetti_carbonara": 91,
    "spring_rolls": 92,
    "steak": 93,
    "strawberry_shortcake": 94,
    "sushi": 95,
    "tacos": 96,
    "takoyaki": 97,
    "tiramisu": 98,
    "tuna_tartare": 99,
    "waffles": 100
  }
  ```
</details>


### Data Splits

 
|   |train|validation|
|----------|----:|---------:|
|# of examples|75750|25250|


## Dataset Creation

### Curation Rationale

[More Information Needed]

### Source Data

#### Initial Data Collection and Normalization

[More Information Needed]

#### Who are the source language producers?

[More Information Needed]

### Annotations

#### Annotation process

[More Information Needed]

#### Who are the annotators?

[More Information Needed]

### Personal and Sensitive Information

[More Information Needed]

## Considerations for Using the Data

### Social Impact of Dataset

[More Information Needed]

### Discussion of Biases

[More Information Needed]

### Other Known Limitations

[More Information Needed]

## Additional Information

### Dataset Curators

[More Information Needed]

### Licensing Information

LICENSE AGREEMENT
=================
 - The Food-101 data set consists of images from Foodspotting [1] which are not
   property of the Federal Institute of Technology Zurich (ETHZ). Any use beyond
   scientific fair use must be negociated with the respective picture owners
   according to the Foodspotting terms of use [2].

[1] http://www.foodspotting.com/
[2] http://www.foodspotting.com/terms/


### Citation Information

```
 @inproceedings{bossard14,
  title = {Food-101 -- Mining Discriminative Components with Random Forests},
  author = {Bossard, Lukas and Guillaumin, Matthieu and Van Gool, Luc},
  booktitle = {European Conference on Computer Vision},
  year = {2014}
}
```

### Contributions

Thanks to [@nateraw](https://github.com/nateraw) for adding this dataset.
