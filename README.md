# Gryphons-CTF-2021
Writeups on some challenges for SP DISM Gryphons CTF 2021
# Table of Contents
* [Misc](https://github.com/ZYChua02/Gryphons-CTF-2021#misc)
  * [Head and toes](https://github.com/ZYChua02/Gryphons-CTF-2021#head-and-toes)
  * [Word search](https://github.com/ZYChua02/Gryphons-CTF-2021#word-search)
* [Crypto](https://github.com/ZYChua02/Gryphons-CTF-2021#crypto)
  * [Story of louis](https://github.com/ZYChua02/Gryphons-CTF-2021#story-of-louis)
* [Personal thoughts on the CTF](https://github.com/ZYChua02/Gryphons-CTF-2021#personal-thoughts-on-the-ctf)
# Misc
## Head and toes
## Challenge Description
What do these numbers mean?
</br>
</br>
01000111 01000011 01010100 01000110 01111011 00110001 01110011 01000001
</br>
</br>
http://c1.2021.gryphonctf.com:9002/
</br>
</br>
Hint : What is MSB and LSB?
## Approach
Upon seeing the binary numbers in the description, the first thing we did on was to convert it using cyberchef
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/136686261-b49c291a-0f1b-42b4-90a2-6322b77b6f56.png)
</br>
</br>
This gave us a part of the flag so we took the hint and went to the link, and by entering the MSB of the binary number on the left side and LSB of the each binary number on the right side, the second part of the flag will show.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/136686374-7587e4dc-5ade-4996-b630-61be8e18cf82.png)
## The flag
`GCTF{1sAnD0s}`
## Word search
## Challenge Description
Amongst the flooded page, all will be revealed when you find it inside.
</br>
</br>
http://c1.2021.gryphonctf.com:9011/
## Approach
Upon clicking into the link that was provided, there was a bunch of words scattered all over the page.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/136686554-785eddfd-b50b-4906-8b0f-5114e4a69645.png)
</br>
</br>
However upon closer insepction, there was actually a link hidden among the words.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/136686601-d741d19a-7d9b-424f-b7e0-2406b0fa3c55.png)
</br>
</br>
The link: https://bit.ly/3cUcg1q
</br>
</br>
Clicking the link leads to Google Drive file named Finance_Background2.png
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/136686664-bff4be28-9569-4a7a-9c4f-b1e38d28af66.png)
</br>
</br>
However the image cannot be opened using a image viewer.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/136686735-65c17858-878d-4d0d-922d-1ef3a8c6a774.png)
</br>
</br>
Using the command ```strings Finance_Background2.png``` leads to finding the Flag Hint.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/136686824-ebeec1b8-5f97-4ffe-959b-1635576701e8.png)
</br>
</br>
Since most of the challenges were encoded in Base64, I guessed that it was encoded in Base64 and it turned out to be a Base64 Encoded version of words on the Web Page.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/136686962-361e8c40-262e-4d2b-bc11-a6c1a3b0613f.png)
</br>
</br>
Scrolling through it will show the flag as part of the words.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/136687001-6edab9c1-1765-4707-9401-675b2af9a6a9.png)
## The flag
`GCTF{StuCk W3th y3W}`
## Story of louis
## Challenge Description
Have a look through the web and have fun discovering it!
</br>
</br>
http://c1.2021.gryphonctf.com:9008/
</br>
</br>
Hint 1: Louis's favourite number was S1X and he was the inventor of a reading and writing system for use by people who are visually impaired.
## Approach
Upon clicking the link in the Description, an article on Louis Braille is shown.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/136687657-5b4fc726-3237-49bb-bb65-e5a05c908533.png)
</br>
</br>
I decided to use inspect element to look if anything was hidden was in the comments of the HTML page, and a Google Drive link was hidden with a hint indicating that we should look for things hidden behind the image(s).
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/136687769-5ab6d7af-aa22-49b3-998c-e845f389a208.png)
</br>
</br>
Clicking in the Google Drive link will reveal three images.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/136687860-0ed985d4-8d38-408f-8242-b3b3c336a007.png)
</br>
</br>
I initially did a reverse image search on the images to find out on the origin of the images, but just found some articles on braille and an article on representing binary as electric signals, which was a good read. 
</br>
</br>
Article link: https://medium.com/@yurachoi/i-got-1100011-problems-but-a-bit-aint-one-72e9de535d2e
</br>
</br>
After not getting anything, I changed my approach to using strings on the images instead and found the flag encoded in binary in hint2.png
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/136688058-3de1a708-9d6c-4596-9dfd-7ccf4d26bd55.png)
</br>
</br>
I took a hint and reliased it was using not the usual binary but rather binary represented with braille, then I remembered that using dcode Braille translator was able to quickly convert the binary into text.
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/136688197-6ff73b86-c2f0-4532-a86d-70b7a33d76f0.png)
## The flag
`GCTF{LOUIS_BRAILLE}`
# Personal thoughts on the CTF
The CTF was a much easier one compared to some of the previous ones that I took part in. The challenges were much more straightforward in a sense that I have seen encountered them from other CTFs and the choice of hiding the hints was always in comments or strings in images and always encoded in Base64. I managed to solve 4 challenges on the last day, which was quite surprising because usually I was only able to solve only 1 or 2 Challenges in CTFs whenever I participated as a team. It could be because I was relaxed throughout this CTF and did not take it as seriously as the previous ones I was in.
</br>
</br>
I learnt about the Polybius cipher as part of the challenge, which was something I had not encountered in previous CTFs that I participated (Did not write up this particular challenge).
</br>
</br>
Challenges that I solved:
</br>
</br>
![image](https://user-images.githubusercontent.com/65858555/136689030-075bd4f6-a5b0-46a1-8d41-6d173d6d0b14.png)























