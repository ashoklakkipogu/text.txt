{"web":{"client_id":"356189132276-stkpokhpltc18bk1v425jhouu22rfllg.apps.googleusercontent.com","project_id":"pc-api-5334270119157250243-146","auth_uri":"https://accounts.google.com/o/oauth2/auth","token_uri":"https://oauth2.googleapis.com/token","auth_provider_x509_cert_url":"https://www.googleapis.com/oauth2/v1/certs","client_secret":"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","redirect_uris":["http://localhost"]}}






a) Generate client id and secret key.

b) Add Google logged in user as a Test user in consent screen.

c) Generate Authorization Code (One Time)

https://accounts.google.com/o/oauth2/auth?client_id=xxxxxxxx&redirect_uri=http://localhost&response_type=code&scope=https://www.googleapis.com/auth/drive&access_type=offline
d) Generate Refresh Token (One Time)
curl --request POST --data "code=xxxxxxxx&client_id=xxxxxxxxxxxx&client_secret=xxxxxxxxxxxx&redirect_uri=http://localhost&grant_type=authorization_code" https://oauth2.googleapis.com/token
e) Generate Access Token from Refresh token (Always)
curl --request POST --data "client_id=xxxxxxxxxxx&client_secret=xxxxxxxxxxxxxxx&refresh_token=xxxxxxxxxxxxx&grant_type=refresh_token" https://oauth2.googleapis.com/token



https://www.googleapis.com/auth/androidpublisher


https://accounts.google.com/o/oauth2/auth?client_id=356189132276-stkpokhpltc18bk1v425jhouu22rfllg.apps.googleusercontent.com&redirect_uri=http://localhost&response_type=code&scope=https://www.googleapis.com/auth/androidpublisher&access_type=offline

http://localhost/?code=4/0AfJohXluIhTM8zcsv9_kvoFGPmlHXjCotF2QzbqEetmGkIDiIwL4ZcYdSnR6VMyrUffv6Q&scope=https://www.googleapis.com/auth/androidpublisher


http://localhost/?code=4%2F0AfJohXmrgb0xZAMpRAMQdjHF5nDwbRKboUnAlgapQs520HrD8s7o3oQDquZG5CFLhv28gw&scope=https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fdrive




http://localhost/?code=4/0AfJohXn5SyVsWZEhaK6eLmZkSokcPTEhcaszvDIt9S5R4q0FfMJhfc5bbC8ZJXJ6auejcg&scope=https://www.googleapis.com/auth/drive


curl --request POST --data "code=4/0AfJohXluIhTM8zcsv9_kvoFGPmlHXjCotF2QzbqEetmGkIDiIwL4ZcYdSnR6VMyrUffv6Q&client_id=356189132276-stkpokhpltc18bk1v425jhouu22rfllg.apps.googleusercontent.com&client_secret=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&redirect_uri=http://localhost&grant_type=authorization_code" https://oauth2.googleapis.com/token



curl --request POST --data "client_id=356189132276-stkpokhpltc18bk1v425jhouu22rfllg.apps.googleusercontent.com&client_secret=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&refresh_token=1//0gTNOHpQgwXuKCgYIARAAGBASNwF-L9IrRsgTA8lZayJQs-htzBV1NopXIyg8EpVpKQNzpTBCDav1N3c9Ar1kmGgAaFJ6ahpxoqk&grant_type=refresh_token" https://oauth2.googleapis.com/token


{
  "access_token": "ya29.a0AfB_byCzQ4zoNbqqfZModW0JWxgFGxx2LC_P1jU_IijbP8rrXG_UWZ8NhEVj_E2_MSXjYyAXfXDb91fPGbQIaOTh32OiS_X6TY-IwmQjUX5EXAfQR3qVhQjjMguk59w1f_-elvJWofC4xXxInNCPhEJiCeebWrLmSJtraCgYKAfkSARISFQGOcNnCh8d6_07ryL3Kh9Zjp7d6yA0171",
  "expires_in": 3599,
  "refresh_token": "1//0gTNOHpQgwXuKCgYIARAAGBASNwF-L9IrRsgTA8lZayJQs-htzBV1NopXIyg8EpVpKQNzpTBCDav1N3c9Ar1kmGgAaFJ6ahpxoqk",
  "scope": "https://www.googleapis.com/auth/drive",
  "token_type": "Bearer"
}





https://developers.google.com/android-publisher/api-ref/rest/v3/edits.tracks/list

https://developers.google.com/android-publisher/api-ref/rest/v3/edits/insert



POST https://androidpublisher.googleapis.com/androidpublisher/v3/applications/com.cbse.study/edits?key=[YOUR_API_KEY] HTTP/1.1

Authorization: Bearer [YOUR_ACCESS_TOKEN]
Accept: application/json
Content-Type: application/json

{}



curl --request POST "https://androidpublisher.googleapis.com/androidpublisher/v3/applications/com.cbse.study/edits" --header "Authorization: Bearer ya29.a0AfB_byDrLyhV3TRnVdne08V-WlYUplTxw31tud9RJNavM-9pp93y7nlI3kGCVed4FqJO-PO6rxY3aCW8HN9lzvXwfxfPJ0B4ZW5FxGkGy_y4preDGFWBF-c2WIgctODRFR4P0HGFeoubPNCgFC54yHcaOqjaOlFlOW-waCgYKAQwSARISFQHGX2MiGmeAVSKu-RYbjr6Ez7Ysmg0171" --header "Accept: application/json" --header "Content-Type: application/json" --data "{}"--compressed



testingtrack@pc-api-5334270119157250243-146.iam.gserviceaccount.com

api_key:
40bc7460126859af262a00654e01fcd1170a4300



















curl --request POST --url https://androidpublisher.googleapis.com/androidpublisher/v3/applications/com.cbse.study/edits --header 'accept: application/json' --header 'authorization: Bearer ya29.a0AfB_byAb2JPerrupb8arKSPOkPC3d-H_DrXeOy7yYEFOLBNW8Yc9qoqRpr6ObuQrpSEXSeit11kawpGbs1ogoe4tOfp7sKc4hJpzrvbjelf5_GKOajrNaSuqdTMxqC4-D2Og_mtc5d0ZUS-lBN-PVCJ_4izHN49Tsp1PaCgYKAVkSARISFQGOcNnC3MJMuBR0CJlWkFQciOMvPw0171'


https://developers.google.com/android-publisher/api-ref/rest/v3/applications.deviceTierConfigs/create?apix_params=%7B%22packageName%22%3A%22com.cbse.study%22%2C%22resource%22%3A%7B%7D%7D
