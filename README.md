## Introduction to Streamlit Demo App  

The **Streamlit Demo App** is a simple yet powerful web application designed to showcase the capabilities of **Streamlit**, a Python framework for building interactive web applications. This repository provides a ready-to-run example that demonstrates various **Streamlit widgets, data visualization techniques, and layout components** to help users quickly create and deploy interactive applications.  

With just a few lines of code, **Streamlit** enables developers to build dashboards, machine learning interfaces, and data-driven web applications—without requiring deep web development knowledge.  

### This demo includes:  
- ✅ **Interactive Widgets** – Sliders, text inputs, buttons, checkboxes, and more.  
- ✅ **Data Visualization** – Charts using Matplotlib, Altair, and Plotly.  
- ✅ **Dynamic Layouts** – Columns, sidebars, and expanders for better content organization.  
- ✅ **User Interaction** – Text inputs, dropdowns, and file uploads to enhance interactivity.  

Whether you're a beginner exploring **Streamlit** or an experienced developer looking for a quick reference, this repository provides a hands-on guide to building **interactive Python web applications with ease**. 🚀


### Step 1: Create a GitHub Repository
1. Go to [GitHub](https://github.com) and log in to your account.
2. Click on the `+` sign in the top-right corner and select **New repository**.
3. Name your repository (e.g., `streamlit-demo`).
4. Add a description (optional).
5. Choose whether the repository should be public or private.
6. Initialize the repository with a `README.md` file (optional).
7. Click **Create repository**.

---

### Step 2: Add Files to the Repository
1. Clone the repository to your local machine:
   ```bash
   git clone https://github.com/your-username/streamlit-demo.git
   ```
2. Navigate to the repository folder:
   ```bash
   cd streamlit-demo
   ```

---

### Step 3: Add the Code File
1. Create a new file named `app.py` and paste the provided code into it. The file should look like this:

```python
import streamlit as st
import pandas as pd
import numpy as np
import altair as alt
import plotly.express as px
import matplotlib.pyplot as plt

# Create columns
col1, col2 = st.columns(2)

# Add content to the first column
with col1:
    st.header("Column 1")
    st.write("This is the first column.")

# Add content to the second column
with col2:
    st.header("Column 2")
    st.write("This is the second column.")

# Create an expander
with st.expander("Click to expand"):
    st.write("This content is hidden by default.")
    st.write("You can add more content here.")

# Add widgets to the sidebar
st.sidebar.header("Sidebar")
selected_city = st.sidebar.selectbox("Select a city", ["New York", "Los Angeles", "Chicago"])
st.sidebar.write(f"You selected {selected_city}.")

# Text input
name = st.text_input("Enter your name", "John Doe")
st.write(f"Hello, {name}!")

# Number input
age = st.number_input("Enter your age", min_value=0, max_value=100, value=25)
st.write(f"You are {age} years old.")

# Slider
height = st.slider("Select your height (in cm)", 100, 200, 175)
st.write(f"Your height is {height} cm.")

# Selectbox
city = st.selectbox("Select your city", ["New York", "Los Angeles", "Chicago"])
st.write(f"You selected {city}.")

# Multiselect
hobbies = st.multiselect("Select your hobbies", ["Reading", "Traveling", "Coding", "Sports"])
st.write(f"Your hobbies are: {', '.join(hobbies)}")

# Checkbox
agree = st.checkbox("I agree to the terms and conditions")
if agree:
    st.write("Thank you for agreeing!")

# Create a DataFrame
data = pd.DataFrame({
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'City': ['New York', 'Los Angeles', 'Chicago']
})

# Display DataFrame
st.write("Displaying a DataFrame:")
st.dataframe(data)

# Display static table
st.table(data)

# Display JSON
st.json(data.to_dict())

# Title
st.title("My First Streamlit App")

# Header
st.header("This is a header")

# Subheader
st.subheader("This is a subheader")

# Text
st.text("This is some text.")

# Markdown
st.markdown("*This is bold text* using Markdown.")

# Write (flexible function for displaying text, data, or plots)
st.write("This is written using st.write.")

user_input = st.text_input('Enter a custom message:', 'Hello, Streamlit!')

df = pd.DataFrame(np.random.randn(500, 3), columns=['x', 'y', 'z'])
chart = alt.Chart(df).mark_circle().encode(
    x='x', y='y', size='z', color='z', tooltip=['x', 'y', 'z']
)
st.altair_chart(chart, use_container_width=True)

df = pd.DataFrame(np.random.randn(10, 2), columns=['x', 'y'])
st.bar_chart(df)

df = pd.DataFrame(np.random.randn(10, 2), columns=['x', 'y'])
st.line_chart(df)

df = pd.DataFrame(np.random.randn(10, 2), columns=['x', 'y'])
st.area_chart(df)

data = pd.DataFrame({"x": [1, 2, 3], "y": [10, 20, 30]})

# Display the data in the Streamlit app
st.write(data)

# Create a Plotly figure
fig = px.line(data, x="x", y="y", title="Simple Plotly Example")

# Display the plot in the Streamlit app
st.plotly_chart(fig)

number = st.slider("Pick a number", 1, 100)
st.write(f"You picked: {number}")

st.title("Streamlit is amazing")

# Header
st.header("This is a header")

# Subheader
st.subheader("This is a subheader")

# Text
st.text("Hello GeeksForGeeks!!!")

# Markdown
st.markdown("### This is a markdown")

# success
st.success("Success")

# success
st.info("Information")

# success
st.warning("Warning")

# success
st.error("Error")

# Exception - This has been added later
exp = ZeroDivisionError("Trying to divide by Zero")
st.exception(exp)

# Write text
st.write("Text with write")

# Writing python inbuilt function range()
st.write(range(10))

# Display Images

# import Image from pillow to open images
from PIL import Image
img = Image.open("streamlit.png")

# display image using streamlit
# width is used to set the width of an image
st.image(img, width=200)

# checkbox
# check if the checkbox is checked
# title of the checkbox is 'Show/Hide'
if st.checkbox("Show/Hide"):
    # display the text if the checkbox returns True value
    st.text("Showing the widget")

# radio button
# first argument is the title of the radio button
# second argument is the options for the radio button
status = st.radio("Select Gender: ", ('Male', 'Female'))

# conditional statement to print
# Male if male is selected else print female
# show the result using the success function
if (status == 'Male'):
    st.success("Male")
else:
    st.success("Female")

# Selection box

# first argument takes the titleof the selectionbox
# second argument takes options
hobby = st.selectbox("Hobbies: ",
                     ['Dancing', 'Reading', 'Sports'])

# print the selected hobby
st.write("Your hobby is: ", hobby)

# multi select box

# first argument takes the box title
# second argument takes the options to show
hobbies = st.multiselect("Hobbies: ",
                         ['Dancing', 'Reading', 'Sports'])

# write the selected options
st.write("You selected", len(hobbies), 'hobbies')

# Create a simple button that does nothing
st.button("Click me for no reason")

# Create a button, that when clicked, shows a text
if(st.button("About")):
    st.text("Welcome To GeeksForGeeks!!!")

# Text Input

# save the input text in the variable 'name'
# first argument shows the title of the text input box
# second argument displays a default text inside the text input area
name = st.text_input("Enter Your name", "Type Here ...")

# display the name when the submit button is clicked
# .title() is used to get the input text string
if(st.button('Submit')):
    result = name.title()
    st.success(result)

# slider

# first argument takes the title of the slider
# second argument takes the starting of the slider
# last argument takes the end number
level = st.slider("Select the level", 1, 5)

# print the level
# format() is used to print value
# of a variable at a specific position
st.text('Selected: {}'.format(level))

st.image("kid.jpg", caption="A kid playing")
# st.audio("audio.mp3")
# st.video("video.mp4")

st.checkbox('Yes')
st.button('Click Me')
st.radio('Pick your gender', ['Male', 'Female'])
st.selectbox('Pick a fruit', ['Apple', 'Banana', 'Orange'])
st.multiselect('Choose a planet', ['Jupiter', 'Mars', 'Neptune'])
st.select_slider('Pick a mark', ['Bad', 'Good', 'Excellent'])
st.slider('Pick a number', 0, 50)

st.number_input('Pick a number', 0, 10)
st.text_input('Email address')
st.date_input('Traveling date')
st.time_input('School time')
st.text_area('Description')
st.file_uploader('Upload a photo')
st.color_picker('Choose your favorite color')

st.balloons()  # Celebration balloons
st.progress(10)  # Progress bar
with st.spinner('Wait for it...'):
    time.sleep(10)  # Simulating a process delay

with st.container():
    st.write("This is inside the container")
```

---

### Step 4: Format the `README.md` File
Open the `README.md` file and add the following Markdown content:

```markdown
# Streamlit Demo App

This repository contains a Python script demonstrating various features of Streamlit, a powerful framework for building interactive web applications.

---

## Features

The script includes the following features:

- **Interactive Widgets**: Text inputs, sliders, checkboxes, radio buttons, and more.
- **Data Visualization**: Bar charts, line charts, area charts, and interactive charts using Altair and Plotly.
- **Layouts**: Columns, expanders, and sidebars for organizing content.

---

## Code Overview

### Widgets
The script demonstrates the use of the following widgets:

- **Text Input**: `st.text_input`
- **Slider**: `st.slider`
- **Checkbox**: `st.checkbox`
- **Radio Button**: `st.radio`
- **Selectbox**: `st.selectbox`
- **Multiselect**: `st.multiselect`

### Data Visualization
The script showcases how to create:

- **Bar Charts**: `st.bar_chart`
- **Line Charts**: `st.line_chart`
- **Area Charts**: `st.area_chart`
- **Interactive Charts**: Using Altair and Plotly.

### Layouts
- **Columns**: `st.columns`
- **Expander**: `st.expander`
- **Sidebar**: `st.sidebar`

---

## How to Run the App

1. Install Streamlit:
   ```bash
   pip install streamlit
   ```
2. Run the script:
   ```bash
   streamlit run app.py
   ```
3. Open your browser and navigate to `http://localhost:8501`.

---

## Example Code

Here is a snippet from the script:

```python
import streamlit as st

# Text input
name = st.text_input("Enter your name", "John Doe")
st.write(f"Hello, {name}!")
```

> **Note**: Make sure to install all required dependencies before running the script.

---

## Screenshots

![Streamlit App](https://via.placeholder.com/600x400) *(Replace with actual screenshot)*

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
```

---

### Step 5: Commit and Push Changes
1. Add the files to Git:
   ```bash
   git add app.py README.md
   ```
2. Commit the changes:
   ```bash
   git commit -m "Added Streamlit demo script and formatted README.md"
   ```
3. Push the changes to GitHub:
   ```bash
   git push origin main
   ```

---

### Step 6: Verify on GitHub
1. Go to your GitHub repository.
2. Verify that the `app.py` file and the formatted `README.md` are visible.
3. Check that the Markdown formatting (e.g., headers, code blocks, lists) is correctly rendered.

---

### Example Repository Structure
Your repository should look like this:

```
streamlit-demo/
├── app.py
├── README.md
└── LICENSE
