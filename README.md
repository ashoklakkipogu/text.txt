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















from googleapiclient import discovery
from google.oauth2 import service_account
import requests

package_name = "com.cbse.study"

scopes = ['https://www.googleapis.com/auth/androidpublisher']
sa_file = "api_service.json"

credentials = service_account.Credentials.from_service_account_file(sa_file, scopes=scopes)
print(credentials)

# see the list of discoverable api's here https://www.googleapis.com/discovery/v1/apis
service = discovery.build('androidpublisher', 'v3', credentials=credentials)

# note that insert() returns a request that needs to be exexuted
request = service.edits().insert(packageName=package_name)
response = request.execute()
editId = response['id']
print(editId)


# API_URL = "https://androidpublisher.googleapis.com/androidpublisher/v3/applications/"+package_name+"/edits/"+editId+"/tracks"

# print(API_URL)
# response = requests.get(API_URL)
requestTracks = service.edits().tracks().list(editId=editId, packageName=package_name)
response = requestTracks.execute()
print(response)


# body={u'googleGroups': [
# u'test@gmail.com']}


# requestTesterGet = service.edits().testers().get(track="production", editId=editId, packageName=package_name)
# response = requestTesterGet.execute()
# print(response)




body= {"googleGroups":["lakkipogu", "lakkipogu"]},
requestTester = service.edits().testers().patch(packageName=package_name, editId=editId, track="beta", content=body)
response = requestTester.execute()
print(response)


# say you want to know the details about your package
request = service.edits().details().get(packageName=package_name, editId=editId)
response = request.execute()
print(response)







{
  "type": "service_account",
  "project_id": "pc-api-5334270119157250243-146",
  "private_key_id": "492fa8caa4acd8cfe993475fa296c8d617f7f38e",
  "private_key": "-----BEGIN PRIVATE KEY-----\nMIIEugIBADANBgkqhkiG9w0BAQEFAASCBKQwggSgAgEAAoIBAQCLfX6V5lQ3jnWQ\nOrCIG94g45qLiz/T7xkre/F+zsMg2p83xCR1LUWn3fIawxhXf27rEI6wmKzFWKts\nnpBK7WpzwiMQGZ1VNwy1Jl0UpOcz67R3fHAbMAgQwaQu8vH5RmNDxOXxjobWg4Un\njbK5mfdIirqq5uvfzEVkg6MiznPWqv0tThbQnrdPUNIbWu+JINcRGRib70M6tjE8\nUfrMc/MCQhk2arLja39hZc1PRzup267jHCStULvWo972OAD0yBkJhcqnHMSrGUgP\nKSIZWhAtPPRAjTm6w2fZ51huIiaoyYQFyCtOCsBwWyZe5Wa/Su7v95n3CUmlEQ2R\nWOgtEIkhAgMBAAECggEAAYWV+vavVofUWoV5ZZLAQqWZCwqy4JIMOUA560NAN7yK\n3iXiq/CZgPJX8NjODC5UvHXKyLxxrhmAjUfRlS+v6KFmlodhAwv9tIA9pbsC1rss\nld0ir/k/LUefje+SmkCdVqDwTUlbyT1YF41hNMssOntg+/pW+nMVErqo7flIpD/n\nMTLFbWPhlNWmG9qZtD/Ksv5WFKz0HJMWDcnSFiF8tVIaw9tb1/I8PDhDW7HVMPwc\nsfVD7Pd9gLovQNT7/bKaWz9i0I2xEDrPlDb2j5TLcthwtypHJ1AmgRcycVHZjwwN\nHHTZwify62ClxlidieTioOeNssT1OxOUBztuMSQwEQKBgQDChD7xEvBwEpWvZcuS\n7DSciY0Pz5VI3izunv2L5PRplyRb/CYmnS8M7A+t7SKbVm4+kE/tAOEY6NvzvbFs\nxVuwzvOD2JhhEj3tHFyY8J3GfIwKvqN301eyLop2sV5yFUU4tR0q7mt/2OX4anUW\nKuis7uop/k+ma+LFOU54c7YSNQKBgQC3lKn0oaSfDy1fCc3Rvx4D03BwRKQrOWCT\nk7UmPTkPZRiyJGIDwEzaIKj7PHr0h/N2BugvtquejfAGyLtGPvbzM9xedYqc6XYZ\nDz+ML8Tew7UB/t9ClmT45R1RQuzsd7qo8Ln2WJDnUoK7Bo8lykvfQoJNIDubVYjU\nZ/0JejO4vQJ/TkLnEBeOpYjUsL1EKtjeUh0FpFbguXCqo1dUq/RyYgltl5TbxK15\nQLm5lUDTq6warxFhFvpDlsIZvPeVay38tiaN035R0LyGLeA7YU1uLW3u6mPJYWym\n3Andq+OxHDVypF46XguPNOEPpeMvOLwK4Yk+raakZVEC7FciO1RS7QKBgBju6wpb\nreUghZQD291h7KyuWfYVjIqGV3STuiXAaPCLVYhUYq+JvaZeizTcKQLvOATOuVhJ\nohN9yZzSRIUs5hNv9r0pj7LyDmUm6gWbM0ziHcJwoFgF3x7i11GDGnSfak2prEgm\nDUAtt625HVYPnLBs8w+QkiftvRDEMtzHqSCtAoGAFMF/RjBvhEcdzhxmCeyutw1Q\nAxPi7hHv3X8mgQ8odbV7Ep17f5x+aGQTOwZn2kUqB6bukuBdHLX6+wYWz/BGzo5L\nCf3gMwMpd2iQzNOJK5jPli/DbK9czvHryXmQi5WGr39K/ag4lLeun3n40UhgdzVo\nXuCvyszSixw0Hoy+8uM=\n-----END PRIVATE KEY-----\n",
  "client_email": "firebase-app-distributor@pc-api-5334270119157250243-146.iam.gserviceaccount.com",
  "client_id": "110466837655981551698",
  "auth_uri": "https://accounts.google.com/o/oauth2/auth",
  "token_uri": "https://oauth2.googleapis.com/token",
  "auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs",
  "client_x509_cert_url": "https://www.googleapis.com/robot/v1/metadata/x509/firebase-app-distributor%40pc-api-5334270119157250243-146.iam.gserviceaccount.com",
  "universe_domain": "googleapis.com"
}






curl --request POST --url https://androidpublisher.googleapis.com/androidpublisher/v3/applications/com.cbse.study/edits --header 'accept: application/json' --header 'authorization: Bearer ya29.a0AfB_byAb2JPerrupb8arKSPOkPC3d-H_DrXeOy7yYEFOLBNW8Yc9qoqRpr6ObuQrpSEXSeit11kawpGbs1ogoe4tOfp7sKc4hJpzrvbjelf5_GKOajrNaSuqdTMxqC4-D2Og_mtc5d0ZUS-lBN-PVCJ_4izHN49Tsp1PaCgYKAVkSARISFQGOcNnC3MJMuBR0CJlWkFQciOMvPw0171'


https://developers.google.com/android-publisher/api-ref/rest/v3/applications.deviceTierConfigs/create?apix_params=%7B%22packageName%22%3A%22com.cbse.study%22%2C%22resource%22%3A%7B%7D%7D
