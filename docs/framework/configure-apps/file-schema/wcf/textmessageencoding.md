---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: c9f8347b4ee5f8fdbcf5c65c9a38b171ea6309de
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289601"
---
# <a name="textmessageencoding"></a><span data-ttu-id="4065b-101">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="4065b-101">\<textMessageEncoding></span></span>
<span data-ttu-id="4065b-102">Specifica le impostazioni di codifica e controllo di versione dei messaggi XML basati sul testo.</span><span class="sxs-lookup"><span data-stu-id="4065b-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="4065b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4065b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="4065b-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="4065b-104">\<bindings></span></span>  
<span data-ttu-id="4065b-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4065b-105">\<customBinding></span></span>  
<span data-ttu-id="4065b-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="4065b-106">\<binding></span></span>  
<span data-ttu-id="4065b-107">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="4065b-107">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4065b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4065b-108">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4065b-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4065b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4065b-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4065b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4065b-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="4065b-111">Attributes</span></span>  
  
|<span data-ttu-id="4065b-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="4065b-112">Attribute</span></span>|<span data-ttu-id="4065b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4065b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4065b-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="4065b-114">maxReadPoolSize</span></span>|<span data-ttu-id="4065b-115">Numero intero che specifica il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi reader.</span><span class="sxs-lookup"><span data-stu-id="4065b-115">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="4065b-116">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="4065b-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4065b-117">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="4065b-117">The default is 64.</span></span>|  
|<span data-ttu-id="4065b-118">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="4065b-118">maxWritePoolSize</span></span>|<span data-ttu-id="4065b-119">Numero intero che specifica il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="4065b-119">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="4065b-120">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="4065b-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4065b-121">Il valore predefinito è 16.</span><span class="sxs-lookup"><span data-stu-id="4065b-121">The default is 16.</span></span>|  
|<span data-ttu-id="4065b-122">messageVersion</span><span class="sxs-lookup"><span data-stu-id="4065b-122">messageVersion</span></span>|<span data-ttu-id="4065b-123">Specifica la versione SOAP dei messaggi inviati usando l'associazione.</span><span class="sxs-lookup"><span data-stu-id="4065b-123">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="4065b-124">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="4065b-124">Valid values are</span></span><br /><br /> <span data-ttu-id="4065b-125">-   Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="4065b-125">-   Soap11Addressing10</span></span><br /><span data-ttu-id="4065b-126">-   Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="4065b-126">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="4065b-127">L'impostazione predefinita è Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="4065b-127">The default is Soap12Addressing10.</span></span> <span data-ttu-id="4065b-128">L'attributo è di tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="4065b-128">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="4065b-129">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="4065b-129">writeEncoding</span></span>|<span data-ttu-id="4065b-130">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="4065b-130">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="4065b-131">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="4065b-131">Valid values are</span></span><br /><br /> <span data-ttu-id="4065b-132">-UnicodeFffeTextEncoding: Codifica Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="4065b-132">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="4065b-133">-   Utf16TextEncoding: Codifica Unicode</span><span class="sxs-lookup"><span data-stu-id="4065b-133">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="4065b-134">-   Utf8TextEncoding: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="4065b-134">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="4065b-135">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="4065b-135">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="4065b-136">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="4065b-136">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4065b-137">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4065b-137">Child Elements</span></span>  
  
|<span data-ttu-id="4065b-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="4065b-138">Element</span></span>|<span data-ttu-id="4065b-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4065b-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4065b-140">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="4065b-140">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="4065b-141">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="4065b-141">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="4065b-142">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="4065b-142">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4065b-143">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4065b-143">Parent Elements</span></span>  
  
|<span data-ttu-id="4065b-144">Elemento</span><span class="sxs-lookup"><span data-stu-id="4065b-144">Element</span></span>|<span data-ttu-id="4065b-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4065b-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4065b-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="4065b-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="4065b-147">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4065b-147">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4065b-148">Note</span><span class="sxs-lookup"><span data-stu-id="4065b-148">Remarks</span></span>  
 <span data-ttu-id="4065b-149">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="4065b-149">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="4065b-150">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="4065b-150">Decoding is the reverse process.</span></span> <span data-ttu-id="4065b-151">Windows Communication Foundation (WCF) include tre tipi di codifica per i messaggi SOAP: Testo, binaria e MTOM (MTOM).</span><span class="sxs-lookup"><span data-stu-id="4065b-151">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="4065b-152">La codifica di testo rappresentata dall'elemento `textMessageEncoding` è la più interoperativa, ma la meno efficiente per i messaggi XML.</span><span class="sxs-lookup"><span data-stu-id="4065b-152">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="4065b-153">Il codificatore di testo crea messaggi in transito basati su testo.</span><span class="sxs-lookup"><span data-stu-id="4065b-153">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="4065b-154">I messaggi prodotti da questo codificatore sono adatti per l'interoperabilità basata su WS-\*.</span><span class="sxs-lookup"><span data-stu-id="4065b-154">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="4065b-155">In genere il servizio Web o il client di tale servizio è in grado di comprendere codice XML in formato testo.</span><span class="sxs-lookup"><span data-stu-id="4065b-155">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="4065b-156">Tuttavia, la trasmissione di grandi blocchi di dati binari come testo è il metodo meno efficiente per la codifica di messaggi XML.</span><span class="sxs-lookup"><span data-stu-id="4065b-156">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4065b-157">Esempio</span><span class="sxs-lookup"><span data-stu-id="4065b-157">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="4065b-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4065b-158">See also</span></span>
- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="4065b-159">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="4065b-159">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="4065b-160">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="4065b-160">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="4065b-161">Associazioni</span><span class="sxs-lookup"><span data-stu-id="4065b-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="4065b-162">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="4065b-162">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4065b-163">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="4065b-163">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4065b-164">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4065b-164">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
