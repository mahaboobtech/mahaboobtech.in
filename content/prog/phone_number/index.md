+++
title = 'Phone_number'
date = 2024-10-01T09:55:54+05:30
draft = false
tags = [""]
Categories = [""]
+++
{{< katex >}}

while i was chatting with my friends on WhatsApp and telegram, where i have all the numbers of my B.Tech friends but problem is they don't have my number because i was introvert so they dont know me well even though i have pretty friends to chat well thats not the point here, i was wondering what if i have the all the Indian number in my whatsapp so that i can see their status and also telegram status and signal status well that is the point where i got this content and it is a disaster for me , let me explain what are the problems I have got 

## approach 
As a software programmer i tried in coding style and wrote the code in python using vobject module  but it always get error 

here my code 

```
import vobject

  

def cardwritingprocess(name, number, filename):

    cardwriter = vobject.vCard()

    cardwriter.add("fn").value = name

    cardwriter.add("tel").value = number

    with open(filename, "a") as file:  # Append mode

        file.write(cardwriter.serialize())

        file.write("\n")  # Optional: Add a newline between vCards

  

# Change the number format to a 10-digit number

for i in range(6, 10):

    for j in range(10):

        for k in range(10):

            for l in range(10):

                for m in range(10):

                    for n in range(10):

                        for o in range(10):

                            for p in range(10):

                                for q in range(10):

                                    for r in range(10):

                                        number = str(i) + str(j) + str(k) + str(l) + str(m) + str(n) + str(o) + str(p) + str(q) + str(r)

                                        name = f"Contact_{number}"  # Example name

                                        print(f"Creating vCard for {name} with number {number}")

                                        cardwritingprocess(name, number, "realdraft.vcf")

```

which is a variable cant store such data at once ! 

i was like damn what the fish ! 
so you know like every one i googled this things and finally i figured it out the problem and...............

after  rectifying the error heres the new code, 
with neat commented ...................
```
import vobject

import os

  

def generate_vcards_to_file(filename, start_count, end_count, batch_size=10000):

    with open(filename, 'w') as file:

        count = start_count

        for first_digit in range(6, 10):  # First digit from 6 to 9

            for i in range(10**9):  # Iterate through 9-digit numbers

                phone_number = f"{first_digit}{i:09d}"

                name = str(count)

                # Create vCard entry

                cardwriter = vobject.vCard()

                cardwriter.add("fn").value = name

                cardwriter.add("tel").value = phone_number

                # Serialize and strip any extra newlines

                serialized_card = cardwriter.serialize().strip()

                # Write the vCard entry to the file without extra newlines

                file.write(serialized_card + "\n")  # Add only one newline to separate entries

  

                count += 1

                if count > end_count:

                    return  # Exit after reaching the end count

  

                # Write in batches to avoid excessive I/O operations

                if (count - start_count) % batch_size == 0:

                    file.flush()  # Ensure data is written to disk

  

def generate_vcards():

    # File handling

    base_filename = "all_contacts_part_"

    start_count = 1

    end_count = 1000000  # Adjust as needed

    batch_size = 100000  # Number of entries to write before flushing

  

    file_index = 0

    while start_count <= 4_000_000_000:

        filename = f"{base_filename}{file_index}.vcf"

        generate_vcards_to_file(filename, start_count, start_count + end_count - 1, batch_size)

        start_count += end_count

        file_index += 1

  

# Run the function to generate vCards

generate_vcards()
```

the first time i run the code it was like okay lets wait and see may be it would take minutes ...................

but after so many minutes like 15 minutes batching the files it was so much MB (mega bytes) then later i again recalculate the thing how much data it would take and also how much time it would take to generate ............. 

later i seared on the internet then i realize its not gonna make it ! where i realize and the whats and telegram wouldnt be sync that kind of data and because if the generate all the files it will took around 242.2 gb which actually my phone doesnt have such space and even my google drive which is limit to 15 gb 

well you may wondering how it would be possible well let me explain this thing from now will be complicated so put your hands on your device carefully 

## calculation part 

### data part 
we need to know why such a hug amount of data is being used well here the answer 
first we need to familiar with vcard file which used to save the contacts in our mobile 

vcard is nothing but a text file where it store a contact like this 

```
BEGIN:VCARD
VERSION:3.0
FN:1
TEL:6000000000
END:VCARD
```

this is only stored only number as you can see FN  = full name , TEL = phone number 

right ! 

so how many number we need to write actually its 4000000000 4 billion number 
well lets see 
we can see out number is starting with 6,7,8,9 only we can see according to TRIA  an Indian government agency settled this thing and as we know indian phone code starting number is +91 

so from 6000000000 to 9999999999 well if we find the difference we get number 4 billion 
right then 
we need to write the 4 billion number 

heres the first question 
1. how much data it will take to write or save one contact 
	for every word in a file takes one byte means 8 bit okay 
	like if you write a word or letter in file 
	like 
	 note pad : hello 
	then the size of its file will be 5 bytes 
	if there is new line like \n then it will take extra 1/2 byte then total 6(linux), 7(windows) bytes 
	yes both works differently so it will take differently 
	
	so as i was telling for saving one contact how much data 
	
	Here’s a rough estimation process:

	1. **Estimate the Size of a Single vCard Entry:**
    
	    - **`BEGIN:VCARD` Line**:
    
	    - 11 bytes for `BEGIN:VCARD`
	    - 2 bytes for newline (`\r\n`)
	    
	    **Total for `BEGIN:VCARD` line**: 13 bytes
	    
	- **Similarly for Other Lines**:
	    
	    - `VERSION:3.0` (9 bytes + 2 bytes newline) = 11 bytes
	    - `FN:<name>` (3 bytes + length of name + 2 bytes newline)
	    - `TEL:<phone number>` (4 bytes + length of phone number + 2 bytes newline)
	    - `END:VCARD` (11 bytes + 2 bytes newline)
	- **Putting It All Together**:
	    
	    - **`BEGIN:VCARD`**: 13 bytes
	    - **`VERSION:3.0`**: 11 bytes
	    - **`FN:<name>`**: 3 bytes + length of `<name>` + 2 bytes newline
	    - **`TEL:<phone number>`**: 4 bytes + length of `<phone number>` + 2 bytes newline
	    - **`END:VCARD`**: 13 bytes (11 bytes for `END:VCARD` + 2 bytes newline)
	    
	    Summing these, assuming `<name>` and `<phone number>` are relatively short:
	    
	    - `BEGIN:VCARD`: 13 bytes
	    - `VERSION:3.0`: 11 bytes
	    - `FN:<name>`: Approx. 3 bytes + length of `<name>` + 2 bytes
	    - `TEL:<phone number>`: Approx. 4 bytes + length of `<phone number>` + 2 bytes
	    - `END:VCARD`: 13 bytes
	    
	    **Total Approximation**:
	    
	    - Without `<name>` and `<phone number>`, it’s around 13 + 11 + 13 + 13 = 50 bytes
	    - Add length of `<name>` and `<phone number>` plus their newlines
	    
	    For a rough estimate, assume a short name (e.g., 1 byte) and phone number (e.g., 10 bytes):
	    
	    - **Per vCard Entry**: 50 bytes + 1 byte (name) + 10 bytes (phone) + 4 bytes (newlines) = 65 bytes (approx.)
	    then total 4 billion number for each it takes 65 (approx.) then 
	    65 x 4 billion 2,60,00,00,00,000 bytes in GB it will be 2,47,955.322265625 which is approx. 248 GB or 246 GB it may differ according to data but in worst case we can assume 248 GB
2. now you told it going to batches then how much a file will contain and how many files will be there 
	Certainly! Let’s calculate everything based on number of phone numbers, which is 4 billion.

 **1. Total Number of vCards**

- **Phone Numbers**: 4,000,000,000

**2. Size of Each File**

Assuming you generate files with 100,000 vCards each:

- **Number of vCards per File**: 100,000
- **Size per vCard**: 65 bytes

**Size of Each File**:

$$
\text{Size of Each File} = \text{Number of vCards per File} \times \text{Size per vCard}
= 100,000 \times 65 \text{ bytes}
= 6,500,000 \text{ bytes}
$$

Convert to megabytes:

$$
\text{Size of Each File} = \frac{6,500,000 \text{ bytes}}{1024 \times 1024} \approx 6.2 \text{ MB}
$$
 **3. Total Number of Files**

$$
\text{Total Number of Files} = \frac{\text{Total Number of Phone Numbers}}{\text{Number of vCards per File}}
= \frac{4,000,000,000}{100,000}
= 40,000 \text{ files}
$$

 **4. Total File Size**

**Total Size of All Files**:
$$
\text{Total File Size} = \text{Number of Files} \times \text{Size of Each File}
= 40,000 \times 6.2 \text{ MB}
= 248,000 \text{ MB}
$$


Convert to gigabytes:


$$
\text{Total File Size} = \frac{248,000 \text{ MB}}{1024} \approx 242.2 \text{ GB}
$$

3. so how much time it going to take 

**Estimated Time to Process**
as i have small computer so yes 4 cores ! 
**Assumptions**:
- **Time per vCard**: 0.1 milliseconds (0.0001 seconds)
- **Number of vCards**: 4,000,000,000
- **Number of Cores**: 4

**Total Processing Time**:


$$
\text{Total Time} = \text{Number of vCards} \times \text{Time per vCard}
= 4,000,000,000 \times 0.0001 \text{ seconds}
= 400,000 \text{ seconds}
$$

Convert to hours:

$$
\text{Total Time in Hours} = \frac{400,000 \text{ seconds}}{3600} \approx 111.1 \text{ hours}
$$

**Parallel Processing Time**:

$$
\text{Parallel Processing Time} = \frac{\text{Total Time}}{\text{Number of Cores}}
= \frac{400,000 \text{ seconds}}{4}
= 100,000 \text{ seconds}
$$

Convert to hours:

$$
\text{Parallel Processing Time in Hours} = \frac{100,000 \text{ seconds}}{3600} \approx 27.8 \text{ hours}
$$

heres the data 
### data 

- **Total Number of Phone Numbers**: 4 billion
- **Size of Each File**: Approximately 6.2 MB
- **Total Size of All Files**: Approximately 242.2 GB
- **Estimated Time Without Parallelism**: Approximately 111.1 hours
- **Estimated Time With 4 Cores**: Approximately 27.8 hours

These estimates assume ideal conditions and average processing times. Actual performance may vary based on system load and I/O speeds.

4. next question shall i do this by taking so much of storage and time after writing this code 
	answer is quite simple **NO** 

i mean after all mine is a small android phone which doesnt have space to install new game and needed to have 200 gb file very weird so i finally decided to shut the phone and laptap and go to sleep 

anyway if you like my content please see other articles in my website and dont forget to follow me in social media  ! 

thank you  
