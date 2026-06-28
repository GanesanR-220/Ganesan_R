POST /dvwsuserservice/ HTTP/1.1
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/85.0.4164.0 Safari/537.36 autochrome/red
Connection: close
SOAPAction: Username
Content-Type: text/xml;charset=UTF-8
Host: dvws.local
Content-Length: 463

<soapenv:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:examples:usernameservice">
<soapenv:Header/>
<soapenv:Body>
 <urn:Username soapenv:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">
 <username xsi:type="xsd:string">gero et</username>
</urn:Username>
</soapenv:Body>
</soapenv:Envelope>
