def fetch_img(img_link):
     try:        
         img_response = urlopen(img_link)
         img_data = img_response.read()
         img_response.close()
         img = Image.open(io.BytesIO(img_data))
         st.image(img, use_column_width=True)
     except (URLError, HTTPError):
         st.image(r"https://via.placeholder.com /150")