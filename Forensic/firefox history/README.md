Đề bài cho 1 file sqlite, mở bằng online tool. Đề có nói rằng: 
> *On what date and time was the jerseyctf.com website LAST accessed?*

check trong bảng `moz_place`, trang 5, ta thấy được dòng log jerseyctf.com lần cuối:

![image](https://user-images.githubusercontent.com/113530029/233174986-f36473f6-ef92-440b-ab6c-3457139158e2.png)

Lấy Epoch time của dòng đó ra và decode, ta được thời gian:

![image](https://user-images.githubusercontent.com/113530029/233175728-1fce56c1-e18a-4299-97eb-4c90ae810b89.png)

Flag : `jctf{2023-01-28-12-01-04}`
