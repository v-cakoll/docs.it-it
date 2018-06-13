---
title: "Preparazione all'adozione di Windows Communication Foundation: facilitare l'integrazione futura"
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: f81e158a5e7f897307c0c6d376dfe01dac127ead
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489596"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>Preparazione all'adozione di Windows Communication Foundation: facilitare l'integrazione futura
Se si utilizza ASP.NET oggi e preveda l'utilizzo di WCF in futuro, questo argomento fornisce indicazioni per assicurare il funzionano dei nuovi servizi Web ASP.NET bene con applicazioni WCF.  
  
## <a name="general-recommendations"></a>Suggerimenti generali  
 Adottare ASP.NET 2.0 per qualsiasi nuovo servizio. In tal modo sarà possibile accedere ai miglioramenti e ai potenziamenti della nuova versione. Tuttavia, consente inoltre la possibilità di utilizzo dei componenti di ASP.NET 2.0 con i componenti WCF nella stessa applicazione.  
  
## <a name="protocols"></a>Protocolli  
 Utilizzare la nuova funzionalità di ASP.NET 2.0 per convalidare la conformità a WS-I Basic Profile 1.1:  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 Servizi Web ASP.NET conformi alla specifica WS-I Basic Profile 1.1 sarà interoperativo con client WCF usando l'associazione, predefiniti WCF <xref:System.ServiceModel.BasicHttpBinding>.  
  
## <a name="service-development"></a>Sviluppo del servizio  
 Evitare di utilizzare l'attributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> per instradare i messaggi a metodi basati sul nome completo dell'elemento del corpo del messaggio SOAP anziché sull'intestazione HTTP SOAPAction. WCF utilizza l'intestazione HTTP SOAPAction per instradare i messaggi.  
  
## <a name="data-representation"></a>Rappresentazione dei dati  
 Il codice XML in cui l'oggetto <xref:System.Xml.Serialization.XmlSerializer> serializza un tipo è per impostazione predefinita semanticamente identico al codice XML in cui l'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> serializza un tipo, purché lo spazio dei nomi del codice XML sia stato definito in modo esplicito. Quando si definisce un tipo di dati per l'uso con servizi Web ASP.NET in previsione di adozione WCF in futuro, eseguire le operazioni seguenti:  
  
1.  Definire il tipo utilizzando classi .NET Framework anziché l'XML Schema.  
  
2.  Aggiungere solo gli attributi <xref:System.SerializableAttribute> e <xref:System.Xml.Serialization.XmlRootAttribute> alla classe, utilizzando quest'ultimo per definire in modo esplicito lo spazio dei nomi del tipo. Evitare di aggiungere attributi aggiuntivi dallo spazio dei nomi <xref:System.Xml.Serialization> per controllare la modalità di conversione della classe .NET Framework in XML.  
  
 Tramite questo approccio è possibile convertire successivamente le classi .NET in contratti di dati aggiungendo gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> senza modificare in modo significativo il codice XML nel quale le classi vengono serializzate per la trasmissione. I tipi utilizzati nei messaggi dai servizi Web ASP.NET potranno essere elaborati come contratti dati da applicazioni di WCF, producendo tra altri vantaggi, prestazioni migliori nelle applicazioni WCF.  
  
## <a name="security"></a>Sicurezza  
 Evitare di utilizzare le opzioni di autenticazione fornite in Internet Information Services (IIS), I client WCF non le supportano. Se un servizio deve essere protetto, utilizzare le opzioni fornite da WCF, perché queste opzioni sono infatti più affidabili e sono basate su protocolli standard.  
  
## <a name="see-also"></a>Vedere anche  
 [Preparazione all'adozione di Windows Communication Foundation: semplificazione della migrazione futura](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
