# Cryptography
## Small P Problems
### Deskripsi Soal

My buddies Whitfield and Martin were trying to share a secret key between themselves, and I was able to eavesdrop on their conversation. I bet I could probably figure out their shared secret with a little math...

p = 69691
g = 1001

A = 17016
B = 47643
Note: submit either the shared secret or the shared secret wrapped in utflag{}

### Penyelesaian
Di sini deskripsi soal menjelaskan tipe kriptografi yang digunakan dalam challenge ini, yaitu adalah **Diffie–Hellman key exchange**, sehingga saya menggunakan bantuan python untuk membuat program brute force, dengan diketahui bahwa password berada di antara 1-69691

```python
# mod = int(input('Public mod: '))
# base = int(input('Public base: '))
#
# a_secret = int(input('A secret: '))
# b_secret = int(input('B secret: '))

mod = 69691
base = 1001
a_secret = 12552
b_secret = 7919

a_public = (base ** a_secret) % mod
b_public = (base ** b_secret) % mod

print('=================')

print('A public = ' + str(a_public))
print('B public = ' + str(b_public))

a_shared = (b_public ** a_secret) % mod
b_shared = (a_public ** b_secret) % mod

print('A shared secret = ' + str(a_shared))
print('B shared secret = ' + str(b_shared))
```

```python
for i in range(1,69691): # try all values 1-p
    if (1001 ** i) % 69691 == 17016: # if g^i mod p = A
        print(str((47643 ** i) % 69691)) # print B^a mod p
        exit()
```

Maka akan ditemukan flag yang diinginkan.

**Flag: utflag{53919}**

# Web
## Cutest Cookie Clicker Rip-Off

### Deskripsi Soal

I built this awesome game based off of cookie clicker! Bet you'll never beat my high score. Hehehe!

http://web1.utctf.live:4270

### Penyelesaian

Di web yang disediakan, terdapat sebuah game di mana kita harus mengalahkan high score (1.000.000 klik) dalam lomba click-on-screen. Di sini, saya terpikir untuk memainkan game nya terlebih dahulu dan setelah kalah, saya terpikirkan kembali untuk memodifikasi body dari post request sehingga score yang diperoleh sebelumnya dapat diubah.

**Flag: utflag{numnum_cookies_r_yumyum}**

# Miscellaneous
## Emoji Encryption
### Deskripsi Soal

I came up with this rad new encryption. Bet no one can break it

☂️🦃🔥🦁🍎🎸{🐘🥭🧅🤹🧊☀️_💣🐘_🌋🐘🌈☀️🍎🦃🧊🦁🐘}
### Penyelesaian

Jika melihat formatnya, saya terpikirkan bahwa format hampir sama dengan format flag, yaitu **utflag{}**. Kemudian, saya coba menulis emoji yang terletak di luar kurung dalam bahasa inggris:
**U**mbrella **T**urkey **F**ire **L**ion **A**pple **G**uitar
ternyata benar saja, bahwa jika diperhatikan bahwa huruf depan setiap huruf kalau disambung menjadi utflag. Sehingga, tinggal kita mengartikan sisanya.
**Flag: utflag{emojis_be_versatile}**

# Forensic
## SHIFT
## Double Deleted Data
## Sandwiched

# Beginner
## Half-time Survey
## Sanity Check
## Run-ELF
## Stringy Things
## Cipher gauntlet
## Magic Bytes
## HTML
## Sizzling Bacon
## Various Vernacular
