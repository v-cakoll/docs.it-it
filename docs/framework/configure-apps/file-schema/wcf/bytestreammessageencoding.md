---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: c8dfd6824877d6f9e5b089a538cce35ffe51320b
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674282"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="384fc-101">\<byteStreamMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="384fc-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="384fc-102">Specifica la codifica dei messaggi come flusso di byte, con l'opzione che consente di specificare la codifica dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="384fc-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="384fc-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="384fc-103">\<system.serviceModel></span></span>  
<span data-ttu-id="384fc-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="384fc-104">\<bindings></span></span>  
<span data-ttu-id="384fc-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="384fc-105">\<customBinding></span></span>  
<span data-ttu-id="384fc-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="384fc-106">\<binding></span></span>  
<span data-ttu-id="384fc-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="384fc-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="384fc-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="384fc-108">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="384fc-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="384fc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="384fc-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="384fc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="384fc-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="384fc-111">Attributes</span></span>  
  
|<span data-ttu-id="384fc-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="384fc-112">Attribute</span></span>|<span data-ttu-id="384fc-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="384fc-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="384fc-114">messageVersion</span><span class="sxs-lookup"><span data-stu-id="384fc-114">messageVersion</span></span>|<span data-ttu-id="384fc-115">Specifica la versione SOAP dei messaggi inviati usando l'associazione.</span><span class="sxs-lookup"><span data-stu-id="384fc-115">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="384fc-116">È possibile impostare questa proprietà solo sul valore relativo alla versione del messaggio <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="384fc-116">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="384fc-117">Il codificatore di messaggi del flusso di byte non supporta altre versioni del messaggio.</span><span class="sxs-lookup"><span data-stu-id="384fc-117">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="384fc-118">L'attributo è di tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="384fc-118">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="384fc-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="384fc-119">Child Elements</span></span>  
  
|<span data-ttu-id="384fc-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="384fc-120">Element</span></span>|<span data-ttu-id="384fc-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="384fc-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="384fc-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="384fc-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="384fc-123">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="384fc-123">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="384fc-124">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="384fc-124">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="384fc-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="384fc-125">Parent Elements</span></span>  
  
|<span data-ttu-id="384fc-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="384fc-126">Element</span></span>|<span data-ttu-id="384fc-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="384fc-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="384fc-128">\<binding></span><span class="sxs-lookup"><span data-stu-id="384fc-128">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="384fc-129">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="384fc-129">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="384fc-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="384fc-130">See also</span></span>
- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="384fc-131">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="384fc-131">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="384fc-132">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="384fc-132">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="384fc-133">Associazioni</span><span class="sxs-lookup"><span data-stu-id="384fc-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="384fc-134">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="384fc-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="384fc-135">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="384fc-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="384fc-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="384fc-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
