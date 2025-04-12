+++
title = 'Wifi_vulnerablities'
date = 2024-10-01T10:50:55+05:30
draft = false
tags = [""]
Categories = [""]
+++
see folks hacking WIFI is not a simple thing and if you use it for bad thing then it is crime and offense but this article about how to secure your network and what are the vulnerabilities 
lets get start 

first we need to know about the security protocols of the wifi 
wep released on 1997 which is algorithm is easily breakable 
wpa released on 2003 which was temporary solution for wep 
wpa2 released on 2004 which is the most expandable usage protocol and it is vulnerable 
wpa3 released on 2018 which is most secure but still it can be hackable method called dragonblood 

here i am not focussing on attack on wpa3 which is almost secure but here i am focusing on wpa2 right? 
note : so while buying a router you should check weather it supports wpa3 protocol or not right 

so you need to check whether the wifi is wpa2 or wep or wpa if it is then 80% it can be hackable 
while wpa3 makes hacker to hack expensive 

okay now we will look how the hacker hacks the wpa2 protocol network 
## wpa2 hackable 

### requirements 
1. pen drive around 8 gb recommended 
2. wifi module (optional but highly recommended)
3. laptap or pc 
### operation 

you need to install kali linux on pen drive so that we can boot from pendrive 
go to rufus.ie where a software which help to boot and go to kali.org and there download the bootable iso file now 
pendrive + rufus + iso 

set the required config make sure set 8 gb for internal storage on rufus and then make boot it 

step 1 is over 

now shutdown pc / laptop now boot it into one time boot by pressing F12 button and select pendrive 

right now  press shortcut 

```
ctrl + alt + t
```

or you can open terminal on searching above by pressing kali button 

now press 

```
sudo wifite
```

make sure your wifi module is connected 
and then select the wifi you want 

and make sure 

```
sudo apt-get install hcxtools
```

```
sudo apt-get install hcxdumptool
```

 both installed correctly if you get any error just google it 

just nothing to do just make sure the target signal is strength is high 

try twice or trice it should work else you can see there is hand sake packet which is nothing but a hashed packet by that we can crack the password 

### cracking password 

there are two ways that you can crack the password 
1. using rock you text file default option via hashcat or john the ripper (which dones automatically by the wifite)
2. or generate your own password list which your predicts may come true and you can get your wifi password 

note: this path you must choose only if the wifite software unable to crack using security vulnerable like wpa or duster or wep (security vulnerable)

and this predicting method is kinda of hard but if you try to guess it then yes it may possible 

1. crunch 
2. cupp
3. mentalist 

first crunch is kind of advance usage but it is useful i recommend using after trying 2,3 option 
okay now if i talking abou.pyt 2. cupp it is simple easy to use software 

2. cupp 
	it is present in https://github.com/Mebus/cupp go there and download and run the script 

```
python3 cupp.py -h
```

now features 
1. it has default password list from online 
2. it has custom password list from online 
3. interactive mode by entering custom hints 

just see the instruction on the git hub 

3. mentalist 
	you no need to worry about this thing because its gui just download from https://github.com/sc0tfree/mentalist
 
```
python setup.py
```

or     
       
```
pip3 install -r requirements.txt
```    
- **Run Mentalist**: You can start Mentalist by running the following:
    
    Copy code
    
```
    python3 mentalist.py
```

according to versions 
here now after setup of cupp file now insert that file into the mentalist and then add set of rules to implement and then thats it you will get a large number of pass list with huge size 

if you feel that there are duplicates then try python code to make faster 

```
def remove_duplicates_from_large_file(input_file, output_file):
    try:
        # Set to keep track of unique passwords
        unique_passwords = set()

        # Open the input file and read line by line
        with open(input_file, 'r') as infile:
            for line in infile:
                password = line.strip()
                
                # Add the password to the set if not already present
                if password not in unique_passwords:
                    unique_passwords.add(password)

        # Write the unique passwords to the output file
        with open(output_file, 'w') as outfile:
            for password in unique_passwords:
                outfile.write(password + '\n')

        print(f"Unique passwords saved to {output_file}")
    except FileNotFoundError:
        print(f"File {input_file} not found.")
    except Exception as e:
        print(f"An error occurred: {e}")

# Example usage
input_file = 'large_passlist.txt'  # Large input file with passwords
output_file = 'unique_large_passlist.txt'  # Output file for unique passwords

remove_duplicates_from_large_file(input_file, output_file)

```

alright so finally replace the word list in the place where the wifite try to crack the handshake where via hashcat or the john the ripper what ever you select this process will be easier 

okay i think crunch is unusable but still can do a lot of things 

```
crunch 4 5 -o output.txt 
```


4. cewl 
	additionally it will scrap data from website 
```
cewl https://example.com -o output.txt
```

well this will create the pass list from a-z where min of 4 and max of 5 like permutation 

so thats it i have wrote this article for be aware of the things and also get knowledge about some tools where it is easily accessible to internet the above procedure tells make sure a strong password to your wifi or any where of your accounts that makes a secure to your account where strong password means as the above unpredictable that i may put this kind of password 

reference : 
1. https://www.youtube.com/watch?v=01-Dcz1hFw8
2. https://www.youtube.com/watch?v=bf5dIMn6rp4   (crunch)

ya thank for reading this article ... 
if you like our content just read other articles and also follow our social media handles 
