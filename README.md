# [Paper Materials] Exploring ‘pseudorandom’ value addition operations in datasets: A layered approach to escape from normal-Gaussian patterns

### Dataset generated in *"Exploring ‘pseudorandom’ value addition operations in datasets: A layered approach to escaping from normal-Gaussian patterns"*, available at [arXiv:2402.05867](https://arxiv.org/abs/2402.05867).

**Abstract:** In the realm of statistical exploration, the manipulation of pseudo-random values to discern their impact on data distribution presents a compelling avenue of inquiry. This article investigates the question: ‘Is it possible to add pseudo-random values without compelling a shift towards a normal distribution?’. Employing Python techniques, the study explores the nuances of pseudo-random value addition within the context of additions, aiming to unravel the interplay between randomness and resulting statistical characteristics. The Materials and Methods chapter details the construction of datasets comprising up to 300 billion pseudo-random values, employing three distinct layers of manipulation. The Results chapter visually and quantitatively explores the generated datasets, emphasizing distribution and standard deviation metrics. The study concludes with reflections on the implications of pseudo-random value manipulation and suggests avenues for future research. In the layered exploration, the first layer introduces subtle normalization with increasing summations, while the second layer enhances normality. The third layer disrupts typical distribution patterns, leaning towards randomness despite pseudo-random value summation. Standard deviation patterns across layers further illuminate the dynamic interplay of pseudo-random operations on statistical characteristics. While not aiming to disrupt academic norms, this work modestly contributes insights into data distribution complexities. Future studies are encouraged to delve deeper into the implications of data manipulation on statistical outcomes, extending the understanding of pseudo-random operations in diverse contexts.

| Layer | Dataset |
| ------------- | ------------- |
| Pseudorandom numbers generated in the **1st layer**  | 🔗 [1st part](https://github.com/ergoncugler/pseudorandom/blob/main/df_1st_layer_part_1.xlsx), 🔗 [2nd part](https://github.com/ergoncugler/pseudorandom/blob/main/df_1st_layer_part_2.xlsx), 🔗 [3rd part](https://github.com/ergoncugler/pseudorandom/blob/main/df_1st_layer_part_3.xlsx) and 🔗 [4th part](https://github.com/ergoncugler/pseudorandom/blob/main/df_1st_layer_part_4.xlsx) |
| Pseudorandom numbers generated in the **2nd layer**  | 🔗 [All parts](https://github.com/ergoncugler/pseudorandom/blob/main/df_2nd_layer.xlsx) [a single excel file] |
| Pseudorandom numbers generated in the **3rd layer**  | 🔗 [All parts](https://github.com/ergoncugler/pseudorandom/blob/main/df_3rd_layer.xlsx) [a single excel file] |

## About the code behind

We employed a variety of Python libraries to conduct our statistical analyses and visualization tasks. The scipy.stats library provided essential statistical functions such as skewness, kurtosis, Shapiro-Wilk test, Kolmogorov-Smirnov test, and the normal distribution. For streamlined and interactive data visualization, we leveraged the capabilities of plotly.express, enabling us to create insightful plots and charts. Data manipulation and handling were efficiently managed using the versatile pandas library, while numerical operations and array handling were facilitated by numpy. Additionally, the statistics library proved useful for basic statistical calculations, and the random module allowed for the generation of random numbers when necessary. Lastly, we utilized the time module to measure and monitor certain processes.

```python
max_number = 100
total_numbers = 1000
total_sets = 10000
total_additions = 10000
```

**1st Pseudo-Randomity Layer:** No added randomness within the set or quantity loop, just progressive additions as you go through the loop. Here the data is generated with additions progressively. In the first set, there is just a random number; In the second set, there are two random numbers added together; (...) In the last set, there are 10,000 random numbers added together.

```python
# Sets loop
for set in range(1, total_sets + 1): 
    data = []


    # Amount loop
    for _ in range(total_numbers):
        value = random.randint(1, max_number)            


        # Addition loop
        for loop in range(total_additions - 1):
            value = value + random.randint(1, max_number)
        data.append(value)
```

**2nd Pseudo-Randomity Layer:** Addition of randomness inside the set loop but outside the quantity loop, i.e. each number in the set contains the same random amount of additions. Here data is generated with random additions. The first set can have between 1 and 10,000 random numbers added together; The second set can have between 1 and 10,000 random numbers added together; (...) The last set can have between 1 and 10,000 random numbers added together.

```python
# Sets loop
for set in range(1, total_sets + 1):
    data = []
    random_additions = random.randint(1, total_additions)


    # Amount loop
    for _ in range(total_numbers):
        value = random.randint(1, max_number)


        # Addition loop
        for loop in range(random_additions - 1):
            value = value + random.randint(1, max_number)
        data.append(value)
```

**3rd Pseudo-Randomity Layer:** Addition of randomness within the quantity loop, i.e. each number in the set contains a random quantity of additions. Here the data is generated with random additions within the sets themselves. Each of the 1,000 numbers in the first set can have between 1 and 10,000 random numbers added together; Each of the 1,000 numbers in the second set can have between 1 and 10,000 random numbers added together; (...) Each of the 1,000 numbers in the last set can have between 1 and 10,000 random numbers added together.

```python
# Sets loop
for set in range(1, total_sets + 1):
    data = []


    # Amount loop
    for _ in range(total_numbers):
        random_additions = random.randint(1, total_additions)
        value = random.randint(1, max_number)


        # Addition loop
        for loop in range(random_additions - 1):
            value = value + random.randint(1, max_number)
       data.append(value)
```

___

## More About:

Its use is highly encouraged and recommended for academic and scientific research, content analysis, sentiment and speech. It is free and open, and academic use is encouraged. Its responsible use is the sole responsibility of those who adapt and manipulate the data.

___

## Author Info:

Ergon Cugler de Moraes Silva, from Brazil, mailto: <a href="contato@ergoncugler.com">contato@ergoncugler.com</a> / Master's Program in Public Administration and Government, Getulio Vargas Foundation (FGV).

### How to Cite it:

**SILVA, Ergon Cugler de Moraes. Exploring ‘pseudorandom’ value addition operations in datasets: A layered approach to escape from normal-Gaussian patterns. (feb) 2024. Avaliable at: <a>https://github.com/ergoncugler/pseudorandom/<a>.**
