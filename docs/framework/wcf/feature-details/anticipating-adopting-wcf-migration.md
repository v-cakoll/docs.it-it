---
title: "Preparazione all'adozione di Windows Communication Foundation: facilitazione dell'integrazione futura"
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: 995bdaaaba96bf8697ea75c1f1a17fa8e51ec2d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185465"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Preparazione all'adozione di Windows Communication Foundation: facilitazione dell'integrazione futura
Per garantire una migrazione futura più semplice di nuove applicazioni di ASP.NET a WCF, seguire le raccomandazioni precedenti e le raccomandazioni seguenti.  
  
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
  
 Questa operazione è consigliabile perché WCF richiede messaggi conformi a protocolli diversi, ad esempio SOAP 1.1 e SOAP 1.2, per utilizzare endpoint diversi. Se un servizio Web ASP.NET 2.0 è configurato per supportare sia SOAP 1.1 che SOAP 1.2, che è la configurazione predefinita, non è possibile eseguirne la migrazione a un singolo endpoint WCF all'indirizzo originale che sarebbe certamente compatibile con tutte le ASP.NET Web clienti esistenti del servizio. La scelta di SOAP 1.2 anziché la versione 1.1 restringerà inoltre sensibilmente il numero di clienti del servizio.  
  
## <a name="service-development"></a>Sviluppo del servizio  
 WCF consente di definire i contratti <xref:System.ServiceModel.ServiceContractAttribute> di servizio applicando l'oggetto alle interfacce o alle classi. È consigliabile applicare l'attributo a un'interfaccia piuttosto che a una classe perché in questo modo viene creata una definizione di contratto che può essere implementata in vari modi da un numero qualsiasi di classi. ASP.NET supporta l'opzione relativa all'applicazione dell'attributo <xref:System.Web.Services.WebService> a interfacce e classi. Tuttavia, come già menzionato, ASP.NET 2.0 presenta un difetto a causa del quale il parametro Namespace dell'attributo <xref:System.Web.Services.WebService> non produce alcun effetto quando l'attributo viene applicato a un'interfaccia anziché a una classe. Poiché è in genere consigliabile modificare lo spazio `http://tempuri.org`dei nomi di un <xref:System.Web.Services.WebService> servizio dal valore predefinito, , utilizzando <xref:System.ServiceModel.ServiceContractAttribute> il parametro Namespace dell'attributo , è necessario continuare a definire ASP.NET Web Services applicando l'attributo alle interfacce o alle classi.  
  
- Usare meno codice possibile nei metodi mediante i quali vengono definite queste interfacce. Fare in modo che deleghino il lavoro ad altre classi. I nuovi tipi di servizio WCF potrebbero quindi anche delegare il proprio lavoro sostanziale a tali classi.  
  
- Fornire nomi espliciti per le operazioni di un servizio usando il parametro `MessageName` di <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     Questa operazione è importante, perché i nomi predefiniti per le operazioni in ASP.NET sono diversi dai nomi predefiniti forniti da WCF. Fornendo nomi espliciti non è necessario basarsi su quelli predefiniti.  
  
- Non implementare operazioni del servizio Web ASP.NET con metodi polimorfici, poiché WCF non supporta l'implementazione di operazioni con metodi polimorfici.  
  
- Usare <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> per fornire valori espliciti per le intestazioni HTTP SOAPAction mediante le quali le richieste HTTP verranno indirizzate ai metodi.  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     L'attivazione di questo approccio eluderà di dover fare affidamento sui valori SOAPAction predefiniti utilizzati da ASP.NET e WCF uguali.  
  
- Evitare l'uso di estensioni SOAP. Se sono necessarie estensioni SOAP, determinare se lo scopo per cui vengono considerate è una funzionalità già fornita da WCF. Se questo è effettivamente il caso, quindi riconsiderare la scelta di non adottare WCF subito.  
  
## <a name="state-management"></a>Gestione dello stato  
 Evitare di dover gestire lo stato nei servizi. Non solo il mantenimento dello stato tende a compromettere la scalabilità di un'applicazione, ma i meccanismi di gestione dello stato di ASP.NET e WCF sono molto diversi, anche se WCF supporta i meccanismi di ASP.NET in modalità compatibilità ASP.NET.  
  
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
  
 Queste classi di eccezione saranno <xref:System.ServiceModel.FaultException%601> facilmente riutilizzabili con la classe WCF per generare un nuovo`FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>Security  
 Di seguito sono riportati alcuni consigli sulla protezione.  
  
- Evitare di usare ASP.NET profili 2.0, poiché il loro utilizzo limiterebbe l'utilizzo di ASP.NET modalità di integrazione se il servizio è stato migrato a WCF.  
  
- Evitare di utilizzare gli ACL per controllare l'accesso ai servizi, come ASP.NET servizi Web supporta gli ACL che utilizzano Internet Information Services (IIS), WCF non è, perché ASP.NET servizi Web dipendono da IIS per l'hosting e WCF non deve necessariamente essere ospitato in IIS.  
  
- Prendere in considerazione l'uso dei provider di ruoli di ASP.NET 2.0 per l'autorizzazione dell'accesso alle risorse di un servizio.  
  
## <a name="see-also"></a>Vedere anche

- [Preparazione all'adozione di Windows Communication Foundation: facilitare l'integrazione futura](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
