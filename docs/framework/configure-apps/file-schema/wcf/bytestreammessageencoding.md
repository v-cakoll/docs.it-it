---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: b11f472c0e33003e50be4b45bb49196c64ecb70d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919725"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="822c4-101">\<byteStreamMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="822c4-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="822c4-102">Specifica la codifica dei messaggi come flusso di byte, con l'opzione che consente di specificare la codifica dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="822c4-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="822c4-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="822c4-103">\<system.serviceModel></span></span>  
<span data-ttu-id="822c4-104">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="822c4-104">\<bindings></span></span>  
<span data-ttu-id="822c4-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="822c4-105">\<customBinding></span></span>  
<span data-ttu-id="822c4-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="822c4-106">\<binding></span></span>  
<span data-ttu-id="822c4-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="822c4-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="822c4-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="822c4-108">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="822c4-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="822c4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="822c4-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="822c4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="822c4-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="822c4-111">Attributes</span></span>  
  
|<span data-ttu-id="822c4-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="822c4-112">Attribute</span></span>|<span data-ttu-id="822c4-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="822c4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="822c4-114">messageVersion</span><span class="sxs-lookup"><span data-stu-id="822c4-114">messageVersion</span></span>|<span data-ttu-id="822c4-115">Specifica la versione SOAP dei messaggi inviati usando l'associazione.</span><span class="sxs-lookup"><span data-stu-id="822c4-115">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="822c4-116">È possibile impostare questa proprietà solo sul valore relativo alla versione del messaggio <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="822c4-116">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="822c4-117">Il codificatore di messaggi del flusso di byte non supporta altre versioni del messaggio.</span><span class="sxs-lookup"><span data-stu-id="822c4-117">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="822c4-118">L'attributo è di tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="822c4-118">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="822c4-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="822c4-119">Child Elements</span></span>  
  
|<span data-ttu-id="822c4-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="822c4-120">Element</span></span>|<span data-ttu-id="822c4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="822c4-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="822c4-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="822c4-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="822c4-123">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="822c4-123">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="822c4-124">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="822c4-124">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="822c4-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="822c4-125">Parent Elements</span></span>  
  
|<span data-ttu-id="822c4-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="822c4-126">Element</span></span>|<span data-ttu-id="822c4-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="822c4-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="822c4-128">\<binding></span><span class="sxs-lookup"><span data-stu-id="822c4-128">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="822c4-129">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="822c4-129">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="822c4-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="822c4-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="822c4-131">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="822c4-131">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="822c4-132">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="822c4-132">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="822c4-133">Associazioni</span><span class="sxs-lookup"><span data-stu-id="822c4-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="822c4-134">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="822c4-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="822c4-135">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="822c4-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="822c4-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="822c4-136">\<customBinding></span></span>](custombinding.md)
