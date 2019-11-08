---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: afe0479d9cbf6d754b309c18e23d3a479870177c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739080"
---
# <a name="binarymessageencoding"></a><span data-ttu-id="a711c-101">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="a711c-101">\<binaryMessageEncoding></span></span>
<span data-ttu-id="a711c-102">Definisce un codificatore di messaggi binario che codifica messaggi di Windows Communication Foundation (WCF) in transito in formato binario.</span><span class="sxs-lookup"><span data-stu-id="a711c-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
<span data-ttu-id="a711c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a711c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a711c-104">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a711c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a711c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="a711c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="a711c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="a711c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="a711c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="a711c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a711c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<binaryMessageEncoding >**</span><span class="sxs-lookup"><span data-stu-id="a711c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binaryMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a711c-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a711c-109">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a711c-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a711c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a711c-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a711c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a711c-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="a711c-112">Attributes</span></span>  
  
|<span data-ttu-id="a711c-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="a711c-113">Attribute</span></span>|<span data-ttu-id="a711c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a711c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a711c-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="a711c-115">maxReadPoolSize</span></span>|<span data-ttu-id="a711c-116">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="a711c-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="a711c-117">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="a711c-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="a711c-118">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="a711c-118">The default is 64.</span></span>|  
|<span data-ttu-id="a711c-119">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="a711c-119">maxSessionSize</span></span>|<span data-ttu-id="a711c-120">Numero intero positivo che imposta la dimensione, in byte, del buffer usato per la codifica.</span><span class="sxs-lookup"><span data-stu-id="a711c-120">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="a711c-121">Un buffer più grande aumenta la velocità di codifica a spese della dimensione del working set.</span><span class="sxs-lookup"><span data-stu-id="a711c-121">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="a711c-122">Il valore predefinito è 2048.</span><span class="sxs-lookup"><span data-stu-id="a711c-122">The default is 2048.</span></span>|  
|<span data-ttu-id="a711c-123">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="a711c-123">maxWritePoolSize</span></span>|<span data-ttu-id="a711c-124">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="a711c-124">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="a711c-125">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="a711c-125">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="a711c-126">Il valore predefinito è 16.</span><span class="sxs-lookup"><span data-stu-id="a711c-126">The default is 16.</span></span>|  
|<span data-ttu-id="a711c-127">messageVersion</span><span class="sxs-lookup"><span data-stu-id="a711c-127">messageVersion</span></span>|<span data-ttu-id="a711c-128">Specifica le versioni del messaggio SOAP e WS-Addressing usate o previste.</span><span class="sxs-lookup"><span data-stu-id="a711c-128">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a711c-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a711c-129">Child Elements</span></span>  
  
|<span data-ttu-id="a711c-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="a711c-130">Element</span></span>|<span data-ttu-id="a711c-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a711c-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a711c-132">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a711c-132">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="a711c-133">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="a711c-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="a711c-134">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="a711c-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a711c-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a711c-135">Parent Elements</span></span>  
  
|<span data-ttu-id="a711c-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="a711c-136">Element</span></span>|<span data-ttu-id="a711c-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a711c-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a711c-138">\<binding ></span><span class="sxs-lookup"><span data-stu-id="a711c-138">\<binding></span></span>](bindings.md)|<span data-ttu-id="a711c-139">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="a711c-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a711c-140">Note</span><span class="sxs-lookup"><span data-stu-id="a711c-140">Remarks</span></span>  
 <span data-ttu-id="a711c-141">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="a711c-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="a711c-142">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="a711c-142">Decoding is the reverse process.</span></span> <span data-ttu-id="a711c-143">Windows Communication Foundation (WCF) include tre tipi di codifica per i messaggi SOAP, ovvero testo, binaria e MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="a711c-143">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="a711c-144">L'elemento `binaryMessageEncoding` specifica il formato binario .NET per XML e dispone delle opzioni che consentono di specificare la codifica dei caratteri e le versioni SOAP e WS-Addressing da usare.</span><span class="sxs-lookup"><span data-stu-id="a711c-144">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="a711c-145">Il codificatore di messaggi binario codifica messaggi di Windows Communication Foundation (WCF) in transito in formato binario.</span><span class="sxs-lookup"><span data-stu-id="a711c-145">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="a711c-146">Se da un lato questa codifica comporta una trasmissione molto veloce dei messaggi, dall'altro si perde l'interoperabilità basata sugli standard WS - \*.</span><span class="sxs-lookup"><span data-stu-id="a711c-146">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a711c-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="a711c-147">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="a711c-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a711c-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="a711c-149">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="a711c-149">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="a711c-150">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="a711c-150">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="a711c-151">Associazioni</span><span class="sxs-lookup"><span data-stu-id="a711c-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a711c-152">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="a711c-152">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a711c-153">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="a711c-153">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a711c-154">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="a711c-154">\<customBinding></span></span>](custombinding.md)
