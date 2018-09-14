---
title: Associazioni personalizzate
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, endpoints
- Windows Communication Foundation, configuration
ms.assetid: 58532b6d-4eea-4a4f-854f-a1c8c842564d
ms.openlocfilehash: 694b4faaafea62799a96aabe8f023a0d495f8d50
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45507287"
---
# <a name="custom-bindings"></a><span data-ttu-id="746bc-102">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="746bc-102">Custom Bindings</span></span>
<span data-ttu-id="746bc-103">Quando una delle associazioni fornite dal sistema non soddisfa i requisiti del servizio è possibile utilizzare la classe <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="746bc-103">You can use the <xref:System.ServiceModel.Channels.CustomBinding> class when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="746bc-104">Tutte le associazioni sono costruite a partire da un set ordinato di elementi di associazione.</span><span class="sxs-lookup"><span data-stu-id="746bc-104">All bindings are constructed from an ordered set of binding elements.</span></span> <span data-ttu-id="746bc-105">Le associazioni personalizzate possono essere compilate a partire da un set di elementi di associazione forniti dal sistema oppure possono includere elementi di associazione personalizzati definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="746bc-105">Custom bindings can be built from a set of system-provided binding elements or can include user-defined custom binding elements.</span></span> <span data-ttu-id="746bc-106">È ad esempio possibile utilizzare elementi di associazione personalizzati per consentire l'utilizzo di nuovi trasporti o codificatori presso un endpoint di servizio.</span><span class="sxs-lookup"><span data-stu-id="746bc-106">You can use custom binding elements, for example, to enable the use of new transports or encoders at a service endpoint.</span></span> <span data-ttu-id="746bc-107">Per alcuni esempi funzionanti, vedere [esempi di associazione personalizzate](https://msdn.microsoft.com/library/657e8143-beb0-472d-9cfe-ed1a19c2ab08).</span><span class="sxs-lookup"><span data-stu-id="746bc-107">For working examples, see [Custom Binding Samples](https://msdn.microsoft.com/library/657e8143-beb0-472d-9cfe-ed1a19c2ab08).</span></span> <span data-ttu-id="746bc-108">Per altre informazioni, vedere [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="746bc-108">For more information, see [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
## <a name="construction-of-a-custom-binding"></a><span data-ttu-id="746bc-109">Costruzione di un'associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="746bc-109">Construction of a Custom Binding</span></span>  
 <span data-ttu-id="746bc-110">Un'associazione personalizzata viene costruita utilizzando il costruttore <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> a partire da una raccolta di elementi di associazione contenuti in uno stack ordinato nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="746bc-110">A custom binding is constructed using the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> constructor from a collection of binding elements that are "stacked" in a specific order:</span></span>  
  
-   <span data-ttu-id="746bc-111">All'inizio si trova un oggetto <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> facoltativo che consente la propagazione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="746bc-111">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> class that allows flowing transactions.</span></span>  
  
-   <span data-ttu-id="746bc-112">Segue quindi un oggetto <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> facoltativo che oltre a una sessione fornisce meccanismi di ordinamento in conformità a quanto definito nella specifica WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="746bc-112">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> class that provides a session and ordering mechanisms as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="746bc-113">Una sessione può coinvolgere intermediari SOAP e di trasporto.</span><span class="sxs-lookup"><span data-stu-id="746bc-113">A session can cross SOAP and transport intermediaries.</span></span>  
  
-   <span data-ttu-id="746bc-114">Segue quindi un oggetto <xref:System.ServiceModel.Channels.SecurityBindingElement> facoltativo che fornisce alcune funzionalità di sicurezza, fra cui: autorizzazione, autenticazione, protezione e riservatezza.</span><span class="sxs-lookup"><span data-stu-id="746bc-114">Next is an optional <xref:System.ServiceModel.Channels.SecurityBindingElement> class that provides security features such as authorization, authentication, protection, and confidentiality.</span></span>  
  
-   <span data-ttu-id="746bc-115">La successiva è una classe <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> facoltativa che fornisce la possibilità di avere due modalità comunicazione duplex con un protocollo di trasporto che non supporta a livello nativo la comunicazione duplex, ad esempio il protocollo HTTP.</span><span class="sxs-lookup"><span data-stu-id="746bc-115">Next is an optional <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> class that provides the ability to have two way duplex communication with a transport protocol that does not support duplex communication natively, such as HTTP.</span></span>  
  
-   <span data-ttu-id="746bc-116">La successiva è una classe <xref:System.ServiceModel.Channels.OneWayBindingElement> facoltativa che fornisce comunicazione unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="746bc-116">Next is an optional <xref:System.ServiceModel.Channels.OneWayBindingElement>) class that provides one-way communication.</span></span>  
  
-   <span data-ttu-id="746bc-117">Il successivo è un elemento di associazione di sicurezza di flusso facoltativo che può essere uno degli elementi seguenti.</span><span class="sxs-lookup"><span data-stu-id="746bc-117">Next is an optional stream security binding element which can be one of the following.</span></span>  
  
    -   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
-   <span data-ttu-id="746bc-118">Segue quindi un elemento di associazione obbligatorio di codifica dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="746bc-118">Next is a required message encoding binding element.</span></span> <span data-ttu-id="746bc-119">È possibile utilizzare un codificatore di messaggi personalizzato oppure scegliere fra le tre associazioni di codifica dei messaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="746bc-119">You can use your own message encoder or one of the three message encoding bindings:</span></span>  
  
    -   <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>  
  
 <span data-ttu-id="746bc-120">Segue infine un elemento di trasporto obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="746bc-120">At the bottom is a required transport element.</span></span> <span data-ttu-id="746bc-121">È possibile usare un trasporto personalizzato o uno dei seguenti elementi di associazione di trasporto fornisce Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="746bc-121">You can use your own transport or one of the following transport binding elements Windows Communication Foundation (WCF) provides:</span></span>  
  
-   <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.PeerTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>  
  
-   <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>  
  
-   <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>  
  
 <span data-ttu-id="746bc-122">Nella tabella seguente viene fornito un riepilogo delle opzioni per ogni livello.</span><span class="sxs-lookup"><span data-stu-id="746bc-122">The following table summarizes the options for each layer.</span></span>  
  
|<span data-ttu-id="746bc-123">Livello</span><span class="sxs-lookup"><span data-stu-id="746bc-123">Layer</span></span>|<span data-ttu-id="746bc-124">Opzioni</span><span class="sxs-lookup"><span data-stu-id="746bc-124">Options</span></span>|<span data-ttu-id="746bc-125">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="746bc-125">Required</span></span>|  
|-----------|-------------|--------------|  
|<span data-ttu-id="746bc-126">Transazioni</span><span class="sxs-lookup"><span data-stu-id="746bc-126">Transactions</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="746bc-127">No</span><span class="sxs-lookup"><span data-stu-id="746bc-127">No</span></span>|  
|<span data-ttu-id="746bc-128">Affidabilità</span><span class="sxs-lookup"><span data-stu-id="746bc-128">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="746bc-129">No</span><span class="sxs-lookup"><span data-stu-id="746bc-129">No</span></span>|  
|<span data-ttu-id="746bc-130">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="746bc-130">Security</span></span>|<xref:System.ServiceModel.Channels.SecurityBindingElement>|<span data-ttu-id="746bc-131">No</span><span class="sxs-lookup"><span data-stu-id="746bc-131">No</span></span>|  
|<span data-ttu-id="746bc-132">Codifica</span><span class="sxs-lookup"><span data-stu-id="746bc-132">Encoding</span></span>|<span data-ttu-id="746bc-133">Testo, binario, MTOM (Message Transmission Optimization Mechanism, meccanismo di ottimizzazione della trasmissione dei messaggi), personalizzato</span><span class="sxs-lookup"><span data-stu-id="746bc-133">Text, binary, Message Transmission Optimization Mechanism (MTOM), custom</span></span>|<span data-ttu-id="746bc-134">Yes</span><span class="sxs-lookup"><span data-stu-id="746bc-134">Yes</span></span>|  
|<span data-ttu-id="746bc-135">Trasporto</span><span class="sxs-lookup"><span data-stu-id="746bc-135">Transport</span></span>|<span data-ttu-id="746bc-136">TCP, HTTP, HTTPS, pipe con nome (anche noto come IPC), Peer-to-peer (P2P), sistema di accodamento dei messaggi (anche noto come MSMQ), personalizzato</span><span class="sxs-lookup"><span data-stu-id="746bc-136">TCP, HTTP, HTTPS, named pipes (also known as IPC), Peer-to-Peer (P2P), Message Queuing (also known as MSMQ), Custom</span></span>|<span data-ttu-id="746bc-137">Yes</span><span class="sxs-lookup"><span data-stu-id="746bc-137">Yes</span></span>|  
  
 <span data-ttu-id="746bc-138">È inoltre possibile definire elementi di associazione personalizzati e inserirli tra i livelli appena elencati.</span><span class="sxs-lookup"><span data-stu-id="746bc-138">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="746bc-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="746bc-139">See Also</span></span>  
 [<span data-ttu-id="746bc-140">Panoramica della creazione di endpoint</span><span class="sxs-lookup"><span data-stu-id="746bc-140">Endpoint Creation Overview</span></span>](../../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [<span data-ttu-id="746bc-141">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="746bc-141">Using Bindings to Configure Services and Clients</span></span>](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="746bc-142">Associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="746bc-142">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [<span data-ttu-id="746bc-143">Procedura: Personalizzare un'associazione specificata dal sistema</span><span class="sxs-lookup"><span data-stu-id="746bc-143">How to: Customize a System-Provided Binding</span></span>](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)  
 [<span data-ttu-id="746bc-144">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="746bc-144">\<customBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="746bc-145">Associazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="746bc-145">Custom Binding</span></span>](../../../../docs/framework/wcf/samples/custom-binding.md)
