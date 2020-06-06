---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: d67d623736f3cbf50568356132a74d2b234fdfd9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736214"
---
# \<textMessageEncoding>
<span data-ttu-id="2e6e3-101">Specifica le impostazioni di codifica e controllo di versione dei messaggi XML basati sul testo.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-101">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="2e6e3-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e6e3-102">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e6e3-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2e6e3-103">Attributes and Elements</span></span>  
 <span data-ttu-id="2e6e3-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e6e3-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="2e6e3-105">Attributes</span></span>  
  
|<span data-ttu-id="2e6e3-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="2e6e3-106">Attribute</span></span>|<span data-ttu-id="2e6e3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e6e3-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2e6e3-108">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="2e6e3-108">maxReadPoolSize</span></span>|<span data-ttu-id="2e6e3-109">Numero intero che specifica il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi reader.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-109">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="2e6e3-110">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-110">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="2e6e3-111">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-111">The default is 64.</span></span>|  
|<span data-ttu-id="2e6e3-112">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="2e6e3-112">maxWritePoolSize</span></span>|<span data-ttu-id="2e6e3-113">Numero intero che specifica il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-113">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="2e6e3-114">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-114">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="2e6e3-115">Il valore predefinito è 16.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-115">The default is 16.</span></span>|  
|<span data-ttu-id="2e6e3-116">messageVersion</span><span class="sxs-lookup"><span data-stu-id="2e6e3-116">messageVersion</span></span>|<span data-ttu-id="2e6e3-117">Specifica la versione SOAP dei messaggi inviati usando l'associazione.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-117">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="2e6e3-118">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="2e6e3-118">Valid values are</span></span><br /><br /> <span data-ttu-id="2e6e3-119">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="2e6e3-119">-   Soap11Addressing10</span></span><br /><span data-ttu-id="2e6e3-120">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="2e6e3-120">-   Soap12Addressing10</span></span><br /><span data-ttu-id="2e6e3-121">-Soap11</span><span class="sxs-lookup"><span data-stu-id="2e6e3-121">-   Soap11</span></span><br /><span data-ttu-id="2e6e3-122">-Soap12</span><span class="sxs-lookup"><span data-stu-id="2e6e3-122">-  Soap12</span></span><br /><br /><span data-ttu-id="2e6e3-123">L'impostazione predefinita è Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-123">The default is Soap12Addressing10.</span></span> <span data-ttu-id="2e6e3-124">L'attributo è di tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-124">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="2e6e3-125">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="2e6e3-125">writeEncoding</span></span>|<span data-ttu-id="2e6e3-126">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-126">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="2e6e3-127">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="2e6e3-127">Valid values are</span></span><br /><br /> <span data-ttu-id="2e6e3-128">-UnicodeFffeTextEncoding: codifica Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="2e6e3-128">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="2e6e3-129">-Utf16TextEncoding: codifica Unicode</span><span class="sxs-lookup"><span data-stu-id="2e6e3-129">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="2e6e3-130">-Utf8TextEncoding: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="2e6e3-130">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="2e6e3-131">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-131">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="2e6e3-132">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-132">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e6e3-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2e6e3-133">Child Elements</span></span>  
  
|<span data-ttu-id="2e6e3-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="2e6e3-134">Element</span></span>|<span data-ttu-id="2e6e3-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e6e3-135">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="2e6e3-136">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-136">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="2e6e3-137">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-137">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2e6e3-138">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2e6e3-138">Parent Elements</span></span>  
  
|<span data-ttu-id="2e6e3-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="2e6e3-139">Element</span></span>|<span data-ttu-id="2e6e3-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e6e3-140">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="2e6e3-141">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-141">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e6e3-142">Commenti</span><span class="sxs-lookup"><span data-stu-id="2e6e3-142">Remarks</span></span>  
 <span data-ttu-id="2e6e3-143">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-143">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="2e6e3-144">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-144">Decoding is the reverse process.</span></span> <span data-ttu-id="2e6e3-145">Windows Communication Foundation (WCF) include tre tipi di codifica per i messaggi SOAP, ovvero testo, binaria e MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="2e6e3-145">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="2e6e3-146">La codifica di testo rappresentata dall'elemento `textMessageEncoding` è la più interoperativa, ma la meno efficiente per i messaggi XML.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-146">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="2e6e3-147">Il codificatore di testo crea messaggi in transito basati su testo.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-147">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="2e6e3-148">I messaggi prodotti da questo codificatore sono adatti per l'interoperabilità basata su WS-\*.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-148">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="2e6e3-149">In genere il servizio Web o il client di tale servizio è in grado di comprendere codice XML in formato testo.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-149">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="2e6e3-150">Tuttavia, la trasmissione di grandi blocchi di dati binari come testo è il metodo meno efficiente per la codifica di messaggi XML.</span><span class="sxs-lookup"><span data-stu-id="2e6e3-150">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e6e3-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="2e6e3-151">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="2e6e3-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e6e3-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="2e6e3-153">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="2e6e3-153">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="2e6e3-154">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="2e6e3-154">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="2e6e3-155">Binding</span><span class="sxs-lookup"><span data-stu-id="2e6e3-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2e6e3-156">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="2e6e3-156">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2e6e3-157">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="2e6e3-157">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
