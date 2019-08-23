---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: e2fec2c2e5979b08ed0d832f636b3d0847b9a5dc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915652"
---
# <a name="textmessageencoding"></a><span data-ttu-id="346d8-101">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="346d8-101">\<textMessageEncoding></span></span>
<span data-ttu-id="346d8-102">Specifica le impostazioni di codifica e controllo di versione dei messaggi XML basati sul testo.</span><span class="sxs-lookup"><span data-stu-id="346d8-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="346d8-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="346d8-103">\<system.serviceModel></span></span>  
<span data-ttu-id="346d8-104">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="346d8-104">\<bindings></span></span>  
<span data-ttu-id="346d8-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="346d8-105">\<customBinding></span></span>  
<span data-ttu-id="346d8-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="346d8-106">\<binding></span></span>  
<span data-ttu-id="346d8-107">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="346d8-107">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="346d8-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="346d8-108">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="346d8-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="346d8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="346d8-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="346d8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="346d8-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="346d8-111">Attributes</span></span>  
  
|<span data-ttu-id="346d8-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="346d8-112">Attribute</span></span>|<span data-ttu-id="346d8-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="346d8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="346d8-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="346d8-114">maxReadPoolSize</span></span>|<span data-ttu-id="346d8-115">Numero intero che specifica il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi reader.</span><span class="sxs-lookup"><span data-stu-id="346d8-115">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="346d8-116">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="346d8-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="346d8-117">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="346d8-117">The default is 64.</span></span>|  
|<span data-ttu-id="346d8-118">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="346d8-118">maxWritePoolSize</span></span>|<span data-ttu-id="346d8-119">Numero intero che specifica il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="346d8-119">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="346d8-120">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="346d8-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="346d8-121">Il valore predefinito è 16.</span><span class="sxs-lookup"><span data-stu-id="346d8-121">The default is 16.</span></span>|  
|<span data-ttu-id="346d8-122">messageVersion</span><span class="sxs-lookup"><span data-stu-id="346d8-122">messageVersion</span></span>|<span data-ttu-id="346d8-123">Specifica la versione SOAP dei messaggi inviati usando l'associazione.</span><span class="sxs-lookup"><span data-stu-id="346d8-123">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="346d8-124">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="346d8-124">Valid values are</span></span><br /><br /> <span data-ttu-id="346d8-125">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="346d8-125">-   Soap11Addressing10</span></span><br /><span data-ttu-id="346d8-126">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="346d8-126">-   Soap12Addressing10</span></span><br /><span data-ttu-id="346d8-127">-Soap11</span><span class="sxs-lookup"><span data-stu-id="346d8-127">-   Soap11</span></span><br /><span data-ttu-id="346d8-128">-Soap12</span><span class="sxs-lookup"><span data-stu-id="346d8-128">-  Soap12</span></span><br /><br /><span data-ttu-id="346d8-129">L'impostazione predefinita è Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="346d8-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="346d8-130">L'attributo è di tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="346d8-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="346d8-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="346d8-131">writeEncoding</span></span>|<span data-ttu-id="346d8-132">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="346d8-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="346d8-133">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="346d8-133">Valid values are</span></span><br /><br /> <span data-ttu-id="346d8-134">UnicodeFffeTextEncoding Codifica Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="346d8-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="346d8-135">Utf16TextEncoding Codifica Unicode</span><span class="sxs-lookup"><span data-stu-id="346d8-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="346d8-136">Utf8TextEncoding codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="346d8-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="346d8-137">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="346d8-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="346d8-138">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="346d8-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="346d8-139">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="346d8-139">Child Elements</span></span>  
  
|<span data-ttu-id="346d8-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="346d8-140">Element</span></span>|<span data-ttu-id="346d8-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="346d8-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="346d8-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="346d8-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="346d8-143">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="346d8-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="346d8-144">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="346d8-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="346d8-145">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="346d8-145">Parent Elements</span></span>  
  
|<span data-ttu-id="346d8-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="346d8-146">Element</span></span>|<span data-ttu-id="346d8-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="346d8-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="346d8-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="346d8-148">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="346d8-149">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="346d8-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="346d8-150">Note</span><span class="sxs-lookup"><span data-stu-id="346d8-150">Remarks</span></span>  
 <span data-ttu-id="346d8-151">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="346d8-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="346d8-152">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="346d8-152">Decoding is the reverse process.</span></span> <span data-ttu-id="346d8-153">Windows Communication Foundation (WCF) include tre tipi di codifica per i messaggi SOAP: Testo, binario e MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="346d8-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="346d8-154">La codifica di testo rappresentata dall'elemento `textMessageEncoding` è la più interoperativa, ma la meno efficiente per i messaggi XML.</span><span class="sxs-lookup"><span data-stu-id="346d8-154">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="346d8-155">Il codificatore di testo crea messaggi in transito basati su testo.</span><span class="sxs-lookup"><span data-stu-id="346d8-155">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="346d8-156">I messaggi prodotti da questo codificatore sono adatti per l'interoperabilità basata su WS-\*.</span><span class="sxs-lookup"><span data-stu-id="346d8-156">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="346d8-157">In genere il servizio Web o il client di tale servizio è in grado di comprendere codice XML in formato testo.</span><span class="sxs-lookup"><span data-stu-id="346d8-157">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="346d8-158">Tuttavia, la trasmissione di grandi blocchi di dati binari come testo è il metodo meno efficiente per la codifica di messaggi XML.</span><span class="sxs-lookup"><span data-stu-id="346d8-158">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="346d8-159">Esempio</span><span class="sxs-lookup"><span data-stu-id="346d8-159">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="346d8-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="346d8-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="346d8-161">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="346d8-161">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="346d8-162">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="346d8-162">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="346d8-163">Associazioni</span><span class="sxs-lookup"><span data-stu-id="346d8-163">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="346d8-164">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="346d8-164">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="346d8-165">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="346d8-165">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="346d8-166">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="346d8-166">\<customBinding></span></span>](custombinding.md)
