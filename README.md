# Judging-a-book-by-its-cover
> OpenCV, Machine Learning

https://medium.com/@nkartik94/judging-a-book-by-its-cover-1365d001ef50

This project is an improvised version of a CBIR (Content Based Image Retrieval) system. Once the user clicks a picture of a book-cover in real-time, we use a 3-Level matching system to retrieve closest matches of the book-cover and based on the retrieved book-cover it displays the summarised information about various aspects of the book that is obtained from sites such as Goodreads and Amazon.

## 3-Level matching system:
* Level-1: RGB Colour Histogram.
* Level-2: Structural Similarity Index Measure (SSIM).
* Level-3: FLANN matching using SIFT features.

## 10-Step Process:
* Step-1: Build a repository of all the available book covers along with their respective ISBN number.
* Step-2: Compute RGB Colour Histograms for all the book-cover images in repository.
* Step-3: Read-in the query book-cover and compute its colour histogram.
* Step-4: Search for closest matches of the query book-cover in the image repository based on correlation between histograms. (Level-1 Matcher).
* Step-5: Search for closest matches of query book-cover from the matches obtained in Step-4 using SSIM. (Level-2 Matcher).
* Step-6: Search for closest matches of query book-cover from the matches obtained in Step-5 using FLANN. (Level-3 Matcher).
* Step-7: Display the top-4 matches obtained after 3 levels of matching. Also display the number of SIFT features matched in those top-4 retrieved images.
* Step-8: Draw the matches between query book-cover image and top match.
* Step-9: Create a web crawler to scrape information from Goodreads and Amazon.
* Step-10: Using ISBN of the top match and the crawler designed in Step-9, retrieve additional book information such as number of ratings, average rating, helpful comments, number of pages in book, author details, etc. And finally display a summarised version of the information obtained.
