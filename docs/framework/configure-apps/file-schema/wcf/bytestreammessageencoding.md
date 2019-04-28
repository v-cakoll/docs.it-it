---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: ce9f282ea1101befe3bf99762efa61e9b47b74cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673373"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="d17ac-101">\<byteStreamMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="d17ac-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="d17ac-102">Specifica la codifica dei messaggi come flusso di byte, con l'opzione che consente di specificare la codifica dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="d17ac-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="d17ac-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d17ac-103">\<system.serviceModel></span></span>  
<span data-ttu-id="d17ac-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="d17ac-104">\<bindings></span></span>  
<span data-ttu-id="d17ac-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d17ac-105">\<customBinding></span></span>  
<span data-ttu-id="d17ac-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="d17ac-106">\<binding></span></span>  
<span data-ttu-id="d17ac-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="d17ac-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d17ac-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d17ac-108">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d17ac-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d17ac-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d17ac-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d17ac-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d17ac-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="d17ac-111">Attributes</span></span>  
  
|<span data-ttu-id="d17ac-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="d17ac-112">Attribute</span></span>|<span data-ttu-id="d17ac-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d17ac-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d17ac-114">messageVersion</span><span class="sxs-lookup"><span data-stu-id="d17ac-114">messageVersion</span></span>|<span data-ttu-id="d17ac-115">Specifica la versione SOAP dei messaggi inviati usando l'associazione.</span><span class="sxs-lookup"><span data-stu-id="d17ac-115">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="d17ac-116">È possibile impostare questa proprietà solo sul valore relativo alla versione del messaggio <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="d17ac-116">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="d17ac-117">Il codificatore di messaggi del flusso di byte non supporta altre versioni del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d17ac-117">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="d17ac-118">L'attributo è di tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="d17ac-118">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d17ac-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d17ac-119">Child Elements</span></span>  
  
|<span data-ttu-id="d17ac-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="d17ac-120">Element</span></span>|<span data-ttu-id="d17ac-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d17ac-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d17ac-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d17ac-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="d17ac-123">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="d17ac-123">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d17ac-124">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="d17ac-124">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d17ac-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d17ac-125">Parent Elements</span></span>  
  
|<span data-ttu-id="d17ac-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="d17ac-126">Element</span></span>|<span data-ttu-id="d17ac-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d17ac-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d17ac-128">\<binding></span><span class="sxs-lookup"><span data-stu-id="d17ac-128">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d17ac-129">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="d17ac-129">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d17ac-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d17ac-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="d17ac-131">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="d17ac-131">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="d17ac-132">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="d17ac-132">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="d17ac-133">Associazioni</span><span class="sxs-lookup"><span data-stu-id="d17ac-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="d17ac-134">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="d17ac-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d17ac-135">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="d17ac-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d17ac-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d17ac-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
