Dựa vào hint: 
> "No one cared who I was until I put on the mask" -Bane

Và dựa vào password formation trong đề bài:
> the first character must be a digit, the second must be a special character followed by a pet name, then followed by an uppercase letter and lastly a lowercase letter, in that order

Hướng đi sẽ là sử dụng plugin `mask` của johntheripper.

Ta sẽ lấy 1 số keyword khác trong phần description ra: John, Skynet, pet name.

Hint của bài này đề cập đến iconic quotes của Bane trong The Dark Knight Rises, thì khả năng phần des cũng y hệt thế. Dựa vào keyword mình liệt kê ra ở trên thì khả năng John ở đây là John Connor trong Terminator 2.

Và nó relate tới cái đoạn này : https://www.youtube.com/watch?v=H4OzlOWNmIM

Từ đó ta biết pet name ở đây là `Max`. Con chó của John Connor.

Run john để crack 7z với những gì đã có ở trên:

```
$ 7z2john challenge.7z > hash.txt
$ john --mask='?d?smax?u?l' hash.txt
```

Done. Pass là `4#maxDc`.

Ta extract được 1 file PDF, sử dụng `pdf-parser` để xem stat của file này:

![image](https://user-images.githubusercontent.com/113530029/233207410-54054de1-0546-4622-bd0c-ea0e225ab998.png)

Để ý thấy có JavaScript trong Object Stream 3, extract nó ra và xem:

![image](https://user-images.githubusercontent.com/113530029/233207587-1e68c4e9-3577-4b04-9b87-20387ec3c208.png)

Ta thấy dòng hex này: `636F6E737420666C6167203D207B634D73673A2027272C206E49636F6E3A20332C206E547970653A20302C20635469746C653A20276A6374667B6831355F6E416D335F31535F6E30745F776F6C6669657D7D907D3B`

Decode ra và có flag: 

![image](https://user-images.githubusercontent.com/113530029/233207725-cb3563f9-28eb-4ce7-8273-db70f01292f5.png)

Flag: `jctf{h15_nAm3_1S_n0t_wolfie}`
