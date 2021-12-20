import json
from urllib import request

url = "https://covid19-public.digitalservice.id/api/v1/rekapitulasi_v2/jabar/harian?level=kab"

# lakukan http request
response = request.urlopen(url)

# parsing data json
data = json.loads(response.read())

# gunakan perulangan untuk menampilkan data
for covid in data['data']:
    print(f"- {covid['provinsi']}:")
    print(f"  🤒Positif: {covid['kasusPosi']}")
    print(f"  🙂Sembuh: {covid['kasusSemb']}")
    print(f"  ☠ Meninggal: {covid['kasusMeni']}")
