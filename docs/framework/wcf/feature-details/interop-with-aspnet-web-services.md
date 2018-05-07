---
title: Interoperabilità con i servizi Web ASP.NET
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: 8a0737a36989dd8bc6f5d5670555c7b2218798bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="interoperability-with-aspnet-web-services"></a>Interoperabilità con i servizi Web ASP.NET
Interoperabilità tra [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] servizi Web e servizi Web di Windows Communication Foundation (WCF) possono essere ottenuti, garantendo che i servizi implementati utilizzando entrambe le tecnologie siano conformi a WS-I Basic Profile 1.1 specifica. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Servizi Web che è conforme a WS-I Basic Profile 1.1 sono interoperativi con i client WCF utilizzando l'associazione fornita dal sistema WCF, <xref:System.ServiceModel.BasicHttpBinding>.  
  
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
  
 Evitare di utilizzare l'attributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> per instradare i messaggi a metodi basati sul nome completo dell'elemento del corpo del messaggio SOAP anziché sull'intestazione HTTP `SOAPAction`. WCF Usa il `SOAPAction` intestazione HTTP per il routing dei messaggi.  
  
 Il codice XML in cui l'oggetto <xref:System.Xml.Serialization.XmlSerializer> serializza un tipo è per impostazione predefinita semanticamente identico al codice XML in cui l'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> serializza un tipo, purché lo spazio dei nomi del codice XML sia stato definito in modo esplicito. Quando si definisce un tipo di dati per l'utilizzo con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Web services perché si prevede di utilizzare WCF, eseguire le operazioni seguenti:  
  
-   Definire il tipo utilizzando classi .NET Framework anziché l'XML Schema.  
  
-   Aggiungere solo gli attributi <xref:System.SerializableAttribute> e <xref:System.Xml.Serialization.XmlRootAttribute> alla classe, utilizzando quest'ultimo per definire in modo esplicito lo spazio dei nomi del tipo. Evitare di aggiungere attributi aggiuntivi dello spazio dei nomi <xref:System.Xml.Serialization> per controllare la modalità di conversione della classe .NET Framework in XML.  
  
-   Tramite questo approccio è possibile convertire successivamente le classi .NET in contratti di dati aggiungendo gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> senza modificare in modo significativo il codice XML nel quale le classi vengono serializzate per la trasmissione. I tipi utilizzati nei messaggi dai [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] servizi Web possono essere elaborati come contratti di dati dalle applicazioni di WCF, cede il controllo, tra gli altri vantaggi, prestazioni migliori nelle applicazioni WCF.  
  
 Evitare di utilizzare le opzioni di autenticazione fornite in Internet Information Services (IIS), I client WCF non le supportano. Se un servizio deve essere protetto, utilizzare le opzioni fornite da WCF, perché queste opzioni sono affidabili e sono basate su protocolli standard.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>Impatto sulle prestazioni causato dal caricamento di ServiceModel HttpModule  
 In .NET Framework 3.0, WCF `HttpModule` è stato installato nel file Web.config di primo livello in modo tale che qualsiasi applicazione ASP.NET supporti WCF. Ciò può avere effetti negativi sulle prestazioni, pertanto è possibile eliminare `ServiceModel` per il file Web.config come illustrato nell'esempio seguente.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Configurare un servizio WCF per l'interoperabilità con client di servizi Web ASP.NET](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
