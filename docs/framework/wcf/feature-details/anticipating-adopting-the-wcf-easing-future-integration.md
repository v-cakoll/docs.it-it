---
title: "Preparazione all'adozione di Windows Communication Foundation: Semplificazione dell'integrazione futura"
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: f4cc450b04fd05d390a1f41f3d14c19f4b23be29
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155145"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>Preparazione all'adozione di Windows Communication Foundation: Semplificazione dell'integrazione futura
Se si utilizzano oggi ASP.NET e si prevede l'utilizzo di WCF in futuro, questo argomento fornisce indicazioni per garantire che i nuovi servizi Web ASP.NET funzionerà anche con le applicazioni WCF.  
  
## <a name="general-recommendations"></a>Suggerimenti generali  
 Adottare ASP.NET 2.0 per qualsiasi nuovo servizio. In tal modo sarà possibile accedere ai miglioramenti e ai potenziamenti della nuova versione. Tuttavia, consentirà anche per la possibilità di usare i componenti di ASP.NET 2.0 con i componenti WCF nella stessa applicazione.  
  
## <a name="protocols"></a>Protocolli  
 Utilizzare la nuova funzionalità di ASP.NET 2.0 per convalidare la conformità a WS-I Basic Profile 1.1:  
  
```csharp  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 Servizi Web ASP.NET conformi alla specifica WS-I Basic Profile 1.1 è interoperativo con client WCF usando, binding predefiniti WCF <xref:System.ServiceModel.BasicHttpBinding>.  
  
## <a name="service-development"></a>Sviluppo del servizio  
 Evitare di utilizzare l'attributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> per instradare i messaggi a metodi basati sul nome completo dell'elemento del corpo del messaggio SOAP anziché sull'intestazione HTTP SOAPAction. WCF utilizza l'intestazione HTTP SOAPAction per instradare i messaggi.  
  
## <a name="data-representation"></a>Rappresentazione dei dati  
 Il codice XML in cui l'oggetto <xref:System.Xml.Serialization.XmlSerializer> serializza un tipo è per impostazione predefinita semanticamente identico al codice XML in cui l'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> serializza un tipo, purché lo spazio dei nomi del codice XML sia stato definito in modo esplicito. Quando si definisce un tipo di dati per l'uso con i servizi Web ASP.NET in previsione di WCF adozione in futuro, eseguire le operazioni seguenti:  
  
1.  Definire il tipo utilizzando classi .NET Framework anziché l'XML Schema.  
  
2.  Aggiungere solo gli attributi <xref:System.SerializableAttribute> e <xref:System.Xml.Serialization.XmlRootAttribute> alla classe, utilizzando quest'ultimo per definire in modo esplicito lo spazio dei nomi del tipo. Evitare di aggiungere attributi aggiuntivi dallo spazio dei nomi <xref:System.Xml.Serialization> per controllare la modalità di conversione della classe .NET Framework in XML.  
  
 Tramite questo approccio è possibile convertire successivamente le classi .NET in contratti di dati aggiungendo gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> senza modificare in modo significativo il codice XML nel quale le classi vengono serializzate per la trasmissione. I tipi utilizzati nei messaggi dai servizi Web ASP.NET potranno essere in grado di essere elaborati come contratti dati da applicazioni WCF, cede il controllo, tra gli altri vantaggi, prestazioni migliori in applicazioni WCF.  
  
## <a name="security"></a>Sicurezza  
 Evitare di utilizzare le opzioni di autenticazione fornite in Internet Information Services (IIS), I client WCF non li supportano. Se un servizio deve essere protetto, utilizzare le opzioni fornite da WCF, perché queste opzioni sono infatti più affidabili e sono basate su protocolli standard.  
  
## <a name="see-also"></a>Vedere anche  
 [Preparazione all'adozione di Windows Communication Foundation: Semplificazione della migrazione futura](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
