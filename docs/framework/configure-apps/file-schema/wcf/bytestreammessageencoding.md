---
title: '&lt;byteStreamMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1788300407ad84a5ff7e3929eaa728f5399961ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltbytestreammessageencodinggt"></a><span data-ttu-id="d81f3-102">&lt;byteStreamMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="d81f3-102">&lt;byteStreamMessageEncoding&gt;</span></span>
<span data-ttu-id="d81f3-103">Specifica la codifica dei messaggi come flusso di byte, con l'opzione che consente di specificare la codifica dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="d81f3-103">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="d81f3-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d81f3-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d81f3-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="d81f3-105">\<bindings></span></span>  
<span data-ttu-id="d81f3-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d81f3-106">\<customBinding></span></span>  
<span data-ttu-id="d81f3-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="d81f3-107">\<binding></span></span>  
<span data-ttu-id="d81f3-108">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="d81f3-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d81f3-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d81f3-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d81f3-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d81f3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d81f3-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d81f3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d81f3-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="d81f3-112">Attributes</span></span>  
  
|<span data-ttu-id="d81f3-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="d81f3-113">Attribute</span></span>|<span data-ttu-id="d81f3-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d81f3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d81f3-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="d81f3-115">messageVersion</span></span>|<span data-ttu-id="d81f3-116">Specifica la versione SOAP dei messaggi inviati usando l'associazione.</span><span class="sxs-lookup"><span data-stu-id="d81f3-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="d81f3-117">È possibile impostare questa proprietà solo sul valore relativo alla versione del messaggio <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="d81f3-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="d81f3-118">Il codificatore di messaggi del flusso di byte non supporta altre versioni del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d81f3-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="d81f3-119">L'attributo è di tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="d81f3-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d81f3-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d81f3-120">Child Elements</span></span>  
  
|<span data-ttu-id="d81f3-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d81f3-121">Element</span></span>|<span data-ttu-id="d81f3-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d81f3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d81f3-123">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="d81f3-123">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="d81f3-124">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="d81f3-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d81f3-125">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="d81f3-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d81f3-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d81f3-126">Parent Elements</span></span>  
  
|<span data-ttu-id="d81f3-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="d81f3-127">Element</span></span>|<span data-ttu-id="d81f3-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d81f3-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d81f3-129">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="d81f3-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d81f3-130">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="d81f3-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d81f3-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d81f3-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>  
 [<span data-ttu-id="d81f3-132">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="d81f3-132">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="d81f3-133">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="d81f3-133">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="d81f3-134">Associazioni</span><span class="sxs-lookup"><span data-stu-id="d81f3-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d81f3-135">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="d81f3-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="d81f3-136">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="d81f3-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="d81f3-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d81f3-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
