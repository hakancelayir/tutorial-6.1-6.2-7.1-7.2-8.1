# tutorial-6.1-6.2-7.1-7.2-8.1
TUTORIAL 6.1: ARITHMETIC OPERATIONS

##Question 1 What are the maximum and minimum values of the original and the adjusted image? Explain your results.

I=imread('cameraman.tif') imshow(I)

J=imadd(I,75) figure

K=subplot(1,2,1),imshow(I),title('Original Image'); L=subplot(1,2,2),imshow(J),title('Brighter Image');
![1](https://user-images.githubusercontent.com/100836971/163063155-5baebfa1-6bc3-4d42-baee-8109dcee37c1.png)
I = imread('cameraman.tif'); J = imread('cameraman2.tif'); figure subplot(1,2,1), imshow(I), title('Original Image'); subplot(1,2,2), imshow(J), title('Altered Image');
![2](https://user-images.githubusercontent.com/100836971/163063298-136dfc14-7b20-4558-9bc4-8e2c7b1f476d.png)
##Question 2 How many pixels had a value of 255 in the original image and how many have a value of 255 in the resulting image?
![3](https://user-images.githubusercontent.com/100836971/163063380-67552cd8-07a3-4dbf-8970-f35f277b495a.png)
##Question 3 How did we scale the image output?

Verilenlere göre yapılan ölçeklendirme komutları..

subplot(2,2,3), imshow(diffim,[]), ...
title('Subtracted Image Scaled');
subplot(2,2,4), imshow(diffim2,[]), ...
title('Abs Diff Image Scaled');
Aynı zamanda;

B = imresize(A,scale) , komutu ile ölçeklendirme yapılır.Komut içerisindeki scale kısmında orijinal fotoğrafa göre küçültme veya büyültme işlemi yapılabilir. Örneğin aşağıda yazmış olduğum kod ile oriijinal fotoğrafa 0.5 kat küçültme işlemi uygulanmıştır.

I = imread('cicek.jpg'); J = imresize(I, 0.5); figure, imshow(I), figure, imshow(J)

##Question 6 When dynamically scaling the moon image, why did the dark regions around the moon not become brighter as in the normally adjusted image?

Z = imdivide(X,Y), X dizisindeki her öğeyi Y dizisindeki karşılık gelen öğeye böler ve sonucu Z çıktı dizisinin karşılık gelen öğesinde döndürür.

Bölüm, X ile aynı boyutta sayısal bir dizi olarak döndürülür. Z, X mantıksal olmadığı sürece X ile aynı sınıftır; bu durumda Z, veri türü double'dır. X bir tamsayı dizisiyse, tamsayı türünün aralığını aşan çıktı öğeleri kesilir ve kesirli değerler yuvarlanır.

![4](https://user-images.githubusercontent.com/100836971/163063595-f09d5d6b-3b98-498b-9ccd-bd1fe932ab60.png)

##Question 7 Why did the multiplication procedure produce the same result as division?

Bölme Z çıktı dizisinin karşılık gelen öğesinde döndürür, çarpma da ürünü Z çıkış dizisinin karşılık gelen öğesinde döndürür.

##Question 8 Write a small script that will verify that the images produced from division and multiplication are equivalent.

I = imread('moon.tif'); J = immultiply(I,0.5); imshow(I) figure imshow(J)

I = imread('rice.png'); J = imdivide(I,2); imshow(I) figure imshow(J)

TUTORIAL 6.2: LOGIC OPERATIONS AND REGION OF INTEREST PROCESSING

##Question 1 How do we add points to the polygon? Yeni bir nokta eklemek için poligonun ilk noktasının üzerine işaretçiyi getirin ve tıklayın.

##Question 2 How do we delete points from the polygon?

İmleci ROI'ye getirin, sağ tıklayın ve içerik menüsünden Çokgeni Sil'i seçin. Ayrıca, deletenesne yöntemini kullanarak ROI'yi programlı olarak silebilirsiniz.

##Question 3 How do we end the process of creating a polygon?

Tepe noktası ve bitiş kısmını birleştirip çift tıklayın,ardından enter'a basın.

##Question 4 What class is the variable bw?

Giriş görüntüsü I uint8, uint16, int16, single veya double sınıfında olabilir. Çıktı görüntüsü BW mantıksal sınıftadır. Diğer tüm girdiler ve çıktılar double sınıfındadır.

##QQuestion 5 What does the variable bw represent?

roipoly, maskeli filtreleme için maske olarak kullanabileceğiniz ikili bir görüntü döndürür.

Question 6 In the above conversion step, what would happen if we used the im2uint8 function to convert the bw image as opposed to just using uint8(bw)? (Hint: after conversion, check what is the maximum value of the image bw2.)

uint8 ,veri tipindeki (sınıf) uint8değişkenler 1 bayt (8-bit) işaretsiz tamsayılar olarak saklanır im2uint8(I) gri tonlamayı, RGB'yi veya ikili görüntüyü I uint8'e dönüştürür, gerektiğinde verileri yeniden ölçeklendirir veya dengeler.

##Question 7 What happens when we logically AND the two images?

AND'nin en belirgin uygulaması, iki görüntünün kesişimini hesaplamaktır. Genel olarak, aralarındaki farklılıkları veya benzerlikleri tespit etmek için AND operatörünü (veya diğer mantıksal operatörleri) iki görüntüye uygulamak, ikili olmaları veya eşikleme kullanılarak ikili biçime dönüştürülmeleri durumunda en uygunudur.

##Question 8 What happened when we complemented the bw2 image?

Morfolojik işlemlerden sonra görüntü, 2 boyutlu mantıksal matris olarak döndürülür.

BW = imread( 'circles.png' ); imshow(BW); BW2 = bwmorph(BW, 'kaldır' ); figür göster(BW2) BW3 = bwmorf (BW, 'skel' , Inf); figür göster(BW3)

Yukarıdaki komut satırlarının sonucunda görüntünün iskeleti alınmıştır.

TUTORIAL 7.1: IMAGE CROPPING, RESIZING, FLIPPING, AND ROTATION

##Question 1 Which numbers did you record for the top left and bottom right co�ordinates and what do they mean? Sol üst için (31,35), sağ alt için (177,245) koordinatları.

##Question 2 Visually compare the three resized images. How do they differ?

![5](https://user-images.githubusercontent.com/100836971/163063943-5e0c5931-3878-489c-8aca-8b9c8e65f662.png)

Yukarıdaki görüntüde görüldüğü üzere ilk görüntü orijinal olan,diğerlerine göre ölçeklendirme olarak daha küçük. Ortadaki pikselli bir görüntüye sahip ve orijinal görüntüye göre ise ölçeklendirilmiştir.Son görüntü ise blur ve orijinal görüntüye göre ölçeklendirilmiştir.

##Question 3 How did we scale the image?

imresize() komutu ile ölçeklendirme yapılmıştırç

I_big2 = imresize(I,3,’nearest’); I_big3 = imresize(I,3,’bilinear’); figure, imshow(I_big2), ... title(’Resized w/ nearest-neighbor interpolation’); figure, imshow(I_big3), ... title(’Resized w/ bilinear interpolation’);

##Question 4 What are the limitations of this technique?

B = imresize(A,m,method), A'nın boyutunun m katı olan bir görüntü döndürür. m, 0 ile 1.0 arasındaysa, B, A'dan küçüktür. m, 1.0'dan büyükse, B, A'dan daha büyüktür.

##Question 5 Inspect the size (number of rows and columns) of I_rot and compare it with the size of I. Why are they different?

Ölçeklendirilme yapılmıştır.imresize() komutu ile.

##Question 6 The previous step rotated the image counterclockwise. How would you rotate the image 35◦ clockwise?

flipub() ve fliplr() komutları ile satır ve sütün olarak döndürülmüştür.

##Question 7 How did bilinear interpolation affect the output of the rotation?

Geometrik dönüşümdeN farklı bir kayma kullanıyormuş gibi görünmesidir.

##Question 8 How did the crop setting change the size of our output?

Aşağıdaki görüntüde görüldüğü üzere çıktıda görüntümüzün bir kısmı kırpılmıştır.

![6](https://user-images.githubusercontent.com/100836971/163064062-4b0131b4-5d5f-439f-a68b-8238c8b43447.png)

TUTORIAL 7.2: SPATIAL TRANSFORMATIONS AND IMAGE REGISTRATION

##Question 1 Compare the two resulting images (I2 and I3). Inspect size, gray�level range, and visual quality. How are they different? Why?
![7](https://user-images.githubusercontent.com/100836971/163064114-61cdc741-5fd5-4285-8528-6c5ef51fa56b.png)

##Question 2 Compare the two resulting images (I4 and I5). Inspect size, gray�level range, and visual quality. How are they different? Why?

![8](https://user-images.githubusercontent.com/100836971/163064177-f0de9417-978c-4718-9ffd-a122f716335a.png)

##Question 3 Compare the two images (I1 and I6). Inspect size, gray-level range, and visual quality. How are they different? Why?
![9](https://user-images.githubusercontent.com/100836971/163064236-255fccc1-ba1f-4cfc-8020-2a92fc7f5fa7.png)

TUTORIAL 8.1: GRAY-LEVEL TRANSFORMATIONS

##QQuestion 2 How can we show that the adjusted image and the original image are equivalent?

Grafik tablomuzdaki doğruya bakarak bunu anlayabiliriz.Aşağıdaki grafikte görüldüğü gibi x=0 grafiği eşdeğer olduğu anlamına gelmektedir.
![10](https://user-images.githubusercontent.com/100836971/163064307-7b692a70-ef48-44c0-b976-8341e4ec340d.png)

##Question 3 How did we create the negative transformation function?

uint8 veri dönüşümü ile bunu sağladık.Aynı zamanda bir önceki soruda eşdeğer olma durumu burada da kanıtlanmış oldu.Dönüşüm fonksiyonu artık x=0 değil.
![11](https://user-images.githubusercontent.com/100836971/163064375-b951318d-ace2-4cc6-9016-78e2deaad8a2.png)












