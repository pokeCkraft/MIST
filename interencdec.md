# picoCTF

## interencdec
Can you get the real meaning from this file.
Download the file here.
link -> https://artifacts.picoctf.net/c_titan/1/enc_flag

### Solution
we open this in the terminal we see -> YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyeG9OakJzTURCcGZRPT0nCg==
we see that it ends with == so its most likely base 64. so we decode it
the output is ->  b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2xoNjBsMDBpfQ=='

it gives a garbage value when put through base 64 decode again, but if we remove -> b' '

when we decode it we get output as -> wpjvJAM{jhlzhy_k3jy9wa3k_lh60l00i}
this looks very close to flag format so we do a caeser shift we run through many of them (i used rot 13 on cyberchef by changing it from 13 to other values). after brute forcing we get the flag at caeser shift of 19.

```
echo "YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyeG9OakJzTURCcGZRPT0nCg==" | base64 --decode
echo "d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2xoNjBsMDBpfQ==" | base64 --decode

can use the rot 13 code and change it to 19.
```

### Flag
> picoCTF{caesar_d3cr9pt3d_ea60e00b}

### Resources
Add any resources you used to solve the challenge.