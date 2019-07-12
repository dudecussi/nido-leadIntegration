# Integração de Leads (NIDO)
Manual de Integração


##Exemplo CURL
```sh
curl -X GET \
  http://eod.dev.lan/NI4Developer/index.php/api/leadIntegration \
  -H 'Accept: */*' \
  -H 'Authorization: JWT eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9uaWRvLmNvbS5iciIsImF1ZCI6Imh0dHA6XC9cL25pZG9pbW92ZWwuY29tLmJyIiwiaWF0IjoxNTQ2MzA4MDAwLCJuYmYiOjE1NDYzMDgwMDAsImRhdGEiOnsiY2xpZW50ZV9pZCI6IjMxIiwiY29kYWdlbmNpYSI6Ik5JIiwid2ViX2NvbmZpZ19pZCI6IjgyIn19.VARfNYjb9yIY7pB01HcUJipMC1HEnaG028307Elfz1s' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'Host: eod.dev.lan' \
  -H 'Postman-Token: d3c1fa03-762c-4cb6-9a2f-37e92e0e77ad,8601efea-16cd-4fb2-9307-35ac541b4d05' \
  -H 'User-Agent: Nido/1.0.0 Decussi/1.0.0' \
  -H 'accept-encoding: gzip, deflate' \
  -H 'cache-control: no-cache' \
  -H 'content-length: 418' \
  -H 'cookie: PHPSESSID=no5igtdd0cj7q4qmsu84kdu8r3' \
  -b PHPSESSID=no5igtdd0cj7q4qmsu84kdu8r3 \
  -d '{
  "leadOrigin": "VivaReal",
  "timestamp": "2017-10-23T15:50:30.619Z",
  "originLeadId": "59ee0fc6e4b043e1b2a6d863",
  "originListingId": "87027856",
  "clientListingId": "a40171",
  "name": "Nome Consumidor",
  "email": "nome.consumidor@email.com",
  "ddd": "11",
  "phone": "999999999",
  "phoneNumber": "11999999999",
  "message": "Olá, tenho interesse neste imóvel. Aguardo o contato. Obrigado.",
}'
```

##Exemplo PHP
```php
$request = new HttpRequest();
$request->setUrl('http://eod.dev.lan/NI4Developer/index.php/api/leadIntegration');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'Connection' => 'keep-alive',
  'content-length' => '418',
  'accept-encoding' => 'gzip, deflate',
  'cookie' => 'PHPSESSID=no5igtdd0cj7q4qmsu84kdu8r3',
  'Host' => 'eod.dev.lan',
  'Postman-Token' => 'd3c1fa03-762c-4cb6-9a2f-37e92e0e77ad,b79d7843-26cd-4b34-8738-7b8eef9fdb18',
  'Cache-Control' => 'no-cache',
  'Accept' => '*/*',
  'Content-Type' => 'application/json',
  'User-Agent' => 'Nido/1.0.0 Decussi/1.0.0',
  'Authorization' => 'JWT eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9uaWRvLmNvbS5iciIsImF1ZCI6Imh0dHA6XC9cL25pZG9pbW92ZWwuY29tLmJyIiwiaWF0IjoxNTQ2MzA4MDAwLCJuYmYiOjE1NDYzMDgwMDAsImRhdGEiOnsiY2xpZW50ZV9pZCI6IjMxIiwiY29kYWdlbmNpYSI6Ik5JIiwid2ViX2NvbmZpZ19pZCI6IjgyIn19.VARfNYjb9yIY7pB01HcUJipMC1HEnaG028307Elfz1s'
));

$request->setBody('{
  "leadOrigin": "VivaReal",
  "timestamp": "2017-10-23T15:50:30.619Z",
  "originLeadId": "59ee0fc6e4b043e1b2a6d863",
  "originListingId": "87027856",
  "clientListingId": "a40171",
  "name": "Nome Consumidor",
  "email": "nome.consumidor@email.com",
  "ddd": "11",
  "phone": "999999999",
  "phoneNumber": "11999999999",
  "message": "Olá, tenho interesse neste imóvel. Aguardo o contato. Obrigado.",
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

##Exemplo C#
```C#
var client = new RestClient("http://eod.dev.lan/NI4Developer/index.php/api/leadIntegration");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("Connection", "keep-alive");
request.AddHeader("content-length", "418");
request.AddHeader("accept-encoding", "gzip, deflate");
request.AddHeader("cookie", "PHPSESSID=no5igtdd0cj7q4qmsu84kdu8r3");
request.AddHeader("Host", "eod.dev.lan");
request.AddHeader("Postman-Token", "d3c1fa03-762c-4cb6-9a2f-37e92e0e77ad,d0ec8586-6ede-4234-b5e0-5ba2b55054ad");
request.AddHeader("Cache-Control", "no-cache");
request.AddHeader("Accept", "*/*");
request.AddHeader("Content-Type", "application/json");
request.AddHeader("User-Agent", "Nido/1.0.0 Decussi/1.0.0");
request.AddHeader("Authorization", "JWT eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9uaWRvLmNvbS5iciIsImF1ZCI6Imh0dHA6XC9cL25pZG9pbW92ZWwuY29tLmJyIiwiaWF0IjoxNTQ2MzA4MDAwLCJuYmYiOjE1NDYzMDgwMDAsImRhdGEiOnsiY2xpZW50ZV9pZCI6IjMxIiwiY29kYWdlbmNpYSI6Ik5JIiwid2ViX2NvbmZpZ19pZCI6IjgyIn19.VARfNYjb9yIY7pB01HcUJipMC1HEnaG028307Elfz1s");
request.AddParameter("undefined", "{\r\n  \"leadOrigin\": \"VivaReal\",\r\n  \"timestamp\": \"2017-10-23T15:50:30.619Z\",\r\n  \"originLeadId\": \"59ee0fc6e4b043e1b2a6d863\",\r\n  \"originListingId\": \"87027856\",\r\n  \"clientListingId\": \"a40171\",\r\n  \"name\": \"Nome Consumidor\",\r\n  \"email\": \"nome.consumidor@email.com\",\r\n  \"ddd\": \"11\",\r\n  \"phone\": \"999999999\",\r\n  \"phoneNumber\": \"11999999999\",\r\n  \"message\": \"Olá, tenho interesse neste imóvel. Aguardo o contato. Obrigado.\",\r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```
