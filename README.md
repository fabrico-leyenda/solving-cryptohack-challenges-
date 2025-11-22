# solving-cryptohack-challenges-
xcuse my english ( i don't have that much time to correct my mistakes ++++ no one will read this repo so i think i'm save ( i think i'm losing my mind))

this is the only possible solution for cryptohack challenges

we will start first with installing a library called pwntools by writing in our vscode's terminal '''pip install pwntools'' then from pwn(pwntools) we import xor

from pwn import xor # Make sure to install pwntools with: pip install pwntools hex = "0e0b213f26041e480b26217f27342e175d0e070a3c5b103e2526217f27342e175d0e077e263451150104" data = bytes.fromhex(hex)

-///using this function we wil be able to transform our bytes from base 16 to binariy

for key in range(256): result = xor(data, key)

/// we will xor using xor fuction our code withe every number between 1 to 256 try:

decoded = result.decode('ascii')   ////then we will decode to ascii 
if all(32 <= ord(c) <= 126 for c in decoded):  //// this line allow us to have a spesific and limited option of character where their assci number is between 32 and 126 ////
    print(f"Key: {key} => {decoded}")    ////then we will print operation result 
except UnicodeDecodeError: continue it will give you an output like this one Key: 1 => rchaej!i !N 
N
|
h
N
w
 Lqj$vn Key: 4 => wfmd{o$l%$K%!KymKr b$af%#'Kvm#qi Key: 5 => vgleazn%m$%J$ JxlJs!c%g$"&Jwl"ph Key: 6 => udofbym&n'&I'#I{oIp"&cd'!%Ito!sk Key: 7 => tengcxl'o&'H&"HznHq#a'be& $Hun rj Key: 8 => {jahlwc()(G)-GuaG~,n(mj)/+Gza/}e Key: 11 => xibkot+c*+D*.DvbD}/m+ni*,(Dyb,f Key: 14 => }lgnjqe.f/.A/+AsgAxh.kl/)-A|g){c Key: 15 => |mfokpd/g./@.@rf@y+i/jm.(,@}f(zb Key: 16 => crypto{0x10_15_my_f4v0ur173_by7e} Key: 17 => bsxqunz1y01^04^lx^g5w1ts062^cx6d| Key: 19 => qzswlx3{23\26\nz\e7u3vq240\az4f Key: 21 => fw|uqj~5}45Z40Zh|Zc1s5pw426Zg|2`x

we can see that our flag wich will always start with cryopto is in the line 16

and that how you solve this challenge sounds easy

there is another methos actaully

first try to decode the string to assci you will find out that it start with s then try to find it in binary 01110011 knowing that our flag wil always start with c wich can be represent as 01100011 soooo c xor something = s but what make xor more speicel is that something = c xor s we will fnd out that someting = 16 sooo th find our flag we xor the string with 16 yws it this simple but just to let you know if you want to use xor calculator you have to xor each charcter and that will take a very long time

here some resources and website

https://www.rapidtables.com/convert/number/binary-to-ascii.html this website allows you to conveet anything to anything ( i'm trying to be funny( it hard) ( it sounds cringe)) )

https://xor.pw/# a xor calculator not that speiciel

https://www.youtube.com/@theshyhat this man is a legend you can check his palylists

https://youtu.be/D8sXCtu4oys?si=T86fzDb4_iKVL4Tr this is one of his videos

special thanks to my mentors for all the guidance and suuport
