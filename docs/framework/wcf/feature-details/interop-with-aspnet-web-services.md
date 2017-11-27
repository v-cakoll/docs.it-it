---
title: "Interoperabilità con i servizi Web ASP.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 933d1bdac8f6e3a9e2bec5278fe398696131678a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="interoperability-with-aspnet-web-services"></a><span data-ttu-id="e1ddf-102">Interoperabilità con i servizi Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e1ddf-102">Interoperability with ASP.NET Web Services</span></span>
<span data-ttu-id="e1ddf-103">Per garantire l'interoperabilità tra i servizi Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] e i servizi Web [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] è possibile implementare i servizi che utilizzano entrambe le tecnologie in modo che siano conformi alla specifica WS-I Basic Profile 1.1.</span><span class="sxs-lookup"><span data-stu-id="e1ddf-103">Interoperability between [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services and [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web services can be achieved by ensuring that services implemented using both technologies conform to the WS-I Basic Profile 1.1 specification.</span></span> <span data-ttu-id="e1ddf-104">Per garantire l'interoperabilità fra i servizi Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] conformi alla specifica WS-I Basic Profile 1.1 e i client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è possibile utilizzare un'associazione di sistema fornita da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], ovvero <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="e1ddf-104">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services that conform to WS-I Basic Profile 1.1 are interoperable with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients by using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
 <span data-ttu-id="e1ddf-105">Utilizzare l'opzione di [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] che consente di aggiungere gli attributi <xref:System.Web.Services.WebService> e <xref:System.Web.Services.WebMethodAttribute> a un'interfaccia anziché a una classe e di scrivere una classe per implementare l'interfaccia, come mostrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e1ddf-105">Use [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] option of adding the <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> attributes to an interface rather than to a class, and writing a class to implement the interface, as shown in the following sample code.</span></span>  
  
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
  
 <span data-ttu-id="e1ddf-106">È preferibile utilizzare questa opzione. Infatti, l'interfaccia avente l'attributo <xref:System.Web.Services.WebService> costituisce un contratto per le operazioni eseguite dal servizio che può essere riutilizzato con varie classi in grado di implementare tale contratto in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="e1ddf-106">Using this option is preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>  
  
 <span data-ttu-id="e1ddf-107">Evitare di utilizzare l'attributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> per instradare i messaggi a metodi basati sul nome completo dell'elemento del corpo del messaggio SOAP anziché sull'intestazione HTTP `SOAPAction`.</span><span class="sxs-lookup"><span data-stu-id="e1ddf-107">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the `SOAPAction` HTTP header.</span></span> <span data-ttu-id="e1ddf-108">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] viene utilizzata l'intestazione HTTP `SOAPAction` per instradare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="e1ddf-108">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses the `SOAPAction` HTTP header for routing messages.</span></span>  
  
 <span data-ttu-id="e1ddf-109">Il codice XML in cui l'oggetto <xref:System.Xml.Serialization.XmlSerializer> serializza un tipo è per impostazione predefinita semanticamente identico al codice XML in cui l'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> serializza un tipo, purché lo spazio dei nomi del codice XML sia stato definito in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="e1ddf-109">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="e1ddf-110">Quando si definisce un tipo di dati per l'utilizzo con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]in previsione di adozione di servizi Web [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1ddf-110">When defining a data type for use with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Web services in anticipation of adopting [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], do the following:</span></span>  
  
-   <span data-ttu-id="e1ddf-111">Definire il tipo utilizzando classi .NET Framework anziché l'XML Schema.</span><span class="sxs-lookup"><span data-stu-id="e1ddf-111">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
-   <span data-ttu-id="e1ddf-112">Aggiungere solo gli attributi <xref:System.SerializableAttribute> e <xref:System.Xml.Serialization.XmlRootAttribute> alla classe, utilizzando quest'ultimo per definire in modo esplicito lo spazio dei nomi del tipo.</span><span class="sxs-lookup"><span data-stu-id="e1ddf-112">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="e1ddf-113">Evitare di aggiungere attributi aggiuntivi dello spazio dei nomi <xref:System.Xml.Serialization> per controllare la modalità di conversione della classe .NET Framework in XML.</span><span class="sxs-lookup"><span data-stu-id="e1ddf-113">Do not add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
-   <span data-ttu-id="e1ddf-114">Tramite questo approccio è possibile convertire successivamente le classi .NET in contratti di dati aggiungendo gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> senza modificare in modo significativo il codice XML nel quale le classi vengono serializzate per la trasmissione.</span><span class="sxs-lookup"><span data-stu-id="e1ddf-114">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="e1ddf-115">I tipi utilizzati nei messaggi dai servizi Web [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] possono essere elaborati come contratti di dati dalle applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Ciò offre diversi vantaggi, fra cui il miglioramento delle prestazioni delle applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1ddf-115">The types used in messages by [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services can be processed as data contracts by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications, yielding, among other benefits, better performance in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
 <span data-ttu-id="e1ddf-116">Evitare di utilizzare le opzioni di autenticazione fornite in Internet Information Services (IIS),</span><span class="sxs-lookup"><span data-stu-id="e1ddf-116">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="e1ddf-117">poiché i client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non le supportano.</span><span class="sxs-lookup"><span data-stu-id="e1ddf-117">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients do not support them.</span></span> <span data-ttu-id="e1ddf-118">Se occorre proteggere un servizio, utilizzare le opzioni fornite in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Queste opzioni sono infatti affidabili e sono basate su protocolli standard.</span><span class="sxs-lookup"><span data-stu-id="e1ddf-118">If a service must be secured, use the options provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], because these options are robust and are based on standard protocols.</span></span>  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a><span data-ttu-id="e1ddf-119">Impatto sulle prestazioni causato dal caricamento di ServiceModel HttpModule</span><span class="sxs-lookup"><span data-stu-id="e1ddf-119">Performance impact caused by loading the ServiceModel HttpModule</span></span>  
 <span data-ttu-id="e1ddf-120">In .NET Framework 3.0, WCF `HttpModule` è stato installato nel file Web.config di primo livello in modo tale che qualsiasi applicazione ASP.NET supporti WCF.</span><span class="sxs-lookup"><span data-stu-id="e1ddf-120">In the .NET Framework 3.0, the WCF `HttpModule` was installed in the root Web.config file such that every ASP.NET application was WCF enabled.</span></span> <span data-ttu-id="e1ddf-121">Ciò può avere effetti negativi sulle prestazioni, pertanto è possibile eliminare `ServiceModel` per il file Web.config come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e1ddf-121">This might affect performance, so you can remove `ServiceModel` for the Web.config file as shown in the following example.</span></span>  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1ddf-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1ddf-122">See Also</span></span>  
 [<span data-ttu-id="e1ddf-123">Procedura: configurare il servizio WCF per interagire con i client del servizio Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e1ddf-123">How to: Configure WCF Service to Interoperate with ASP.NET Web Service Clients</span></span>](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
