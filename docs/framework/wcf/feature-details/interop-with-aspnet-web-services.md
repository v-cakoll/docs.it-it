---
title: Interoperabilità con i servizi Web ASP.NET
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: 41810d8044e4b7ff3193950a914edbf1e61cffb1
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464097"
---
# <a name="interoperability-with-aspnet-web-services"></a>Interoperabilità con i servizi Web ASP.NET
L'interoperabilità tra i servizi Web ASP.NET e i servizi Web Windows Communication Foundation (WCF) può essere ottenuta assicurando che i servizi implementati utilizzando entrambe le tecnologie siano conformi alla specifica WS-I Basic Profile 1.1. ASP.NET servizi Web conformi a WS-I Basic Profile 1.1 sono interoperabili con i <xref:System.ServiceModel.BasicHttpBinding>client WCF utilizzando l'associazione fornita dal sistema WCF, .  
  
 Utilizzare ASP.NET 2.0 opzione <xref:System.Web.Services.WebService> <xref:System.Web.Services.WebMethodAttribute> di aggiunta degli attributi e a un'interfaccia anziché a una classe e di scrivere una classe per implementare l'interfaccia, come illustrato nel codice di esempio seguente.  
  
```csharp
[WebService]  
public interface IEcho  
{  
    [WebMethod]  
    string Echo(string input);  
}  
  
public class Service : IEcho  
{  
  
   public string Echo(string input)  
   {  
        return input;  
    }  
}  
```  
  
 È preferibile utilizzare questa opzione. Infatti, l'interfaccia avente l'attributo <xref:System.Web.Services.WebService> costituisce un contratto per le operazioni eseguite dal servizio che può essere riutilizzato con varie classi in grado di implementare tale contratto in modi diversi.  
  
 Evitare di utilizzare l'attributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> per instradare i messaggi a metodi basati sul nome completo dell'elemento del corpo del messaggio SOAP anziché sull'intestazione HTTP `SOAPAction`. WCF utilizza `SOAPAction` l'intestazione HTTP per il routing dei messaggi.  
  
 Il codice XML in cui l'oggetto <xref:System.Xml.Serialization.XmlSerializer> serializza un tipo è per impostazione predefinita semanticamente identico al codice XML in cui l'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> serializza un tipo, purché lo spazio dei nomi del codice XML sia stato definito in modo esplicito. Quando si definisce un tipo di dati da utilizzare con i servizi ASP.NETWeb in previsione dell'adozione di WCF, eseguire le operazioni seguenti:When defining a data type for use with ASP.NETWeb services in anticipation of adopting WCF, do the following:  
  
- Definire il tipo utilizzando classi .NET Framework anziché l'XML Schema.  
  
- Aggiungere solo gli attributi <xref:System.SerializableAttribute> e <xref:System.Xml.Serialization.XmlRootAttribute> alla classe, utilizzando quest'ultimo per definire in modo esplicito lo spazio dei nomi del tipo. Evitare di aggiungere attributi aggiuntivi dello spazio dei nomi <xref:System.Xml.Serialization> per controllare la modalità di conversione della classe .NET Framework in XML.  
  
- Tramite questo approccio è possibile convertire successivamente le classi .NET in contratti di dati aggiungendo gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> senza modificare in modo significativo il codice XML nel quale le classi vengono serializzate per la trasmissione. I tipi utilizzati nei messaggi dai servizi Web ASP.NET possono essere elaborati come contratti dati dalle applicazioni WCF, producendo, tra gli altri vantaggi, prestazioni migliori nelle applicazioni WCF.  
  
 Evitare di utilizzare le opzioni di autenticazione fornite in Internet Information Services (IIS), I client WCF non li supportano. Se un servizio deve essere protetto, usare le opzioni fornite da WCF, poiché queste opzioni sono affidabili e sono basate su protocolli standard.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>Impatto sulle prestazioni causato dal caricamento di ServiceModel HttpModule  
 In .NET Framework 3.0, WCF `HttpModule` è stato installato nel file Web.config di primo livello in modo tale che qualsiasi applicazione ASP.NET supporti WCF. Ciò può avere effetti negativi sulle prestazioni, pertanto è possibile eliminare `ServiceModel` per il file Web.config come illustrato nell'esempio seguente.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
</httpModules>
```  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: configurare un servizio WCF che interagisca con client di servizi Web ASP.NET](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
