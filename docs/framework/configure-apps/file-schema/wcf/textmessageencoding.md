---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: d67d623736f3cbf50568356132a74d2b234fdfd9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736214"
---
# <a name="textmessageencoding"></a><span data-ttu-id="30c88-101">\<textMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="30c88-101">\<textMessageEncoding></span></span>
<span data-ttu-id="30c88-102">Specifica le impostazioni di codifica e controllo di versione dei messaggi XML basati sul testo.</span><span class="sxs-lookup"><span data-stu-id="30c88-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
<span data-ttu-id="30c88-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="30c88-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="30c88-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="30c88-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="30c88-105">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="30c88-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="30c88-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="30c88-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="30c88-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="30c88-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="30c88-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<textMessageEncoding >**</span><span class="sxs-lookup"><span data-stu-id="30c88-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30c88-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30c88-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30c88-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="30c88-110">Attributes and Elements</span></span>  
 <span data-ttu-id="30c88-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="30c88-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30c88-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="30c88-112">Attributes</span></span>  
  
|<span data-ttu-id="30c88-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="30c88-113">Attribute</span></span>|<span data-ttu-id="30c88-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30c88-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="30c88-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="30c88-115">maxReadPoolSize</span></span>|<span data-ttu-id="30c88-116">Numero intero che specifica il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi reader.</span><span class="sxs-lookup"><span data-stu-id="30c88-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="30c88-117">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="30c88-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="30c88-118">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="30c88-118">The default is 64.</span></span>|  
|<span data-ttu-id="30c88-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="30c88-119">maxWritePoolSize</span></span>|<span data-ttu-id="30c88-120">Numero intero che specifica il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="30c88-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="30c88-121">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="30c88-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="30c88-122">Il valore predefinito è 16.</span><span class="sxs-lookup"><span data-stu-id="30c88-122">The default is 16.</span></span>|  
|<span data-ttu-id="30c88-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="30c88-123">messageVersion</span></span>|<span data-ttu-id="30c88-124">Specifica la versione SOAP dei messaggi inviati usando l'associazione.</span><span class="sxs-lookup"><span data-stu-id="30c88-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="30c88-125">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="30c88-125">Valid values are</span></span><br /><br /> <span data-ttu-id="30c88-126">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="30c88-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="30c88-127">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="30c88-127">-   Soap12Addressing10</span></span><br /><span data-ttu-id="30c88-128">-Soap11</span><span class="sxs-lookup"><span data-stu-id="30c88-128">-   Soap11</span></span><br /><span data-ttu-id="30c88-129">-Soap12</span><span class="sxs-lookup"><span data-stu-id="30c88-129">-  Soap12</span></span><br /><br /><span data-ttu-id="30c88-130">L'impostazione predefinita è Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="30c88-130">The default is Soap12Addressing10.</span></span> <span data-ttu-id="30c88-131">L'attributo è di tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="30c88-131">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="30c88-132">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="30c88-132">writeEncoding</span></span>|<span data-ttu-id="30c88-133">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="30c88-133">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="30c88-134">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="30c88-134">Valid values are</span></span><br /><br /> <span data-ttu-id="30c88-135">-UnicodeFffeTextEncoding: codifica Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="30c88-135">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="30c88-136">-Utf16TextEncoding: codifica Unicode</span><span class="sxs-lookup"><span data-stu-id="30c88-136">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="30c88-137">-Utf8TextEncoding: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="30c88-137">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="30c88-138">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="30c88-138">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="30c88-139">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="30c88-139">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30c88-140">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="30c88-140">Child Elements</span></span>  
  
|<span data-ttu-id="30c88-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="30c88-141">Element</span></span>|<span data-ttu-id="30c88-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30c88-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30c88-143">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="30c88-143">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="30c88-144">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="30c88-144">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="30c88-145">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="30c88-145">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="30c88-146">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="30c88-146">Parent Elements</span></span>  
  
|<span data-ttu-id="30c88-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="30c88-147">Element</span></span>|<span data-ttu-id="30c88-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30c88-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30c88-149">\<binding ></span><span class="sxs-lookup"><span data-stu-id="30c88-149">\<binding></span></span>](bindings.md)|<span data-ttu-id="30c88-150">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="30c88-150">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30c88-151">Note</span><span class="sxs-lookup"><span data-stu-id="30c88-151">Remarks</span></span>  
 <span data-ttu-id="30c88-152">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="30c88-152">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="30c88-153">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="30c88-153">Decoding is the reverse process.</span></span> <span data-ttu-id="30c88-154">Windows Communication Foundation (WCF) include tre tipi di codifica per i messaggi SOAP, ovvero testo, binaria e MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="30c88-154">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="30c88-155">La codifica di testo rappresentata dall'elemento `textMessageEncoding` è la più interoperativa, ma la meno efficiente per i messaggi XML.</span><span class="sxs-lookup"><span data-stu-id="30c88-155">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="30c88-156">Il codificatore di testo crea messaggi in transito basati su testo.</span><span class="sxs-lookup"><span data-stu-id="30c88-156">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="30c88-157">I messaggi prodotti da questo codificatore sono adatti per l'interoperabilità basata su WS-\*.</span><span class="sxs-lookup"><span data-stu-id="30c88-157">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="30c88-158">In genere il servizio Web o il client di tale servizio è in grado di comprendere codice XML in formato testo.</span><span class="sxs-lookup"><span data-stu-id="30c88-158">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="30c88-159">Tuttavia, la trasmissione di grandi blocchi di dati binari come testo è il metodo meno efficiente per la codifica di messaggi XML.</span><span class="sxs-lookup"><span data-stu-id="30c88-159">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30c88-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="30c88-160">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="30c88-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30c88-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="30c88-162">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="30c88-162">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="30c88-163">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="30c88-163">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="30c88-164">Associazioni</span><span class="sxs-lookup"><span data-stu-id="30c88-164">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="30c88-165">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="30c88-165">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="30c88-166">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="30c88-166">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="30c88-167">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="30c88-167">\<customBinding></span></span>](custombinding.md)
