---
Layout: post
Title: "Talend Mapping and Denormalization"
---

| Key | Category | Value |
| ---| ---| ---|
| 12345 | Role | Teacher |
| 12345 | Subject | Science |
| 12346 | Subject | Science |
| 12346 | Subject | Math |


I have Ms. Skelly, teacher 12345, in my system. I need to give her a role of Teacher and a Subject of Science. That’s fine. I just map one to one. But it doesn’t work nearly as well when I try to do Mr. Fell, teacher 12346. He has two subjects!

In Salesforce, I’m solving this problem with a multi-select picklist. My subjects need to be loaded in as semicolon-delimited lists. Luckily, Talend has a “Denormalize” function. I feed it one or more fields to denormalize, along with a delimiter, and it sets them up. So I end up with this, which is much easier to load.  

| Key | Category | Value |
| ---| ---| ---|
| 12345 | Role | Teacher |
| 12345 | Subject | Science |
| 12346 | Subject | Science;Math |

But then I hear that everyone whose role is Teacher should actually be Elementary Teacher!

To solve the endless mapping and remapping, I use a Fixed Flow Input and just create a table with one row per value: category, old value, and new value. That gives me the option to look up the old value and output the new value for any value in the category. 