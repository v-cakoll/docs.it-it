---
title: '&lt;textMessageEncoding&gt;'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5ac17ead3c7054f0125527e3992fe865624770a9
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2018
---
# <a name="lttextmessageencodinggt"></a><span data-ttu-id="4d218-102">&lt;textMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="4d218-102">&lt;textMessageEncoding&gt;</span></span>
<span data-ttu-id="4d218-103">Specifica le impostazioni di codifica e controllo di versione dei messaggi XML basati sul testo.</span><span class="sxs-lookup"><span data-stu-id="4d218-103">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="4d218-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4d218-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4d218-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="4d218-105">\<bindings></span></span>  
<span data-ttu-id="4d218-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4d218-106">\<customBinding></span></span>  
<span data-ttu-id="4d218-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="4d218-107">\<binding></span></span>  
<span data-ttu-id="4d218-108">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="4d218-108">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d218-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d218-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing10/Soap12Addressing10"  
      writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d218-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4d218-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4d218-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4d218-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d218-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="4d218-112">Attributes</span></span>  
  
|<span data-ttu-id="4d218-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="4d218-113">Attribute</span></span>|<span data-ttu-id="4d218-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d218-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d218-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="4d218-115">maxReadPoolSize</span></span>|<span data-ttu-id="4d218-116">Numero intero che specifica il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi reader.</span><span class="sxs-lookup"><span data-stu-id="4d218-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="4d218-117">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="4d218-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4d218-118">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="4d218-118">The default is 64.</span></span>|  
|<span data-ttu-id="4d218-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="4d218-119">maxWritePoolSize</span></span>|<span data-ttu-id="4d218-120">Numero intero che specifica il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="4d218-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="4d218-121">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="4d218-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4d218-122">Il valore predefinito è 16.</span><span class="sxs-lookup"><span data-stu-id="4d218-122">The default is 16.</span></span>|  
|<span data-ttu-id="4d218-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="4d218-123">messageVersion</span></span>|<span data-ttu-id="4d218-124">Specifica la versione SOAP dei messaggi inviati usando l'associazione.</span><span class="sxs-lookup"><span data-stu-id="4d218-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="4d218-125">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="4d218-125">Valid values are</span></span><br /><br /> <span data-ttu-id="4d218-126">-   Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="4d218-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="4d218-127">-   Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="4d218-127">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="4d218-128">L'impostazione predefinita è Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="4d218-128">The default is Soap12Addressing10.</span></span> <span data-ttu-id="4d218-129">L'attributo è di tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="4d218-129">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="4d218-130">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="4d218-130">writeEncoding</span></span>|<span data-ttu-id="4d218-131">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="4d218-131">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="4d218-132">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="4d218-132">Valid values are</span></span><br /><br /> <span data-ttu-id="4d218-133">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span><span class="sxs-lookup"><span data-stu-id="4d218-133">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="4d218-134">-Utf16TextEncoding: Codifica Unicode</span><span class="sxs-lookup"><span data-stu-id="4d218-134">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="4d218-135">-Utf8TextEncoding: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="4d218-135">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="4d218-136">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="4d218-136">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="4d218-137">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="4d218-137">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d218-138">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4d218-138">Child Elements</span></span>  
  
|<span data-ttu-id="4d218-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d218-139">Element</span></span>|<span data-ttu-id="4d218-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d218-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d218-141">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="4d218-141">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="4d218-142">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="4d218-142">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="4d218-143">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="4d218-143">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4d218-144">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4d218-144">Parent Elements</span></span>  
  
|<span data-ttu-id="4d218-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d218-145">Element</span></span>|<span data-ttu-id="4d218-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d218-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d218-147">\<binding></span><span class="sxs-lookup"><span data-stu-id="4d218-147">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="4d218-148">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4d218-148">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d218-149">Note</span><span class="sxs-lookup"><span data-stu-id="4d218-149">Remarks</span></span>  
 <span data-ttu-id="4d218-150">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="4d218-150">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="4d218-151">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="4d218-151">Decoding is the reverse process.</span></span> <span data-ttu-id="4d218-152">Windows Communication Foundation (WCF) include tre tipi di codifica per i messaggi SOAP, ovvero testo, binaria e MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="4d218-152">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="4d218-153">La codifica di testo rappresentata dall'elemento `textMessageEncoding` è la più interoperativa, ma la meno efficiente per i messaggi XML.</span><span class="sxs-lookup"><span data-stu-id="4d218-153">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="4d218-154">Il codificatore di testo crea messaggi in transito basati su testo.</span><span class="sxs-lookup"><span data-stu-id="4d218-154">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="4d218-155">I messaggi prodotti da questo codificatore sono adatti per l'interoperabilità basata su WS-\*.</span><span class="sxs-lookup"><span data-stu-id="4d218-155">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="4d218-156">In genere il servizio Web o il client di tale servizio è in grado di comprendere codice XML in formato testo.</span><span class="sxs-lookup"><span data-stu-id="4d218-156">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="4d218-157">Tuttavia, la trasmissione di grandi blocchi di dati binari come testo è il metodo meno efficiente per la codifica di messaggi XML.</span><span class="sxs-lookup"><span data-stu-id="4d218-157">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d218-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d218-158">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"  
    maxWritePoolSize="2132"  
    messageVersion="Soap12Addressing10"  
    textEncoding="utf-8" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d218-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d218-159">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
 [<span data-ttu-id="4d218-160">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="4d218-160">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="4d218-161">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="4d218-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="4d218-162">Associazioni</span><span class="sxs-lookup"><span data-stu-id="4d218-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4d218-163">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="4d218-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="4d218-164">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="4d218-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="4d218-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4d218-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
