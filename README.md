# Amazon-fashion-discovery-engine-Content-Based-recommendation-
Amazon-fashion-discovery-engine-Content-Based-recommendation-
=========================
<img width=100% src="https://github.com/Raman-Raje/Amazon-fashion-discovery-engine-Content-Based-recommendation-/blob/master/images/amazon-fashion.gif">
## Objective: 
To recommend similar apparel to customers...

## CaseStudy Flow:

- The objective of case study is to recommend similar apparel products(women's top)
- The data was obtained from Amazon Product advertising API.
- Total 183k data point was obtained with 19 features such as asin,author,availability,availability_type, brand, color formatted_price etc.,
- We are considering only 9 features.
  - asin ( Amazon standard identification number)
  - brand ( brand to which the product belongs to )
  - color ( Color information of apparel, it can contain many colors as a value ex: red and black stripes )
  - product_type_name (type of the apperal, ex: SHIRT/TSHIRT )
  - medium_image_url ( url of the image )
  - title (title of the product.)
  - formatted_price (price of product)
- Data pre-processing and cleaning was done. Null values for brand,color was replaced with hypen.
- EDA was done on title of product to remoove similar/analogus titles.
- Final dataframe contains 16k data points with 9 features.
- Categorical features were one hot encoded with the help of countvectorizer.
- Text feature was encoded using bow,tfidf,avg_w2v and tfidf_avg_w2v.
- Similar products based on text was shown to check weather it is working correctly or not.
- VGG16 was used to extract feature from product images.
- Combination of weighted vector [text + (brand + color) + image ] is used to get similar products.
- Observation are noted down whenever necessary.
- Results of case study is summarized at the end.

## Observations:

- Results were best when considered only text,brand and color.
- Recommended products were completly different when considered combination of all the vectors.
- Wide range of different apparels were recommended when feature extracted image vector considered.
- When feature extracted image considered:-
  - Increase in similarity distance found
  - Recommended products were completly different and non relevant.
  - Performance deterioted when higher weights were assignrd.
- The reason behind it could be, that apparel image dataset is far different than imagenet dataset..
- Feature extracted image vector can be improove the product recommendation if VGG16 fine tuned on apparel image dataset.
- Among various text encoding, best result was found in case of tfidf_avg_w2v.


