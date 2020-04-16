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
# <a name="interoperability-with-aspnet-web-services"></a><span data-ttu-id="262d6-102">Interoperabilità con i servizi Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="262d6-102">Interoperability with ASP.NET Web Services</span></span>
<span data-ttu-id="262d6-103">L'interoperabilità tra i servizi Web ASP.NET e i servizi Web Windows Communication Foundation (WCF) può essere ottenuta assicurando che i servizi implementati utilizzando entrambe le tecnologie siano conformi alla specifica WS-I Basic Profile 1.1.</span><span class="sxs-lookup"><span data-stu-id="262d6-103">Interoperability between ASP.NET Web services and Windows Communication Foundation (WCF) Web services can be achieved by ensuring that services implemented using both technologies conform to the WS-I Basic Profile 1.1 specification.</span></span> <span data-ttu-id="262d6-104">ASP.NET servizi Web conformi a WS-I Basic Profile 1.1 sono interoperabili con i <xref:System.ServiceModel.BasicHttpBinding>client WCF utilizzando l'associazione fornita dal sistema WCF, .</span><span class="sxs-lookup"><span data-stu-id="262d6-104">ASP.NET Web services that conform to WS-I Basic Profile 1.1 are interoperable with WCF clients by using WCF system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
 <span data-ttu-id="262d6-105">Utilizzare ASP.NET 2.0 opzione <xref:System.Web.Services.WebService> <xref:System.Web.Services.WebMethodAttribute> di aggiunta degli attributi e a un'interfaccia anziché a una classe e di scrivere una classe per implementare l'interfaccia, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="262d6-105">Use ASP.NET 2.0 option of adding the <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> attributes to an interface rather than to a class, and writing a class to implement the interface, as shown in the following sample code.</span></span>  
  
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
  
 <span data-ttu-id="262d6-106">È preferibile utilizzare questa opzione. Infatti, l'interfaccia avente l'attributo <xref:System.Web.Services.WebService> costituisce un contratto per le operazioni eseguite dal servizio che può essere riutilizzato con varie classi in grado di implementare tale contratto in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="262d6-106">Using this option is preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>  
  
 <span data-ttu-id="262d6-107">Evitare di utilizzare l'attributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> per instradare i messaggi a metodi basati sul nome completo dell'elemento del corpo del messaggio SOAP anziché sull'intestazione HTTP `SOAPAction`.</span><span class="sxs-lookup"><span data-stu-id="262d6-107">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the `SOAPAction` HTTP header.</span></span> <span data-ttu-id="262d6-108">WCF utilizza `SOAPAction` l'intestazione HTTP per il routing dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="262d6-108">WCF uses the `SOAPAction` HTTP header for routing messages.</span></span>  
  
 <span data-ttu-id="262d6-109">Il codice XML in cui l'oggetto <xref:System.Xml.Serialization.XmlSerializer> serializza un tipo è per impostazione predefinita semanticamente identico al codice XML in cui l'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> serializza un tipo, purché lo spazio dei nomi del codice XML sia stato definito in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="262d6-109">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="262d6-110">Quando si definisce un tipo di dati da utilizzare con i servizi ASP.NETWeb in previsione dell'adozione di WCF, eseguire le operazioni seguenti:When defining a data type for use with ASP.NETWeb services in anticipation of adopting WCF, do the following:</span><span class="sxs-lookup"><span data-stu-id="262d6-110">When defining a data type for use with ASP.NETWeb services in anticipation of adopting WCF, do the following:</span></span>  
  
- <span data-ttu-id="262d6-111">Definire il tipo utilizzando classi .NET Framework anziché l'XML Schema.</span><span class="sxs-lookup"><span data-stu-id="262d6-111">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
- <span data-ttu-id="262d6-112">Aggiungere solo gli attributi <xref:System.SerializableAttribute> e <xref:System.Xml.Serialization.XmlRootAttribute> alla classe, utilizzando quest'ultimo per definire in modo esplicito lo spazio dei nomi del tipo.</span><span class="sxs-lookup"><span data-stu-id="262d6-112">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="262d6-113">Evitare di aggiungere attributi aggiuntivi dello spazio dei nomi <xref:System.Xml.Serialization> per controllare la modalità di conversione della classe .NET Framework in XML.</span><span class="sxs-lookup"><span data-stu-id="262d6-113">Do not add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
- <span data-ttu-id="262d6-114">Tramite questo approccio è possibile convertire successivamente le classi .NET in contratti di dati aggiungendo gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> senza modificare in modo significativo il codice XML nel quale le classi vengono serializzate per la trasmissione.</span><span class="sxs-lookup"><span data-stu-id="262d6-114">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="262d6-115">I tipi utilizzati nei messaggi dai servizi Web ASP.NET possono essere elaborati come contratti dati dalle applicazioni WCF, producendo, tra gli altri vantaggi, prestazioni migliori nelle applicazioni WCF.</span><span class="sxs-lookup"><span data-stu-id="262d6-115">The types used in messages by ASP.NET Web services can be processed as data contracts by WCF applications, yielding, among other benefits, better performance in WCF applications.</span></span>  
  
 <span data-ttu-id="262d6-116">Evitare di utilizzare le opzioni di autenticazione fornite in Internet Information Services (IIS),</span><span class="sxs-lookup"><span data-stu-id="262d6-116">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="262d6-117">I client WCF non li supportano.</span><span class="sxs-lookup"><span data-stu-id="262d6-117">WCF clients do not support them.</span></span> <span data-ttu-id="262d6-118">Se un servizio deve essere protetto, usare le opzioni fornite da WCF, poiché queste opzioni sono affidabili e sono basate su protocolli standard.</span><span class="sxs-lookup"><span data-stu-id="262d6-118">If a service must be secured, use the options provided by WCF, because these options are robust and are based on standard protocols.</span></span>  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a><span data-ttu-id="262d6-119">Impatto sulle prestazioni causato dal caricamento di ServiceModel HttpModule</span><span class="sxs-lookup"><span data-stu-id="262d6-119">Performance impact caused by loading the ServiceModel HttpModule</span></span>  
 <span data-ttu-id="262d6-120">In .NET Framework 3.0, WCF `HttpModule` è stato installato nel file Web.config di primo livello in modo tale che qualsiasi applicazione ASP.NET supporti WCF.</span><span class="sxs-lookup"><span data-stu-id="262d6-120">In the .NET Framework 3.0, the WCF `HttpModule` was installed in the root Web.config file such that every ASP.NET application was WCF enabled.</span></span> <span data-ttu-id="262d6-121">Ciò può avere effetti negativi sulle prestazioni, pertanto è possibile eliminare `ServiceModel` per il file Web.config come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="262d6-121">This might affect performance, so you can remove `ServiceModel` for the Web.config file as shown in the following example.</span></span>  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
</httpModules>
```  
  
## <a name="see-also"></a><span data-ttu-id="262d6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="262d6-122">See also</span></span>

- [<span data-ttu-id="262d6-123">Procedura: configurare un servizio WCF che interagisca con client di servizi Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="262d6-123">How to: Configure WCF Service to Interoperate with ASP.NET Web Service Clients</span></span>](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
