---
title: 'Preparazione all''adozione di Windows Communication Foundation: facilitare l''integrazione futura'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ccf6e5363da872d3902c12713bd19f5820370428
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a><span data-ttu-id="650f1-102">Preparazione all'adozione di Windows Communication Foundation: facilitare l'integrazione futura</span><span class="sxs-lookup"><span data-stu-id="650f1-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>
<span data-ttu-id="650f1-103">Se si sta utilizzando ASP.NET ma si prevede di passare a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in futuro, in questo argomento vengono fornite indicazioni per assicurare il corretto funzionamento dei nuovi servizi Web ASP.NET con le applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="650f1-103">If you use ASP.NET today, and anticipate using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in the future, this topic provides guidance to ensure that new ASP.NET Web services will work well together with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="general-recommendations"></a><span data-ttu-id="650f1-104">Suggerimenti generali</span><span class="sxs-lookup"><span data-stu-id="650f1-104">General Recommendations</span></span>  
 <span data-ttu-id="650f1-105">Adottare ASP.NET 2.0 per qualsiasi nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="650f1-105">Adopt ASP.NET 2.0 for any new services.</span></span> <span data-ttu-id="650f1-106">In tal modo sarà possibile accedere ai miglioramenti e ai potenziamenti della nuova versione.</span><span class="sxs-lookup"><span data-stu-id="650f1-106">Doing so will provide access to the improvements and enhancements of the new version.</span></span> <span data-ttu-id="650f1-107">Sarà tuttavia possibile anche utilizzare i componenti ASP.NET 2.0 con i componenti [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nella stessa applicazione.</span><span class="sxs-lookup"><span data-stu-id="650f1-107">However, it will also allow for the possibility of using ASP.NET 2.0 components together with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] components in the same application.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="650f1-108">Protocolli</span><span class="sxs-lookup"><span data-stu-id="650f1-108">Protocols</span></span>  
 <span data-ttu-id="650f1-109">Utilizzare la nuova funzionalità di ASP.NET 2.0 per convalidare la conformità a WS-I Basic Profile 1.1:</span><span class="sxs-lookup"><span data-stu-id="650f1-109">Use ASP.NET 2.0’s new facility for validating conformity to the WS-I Basic Profile 1.1:</span></span>  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 <span data-ttu-id="650f1-110">Per garantire l'interoperabilità tra i servizi Web ASP.NET conformi alla specifica WS-I Basic Profile 1.1 e i client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è possibile utilizzare un'associazione predefinita di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], ovvero <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="650f1-110">ASP.NET Web services that conform to WS-I Basic Profile 1.1 will be interoperable with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients by using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] predefined binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="650f1-111">Sviluppo del servizio</span><span class="sxs-lookup"><span data-stu-id="650f1-111">Service Development</span></span>  
 <span data-ttu-id="650f1-112">Evitare di utilizzare l'attributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> per instradare i messaggi a metodi basati sul nome completo dell'elemento del corpo del messaggio SOAP anziché sull'intestazione HTTP SOAPAction.</span><span class="sxs-lookup"><span data-stu-id="650f1-112">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the SOAPAction HTTP header.</span></span> <span data-ttu-id="650f1-113">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] viene utilizzata l'intestazione HTTP SOAPAction per instradare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="650f1-113">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses the SOAPAction HTTP header for routing messages.</span></span>  
  
## <a name="data-representation"></a><span data-ttu-id="650f1-114">Rappresentazione dei dati</span><span class="sxs-lookup"><span data-stu-id="650f1-114">Data Representation</span></span>  
 <span data-ttu-id="650f1-115">Il codice XML in cui l'oggetto <xref:System.Xml.Serialization.XmlSerializer> serializza un tipo è per impostazione predefinita semanticamente identico al codice XML in cui l'oggetto <xref:System.Runtime.Serialization.DataContractSerializer> serializza un tipo, purché lo spazio dei nomi del codice XML sia stato definito in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="650f1-115">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="650f1-116">Quando si definisce un tipo di dati da utilizzare in servizi Web ASP.NET perché si prevede di utilizzare [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in futuro, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="650f1-116">When defining a data type for use with ASP.NET Web services in anticipation of adopting [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in the future, do the following:</span></span>  
  
1.  <span data-ttu-id="650f1-117">Definire il tipo utilizzando classi .NET Framework anziché l'XML Schema.</span><span class="sxs-lookup"><span data-stu-id="650f1-117">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
2.  <span data-ttu-id="650f1-118">Aggiungere solo gli attributi <xref:System.SerializableAttribute> e <xref:System.Xml.Serialization.XmlRootAttribute> alla classe, utilizzando quest'ultimo per definire in modo esplicito lo spazio dei nomi del tipo.</span><span class="sxs-lookup"><span data-stu-id="650f1-118">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="650f1-119">Evitare di aggiungere attributi aggiuntivi dallo spazio dei nomi <xref:System.Xml.Serialization> per controllare la modalità di conversione della classe .NET Framework in XML.</span><span class="sxs-lookup"><span data-stu-id="650f1-119">Do no add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
 <span data-ttu-id="650f1-120">Tramite questo approccio è possibile convertire successivamente le classi .NET in contratti di dati aggiungendo gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> senza modificare in modo significativo il codice XML nel quale le classi vengono serializzate per la trasmissione.</span><span class="sxs-lookup"><span data-stu-id="650f1-120">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="650f1-121">I tipi utilizzati nei messaggi dai servizi Web ASP.NET potranno essere elaborati come contratti di dati dalle applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Ciò offre diversi vantaggi, tra cui il miglioramento delle prestazioni delle applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="650f1-121">The types used in messages by ASP.NET Web services will be able to be processed as data contracts by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications, yielding, amongst other benefits, better performance in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="security"></a><span data-ttu-id="650f1-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="650f1-122">Security</span></span>  
 <span data-ttu-id="650f1-123">Evitare di utilizzare le opzioni di autenticazione fornite in Internet Information Services (IIS),</span><span class="sxs-lookup"><span data-stu-id="650f1-123">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="650f1-124">poiché i client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non le supportano.</span><span class="sxs-lookup"><span data-stu-id="650f1-124">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients do not support them.</span></span> <span data-ttu-id="650f1-125">Se occorre proteggere un servizio, utilizzare le opzioni fornite in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Queste opzioni sono infatti più affidabili e sono basate su protocolli standard.</span><span class="sxs-lookup"><span data-stu-id="650f1-125">If a service needs to be secured, use the options provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], because these options are richer and are based on standard protocols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="650f1-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="650f1-126">See Also</span></span>  
 [<span data-ttu-id="650f1-127">Preparazione all'adozione di Windows Communication Foundation: facilitazione dell'integrazione futura</span><span class="sxs-lookup"><span data-stu-id="650f1-127">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
