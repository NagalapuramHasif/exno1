# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
           import pandas as pd
           df=pd.read_csv("/content/SAMPLEIDS.csv")
           df
## ![image](https://github.com/user-attachments/assets/ecb96bc7-b5dd-4631-b601-c49ca0979c6a)

          df.isnull().sum()
          
## ![image](https://github.com/user-attachments/assets/07f7c768-aca2-4d65-aefd-1bdb887b4eb8)

          df.isnull().any()

 ## ![image](https://github.com/user-attachments/assets/398c7eaa-7ece-4267-9ad2-cf6e5602b6ad)

         df.dropna()

 ## ![image](https://github.com/user-attachments/assets/f1950823-52be-410d-8338-d459bd08fc63)

        df.fillna(0)

## ![image](https://github.com/user-attachments/assets/c8da69f2-cd89-4777-b373-12dc6ff6afcb)

        df.fillna(method="ffill")

## ![image](https://github.com/user-attachments/assets/121014d4-4517-418a-849e-3915705f4952)

        df.fillna(method='bfill')

## ![image](https://github.com/user-attachments/assets/76d34da4-68e8-42d2-9675-13c57cfb227a)

        df.fillna({"GENDER":"MALE","NAME":"SRI","ADDRESS":"POONAMALEE","M1":99,"M2":88,"M3":77,"M4":66,"TOTAL":350,"AVG":112.6987})

## ![image](https://github.com/user-attachments/assets/df853725-4251-48a2-b3cb-8eff8f15f7ec)

        hasif=pd.read_csv("/content/iris.csv")
        print(hasif)

## ![image](https://github.com/user-attachments/assets/0ab686f0-2617-48d5-89f3-63e25bb2339b)

        hasif.describe()

## ![image](https://github.com/user-attachments/assets/5f8ae5e6-696e-4468-abbf-08b603a9bb0e)

        import seaborn as sns
        sns.boxplot(x='sepal_width',data=hasif)

## ![image](https://github.com/user-attachments/assets/0ddc56e6-30cc-43e0-88e3-9a9b9b1de698)

        q1=hasif.sepal_width.quantile(0.25)
        q3=hasif.sepal_width.quantile(0.75)
        iqr=q3-q1
        print(iqr)

## ![image](https://github.com/user-attachments/assets/2f61d225-6d6e-4105-b1c5-3752938ba0aa)

        rid=hasif[((hasif.sepal_width<(q1-1.5*iqr))|(hasif.sepal_width>(q3+1.5*iqr)))]
        rid['sepal_width']

## ![image](https://github.com/user-attachments/assets/57170d2d-a5ac-483f-9e3f-bc75e70ff91f)

        delid=hasif[~((hasif.sepal_width<(q1-1.5*iqr))|(hasif.sepal_width>(q3+1.5*iqr)))]
        delid

## ![image](https://github.com/user-attachments/assets/dca6c8eb-3271-4a15-8557-5ff6e622f042)

        sns.boxplot(x='sepal_length',data=hasif)

## ![image](https://github.com/user-attachments/assets/fb17e53a-28d6-4abf-acfb-b804816a244d)
      
        q1=hasif.sepal_width.quantile(0.25)
        q3=hasif.sepal_width.quantile(0.75)
        iqr=q3-q1
        print(iqr)

## ![image](https://github.com/user-attachments/assets/39928bb2-44b7-4a62-85de-f57a68a982f8)

        low = q1- 1.5*iqr
        high = q3 + 1.5*iqr
        print(low,high)

## ![image](https://github.com/user-attachments/assets/1336ba77-d6d3-411c-8efb-4cb9efb7c837)
         
        import pandas as pd
        import numpy as np
        import scipy.stats as stats
        dataset=pd.read_csv("/content/heights (1).csv")
        dataset

 ## ![image](https://github.com/user-attachments/assets/ce5144e1-97ab-4dd0-a0cf-c74f4b52b718)

       z=np.abs(stats.zscore(dataset["height"]))
       print(z)

 ## ![image](https://github.com/user-attachments/assets/26d48289-2cac-45bc-aaba-0ce56101cb1b)

      hf=dataset[h<3]
      hf

## ![image](https://github.com/user-attachments/assets/62c40fd4-3e1f-4f80-8e17-3427f73c04d6)
      
# Result
## Thus the given program executed successfully.
