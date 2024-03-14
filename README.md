# CSC245-HW3
# 1. Write a Pandas program to join the two given dataframes along rows and assign all data.
import pandas as pd

student_data1 = pd.DataFrame({
        'student_id': ['S1', 'S2', 'S3', 'S4', 'S5'],
         'name': ['Danniella Fenton', 'Ryder Storey', 'Bryce Jensen', 'Ed Bernal', 'Kwame Morin'], 
        'marks': [200, 210, 190, 222, 199]})

student_data2 = pd.DataFrame({
        'student_id': ['S4', 'S5', 'S6', 'S7', 'S8'],
        'name': ['Scarlette Fisher', 'Carla Williamson', 'Dante Morse', 'Kaiser William', 'Madeeha Preston'], 
        'marks': [201, 200, 198, 219, 201]})

print("Original DataFrames:")
print(student_data1)
print(student_data2)
print("\nJoin the said two dataframes along rows:")
result_data = pd.concat([student_data1, student_data2])
print(result_data)


# 2. Write a Pandas program to join the two given dataframes along columns and assign all data.
import pandas as pd

student_data1 = pd.DataFrame({
        'student_id': ['S1', 'S2', 'S3', 'S4', 'S5'],
         'name': ['Danniella Fenton', 'Ryder Storey', 'Bryce Jensen', 'Ed Bernal', 'Kwame Morin'], 
        'marks': [200, 210, 190, 222, 199]})

student_data2 = pd.DataFrame({
        'student_id': ['S4', 'S5', 'S6', 'S7', 'S8'],
        'name': ['Scarlette Fisher', 'Carla Williamson', 'Dante Morse', 'Kaiser William', 'Madeeha Preston'], 
        'marks': [201, 200, 198, 219, 201]})

print("Original DataFrames:")
print(student_data1)
print("")
print(student_data2)
print("\nJoin the said two dataframes along columns:")
result_data = pd.concat([student_data1, student_data2], axis = 1)
print(result_data)

# 3. Write a Pandas program to append rows to an existing DataFrame and display the combined data.
import pandas as pd

student_data1 = pd.DataFrame({
    'student_id': ['S1', 'S2', 'S3', 'S4', 'S5'],
    'name': ['Danniella Fenton', 'Ryder Storey', 'Bryce Jensen', 'Ed Bernal', 'Kwame Morin'],
    'marks': [200, 210, 190, 222, 199]
})

new_row = pd.DataFrame({
    'student_id': ['S6'],
    'name': ['Scarlette Fisher'],
    'marks': [205]
})

combined_data = pd.concat([student_data1, new_row], ignore_index=True)

print("Original DataFrame:")
print(student_data1)

print("\nNew Row(s):")
print(new_row)

print("\nCombined Data:")
print(combined_data)


# 4. Write a Pandas program to append a list of dictioneries or series to a existing DataFrame and display the combined data.
import pandas as pd

student_data1 = pd.DataFrame({
    'student_id': ['S1', 'S2', 'S3', 'S4', 'S5'],
    'name': ['Danniella Fenton', 'Ryder Storey', 'Bryce Jensen', 'Ed Bernal', 'Kwame Morin'],
    'marks': [200, 210, 190, 222, 199]
})

new_rows = pd.DataFrame([
    {'student_id': 'S6', 'name': 'Scarlette Fisher', 'marks': 203},
    {'student_id': 'S7', 'name': 'Bryce Jensen', 'marks': 207}
])

combined_data = pd.concat([student_data1, new_rows], ignore_index=True)

print("Original DataFrame:")
print(student_data1)

print("\nNew Rows:")
print(new_rows)

print("\nCombined Data:")
print(combined_data)


# 5. Write a Pandas program to join the two given dataframes along rows and merge with another dataframe along the common column id.
import pandas as pd
student_data1 = pd.DataFrame({
        'student_id': ['S1', 'S2', 'S3', 'S4', 'S5'],
         'name': ['Danniella Fenton', 'Ryder Storey', 'Bryce Jensen', 'Ed Bernal', 'Kwame Morin'], 
        'marks': [200, 210, 190, 222, 199]})

student_data2 = pd.DataFrame({
        'student_id': ['S4', 'S5', 'S6', 'S7', 'S8'],
        'name': ['Scarlette Fisher', 'Carla Williamson', 'Dante Morse', 'Kaiser William', 'Madeeha Preston'], 
        'marks': [201, 200, 198, 219, 201]})

exam_data = pd.DataFrame({
        'student_id': ['S1', 'S2', 'S3', 'S4', 'S5', 'S7', 'S8', 'S9', 'S10', 'S11', 'S12', 'S13'],
        'exam_id': [23, 45, 12, 67, 21, 55, 33, 14, 56, 83, 88, 12]})

print("Original DataFrames:")
print(student_data1)
print(student_data2)
print(exam_data)

print("\nJoin first two said dataframes along rows:")
result_data = pd.concat([student_data1, student_data2])
print(result_data)

print("\nNow join the said result_data and df_exam_data along student_id:")
final_merged_data = pd.merge(result_data, exam_data, on='student_id')
print(final_merged_data)


# 6. Write a Pandas program to join the two dataframes using the common column of both dataframes.
import pandas as pd
student_data1 = pd.DataFrame({
        'student_id': ['S1', 'S2', 'S3', 'S4', 'S5'],
         'name': ['Danniella Fenton', 'Ryder Storey', 'Bryce Jensen', 'Ed Bernal', 'Kwame Morin'], 
        'marks': [200, 210, 190, 222, 199]})

student_data2 = pd.DataFrame({
        'student_id': ['S4', 'S5', 'S6', 'S7', 'S8'],
        'name': ['Scarlette Fisher', 'Carla Williamson', 'Dante Morse', 'Kaiser William', 'Madeeha Preston'], 
        'marks': [201, 200, 198, 219, 201]})

print("Original DataFrames:")
print(student_data1)
print(student_data2)
merged_data = pd.merge(student_data1, student_data2, on='student_id', how='inner')
print("Merged data (inner join):")
print(merged_data)


# 7. Write a Pandas program to join the two dataframes with matching records from both sides where available.
import pandas as pd
student_data1 = pd.DataFrame({
        'student_id': ['S1', 'S2', 'S3', 'S4', 'S5'],
         'name': ['Danniella Fenton', 'Ryder Storey', 'Bryce Jensen', 'Ed Bernal', 'Kwame Morin'], 
        'marks': [200, 210, 190, 222, 199]})

student_data2 = pd.DataFrame({
        'student_id': ['S4', 'S5', 'S6', 'S7', 'S8'],
        'name': ['Scarlette Fisher', 'Carla Williamson', 'Dante Morse', 'Kaiser William', 'Madeeha Preston'], 
        'marks': [201, 200, 198, 219, 201]})

print("Original DataFrames:")
print(student_data1)
print(student_data2)
merged_data = pd.merge(student_data1, student_data2, on='student_id', how='outer')
print("Merged data (outer join):")
print(merged_data)


# 8. Write a Pandas program to join (left join) the two dataframes using keys from left dataframe only.
import pandas as pd
data1 = pd.DataFrame({'key1': ['K0', 'K0', 'K1', 'K2'],
                     'key2': ['K0', 'K1', 'K0', 'K1'],
                     'P': ['P0', 'P1', 'P2', 'P3'],
                     'Q': ['Q0', 'Q1', 'Q2', 'Q3']}) 
data2 = pd.DataFrame({'key1': ['K0', 'K1', 'K1', 'K2'],
                      'key2': ['K0', 'K0', 'K0', 'K0'],
                      'R': ['R0', 'R1', 'R2', 'R3'],
                      'S': ['S0', 'S1', 'S2', 'S3']})
print("Original DataFrames:")
print(data1)
print("--------------------")
print(data2)
print("\nMerged Data (keys from data1):")
merged_data = pd.merge(data1, data2, how='left', on=['key1', 'key2'])
print(merged_data)
print("\nMerged Data (keys from data2):")
merged_data = pd.merge(data2, data1, how='left', on=['key1', 'key2'])
print(merged_data)


# 9. Write a Pandas program to join two dataframes using keys from right dataframe only.
import pandas as pd
data1 = pd.DataFrame({'key1': ['K0', 'K0', 'K1', 'K2'],
                     'key2': ['K0', 'K1', 'K0', 'K1'],
                     'P': ['P0', 'P1', 'P2', 'P3'],
                     'Q': ['Q0', 'Q1', 'Q2', 'Q3']}) 
data2 = pd.DataFrame({'key1': ['K0', 'K1', 'K1', 'K2'],
                      'key2': ['K0', 'K0', 'K0', 'K0'],
                      'R': ['R0', 'R1', 'R2', 'R3'],
                      'S': ['S0', 'S1', 'S2', 'S3']})
print("Original DataFrames:")
print(data1)
print("--------------------")
print(data2)
print("\nMerged Data (keys from data2):")
merged_data = pd.merge(data1, data2, how='right', on=['key1', 'key2'])
print(merged_data)
print("\nMerged Data (keys from data1):")
merged_data = pd.merge(data2, data1, how='right', on=['key1', 'key2'])
print(merged_data)


# 10. Write a Pandas program to merge two given datasets using multiple join keys.
import pandas as pd
data1 = pd.DataFrame({'key1': ['K0', 'K0', 'K1', 'K2'],
                     'key2': ['K0', 'K1', 'K0', 'K1'],
                     'P': ['P0', 'P1', 'P2', 'P3'],
                     'Q': ['Q0', 'Q1', 'Q2', 'Q3']}) 
data2 = pd.DataFrame({'key1': ['K0', 'K1', 'K1', 'K2'],
                      'key2': ['K0', 'K0', 'K0', 'K0'],
                      'R': ['R0', 'R1', 'R2', 'R3'],
                      'S': ['S0', 'S1', 'S2', 'S3']})
print("Original DataFrames:")
print(data1)
print("-------------------")
print(data2)
print("\nMerged Data:")
merged_data = pd.merge(data1, data2, on=['key1', 'key2'])
print(merged_data)


# 11. Write a Pandas program to create a new DataFrame based on existing series, using specified argument and override the existing columns names.
import pandas as pd
s1 = pd.Series([0, 1, 2, 3], name='col1')
s2 = pd.Series([0, 1, 2, 3])
s3 = pd.Series([0, 1, 4, 5], name='col3')
df = pd.concat([s1, s2, s3], axis=1, keys=['column1', 'column2', 'column3'])
print(df)


# 12. Write a Pandas program to create a combination from two dataframes where a column id combination appears more than once in both dataframes
import pandas as pd
data1 = pd.DataFrame({'key1': ['K0', 'K0', 'K1', 'K2'],
                     'key2': ['K0', 'K1', 'K0', 'K1'],
                     'P': ['P0', 'P1', 'P2', 'P3'],
                     'Q': ['Q0', 'Q1', 'Q2', 'Q3']}) 
data2 = pd.DataFrame({'key1': ['K0', 'K1', 'K1', 'K2'],
                      'key2': ['K0', 'K0', 'K0', 'K0'],
                      'R': ['R0', 'R1', 'R2', 'R3'],
                      'S': ['S0', 'S1', 'S2', 'S3']})
print("Original DataFrames:")
print(data1)
print("--------------------")
print(data2)
print("\nMerged Data (many-to-many join case):")
result = pd.merge(data1, data2, on='key1')
print(result)


# 13. Write a Pandas program to combine the columns of two potentially differently-indexed DataFrames into a single result DataFrame.
import pandas as pd
data1 = pd.DataFrame({'A': ['A0', 'A1', 'A2'],
                      'B': ['B0', 'B1', 'B2']},
                     index=['K0', 'K1', 'K2'])

data2 = pd.DataFrame({'C': ['C0', 'C2', 'C3'],
                      'D': ['D0', 'D2', 'D3']},
                     index=['K0', 'K2', 'K3'])
 
print("Original DataFrames:")
print(data1)
print("--------------------")
print(data2)
print("\nMerged Data (Joining on index):")
result = data1.join(data2)
print(result)


# 14. Write a Pandas program to merge two given dataframes with different columns.
import pandas as pd
data1 = pd.DataFrame({'key1': ['K0', 'K0', 'K1', 'K2'],
                     'key2': ['K0', 'K1', 'K0', 'K1'],
                     'P': ['P0', 'P1', 'P2', 'P3'],
                     'Q': ['Q0', 'Q1', 'Q2', 'Q3']}) 
data2 = pd.DataFrame({'key1': ['K0', 'K1', 'K1', 'K2'],
                      'key2': ['K0', 'K0', 'K0', 'K0'],
                      'R': ['R0', 'R1', 'R2', 'R3'],
                      'S': ['S0', 'S1', 'S2', 'S3']})
print("Original DataFrames:")
print(data1)
print("--------------------")
print(data2)
print("\nMerge two dataframes with different columns:")
result = pd.concat([data1,data2], axis=0, ignore_index=True)
print(result)


# 15. Write a Pandas program to Combine two DataFrame objects by filling null values in one DataFrame with non-null values from other DataFrame.
import pandas as pd
df1 = pd.DataFrame({'A': [None, 0, None], 'B': [3, 4, 5]})
df2 = pd.DataFrame({'A': [1, 1, 3], 'B': [3, None, 3]})
df1.combine_first(df2)
print("Original DataFrames:")
print(df1)
print("--------------------")
print(df2)
print("\nMerge two dataframes with different columns:")
result = df1.combine_first(df2)
print(result)

