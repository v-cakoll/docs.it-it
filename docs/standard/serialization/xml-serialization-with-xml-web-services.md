---
title: Serializzazione XML con Servizi Web XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XML Web services, XML serialization
- XML serialization, XML Web services
- SOAP, XML serialization
- asmx files
- serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- .asmx files
- encoded XML serialization
- literal XML serialization
- serialization, attributes
ms.assetid: a416192f-8102-458e-bc0a-0b8f3f784da9
ms.openlocfilehash: fdf984cd52441fd2bbe38499f981542386bd56ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591395"
---
# <a name="xml-serialization-with-xml-web-services"></a>Serializzazione XML con Servizi Web XML
La serializzazione XML è il meccanismo di trasporto sottostante utilizzato nell'architettura dei servizi Web XML, eseguita dalla classe <xref:System.Xml.Serialization.XmlSerializer>. Per controllare il codice XML generato da un servizio Web XML, è possibile applicare gli attributi elencati in [Attributi per il controllo della serializzazione XML](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md) e in [Attributi per il controllo della serializzazione SOAP codificata](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md) alle classi, ai valori restituiti, ai parametri e ai campi di un file usato per creare un servizio Web XML (file con estensione asmx). Per altre informazioni sulla creazione di un servizio Web XML, vedere [Building XML Web Services Using ASP.NET](https://msdn.microsoft.com/library/01dfc27c-c68e-4910-a0aa-5e4c2a766b0c) (Creazione di servizi Web XML tramite ASP.NET).  
  
## <a name="literal-and-encoded-styles"></a>Stili letterali e codificati  
 Il codice XML generato da un servizio Web XML può essere formattato in uno di due modi, letterale o codificato, come illustrato in [Personalizzazione dei messaggi SOAP](https://msdn.microsoft.com/library/1d777288-c0d9-4e6a-b638-f010da031952). Esistono pertanto due insiemi di attributi che controllano la serializzazione XML. Gli attributi elencati in [Attributi per il controllo della serializzazione XML](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md) sono progettati per controllare il codice XML con stile letterale. Gli attributi elencati in [Attributi per il controllo della serializzazione SOAP codificata](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md) sono progettati per controllare lo stile codificato. Tramite l'applicazione selettiva di tali attributi, è possibile adattare un'applicazione in modo che restituisca solo uno o entrambi gli stili. Inoltre, questi attributi possono essere applicati (in base alle proprie esigenze) a valori restituiti e parametri.  
  
### <a name="example-of-using-both-styles"></a>Esempio di utilizzo di entrambi gli stili  
 Durante la creazione di un servizio Web XML, è possibile utilizzare entrambi gli insiemi di attributi sui metodi. Nell'esempio di codice riportato di seguito, la classe denominata `MyService` contiene due metodi del servizio Web XML, `MyLiteralMethod` e `MyEncodedMethod`. Entrambi i metodi eseguono la stessa funzione: la restituzione di un'istanza della classe `Order`. Nella classe `Order` gli attributi <xref:System.Xml.Serialization.XmlTypeAttribute> e <xref:System.Xml.Serialization.SoapTypeAttribute> sono entrambi applicati al campo `OrderID` ed entrambi hanno la proprietà `ElementName` impostata su valori diversi.  
  
 Per eseguire l'esempio, incollare il codice in un file con estensione asmx e posizionare il file in una directory virtuale gestita da Internet Information Services (IIS). Da un browser HTML, ad esempio Internet Explorer, digitare il nome del computer, della directory virtuale e del file.  
  
```vb  
<%@ WebService Language="VB" Class="MyService" %>  
Imports System  
Imports System.Web.Services  
Imports System.Web.Services.Protocols  
Imports System.Xml.Serialization  
Public Class Order  
    ' Both types of attributes can be applied. Depending on which type  
    ' the method used, either one will affect the call.  
    <SoapElement(ElementName:= "EncodedOrderID"), _  
    XmlElement(ElementName:= "LiteralOrderID")> _  
    public OrderID As String  
End Class  
  
Public Class MyService  
    <WebMethod, SoapDocumentMethod> _  
    public Function MyLiteralMethod() As Order   
        Dim myOrder As Order = New Order()  
        return myOrder  
    End Function  
    <WebMethod, SoapRpcMethod> _  
    public Function MyEncodedMethod() As Order   
        Dim myOrder As Order = New Order()  
        return myOrder  
    End Function  
End Class  
```  
  
```csharp  
<%@ WebService Language="C#" Class="MyService" %>  
using System;  
using System.Web.Services;  
using System.Web.Services.Protocols;  
using System.Xml.Serialization;  
public class Order{  
    // Both types of attributes can be applied. Depending on which type  
    // the method used, either one will affect the call.  
    [SoapElement(ElementName = "EncodedOrderID")]  
    [XmlElement(ElementName = "LiteralOrderID")]  
    public String OrderID;  
}  
public class MyService{  
    [WebMethod][SoapDocumentMethod]  
    public Order MyLiteralMethod(){  
        Order myOrder = new Order();  
        return myOrder;  
    }  
    [WebMethod][SoapRpcMethod]  
    public Order MyEncodedMethod(){  
        Order myOrder = new Order();  
        return myOrder;  
    }  
}  
```  
  
 Nell'esempio di codice riportato di seguito viene chiamato il metodo `MyLiteralMethod`. Il nome dell'elemento viene modificato in "LiteralOrderID."  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body>  
        <MyLiteralMethodResponse xmlns="http://tempuri.org/">  
            <MyLiteralMethodResult>  
                <LiteralOrderID>string</LiteralOrderID>  
            </MyLiteralMethodResult>  
        </MyLiteralMethodResponse>  
    </soap:Body>  
</soap:Envelope>  
```  
  
 Nell'esempio di codice riportato di seguito viene chiamato il metodo `MyEncodedMethod`. Il nome dell'elemento è "EncodedOrderID."  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenc="http://schemas.xmlsoap.org/soap/encoding/" xmlns:tns="http://tempuri.org/" xmlns:types="http://tempuri.org/encodedTypes" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body soap:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
        <tns:MyEncodedMethodResponse>  
            <MyEncodedMethodResult href="#id1" />  
        </tns:MyEncodedMethodResponse>  
        <types:Order id="id1" xsi:type="types:Order">  
            <EncodedOrderID xsi:type="xsd:string">string</EncodedOrderID>  
        </types:Order>  
    </soap:Body>  
</soap:Envelope>  
```  
  
### <a name="applying-attributes-to-return-values"></a>Applicazione di attributi ai valori restituiti  
 È inoltre possibile applicare attributi ai valori restituiti per controllare lo spazio dei nomi, il nome dell'elemento e così via. Nell'esempio di codice riportato di seguito viene applicato l'attributo `XmlElementAttribute` al valore restituito del metodo `MyLiteralMethod`. Tale operazione consente di controllare lo spazio dei nomi e il nome dell'elemento.  
  
```vb  
<WebMethod, SoapDocumentMethod> _  
public Function MyLiteralMethod() As _  
<XmlElement(Namespace:="http://www.cohowinery.com", _  
ElementName:= "BookOrder")> _  
Order   
    Dim myOrder As Order = New Order()  
    return myOrder  
End Function  
```  
  
```csharp  
[return: XmlElement(Namespace = "http://www.cohowinery.com",  
ElementName = "BookOrder")]  
[WebMethod][SoapDocumentMethod]  
public Order MyLiteralMethod(){  
    Order myOrder = new Order();  
    return myOrder;  
}  
```  
  
 Se richiamato, il codice restituisce l'XML che assomiglia agli elementi seguenti.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body>  
        <MyLiteralMethodResponse xmlns="http://tempuri.org/">  
            <BookOrder xmlns="http://www.cohowinery.com">  
                <LiteralOrderID>string</LiteralOrderID>  
            </BookOrder>  
        </MyLiteralMethodResponse>  
    </soap:Body>  
</soap:Envelope>  
```  
  
### <a name="attributes-applied-to-parameters"></a>Attributi applicati ai parametri  
 È inoltre possibile applicare attributi ai parametri per specificare lo spazio dei nomi, il nome dell'elemento e così via. Nell'esempio di codice riportato di seguito viene aggiunto un parametro al metodo `MyLiteralMethodResponse` e viene applicato l'attributo `XmlAttributeAttribute` al parametro. Il nome dell'elemento e lo spazio dei nomi vengono entrambi impostati per il parametro.  
  
```vb  
<WebMethod, SoapDocumentMethod> _  
public Function MyLiteralMethod(<XmlElement _  
("MyOrderID", Namespace:="http://www.microsoft.com")>ID As String) As _  
<XmlElement(Namespace:="http://www.cohowinery.com", _  
ElementName:= "BookOrder")> _  
Order   
    Dim myOrder As Order = New Order()  
    myOrder.OrderID = ID  
    return myOrder  
End Function  
```  
  
```csharp  
[return: XmlElement(Namespace = "http://www.cohowinery.com",  
ElementName = "BookOrder")]  
[WebMethod][SoapDocumentMethod]  
public Order MyLiteralMethod([XmlElement("MyOrderID",   
Namespace="http://www.microsoft.com")] string ID){  
    Order myOrder = new Order();  
    myOrder.OrderID = ID;  
    return myOrder;  
}   
```  
  
 La richiesta SOAP dovrebbe essere simile alla seguente.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body>  
        <MyLiteralMethod xmlns="http://tempuri.org/">  
            <MyOrderID xmlns="http://www.microsoft.com">string</MyOrderID>  
        </MyLiteralMethod>  
    </soap:Body>  
</soap:Envelope>  
```  
  
### <a name="applying-attributes-to-classes"></a>Applicazione di attributi alle classi  
 Se è necessario controllare lo spazio dei nomi di elementi correlati alle classi, è possibile applicare `XmlTypeAttribute`, `XmlRootAttribute`e `SoapTypeAttribute`, in base alle proprie esigenze. Nell'esempio di codice riportato di seguito, i tre attributi vengono applicati alla classe `Order`.  
  
```vb  
<XmlType("BigBookService"), _  
SoapType("SoapBookService"), _  
XmlRoot("BookOrderForm")> _  
Public Class Order  
    ' Both types of attributes can be applied. Depending on which  
    ' the method used, either one will affect the call.  
    <SoapElement(ElementName:= "EncodedOrderID"), _  
    XmlElement(ElementName:= "LiteralOrderID")> _  
    public OrderID As String  
End Class  
```  
  
```csharp  
[XmlType("BigBooksService", Namespace = "http://www.cpandl.com")]  
[SoapType("SoapBookService")]  
[XmlRoot("BookOrderForm")]  
public class Order{  
    // Both types of attributes can be applied. Depending on which  
    // the method used, either one will affect the call.  
    [SoapElement(ElementName = "EncodedOrderID")]  
    [XmlElement(ElementName = "LiteralOrderID")]  
    public String OrderID;  
}  
```  
  
 I risultati dell'applicazione di `XmlTypeAttribute` e `SoapTypeAttribute` possono essere visualizzati durante l'esame della descrizione del servizio, come illustrato nell'esempio di codice riportato di seguito.  
  
```xml  
    <s:element name="BookOrderForm" type="s0:BigBookService" />   
- <s:complexType name="BigBookService">  
- <s:sequence>  
    <s:element minOccurs="0" maxOccurs="1" name="LiteralOrderID" type="s:string" />   
    </s:sequence>  
  
- <s:schema targetNamespace="http://tempuri.org/encodedTypes">  
- <s:complexType name="SoapBookService">  
- <s:sequence>  
    <s:element minOccurs="1" maxOccurs="1" name="EncodedOrderID" type="s:string" />   
    </s:sequence>  
    </s:complexType>  
    </s:schema>  
```  
  
 L'effetto di `XmlRootAttribute` può essere inoltre visualizzato nei risultati di HTTP GET e HTTP POST, come riportato di seguito.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<BookOrderForm xmlns="http://tempuri.org/">  
    <LiteralOrderID>string</LiteralOrderID>  
</BookOrderForm>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Serializzazione SOAP e XML](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
 [Attributi per il controllo della serializzazione SOAP codificata](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md)  
 [Procedura: Serializzare un oggetto come flusso XML con codifica SOAP](../../../docs/standard/serialization/how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)  
 [Procedura: Eseguire l'override della serializzazione XML con codifica SOAP](../../../docs/standard/serialization/how-to-override-encoded-soap-xml-serialization.md)  
 [Introduzione alla serializzazione XML](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [Procedura: Serializzare un oggetto](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [Procedura: Deserializzare un oggetto](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
