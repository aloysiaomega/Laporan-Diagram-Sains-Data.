PERTANYAAN 1
=================

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

data = pd.read_csv('data.csv')

fig = plt.figure(figsize=(10, 6))
plt.title('Distribusi Usia')
plt.xlabel('Usia')
plt.ylabel('Frekuensi')

chart = plt.subplot()
chart.bar(data['Age'].value_counts().index, data['Age'].value_counts().values)

plt.show()

PERTANYAAN 2
=================
import pandas as pd
import plotly.express as px

data = pd.read_csv('data.csv')

df = data['Gender'].value_counts().reset_index()
df.columns = ['Gender', 'Count']

chart = px.pie(df, values='Count', names='Gender', title='Perbedaan Skor Introversi antara Pria dan Wanita')
chart.show()

PERTANYAAN 3
=================
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

data = pd.read_csv('Cleaned_Personality_Types_Dataset.csv')

plt.figure(figsize=(12, 8))
sns.countplot(x='Education', hue='Personality', data=data)
plt.title('Hubungan antara Tingkat Pendidikan dan Tipe Kepribadian MBTI')
plt.xlabel('Tingkat Pendidikan')
plt.ylabel('Jumlah')
plt.legend(title='MBTI')
plt.show()

PERTANYAAN 4
=================
import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv('data.csv')

interest_counts = data.groupby('Interest')['Sensing Score'].count().sort_values()

fig = plt.figure(figsize=(10, 10))

plt.barh(interest_counts.index, interest_counts.values)

plt.title('Korelasi antara Skor Sensing dan Area Minat Individu')
plt.xlabel('Jumlah')
plt.ylabel('Area Minat')

plt.show()

PERTANYAAN 5
=================
import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv('data.csv')

age_personality_counts = data.groupby(['Age', 'Personality']).size().unstack(fill_value=0)

fig = plt.figure(figsize=(15, 5))

age_personality_counts.plot(kind='bar', stacked=True, ax=plt.gca())

plt.title('Distribusi Tipe Kepribadian MBTI di antara Berbagai Kelompok Usia')
plt.xlabel('Kelompok Usia')
plt.ylabel('Jumlah')

plt.legend(title='MBTI')

plt.show()

PERTANYAAN 6
=================
import pandas as pd
import plotly.express as px

data = pd.read_csv('data.csv')

average_thinking_score = data.groupby('Gender')['Thinking Score'].mean().reset_index()

chart = px.pie(average_thinking_score, values='Thinking Score', names='Gender', title='Rata-rata Skor Thinking berdasarkan Gender')

chart.show()

PERTANYAAN 7
=================
import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv('data.csv')

interest_counts = data.groupby('Interest')['Judging Score'].count().sort_values()

fig = plt.figure(figsize=(10, 10))

plt.bar(interest_counts.index, interest_counts.values)

plt.title('Pengaruh Skor Judging terhadap Preferensi Area Minat')
plt.xlabel('Area Minat')
plt.ylabel('Jumlah')

plt.show()

PERTANYAAN 8
=================
import pandas as pd
import plotly.express as px

data = pd.read_csv('data.csv')

introversion_education_counts = data.groupby('Education')['Introversion Score'].mean().reset_index()

chart = px.pie(introversion_education_counts, values='Introversion Score', names='Education', title='Hubungan antara Skor Introversi Tinggi dan Tingkat Pendidikan')

chart.show()

PERTANYAAN 9
=================
import pandas as pd
import plotly.express as px

data = pd.read_csv('data.csv')
gender_counts = data['Gender'].value_counts().reset_index()
gender_counts.columns = ['Gender', 'Count']

chart = px.pie(gender_counts, values='Count', names='Gender', title='Distribusi Gender dalam Dataset')

chart.show()

PERTANYAAN 10
=================
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

data = pd.read_csv('data.csv')

plt.figure(figsize=(10, 6))
sns.lineplot(x='Age', y='Sensing Score', data=data, label='Sensing Score')
sns.lineplot(x='Age', y='Thinking Score', data=data, label='Thinking Score')
sns.lineplot(x='Age', y='Judging Score', data=data, label='Judging Score')
plt.title('Pola dalam Distribusi Skor Sensing, Thinking, dan Judging Berdasarkan Usia')
plt.xlabel('Usia')
plt.ylabel('Skor')
plt.legend()
plt.show
