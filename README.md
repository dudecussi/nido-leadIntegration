# Integração de Leads (NIDO)
Manual de Integração


##Exemplo CURL
```shell
curl -X POST \
  http://eod.dev.lan/NI4Developer/index.php/api/leadIntegration \
  -H 'Authorization: JWT eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9uaWRvLmNvbS5iciIsImF1ZCI6Imh0dHA6XC9cL25pZG9pbW92ZWwuY29tLmJyIiwiaWF0IjoxNTQ2MzA4MDAwLCJuYmYiOjE1NDYzMDgwMDAsImRhdGEiOnsiY2xpZW50ZV9pZCI6IjMxIiwiY29kYWdlbmNpYSI6Ik5JIiwid2ViX2NvbmZpZ19pZCI6IjgyIn19.VARfNYjb9yIY7pB01HcUJipMC1HEnaG028307Elfz1s' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: Nido/1.0.0 Decussi/1.0.0' \
  -d '{
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
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'Content-Type' => 'application/json',
  'User-Agent' => 'Nido/1.0.0 Decussi/1.0.0',
  'Authorization' => 'JWT eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9uaWRvLmNvbS5iciIsImF1ZCI6Imh0dHA6XC9cL25pZG9pbW92ZWwuY29tLmJyIiwiaWF0IjoxNTQ2MzA4MDAwLCJuYmYiOjE1NDYzMDgwMDAsImRhdGEiOnsiY2xpZW50ZV9pZCI6IjMxIiwiY29kYWdlbmNpYSI6Ik5JIiwid2ViX2NvbmZpZ19pZCI6IjgyIn19.VARfNYjb9yIY7pB01HcUJipMC1HEnaG028307Elfz1s'
));

$request->setBody('{
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
var request = new RestRequest(Method.POST);
request.AddHeader("Content-Type", "application/json");
request.AddHeader("User-Agent", "Nido/1.0.0 Decussi/1.0.0");
request.AddHeader("Authorization", "JWT eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9uaWRvLmNvbS5iciIsImF1ZCI6Imh0dHA6XC9cL25pZG9pbW92ZWwuY29tLmJyIiwiaWF0IjoxNTQ2MzA4MDAwLCJuYmYiOjE1NDYzMDgwMDAsImRhdGEiOnsiY2xpZW50ZV9pZCI6IjMxIiwiY29kYWdlbmNpYSI6Ik5JIiwid2ViX2NvbmZpZ19pZCI6IjgyIn19.VARfNYjb9yIY7pB01HcUJipMC1HEnaG028307Elfz1s");
request.AddParameter("undefined", "{\r\n  \"timestamp\": \"2017-10-23T15:50:30.619Z\",\r\n  \"originLeadId\": \"59ee0fc6e4b043e1b2a6d863\",\r\n  \"originListingId\": \"87027856\",\r\n  \"clientListingId\": \"a40171\",\r\n  \"name\": \"Nome Consumidor\",\r\n  \"email\": \"nome.consumidor@email.com\",\r\n  \"ddd\": \"11\",\r\n  \"phone\": \"999999999\",\r\n  \"phoneNumber\": \"11999999999\",\r\n  \"message\": \"Olá, tenho interesse neste imóvel. Aguardo o contato. Obrigado.\",\r\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```
