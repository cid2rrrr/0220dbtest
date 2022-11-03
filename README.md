Multi Labeled Genre Classificaion via Album Cover
===============

**Notice** Since I reset my Desktop w/o any backup, I can't update anymore

## Thesis

>   Link: [GoogleDrive][googlelink]

[googlelink]: https://drive.google.com/file/d/1v7jKv42lyMqAWx261nqEdu-YXpYzr_F7/view?usp=sharing "GDrive"

</br>

### What I do on this project

>There are some papers about 'Genre Classification via Album Covers'. However, all of them approached only Single-Labeled Classification.  
</br>
Also, as you know, People guess the genre of the album through the artist's race, feeling, etc. on the album cover.   
</br>
So in this project, I'm gonna approach this problem w/ a Multi-Labeled Classification using personal(facial) information.  

</br>


---------

## File Description
</br>

### 01.Crawl.ipynb
</br>

I used 20220201_[master_release database][dblink] from [Discogs.com][discogslink].

[dblink]: https://discogs-data-dumps.s3.us-west-2.amazonaws.com/index.html "Discogs Data"
[discogslink]: https://www.discogs.com/ "Discogs.com"

First, Check the number of ratings of the album through master release id.  
Second, Download the main Album Cover IMG file of the album when satisfying the specific condition.   
The download directory is a string that combines the genres of the album.

It will take a long long time to gather the IMGs.
</br>
</br>
</br>

### 02.MakeCSV.ipynb
</br>

To make various attempts, I collected various info in the Album Cover IMGs and stored them in the form of .csv.  
>   * master_release ID
>   * path of the IMG
>   * whether the genre of the album is multi-labeled
>   * grey level histogram, RGB level histogram(but Failed)
>   * RGB values of dominant color of the Album Cover
>   * Age/Gender/Race/Emotion of the artist in the Album Cover (if there exists).
>   * Genre of the Album (one-hot encoded, 15 genres total)

</br>
</br>
</br>

### 03.Refine_Divide.ipynb
</br>

Since I want to use only 7 major genres, I dropped the albums belonging to other genres.  
Also I dropped the albums not including facial info.
Finallly, I divided the dataset into three, to make it easier to change the model Input.

</br>
</br>
</br>

### Other .ipynb Files
</br>

I tried lot of things. But I can't remember what i did exactly.  
[Inception_7genre.ipynb][incept] is the cleanest file.

[incept]: https://github.com/cid2rrrr/Multi-Labeled-Genre-Classifier-via-Album-Cover/blob/main/Inception_7genre.ipynb "github link"

I compared the Precision and Recall when classifying genres using only Album Cover IMGs and using additional information(facial, color).

</br>
</br>
</br>

## Result
------
Welp, I started this project without knowing Deep Learning and finished it as if I am chased, the result is not very good.  

What I was trying to ascertain is that accuracy(f1-score) increases whn given additional information.  
It looks a little bit up, but not sure.  

If Data Crawling and Refinement had been made more certain, the result would have been clear.


