---
title: '&lt;textMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: e684c21c0b1360a9b270214ebe7b3ad00b42657f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43554500"
---
# <a name="lttextmessageencodinggt"></a><span data-ttu-id="c72f0-102">&lt;textMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="c72f0-102">&lt;textMessageEncoding&gt;</span></span>
<span data-ttu-id="c72f0-103">Specifica le impostazioni di codifica e controllo di versione dei messaggi XML basati sul testo.</span><span class="sxs-lookup"><span data-stu-id="c72f0-103">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="c72f0-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c72f0-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c72f0-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="c72f0-105">\<bindings></span></span>  
<span data-ttu-id="c72f0-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c72f0-106">\<customBinding></span></span>  
<span data-ttu-id="c72f0-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="c72f0-107">\<binding></span></span>  
<span data-ttu-id="c72f0-108">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="c72f0-108">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c72f0-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c72f0-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing10/Soap12Addressing10"  
      writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c72f0-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c72f0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c72f0-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c72f0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c72f0-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c72f0-112">Attributes</span></span>  
  
|<span data-ttu-id="c72f0-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="c72f0-113">Attribute</span></span>|<span data-ttu-id="c72f0-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c72f0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c72f0-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="c72f0-115">maxReadPoolSize</span></span>|<span data-ttu-id="c72f0-116">Numero intero che specifica il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi reader.</span><span class="sxs-lookup"><span data-stu-id="c72f0-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="c72f0-117">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="c72f0-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="c72f0-118">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="c72f0-118">The default is 64.</span></span>|  
|<span data-ttu-id="c72f0-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="c72f0-119">maxWritePoolSize</span></span>|<span data-ttu-id="c72f0-120">Numero intero che specifica il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="c72f0-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="c72f0-121">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="c72f0-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="c72f0-122">Il valore predefinito è 16.</span><span class="sxs-lookup"><span data-stu-id="c72f0-122">The default is 16.</span></span>|  
|<span data-ttu-id="c72f0-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="c72f0-123">messageVersion</span></span>|<span data-ttu-id="c72f0-124">Specifica la versione SOAP dei messaggi inviati usando l'associazione.</span><span class="sxs-lookup"><span data-stu-id="c72f0-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="c72f0-125">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="c72f0-125">Valid values are</span></span><br /><br /> <span data-ttu-id="c72f0-126">-Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="c72f0-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="c72f0-127">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="c72f0-127">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="c72f0-128">L'impostazione predefinita è Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="c72f0-128">The default is Soap12Addressing10.</span></span> <span data-ttu-id="c72f0-129">L'attributo è di tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="c72f0-129">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="c72f0-130">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="c72f0-130">writeEncoding</span></span>|<span data-ttu-id="c72f0-131">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="c72f0-131">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="c72f0-132">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="c72f0-132">Valid values are</span></span><br /><br /> <span data-ttu-id="c72f0-133">-UnicodeFffeTextEncoding: Codifica Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="c72f0-133">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="c72f0-134">-Utf16TextEncoding: Codifica Unicode</span><span class="sxs-lookup"><span data-stu-id="c72f0-134">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="c72f0-135">-Utf8TextEncoding: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="c72f0-135">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="c72f0-136">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="c72f0-136">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="c72f0-137">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="c72f0-137">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c72f0-138">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c72f0-138">Child Elements</span></span>  
  
|<span data-ttu-id="c72f0-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="c72f0-139">Element</span></span>|<span data-ttu-id="c72f0-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c72f0-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c72f0-141">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="c72f0-141">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="c72f0-142">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="c72f0-142">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="c72f0-143">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="c72f0-143">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c72f0-144">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c72f0-144">Parent Elements</span></span>  
  
|<span data-ttu-id="c72f0-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="c72f0-145">Element</span></span>|<span data-ttu-id="c72f0-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c72f0-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c72f0-147">\<binding></span><span class="sxs-lookup"><span data-stu-id="c72f0-147">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="c72f0-148">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="c72f0-148">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c72f0-149">Note</span><span class="sxs-lookup"><span data-stu-id="c72f0-149">Remarks</span></span>  
 <span data-ttu-id="c72f0-150">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="c72f0-150">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="c72f0-151">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="c72f0-151">Decoding is the reverse process.</span></span> <span data-ttu-id="c72f0-152">Windows Communication Foundation (WCF) include tre tipi di codifica per i messaggi SOAP, ovvero testo, binaria e MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="c72f0-152">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="c72f0-153">La codifica di testo rappresentata dall'elemento `textMessageEncoding` è la più interoperativa, ma la meno efficiente per i messaggi XML.</span><span class="sxs-lookup"><span data-stu-id="c72f0-153">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="c72f0-154">Il codificatore di testo crea messaggi in transito basati su testo.</span><span class="sxs-lookup"><span data-stu-id="c72f0-154">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="c72f0-155">I messaggi prodotti da questo codificatore sono adatti per l'interoperabilità basata su WS-\*.</span><span class="sxs-lookup"><span data-stu-id="c72f0-155">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="c72f0-156">In genere il servizio Web o il client di tale servizio è in grado di comprendere codice XML in formato testo.</span><span class="sxs-lookup"><span data-stu-id="c72f0-156">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="c72f0-157">Tuttavia, la trasmissione di grandi blocchi di dati binari come testo è il metodo meno efficiente per la codifica di messaggi XML.</span><span class="sxs-lookup"><span data-stu-id="c72f0-157">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c72f0-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="c72f0-158">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"  
    maxWritePoolSize="2132"  
    messageVersion="Soap12Addressing10"  
    textEncoding="utf-8" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="c72f0-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c72f0-159">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
 [<span data-ttu-id="c72f0-160">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="c72f0-160">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="c72f0-161">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="c72f0-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="c72f0-162">Associazioni</span><span class="sxs-lookup"><span data-stu-id="c72f0-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c72f0-163">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="c72f0-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="c72f0-164">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="c72f0-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="c72f0-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c72f0-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
