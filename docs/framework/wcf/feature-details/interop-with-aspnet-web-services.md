---
title: Interoperabilità con i servizi Web ASP.NET
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: c6fec1d520cd251473d8840b7b1afe879002a04c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108576"
---
# <a name="interoperability-with-aspnet-web-services"></a>Interoperabilità con i servizi Web ASP.NET
Interoperabilità tra [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] servizi Web e servizi Web Windows Communication Foundation (WCF) possono essere ottenuti assicurando che i servizi implementati usando entrambe le tecnologie siano conformi a WS-I Basic Profile 1.1 specifica. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Servizi Web che è conforme a WS-I Basic Profile 1.1 sono interoperativi con i client WCF usando l'associazione fornita dal sistema WCF, <xref:System.ServiceModel.BasicHttpBinding>.  
  
 Utilizzare l'opzione di [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] che consente di aggiungere gli attributi <xref:System.Web.Services.WebService> e <xref:System.Web.Services.WebMethodAttribute> a un'interfaccia anziché a una classe e di scrivere una classe per implementare l'interfaccia, come mostrato nell'esempio di codice seguente.  
  
```  
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
  
 Evitare di utilizzare l'attributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> per instradare i messaggi a metodi basati sul nome completo dell'elemento del corpo del messaggio SOAP anziché sull'intestazione HTTP `SOAPAction`. WCF utilizza il `SOAPAction` intestazione HTTP per il routing dei messaggi.  
  
 Il codice XML in cui l'oggetto <xref:System.Xml.Serialization.XmlSerializer> serializza un tipo è per impostazione predefinita semanticamente identico al codice XML in cui l'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> serializza un tipo, purché lo spazio dei nomi del codice XML sia stato definito in modo esplicito. Quando si definisce un tipo di dati per l'uso con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]servizi Web di prevede di utilizzare WCF, eseguire le operazioni seguenti:  
  
-   Definire il tipo utilizzando classi .NET Framework anziché l'XML Schema.  
  
-   Aggiungere solo gli attributi <xref:System.SerializableAttribute> e <xref:System.Xml.Serialization.XmlRootAttribute> alla classe, utilizzando quest'ultimo per definire in modo esplicito lo spazio dei nomi del tipo. Evitare di aggiungere attributi aggiuntivi dello spazio dei nomi <xref:System.Xml.Serialization> per controllare la modalità di conversione della classe .NET Framework in XML.  
  
-   Tramite questo approccio è possibile convertire successivamente le classi .NET in contratti di dati aggiungendo gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> senza modificare in modo significativo il codice XML nel quale le classi vengono serializzate per la trasmissione. I tipi utilizzati nei messaggi dai [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] servizi Web possono essere elaborati come contratti dati da applicazioni di WCF, cede il controllo, tra gli altri vantaggi, prestazioni migliori in applicazioni WCF.  
  
 Evitare di utilizzare le opzioni di autenticazione fornite in Internet Information Services (IIS), I client WCF non li supportano. Se è necessario proteggere un servizio, usare le opzioni fornite da WCF, perché queste opzioni sono affidabili e sono basate su protocolli standard.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>Impatto sulle prestazioni causato dal caricamento di ServiceModel HttpModule  
 In .NET Framework 3.0, WCF `HttpModule` è stato installato nel file Web.config di primo livello in modo tale che qualsiasi applicazione ASP.NET supporti WCF. Ciò può avere effetti negativi sulle prestazioni, pertanto è possibile eliminare `ServiceModel` per il file Web.config come illustrato nell'esempio seguente.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Configurare un servizio WCF per interagire con i client del servizio Web ASP.NET](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
