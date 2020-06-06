---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: bd38bf812e6d8d9e57d99bf1a5b77ebb776193a5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738847"
---
# \<mtomMessageEncoding>
<span data-ttu-id="1c504-101">Specifica le impostazioni di codifica e controllo di versione dei messaggi SOAP basati sul meccanismo Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="1c504-101">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mtomMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="1c504-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c504-102">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c504-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1c504-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1c504-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1c504-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c504-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="1c504-105">Attributes</span></span>  
  
|<span data-ttu-id="1c504-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="1c504-106">Attribute</span></span>|<span data-ttu-id="1c504-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c504-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1c504-108">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="1c504-108">maxBufferSize</span></span>|<span data-ttu-id="1c504-109">Numero intero che specifica la dimensione massima del buffer che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="1c504-109">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="1c504-110">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="1c504-110">maxReadPoolSize</span></span>|<span data-ttu-id="1c504-111">Numero intero che specifica il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi reader.</span><span class="sxs-lookup"><span data-stu-id="1c504-111">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="1c504-112">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="1c504-112">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="1c504-113">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="1c504-113">The default is 64.</span></span>|  
|<span data-ttu-id="1c504-114">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="1c504-114">maxWritePoolSize</span></span>|<span data-ttu-id="1c504-115">Numero intero che specifica il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="1c504-115">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="1c504-116">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="1c504-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="1c504-117">Il valore predefinito è 16.</span><span class="sxs-lookup"><span data-stu-id="1c504-117">The default is 16.</span></span>|  
|<span data-ttu-id="1c504-118">messageVersion</span><span class="sxs-lookup"><span data-stu-id="1c504-118">messageVersion</span></span>|<span data-ttu-id="1c504-119">Specifica la versione SOAP dei messaggi inviati usando l'associazione.</span><span class="sxs-lookup"><span data-stu-id="1c504-119">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="1c504-120">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="1c504-120">Valid values are</span></span><br /><br /> <span data-ttu-id="1c504-121">- Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="1c504-121">-   Soap11Addressing1</span></span><br /><span data-ttu-id="1c504-122">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="1c504-122">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="1c504-123">L'impostazione predefinita è Soap12Addressing10.</span><span class="sxs-lookup"><span data-stu-id="1c504-123">The default is Soap12Addressing10.</span></span> <span data-ttu-id="1c504-124">L'attributo è di tipo <xref:System.ServiceModel.Channels.MessageVersion>.</span><span class="sxs-lookup"><span data-stu-id="1c504-124">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="1c504-125">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="1c504-125">writeEncoding</span></span>|<span data-ttu-id="1c504-126">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="1c504-126">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="1c504-127">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="1c504-127">Valid values are</span></span><br /><br /> <span data-ttu-id="1c504-128">-UnicodeFffeTextEncoding: codifica Unicode BigEndian</span><span class="sxs-lookup"><span data-stu-id="1c504-128">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="1c504-129">-Utf16TextEncoding: codifica Unicode</span><span class="sxs-lookup"><span data-stu-id="1c504-129">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="1c504-130">-Utf8TextEncoding: codifica a 8 bit</span><span class="sxs-lookup"><span data-stu-id="1c504-130">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="1c504-131">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="1c504-131">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="1c504-132">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="1c504-132">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c504-133">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1c504-133">Child Elements</span></span>  
  
|<span data-ttu-id="1c504-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="1c504-134">Element</span></span>|<span data-ttu-id="1c504-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c504-135">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="1c504-136">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="1c504-136">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="1c504-137">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="1c504-137">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c504-138">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1c504-138">Parent Elements</span></span>  
  
|<span data-ttu-id="1c504-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="1c504-139">Element</span></span>|<span data-ttu-id="1c504-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c504-140">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="1c504-141">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1c504-141">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c504-142">Commenti</span><span class="sxs-lookup"><span data-stu-id="1c504-142">Remarks</span></span>  
 <span data-ttu-id="1c504-143">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="1c504-143">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="1c504-144">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="1c504-144">Decoding is the reverse process.</span></span> <span data-ttu-id="1c504-145">Windows Communication Foundation (WCF) include tre tipi di codifica per i messaggi SOAP, ovvero testo, binaria e MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="1c504-145">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="1c504-146">L'elemento `MtomMessageEncoding` specifica la codifica dei caratteri, la versione dei messaggi e altre impostazioni usate per i messaggi che usano la codifica MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="1c504-146">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="1c504-147">MTOM è una tecnologia efficiente per la trasmissione di dati binari nei messaggi di WCF.</span><span class="sxs-lookup"><span data-stu-id="1c504-147">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="1c504-148">Il codificatore MTOM cerca di creare un equilibrio tra efficienza e interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="1c504-148">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="1c504-149">La codifica MTOM trasmette la maggior parte del codice XML in formato testo, ma ottimizza grandi blocchi di dati binari trasmettendoli senza introdurre modifiche e senza convertirli nel formato codificato Base64.</span><span class="sxs-lookup"><span data-stu-id="1c504-149">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c504-150">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c504-150">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="1c504-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c504-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="1c504-152">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="1c504-152">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="1c504-153">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="1c504-153">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="1c504-154">Binding</span><span class="sxs-lookup"><span data-stu-id="1c504-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1c504-155">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="1c504-155">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="1c504-156">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="1c504-156">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
