![header](header.png)

## Summary
This group project analyzes Cyclistic’s historical bike trip data to design targeted marketing strategies aimed at converting casual riders into annual members. To achieve this, we raised three main questions followed by the findings and recommendations.

| Question | Key Insight | Recommendation |
| --- | --- | --- |
| How are casual riders and subscribers different? | Casual riders and members differ in ride duration, times, bike types, popular stations, monthly, and hourly trend in Q1 2023 | Implement a targeted promotional campaign specifically designed to encourage casual riders to convert into subscribers |
| Why would casual riders buy membership | Pricing analysis reflects the advantage of annual membership, offering per minute cost-free rides | Launch a targeted marketing campaign to promote anual membership benefits, highlighting cost savings on frequent or longer rides |
| How digital media could affect their marketing tactics? | Customer type, time, and location can be used for implementing cost-efficient marketing approach to reach potential subscribers | Utilize customer segmentation based on the features to create personalized advertizing campaigns. |


## Dataset Used In This Project
This project used dataset from Divvy in Q1 2023 (January, February, March) . The files of dataset is downloaded from this [URL](https://divvy-tripdata.s3.amazonaws.com/index.html), and can be directly accessed by running the following script. Please note that the files' size are relatively big, it may time will take a while to run the dataset. 

```python
import pandas as pd
import requests
from zipfile import ZipFile
from io import BytesIO

file_names = [
    '202301-divvy-tripdata.zip',
    '202302-divvy-tripdata.zip',
    '202303-divvy-tripdata.zip'
    ]

base_url = 'https://divvy-tripdata.s3.amazonaws.com/'

dfs = []
for file_name in file_names:
    url = url + file_name
    response = requests.get(url)
    
    with ZipFile(BytesIO(response.content)) as z:
        csv_file = z.namelist()[0]
        df = pd.read_csv(z.open(csv_file))
        dfs.append(df)

combined_df = pd.concat(dfs, ignore_index=True)

combined_df.head()
```

## Collaboration
This project was completed by our team. We welcome collaboration opportunities. Please feel free to contact us for further information.
1. [Aditya Wahyu](https://github.com/AdityaIKO)
2. [Chandra Driastama](https://github.com/chandra879012)
3. [Hamzah Mulyana](https://github.com/hamzahmulyana)
4. [Galuh Anjarweni](https://github.com/Anjarwenig)