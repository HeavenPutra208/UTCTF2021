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
for i in range(1,69691): # try all values 1-p
    if (1001 ** i) % 69691 == 17016: # if g^i mod p = A
        print(str((47643 ** i) % 69691)) # print B^a mod p
        exit()
```

