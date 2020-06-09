---
title: "Preparazione all'adozione di Windows Communication Foundation: facilitare l'integrazione futura"
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: 6392194b3124c999031123225dcc28c8de6171e9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576525"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>Preparazione all'adozione di Windows Communication Foundation: facilitare l'integrazione futura
Se si utilizza ASP.NET oggi e si prevede di utilizzare WCF in futuro, in questo argomento vengono fornite indicazioni per garantire che i nuovi servizi Web ASP.NET funzionino correttamente con le applicazioni WCF.  
  
## <a name="general-recommendations"></a>Suggerimenti generali  
 Adottare ASP.NET 2.0 per qualsiasi nuovo servizio. In tal modo sarà possibile accedere ai miglioramenti e ai potenziamenti della nuova versione. Tuttavia, consente anche di usare i componenti di ASP.NET 2,0 insieme ai componenti WCF nella stessa applicazione.  
  
## <a name="protocols"></a>Protocolli  
 Utilizzare la nuova funzionalità di ASP.NET 2.0 per convalidare la conformità a WS-I Basic Profile 1.1:  
  
```csharp  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 I servizi Web ASP.NET conformi a WS-I Basic Profile 1,1 saranno interoperativi con i client WCF usando l'associazione predefinita WCF, <xref:System.ServiceModel.BasicHttpBinding> .  
  
## <a name="service-development"></a>Sviluppo del servizio  
 Evitare di utilizzare l'attributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> per instradare i messaggi a metodi basati sul nome completo dell'elemento del corpo del messaggio SOAP anziché sull'intestazione HTTP SOAPAction. WCF utilizza l'intestazione HTTP SOAPAction per il routing dei messaggi.  
  
## <a name="data-representation"></a>Rappresentazione dei dati  
 Il codice XML in cui l'oggetto <xref:System.Xml.Serialization.XmlSerializer> serializza un tipo è per impostazione predefinita semanticamente identico al codice XML in cui l'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> serializza un tipo, purché lo spazio dei nomi del codice XML sia stato definito in modo esplicito. Quando si definisce un tipo di dati da utilizzare con i servizi Web di ASP.NET in previsione di adottare WCF in futuro, eseguire le operazioni seguenti:  
  
1. Definire il tipo utilizzando classi .NET Framework anziché l'XML Schema.  
  
2. Aggiungere solo gli attributi <xref:System.SerializableAttribute> e <xref:System.Xml.Serialization.XmlRootAttribute> alla classe, utilizzando quest'ultimo per definire in modo esplicito lo spazio dei nomi del tipo. Evitare di aggiungere attributi aggiuntivi dallo spazio dei nomi <xref:System.Xml.Serialization> per controllare la modalità di conversione della classe .NET Framework in XML.  
  
 Tramite questo approccio è possibile convertire successivamente le classi .NET in contratti di dati aggiungendo gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> senza modificare in modo significativo il codice XML nel quale le classi vengono serializzate per la trasmissione. I tipi utilizzati nei messaggi dai servizi Web di ASP.NET saranno in grado di essere elaborati come contratti dati dalle applicazioni WCF, cedendo, tra gli altri vantaggi, prestazioni migliori nelle applicazioni WCF.  
  
## <a name="security"></a>Sicurezza  
 Evitare di utilizzare le opzioni di autenticazione fornite in Internet Information Services (IIS), I client WCF non li supportano. Se è necessario proteggere un servizio, utilizzare le opzioni fornite da WCF, perché queste opzioni sono più ricche e sono basate su protocolli standard.  
  
## <a name="see-also"></a>Vedere anche

- [Preparazione all'adozione di Windows Communication Foundation: facilitazione dell'integrazione futura](anticipating-adopting-wcf-migration.md)
