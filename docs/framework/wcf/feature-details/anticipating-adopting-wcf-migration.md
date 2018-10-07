---
title: "Preparazione all'adozione di Windows Communication Foundation: facilitazione dell'integrazione futura"
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: 171a31b375eae4c032849c2a1c2090f5d9ff856f
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48837400"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Preparazione all'adozione di Windows Communication Foundation: facilitazione dell'integrazione futura
Per garantire una più facile migrazione futura di nuove applicazioni ASP.NET a WCF, seguire i consigli forniti sopra nonché le indicazioni seguenti.  
  
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
  
 In questo modo è consigliabile poiché WCF i messaggi conformi a protocolli diversi, ad esempio SOAP 1.1 e SOAP 1.2, per passare tramite endpoint diversi. Se Web ASP.NET 2.0 che servizio è configurato per supportare SOAP 1.1 e SOAP 1.2, ovvero la configurazione predefinita, quindi non può essere eseguita la migrazione diretta a un singolo endpoint WCF all'indirizzo originale che sarebbe certamente essere compatibile con tutti i Web ASP.NET client esistenti del servizio. La scelta di SOAP 1.2 anziché la versione 1.1 restringerà inoltre sensibilmente il numero di clienti del servizio.  
  
## <a name="service-development"></a>Sviluppo del servizio  
 WCF consente di definire i contratti di servizio applicando la <xref:System.ServiceModel.ServiceContractAttribute> a interfacce o classi. È consigliabile applicare l'attributo a un'interfaccia piuttosto che a una classe perché in questo modo viene creata una definizione di contratto che può essere implementata in vari modi da un numero qualsiasi di classi. ASP.NET supporta l'opzione relativa all'applicazione dell'attributo <xref:System.Web.Services.WebService> a interfacce e classi. Tuttavia, come già menzionato, ASP.NET 2.0 presenta un difetto a causa del quale il parametro Namespace dell'attributo <xref:System.Web.Services.WebService> non produce alcun effetto quando l'attributo viene applicato a un'interfaccia anziché a una classe. Poiché è generalmente consigliabile modificare lo spazio dei nomi di un servizio il valore predefinito `http://tempuri.org`, usando il parametro Namespace del <xref:System.Web.Services.WebService> attributo, è necessario continuare a definire servizi Web ASP.NET applicando il <xref:System.ServiceModel.ServiceContractAttribute> attributo o a interfacce o classi.  
  
-   Usare meno codice possibile nei metodi mediante i quali vengono definite queste interfacce. Fare in modo che deleghino il lavoro ad altre classi. Nuovi tipi di servizio WCF è stato quindi anche delegare il lavoro effettivo di tali classi.  
  
-   Fornire nomi espliciti per le operazioni di un servizio usando il parametro `MessageName` di <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     In questo modo è importante, perché i nomi predefiniti per le operazioni in ASP.NET sono diversi da quelli predefiniti forniti da WCF. Fornendo nomi espliciti non è necessario basarsi su quelli predefiniti.  
  
-   Non implementare operazioni del servizio Web ASP.NET con metodi polimorfici, poiché WCF non supporta le operazioni di implementazione con metodi polimorfici.  
  
-   Usare <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> per fornire valori espliciti per le intestazioni HTTP SOAPAction mediante le quali le richieste HTTP verranno indirizzate ai metodi.  
  
    ```  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     Questo approccio verrà evitare di dovere si basano sull'impostazione predefinita i valori SOAPAction utilizzati da ASP.NET e WCF in corso lo stesso.  
  
-   Evitare l'uso di estensioni SOAP. Se sono necessarie le estensioni SOAP, determinare se lo scopo per cui vengono considerate è una funzionalità già fornita da WCF. Se è effettivamente questo il caso, riconsiderare la scelta di non adottare sin da subito WCF.  
  
## <a name="state-management"></a>Gestione dello stato  
 Evitare di dover gestire lo stato nei servizi. Non solo gestione dello stato tende a compromettere la scalabilità di un'applicazione, ma i meccanismi di gestione dello stato di ASP.NET e WCF sono molto diversi, anche se WCF supporta i meccanismi ASP.NET nella modalità di compatibilità ASP.NET.  
  
## <a name="exception-handling"></a>Gestione delle eccezioni  
 Nella progettazione delle strutture dei tipi di dati da inviare e ricevere da un servizio, progettare anche strutture che rappresentino i vari tipi di eccezioni che potrebbero verificarsi all'interno di un servizio che si desidera trasmettere a un client.  
  
```  
[Serializable]  
[XmlRoot(  
     Namespace="ExplicitNamespace", IsNullable=true)]  
    public partial class AnticipatedException {  
  
     private string anticipatedExceptionInformationField;  
  
     public string AnticipatedExceptionInformation {  
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
  
```  
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
  
```  
AnctipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 Queste classi di eccezione potranno essere riutilizzate con WCF<xref:System.ServiceModel.FaultException%601> per generare una nuova classe `FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>Sicurezza  
 Di seguito sono riportati alcuni consigli sulla protezione.  
  
-   Evitare usando profili di ASP.NET 2.0 poiché determinerebbe una limitazione l'utilizzo della modalità di integrazione ASP.NET se il servizio è stata eseguita la migrazione a WCF.  
  
-   Evitare di usare gli ACL per controllare l'accesso ai servizi, come servizi Web ASP.NET supporta gli ACL usando Internet Information Services (IIS), non WCF, poiché i servizi Web ASP.NET dipendono da IIS per l'hosting, e WCF non deve necessariamente essere ospitata in IIS.  
  
-   Prendere in considerazione l'uso dei provider di ruoli di ASP.NET 2.0 per l'autorizzazione dell'accesso alle risorse di un servizio.  
  
## <a name="see-also"></a>Vedere anche  
 [Preparazione dell'adozione di Windows Communication Foundation: semplificazione dell'integrazione futura](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
