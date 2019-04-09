---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: e02ed6ef79fcf52bbe9c33bd9b36a14113e19d1d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228380"
---
# <a name="binarymessageencoding"></a><span data-ttu-id="01c45-101">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="01c45-101">\<binaryMessageEncoding></span></span>
<span data-ttu-id="01c45-102">Definisce un codificatore di messaggi binario che codifica messaggi di Windows Communication Foundation (WCF) in transito in formato binario.</span><span class="sxs-lookup"><span data-stu-id="01c45-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="01c45-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="01c45-103">\<system.serviceModel></span></span>  
<span data-ttu-id="01c45-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="01c45-104">\<bindings></span></span>  
<span data-ttu-id="01c45-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="01c45-105">\<customBinding></span></span>  
<span data-ttu-id="01c45-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="01c45-106">\<binding></span></span>  
<span data-ttu-id="01c45-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="01c45-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01c45-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01c45-108">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01c45-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="01c45-109">Attributes and Elements</span></span>  
 <span data-ttu-id="01c45-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="01c45-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01c45-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="01c45-111">Attributes</span></span>  
  
|<span data-ttu-id="01c45-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="01c45-112">Attribute</span></span>|<span data-ttu-id="01c45-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01c45-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01c45-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="01c45-114">maxReadPoolSize</span></span>|<span data-ttu-id="01c45-115">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="01c45-115">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="01c45-116">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="01c45-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="01c45-117">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="01c45-117">The default is 64.</span></span>|  
|<span data-ttu-id="01c45-118">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="01c45-118">maxSessionSize</span></span>|<span data-ttu-id="01c45-119">Numero intero positivo che imposta la dimensione, in byte, del buffer usato per la codifica.</span><span class="sxs-lookup"><span data-stu-id="01c45-119">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="01c45-120">Un buffer più grande aumenta la velocità di codifica a spese della dimensione del working set.</span><span class="sxs-lookup"><span data-stu-id="01c45-120">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="01c45-121">Il valore predefinito è 2048.</span><span class="sxs-lookup"><span data-stu-id="01c45-121">The default is 2048.</span></span>|  
|<span data-ttu-id="01c45-122">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="01c45-122">maxWritePoolSize</span></span>|<span data-ttu-id="01c45-123">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="01c45-123">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="01c45-124">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="01c45-124">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="01c45-125">Il valore predefinito è 16.</span><span class="sxs-lookup"><span data-stu-id="01c45-125">The default is 16.</span></span>|  
|<span data-ttu-id="01c45-126">messageVersion</span><span class="sxs-lookup"><span data-stu-id="01c45-126">messageVersion</span></span>|<span data-ttu-id="01c45-127">Specifica le versioni del messaggio SOAP e WS-Addressing usate o previste.</span><span class="sxs-lookup"><span data-stu-id="01c45-127">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01c45-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="01c45-128">Child Elements</span></span>  
  
|<span data-ttu-id="01c45-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="01c45-129">Element</span></span>|<span data-ttu-id="01c45-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01c45-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01c45-131">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="01c45-131">\<readerQuotas></span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="01c45-132">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="01c45-132">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="01c45-133">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="01c45-133">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="01c45-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="01c45-134">Parent Elements</span></span>  
  
|<span data-ttu-id="01c45-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="01c45-135">Element</span></span>|<span data-ttu-id="01c45-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01c45-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01c45-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="01c45-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="01c45-138">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="01c45-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01c45-139">Note</span><span class="sxs-lookup"><span data-stu-id="01c45-139">Remarks</span></span>  
 <span data-ttu-id="01c45-140">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="01c45-140">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="01c45-141">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="01c45-141">Decoding is the reverse process.</span></span> <span data-ttu-id="01c45-142">Windows Communication Foundation (WCF) include tre tipi di codifica per i messaggi SOAP: Testo, binaria e MTOM (MTOM).</span><span class="sxs-lookup"><span data-stu-id="01c45-142">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="01c45-143">L'elemento `binaryMessageEncoding` specifica il formato binario .NET per XML e dispone delle opzioni che consentono di specificare la codifica dei caratteri e le versioni SOAP e WS-Addressing da usare.</span><span class="sxs-lookup"><span data-stu-id="01c45-143">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="01c45-144">Il codificatore di messaggi binario codifica messaggi di Windows Communication Foundation (WCF) in transito in formato binario.</span><span class="sxs-lookup"><span data-stu-id="01c45-144">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="01c45-145">Se da un lato questa codifica comporta una trasmissione molto veloce dei messaggi, dall'altro si perde l'interoperabilità basata sugli standard WS - \*.</span><span class="sxs-lookup"><span data-stu-id="01c45-145">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01c45-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="01c45-146">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="01c45-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01c45-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="01c45-148">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="01c45-148">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="01c45-149">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="01c45-149">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="01c45-150">Associazioni</span><span class="sxs-lookup"><span data-stu-id="01c45-150">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="01c45-151">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="01c45-151">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="01c45-152">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="01c45-152">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="01c45-153">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="01c45-153">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
