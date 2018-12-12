# OCR assignment report

## Feature Extraction (Max 200 Words)
[I use Principal Component Analysis algorithms to reduce_dimensions(to 10 dimensions). This method maps high-dimensional data to representations in low-dimensional space by liner projection. Because of the eim to retain more of the original data characteristics, the variance of the data in the projectd dimension is the largest.(If all the points are mapped together, then all the information disappears. If the variance after the mapping is large, the points of that data will be scattered, and more data can be retianed). As for the first PCA coefficient is often not very discriminative, I use the PCA coefficient from second one to elventh one. 1. Convert data to a two-dimensional matrix X. 2. Subtract the mean of the line for each line of X. 3. Find the convariance matrix M. 4. Find the eigenvalues of the convariance matrix M and the corresponding eigenvectors. 5. The feature vectors are arranged into a matrix according to the value of the corresponding feature value from top to bottom and the first 10 rows are formed into a matrix P. 6. Y=PX is the data after dimension reduction to k dimension.] 

## Classifier (Max 200 Words)
[I use Nearest Neighbor Classifier algorithms in classifier part. I compare the picture data in the test set have given with the picture data in the training set have given one by one. Then I could find the label corresponding to the training data closest to this test data. The resulting label is the classification category of the test data. I use cosine distance as Measurement method. Use different measurement methods can produce different effects.]

## Error Correction (Max 200 Words)
[My model.json.gz file contains a list of the top 100,000 most frequently-used English words(dictionary). I use bounding box coords of the character to get the interval of the characters close to each other. Then I set a length, if the interval of two characters is larger than the length, I assume they belong to different words. By this way, I could get a list of words by the list of charactors. Since the image may be blurry, some letters in the resulting words may wrong. So I compare the resulting words with words in dictionary. If can find same word in dictionary, it will change nothing. Otherwise, if there are same words in dictionary with only one or two letters different from the word in resulting words, replace it with the one has highest frequency. Because fuzzy pictures are easy to get wrong characters, words, this method is more effective for them. I find 6 as length is the best one for these 6 test pages.]

## Performance
The percentage errors (to 1 decimal place) for the development data are as follows:
- Page 1: [94.7%]
- Page 2: [95.9%]
- Page 3: [79.1%]
- Page 4: [51.1%]
- Page 5: [33.4%]
- Page 6: [25.7%]

## Other information (Optional, Max 100 words)
[Optional: I upload the list of the top 100,000 most frequently-used English words and change all words to lowercase make easy to compare. If I not use error correction I will get Page 1: [98.0% ], Page 2: [96.7%], Page 3: [72.3%], Page 4: [44.5%], Page 5: [30.4%], Page 6: [23.6%]. Error correction help me increase 2.4% average per page]
