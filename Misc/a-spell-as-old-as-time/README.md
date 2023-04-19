Bài này ta sẽ extract RGBA value trong từng ô vuông màu kia ra. Ý tưởng là lấy các giá trị giữa ô vuông ra, để dù có dính 1 ít sai số thì ta cũng không bị ảnh hưởng nhiều.
Bằng tính toán thủ công :v, mình set x, y bằng các giá trị default như code sau và run:

```
from PIL import Image

img = Image.open(r"D:\Downloads\a-spell-as-old-as-time.PNG")
x = 25
y = 21

while y < img.size[1]:
    while x < img.size[0]:
        r, g, b, a = img.getpixel((x, y))
        print(chr(r)+chr(g)+chr(b), end = "")
        x += 50
    x = 25
    y += 42
```

Đầu ra như này:

![image](https://user-images.githubusercontent.com/113530029/233197983-29fb499b-09a0-4a6f-b6ac-d749e3b5e2ea.png)

Hmm. Câu này là lyrics của 1 bài hát rất nổi cho ai chưa biết : `What Makes You Beautiful - One Direction`.

Với câu hỏi đầu đề:

> Who left first?

Tra google xem ai trong nhóm One Direction rời nhóm đầu tiên là ra flag.

Flag : `jctf{Malik}``]
