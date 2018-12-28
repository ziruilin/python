

```python
import urllib, urllib.request, sys
import ssl

# client_id 为官网获取的AK， client_secret 为官网获取的SK
host = 'https://aip.baidubce.com/oauth/2.0/token?grant_type=client_credentials&client_id=hKTyGoTBEF8BAm7joEhpDjpV&client_secret=CWGp62NTi1p2g7fzasbh6EdUHaWv6USI'
request = urllib.request.Request(host)
request.add_header('Content-Type', 'application/json; charset=UTF-8')
response = urllib.request.urlopen(request)
content = response.read()
if (content):
    print(content)
```

    b'{"refresh_token":"25.62b79c499efc51d3016a97fe5c2aee2b.315360000.1861340895.282335-15290392","expires_in":2592000,"session_key":"9mzdAqYtZLI2shel3hQ4eCe7QtuwsJH7VDcYk1LaAPQhj3ZJ4Z03pkcvcs85IzL9BNP\\/AnzfY7rQTKow9q8T\\/e5AYVJ6Ww==","access_token":"24.9db85603f37f7098f7b42c17cc559955.2592000.1548572895.282335-15290392","scope":"public vis-ocr_ocr brain_ocr_scope brain_ocr_general brain_ocr_general_basic brain_ocr_general_enhanced vis-ocr_business_license brain_ocr_webimage brain_all_scope brain_ocr_idcard brain_ocr_driving_license brain_ocr_vehicle_license vis-ocr_plate_number brain_solution brain_ocr_plate_number brain_ocr_accurate brain_ocr_accurate_basic brain_ocr_receipt brain_ocr_business_license brain_solution_iocr brain_ocr_handwriting brain_ocr_vat_invoice brain_numbers brain_ocr_train_ticket brain_ocr_taxi_receipt wise_adapt lebo_resource_base lightservice_public hetu_basic lightcms_map_poi kaidian_kaidian ApsMisTest_Test\\u6743\\u9650 vis-classify_flower lpq_\\u5f00\\u653e cop_helloScope ApsMis_fangdi_permission smartapp_snsapi_base iop_autocar oauth_tp_app smartapp_smart_game_openapi oauth_sessionkey smartapp_swanid_verify","session_secret":"22c41a01c13a1dda1113967467a3c15c"}\n'
    


```python
from aip import AipOcr

""" 你的 APPID AK SK """
APP_ID = '15290392'
API_KEY = 'hKTyGoTBEF8BAm7joEhpDjpV'
SECRET_KEY = 'CWGp62NTi1p2g7fzasbh6EdUHaWv6USI'

client = AipOcr(APP_ID, API_KEY, SECRET_KEY)
```


```python
""" 读取图片 """
def get_file_content(filePath):
    with open(filePath, 'rb') as fp:
        return fp.read()

image = get_file_content('C:\模板.jpg')
templateSign = "cbb351d7b40ed7634c5f96d04587b594"

""" 调用自定义模板文字识别 """
word = client.custom(image,templateSign)['data']['ret'];

print (word)
```

    [{'probability': {'average': 0.999539, 'min': 0.998673, 'variance': 0.0}, 'location': {'height': 20, 'left': 137, 'top': 66, 'width': 182}, 'word_name': '时间安排', 'word': '每天作乐带回,每天'}, {'probability': {'average': 0.999043, 'min': 0.996317, 'variance': 1e-06}, 'location': {'height': 20, 'left': 138, 'top': 33, 'width': 129}, 'word_name': '事件计划', 'word': '每天背50个单词'}, {'probability': {'average': 0.998374, 'min': 0.994838, 'variance': 3e-06}, 'location': {'height': 23, 'left': 140, 'top': 127, 'width': 41}, 'word_name': '提醒形式', 'word': '语音'}]
    


```python
import pandas as pd
df_g1 = pd.DataFrame({ x['word_name']:x['word'] for x in word },index=[0]).T
df_g1
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>时间安排</th>
      <td>每天作乐带回,每天</td>
    </tr>
    <tr>
      <th>事件计划</th>
      <td>每天背50个单词</td>
    </tr>
    <tr>
      <th>提醒形式</th>
      <td>语音</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
