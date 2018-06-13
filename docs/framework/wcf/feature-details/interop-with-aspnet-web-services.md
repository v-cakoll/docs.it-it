---
title: Interoperabilità con i servizi Web ASP.NET
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: 8a0737a36989dd8bc6f5d5670555c7b2218798bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33494296"
---
# <a name="interoperability-with-aspnet-web-services"></a><span data-ttu-id="afa0c-102">Interoperabilità con i servizi Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="afa0c-102">Interoperability with ASP.NET Web Services</span></span>
<span data-ttu-id="afa0c-103">Interoperabilità tra [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] servizi Web e servizi Web di Windows Communication Foundation (WCF) possono essere ottenuti, garantendo che i servizi implementati utilizzando entrambe le tecnologie siano conformi a WS-I Basic Profile 1.1 specifica.</span><span class="sxs-lookup"><span data-stu-id="afa0c-103">Interoperability between [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services and Windows Communication Foundation (WCF) Web services can be achieved by ensuring that services implemented using both technologies conform to the WS-I Basic Profile 1.1 specification.</span></span> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="afa0c-104"> Servizi Web che è conforme a WS-I Basic Profile 1.1 sono interoperativi con i client WCF utilizzando l'associazione fornita dal sistema WCF, <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="afa0c-104"> Web services that conform to WS-I Basic Profile 1.1 are interoperable with WCF clients by using WCF system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
 <span data-ttu-id="afa0c-105">Utilizzare l'opzione di [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] che consente di aggiungere gli attributi <xref:System.Web.Services.WebService> e <xref:System.Web.Services.WebMethodAttribute> a un'interfaccia anziché a una classe e di scrivere una classe per implementare l'interfaccia, come mostrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="afa0c-105">Use [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] option of adding the <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> attributes to an interface rather than to a class, and writing a class to implement the interface, as shown in the following sample code.</span></span>  
  
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
  
 <span data-ttu-id="afa0c-106">È preferibile utilizzare questa opzione. Infatti, l'interfaccia avente l'attributo <xref:System.Web.Services.WebService> costituisce un contratto per le operazioni eseguite dal servizio che può essere riutilizzato con varie classi in grado di implementare tale contratto in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="afa0c-106">Using this option is preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>  
  
 <span data-ttu-id="afa0c-107">Evitare di utilizzare l'attributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> per instradare i messaggi a metodi basati sul nome completo dell'elemento del corpo del messaggio SOAP anziché sull'intestazione HTTP `SOAPAction`.</span><span class="sxs-lookup"><span data-stu-id="afa0c-107">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the `SOAPAction` HTTP header.</span></span> <span data-ttu-id="afa0c-108">WCF Usa il `SOAPAction` intestazione HTTP per il routing dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="afa0c-108">WCF uses the `SOAPAction` HTTP header for routing messages.</span></span>  
  
 <span data-ttu-id="afa0c-109">Il codice XML in cui l'oggetto <xref:System.Xml.Serialization.XmlSerializer> serializza un tipo è per impostazione predefinita semanticamente identico al codice XML in cui l'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> serializza un tipo, purché lo spazio dei nomi del codice XML sia stato definito in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="afa0c-109">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="afa0c-110">Quando si definisce un tipo di dati per l'utilizzo con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Web services perché si prevede di utilizzare WCF, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="afa0c-110">When defining a data type for use with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Web services in anticipation of adopting WCF, do the following:</span></span>  
  
-   <span data-ttu-id="afa0c-111">Definire il tipo utilizzando classi .NET Framework anziché l'XML Schema.</span><span class="sxs-lookup"><span data-stu-id="afa0c-111">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
-   <span data-ttu-id="afa0c-112">Aggiungere solo gli attributi <xref:System.SerializableAttribute> e <xref:System.Xml.Serialization.XmlRootAttribute> alla classe, utilizzando quest'ultimo per definire in modo esplicito lo spazio dei nomi del tipo.</span><span class="sxs-lookup"><span data-stu-id="afa0c-112">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="afa0c-113">Evitare di aggiungere attributi aggiuntivi dello spazio dei nomi <xref:System.Xml.Serialization> per controllare la modalità di conversione della classe .NET Framework in XML.</span><span class="sxs-lookup"><span data-stu-id="afa0c-113">Do not add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
-   <span data-ttu-id="afa0c-114">Tramite questo approccio è possibile convertire successivamente le classi .NET in contratti di dati aggiungendo gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> senza modificare in modo significativo il codice XML nel quale le classi vengono serializzate per la trasmissione.</span><span class="sxs-lookup"><span data-stu-id="afa0c-114">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="afa0c-115">I tipi utilizzati nei messaggi dai [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] servizi Web possono essere elaborati come contratti di dati dalle applicazioni di WCF, cede il controllo, tra gli altri vantaggi, prestazioni migliori nelle applicazioni WCF.</span><span class="sxs-lookup"><span data-stu-id="afa0c-115">The types used in messages by [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services can be processed as data contracts by WCF applications, yielding, among other benefits, better performance in WCF applications.</span></span>  
  
 <span data-ttu-id="afa0c-116">Evitare di utilizzare le opzioni di autenticazione fornite in Internet Information Services (IIS),</span><span class="sxs-lookup"><span data-stu-id="afa0c-116">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="afa0c-117">I client WCF non le supportano.</span><span class="sxs-lookup"><span data-stu-id="afa0c-117">WCF clients do not support them.</span></span> <span data-ttu-id="afa0c-118">Se un servizio deve essere protetto, utilizzare le opzioni fornite da WCF, perché queste opzioni sono affidabili e sono basate su protocolli standard.</span><span class="sxs-lookup"><span data-stu-id="afa0c-118">If a service must be secured, use the options provided by WCF, because these options are robust and are based on standard protocols.</span></span>  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a><span data-ttu-id="afa0c-119">Impatto sulle prestazioni causato dal caricamento di ServiceModel HttpModule</span><span class="sxs-lookup"><span data-stu-id="afa0c-119">Performance impact caused by loading the ServiceModel HttpModule</span></span>  
 <span data-ttu-id="afa0c-120">In .NET Framework 3.0, WCF `HttpModule` è stato installato nel file Web.config di primo livello in modo tale che qualsiasi applicazione ASP.NET supporti WCF.</span><span class="sxs-lookup"><span data-stu-id="afa0c-120">In the .NET Framework 3.0, the WCF `HttpModule` was installed in the root Web.config file such that every ASP.NET application was WCF enabled.</span></span> <span data-ttu-id="afa0c-121">Ciò può avere effetti negativi sulle prestazioni, pertanto è possibile eliminare `ServiceModel` per il file Web.config come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="afa0c-121">This might affect performance, so you can remove `ServiceModel` for the Web.config file as shown in the following example.</span></span>  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="afa0c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afa0c-122">See Also</span></span>  
 [<span data-ttu-id="afa0c-123">Procedura: Configurare un servizio WCF per l'interoperabilità con client di servizi Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="afa0c-123">How to: Configure WCF Service to Interoperate with ASP.NET Web Service Clients</span></span>](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
