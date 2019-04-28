---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 61b23957c56bad81598dd65b0dd68f7b44d329e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772385"
---
# <a name="mtommessageencoding"></a><span data-ttu-id="08a82-101">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="08a82-101">\<mtomMessageEncoding></span></span>
<span data-ttu-id="08a82-102">Specifica le impostazioni di codifica e controllo di versione dei messaggi SOAP basati sul meccanismo Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="08a82-102">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="08a82-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="08a82-103">\<system.serviceModel></span></span>  
<span data-ttu-id="08a82-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="08a82-104">\<bindings></span></span>  
<span data-ttu-id="08a82-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="08a82-105">\<customBinding></span></span>  
<span data-ttu-id="08a82-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="08a82-106">\<binding></span></span>  
<span data-ttu-id="08a82-107">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="08a82-107">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08a82-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08a82-108">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08a82-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="08a82-109">Attributes and Elements</span></span>  
 <span data-ttu-id="08a82-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="08a82-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08a82-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="08a82-111">Attributes</span></span>  
  
|<span data-ttu-id="08a82-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="08a82-112">Attribute</span></span>|<span data-ttu-id="08a82-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08a82-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="08a82-114">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="08a82-114">maxBufferSize</span></span>|<span data-ttu-id="08a82-115">Numero intero che specifica la dimensione massima del buffer che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="08a82-115">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="08a82-116">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="08a82-116">maxReadPoolSize</span></span>|<span data-ttu-id="08a82-117">Numero intero che specifica il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi reader.</span><span class="sxs-lookup"><span data-stu-id="08a82-117">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="08a82-118">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="08a82-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="08a82-119">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="08a82-119">The default is 64.</span></span>|  
|<span data-ttu-id="08a82-120">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="08a82-120">maxWritePoolSize</span></span>|<span data-ttu-id="08a82-121">Numero intero che specifica il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="08a82-121">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="08a82-122">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="08a82-122">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="08a82-123">Il valore predefinito è 16.</span><span class="sxs-lookup"><span data-stu-id="08a82-123">The default is 16.</span></span>|  
|<span data-ttu-id="08a82-124">messageVersion</span><span class="sxs-lookup"><span data-stu-id="08a82-124">messageVersion</span></span>|<span data-ttu-id="08a82-125">Specifica la versione SOAP dei messaggi inviati usando l'associazione.</span><span class="sxs-lookup"><span data-stu-id="08a82-125">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="08a82-126">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="08a82-126">Valid values are</span></span><br /><br /> <span data-ttu-id="08a82-127">-   Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="08a82-127">-   Soap11Addressing1</span></span><br /><span data-ttu-id="08a82-128">-   Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="08a82-128">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="08a82-129">L'impostazione predefinita è Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="08a82-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="08a82-130">L'attributo è di tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="08a82-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="08a82-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="08a82-131">writeEncoding</span></span>|<span data-ttu-id="08a82-132">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="08a82-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="08a82-133">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="08a82-133">Valid values are</span></span><br /><br /> <span data-ttu-id="08a82-134">-UnicodeFffeTextEncoding: Codifica Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="08a82-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="08a82-135">-   Utf16TextEncoding: Codifica Unicode</span><span class="sxs-lookup"><span data-stu-id="08a82-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="08a82-136">-   Utf8TextEncoding: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="08a82-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="08a82-137">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="08a82-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="08a82-138">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="08a82-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08a82-139">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="08a82-139">Child Elements</span></span>  
  
|<span data-ttu-id="08a82-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="08a82-140">Element</span></span>|<span data-ttu-id="08a82-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08a82-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08a82-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="08a82-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="08a82-143">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="08a82-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="08a82-144">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="08a82-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="08a82-145">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="08a82-145">Parent Elements</span></span>  
  
|<span data-ttu-id="08a82-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="08a82-146">Element</span></span>|<span data-ttu-id="08a82-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08a82-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08a82-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="08a82-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="08a82-149">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="08a82-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08a82-150">Note</span><span class="sxs-lookup"><span data-stu-id="08a82-150">Remarks</span></span>  
 <span data-ttu-id="08a82-151">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="08a82-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="08a82-152">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="08a82-152">Decoding is the reverse process.</span></span> <span data-ttu-id="08a82-153">Windows Communication Foundation (WCF) include tre tipi di codifica per i messaggi SOAP: Testo, binaria e MTOM (MTOM).</span><span class="sxs-lookup"><span data-stu-id="08a82-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="08a82-154">L'elemento `MtomMessageEncoding` specifica la codifica dei caratteri, la versione dei messaggi e altre impostazioni usate per i messaggi che usano la codifica MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="08a82-154">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="08a82-155">MTOM è una tecnologia efficiente per la trasmissione di dati binari nei messaggi di WCF.</span><span class="sxs-lookup"><span data-stu-id="08a82-155">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="08a82-156">Il codificatore MTOM cerca di creare un equilibrio tra efficienza e interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="08a82-156">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="08a82-157">La codifica MTOM trasmette la maggior parte del codice XML in formato testo, ma ottimizza grandi blocchi di dati binari trasmettendoli senza introdurre modifiche e senza convertirli nel formato codificato Base64.</span><span class="sxs-lookup"><span data-stu-id="08a82-157">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08a82-158">Esempio</span><span class="sxs-lookup"><span data-stu-id="08a82-158">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="08a82-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08a82-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="08a82-160">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="08a82-160">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="08a82-161">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="08a82-161">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="08a82-162">Associazioni</span><span class="sxs-lookup"><span data-stu-id="08a82-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="08a82-163">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="08a82-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="08a82-164">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="08a82-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="08a82-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="08a82-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
