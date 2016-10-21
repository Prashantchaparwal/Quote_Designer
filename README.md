# Quote_Designer

import unirest
　
while(1):   # To repeat the statement if User wants to play again.
    categ = raw_input('Enter the category of quote you want: "movies" or "famous" \n') #Takes input from the user
    print('You have asked for '+categ + ' quote') 
    our_url = "https://andruxnet-random-famous-quotes.p.mashape.com/?cat="+categ
    response = unirest.post(our_url,
                            headers={
                                     "X-Mashape-Key": "xxx",
                                     "Content-Type": "application/x-www-form-urlencoded",
                                     "Accept": "application/json"
                                     }
                                     )
    for key in response.body:    
        print("\n")
        print(key + ':' +response.body[key]) # Displays a dict with key and its value.
        print("\n")
    ch=raw_input("\n Do you want to Continue. Yes Or No")
    if(ch=="Yes"): 
        print("") 
    if(ch=="No"):  
        print("Thank you for playing....") 
        break;
