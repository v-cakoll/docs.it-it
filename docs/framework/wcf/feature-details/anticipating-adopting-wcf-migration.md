---
title: "Preparazione all'adozione di Windows Communication Foundation: facilitazione dell'integrazione futura"
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: b43f509bd49ebe89d7ed0be4c37b3ed179aaeb8c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576499"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Preparazione all'adozione di Windows Communication Foundation: facilitazione dell'integrazione futura
Per garantire una migrazione futura più semplice delle nuove applicazioni ASP.NET a WCF, seguire le indicazioni precedenti, nonché i consigli seguenti.  
  
## <a name="protocols"></a>Protocolli  
 Disattivare il supporto di ASP.NET 2.0 per SOAP 1.2:  
  
```xml  
<configuration>  
     <system.web>  
      <webServices >  
          <protocols>  
           <remove name="HttpSoap12"/>  
          </protocols>
      </webServices>  
     </system.web>
</configuration>  
```  
  
 Questa operazione è consigliabile perché WCF richiede che i messaggi conformi a diversi protocolli, come SOAP 1,1 e SOAP 1,2, vengano usati con endpoint diversi. Se un servizio Web ASP.NET 2,0 è configurato per supportare sia SOAP 1,1 che SOAP 1,2, ovvero la configurazione predefinita, non è possibile eseguirne la migrazione in un singolo endpoint WCF con l'indirizzo originale che sarebbe certamente compatibile con tutti i client esistenti del servizio Web ASP.NET. La scelta di SOAP 1.2 anziché la versione 1.1 restringerà inoltre sensibilmente il numero di clienti del servizio.  
  
## <a name="service-development"></a>Sviluppo del servizio  
 WCF consente di definire i contratti di servizio applicando <xref:System.ServiceModel.ServiceContractAttribute> a interfacce o a classi. È consigliabile applicare l'attributo a un'interfaccia piuttosto che a una classe perché in questo modo viene creata una definizione di contratto che può essere implementata in vari modi da un numero qualsiasi di classi. ASP.NET supporta l'opzione relativa all'applicazione dell'attributo <xref:System.Web.Services.WebService> a interfacce e classi. Tuttavia, come già menzionato, ASP.NET 2.0 presenta un difetto a causa del quale il parametro Namespace dell'attributo <xref:System.Web.Services.WebService> non produce alcun effetto quando l'attributo viene applicato a un'interfaccia anziché a una classe. Poiché è generalmente consigliabile modificare lo spazio dei nomi di un servizio dal valore predefinito, `http://tempuri.org` , usando il parametro Namespace dell' <xref:System.Web.Services.WebService> attributo, è necessario continuare a definire i servizi Web ASP.NET applicando l' <xref:System.ServiceModel.ServiceContractAttribute> attributo alle interfacce o alle classi.  
  
- Usare meno codice possibile nei metodi mediante i quali vengono definite queste interfacce. Fare in modo che deleghino il lavoro ad altre classi. I nuovi tipi di servizio WCF possono quindi delegare il lavoro sostanziale a tali classi.  
  
- Fornire nomi espliciti per le operazioni di un servizio usando il parametro `MessageName` di <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     Questa operazione è importante, perché i nomi predefiniti per le operazioni in ASP.NET sono diversi da quelli predefiniti forniti da WCF. Fornendo nomi espliciti non è necessario basarsi su quelli predefiniti.  
  
- Non implementano le operazioni del servizio Web ASP.NET con metodi polimorfici perché WCF non supporta l'implementazione di operazioni con metodi polimorfici.  
  
- Usare <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> per fornire valori espliciti per le intestazioni HTTP SOAPAction mediante le quali le richieste HTTP verranno indirizzate ai metodi.  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     L'adozione di questo approccio elude la necessità di basarsi sui valori SOAPAction predefiniti utilizzati da ASP.NET e WCF.  
  
- Evitare l'uso di estensioni SOAP. Se sono necessarie estensioni SOAP, determinare se lo scopo per il quale vengono considerate è una funzionalità già fornita da WCF. In caso contrario, riconsiderare la scelta di non adottare immediatamente WCF.  
  
## <a name="state-management"></a>Gestione dello stato  
 Evitare di dover gestire lo stato nei servizi. Non solo la gestione dello stato tende a compromettere la scalabilità di un'applicazione, ma i meccanismi di gestione dello stato di ASP.NET e WCF sono molto diversi, sebbene WCF supporti i meccanismi ASP.NET in modalità di compatibilità ASP.NET.  
  
## <a name="exception-handling"></a>Gestione delle eccezioni  
 Nella progettazione delle strutture dei tipi di dati da inviare e ricevere da un servizio, progettare anche strutture che rappresentino i vari tipi di eccezioni che potrebbero verificarsi all'interno di un servizio che si desidera trasmettere a un client.  
  
```csharp  
[Serializable]  
[XmlRoot(Namespace="ExplicitNamespace", IsNullable=true)]  
public partial class AnticipatedException
{
    private string anticipatedExceptionInformationField;  

    public string AnticipatedExceptionInformation
    {  
        get {
            return this.anticipatedExceptionInformationField;  
        }  
        set {  
            this.anticipatedExceptionInformationField = value;  
        }  
    }  
}  
```  
  
 Impostare queste classi in modo che siano in grado di serializzarsi in XML:  
  
```csharp  
public XmlNode ToXML()  
{  
     XmlSerializer serializer = new XmlSerializer(  
      typeof(AnticipatedException));  
     MemoryStream memoryStream = new MemoryStream();  
     XmlTextWriter writer = new XmlTextWriter(  
     memoryStream, UnicodeEncoding.UTF8);  
     serializer.Serialize(writer, this);  
     XmlDocument document = new XmlDocument();  
     document.LoadXml(new string(  
     UnicodeEncoding.UTF8.GetChars(  
     memoryStream.GetBuffer())).Trim());  
    return document.DocumentElement;  
}  
```  
  
 Le classi potranno quindi essere usate per fornire i dettagli per le istanze <xref:System.Web.Services.Protocols.SoapException> generate in modo esplicito:  
  
```csharp  
AnticipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 Queste classi di eccezioni saranno immediatamente riutilizzabili con la <xref:System.ServiceModel.FaultException%601> classe WCF per generare un nuovo`FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>Sicurezza  
 Di seguito sono riportati alcuni consigli sulla protezione.  
  
- Evitare di utilizzare i profili ASP.NET 2,0, in quanto l'utilizzo di tali profili limita l'utilizzo della modalità di integrazione ASP.NET se è stata eseguita la migrazione del servizio in WCF.  
  
- Evitare di utilizzare gli ACL per controllare l'accesso ai servizi, perché i servizi Web di ASP.NET supportano gli ACL tramite Internet Information Services (IIS), WCF non, perché i servizi Web ASP.NET dipendono da IIS per l'hosting e WCF non deve necessariamente essere ospitato in IIS.  
  
- Prendere in considerazione l'uso dei provider di ruoli di ASP.NET 2.0 per l'autorizzazione dell'accesso alle risorse di un servizio.  
  
## <a name="see-also"></a>Vedere anche

- [Preparazione all'adozione di Windows Communication Foundation: facilitare l'integrazione futura](anticipating-adopting-the-wcf-easing-future-integration.md)
