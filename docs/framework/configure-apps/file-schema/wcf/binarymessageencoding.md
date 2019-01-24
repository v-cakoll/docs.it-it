---
title: '&lt;binaryMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: 7753340be01c407157d9a0576f31db4245c0b4f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672843"
---
# <a name="ltbinarymessageencodinggt"></a><span data-ttu-id="1f3ce-102">&lt;binaryMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="1f3ce-102">&lt;binaryMessageEncoding&gt;</span></span>
<span data-ttu-id="1f3ce-103">Definisce un codificatore di messaggi binario che codifica messaggi di Windows Communication Foundation (WCF) in transito in formato binario.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-103">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="1f3ce-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1f3ce-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1f3ce-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="1f3ce-105">\<bindings></span></span>  
<span data-ttu-id="1f3ce-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1f3ce-106">\<customBinding></span></span>  
<span data-ttu-id="1f3ce-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1f3ce-107">\<binding></span></span>  
<span data-ttu-id="1f3ce-108">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="1f3ce-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f3ce-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f3ce-109">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f3ce-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1f3ce-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1f3ce-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f3ce-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="1f3ce-112">Attributes</span></span>  
  
|<span data-ttu-id="1f3ce-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="1f3ce-113">Attribute</span></span>|<span data-ttu-id="1f3ce-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f3ce-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1f3ce-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="1f3ce-115">maxReadPoolSize</span></span>|<span data-ttu-id="1f3ce-116">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="1f3ce-117">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="1f3ce-118">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-118">The default is 64.</span></span>|  
|<span data-ttu-id="1f3ce-119">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="1f3ce-119">maxSessionSize</span></span>|<span data-ttu-id="1f3ce-120">Numero intero positivo che imposta la dimensione, in byte, del buffer usato per la codifica.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-120">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="1f3ce-121">Un buffer più grande aumenta la velocità di codifica a spese della dimensione del working set.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-121">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="1f3ce-122">Il valore predefinito è 2048.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-122">The default is 2048.</span></span>|  
|<span data-ttu-id="1f3ce-123">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="1f3ce-123">maxWritePoolSize</span></span>|<span data-ttu-id="1f3ce-124">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-124">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="1f3ce-125">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-125">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="1f3ce-126">Il valore predefinito è 16.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-126">The default is 16.</span></span>|  
|<span data-ttu-id="1f3ce-127">messageVersion</span><span class="sxs-lookup"><span data-stu-id="1f3ce-127">messageVersion</span></span>|<span data-ttu-id="1f3ce-128">Specifica le versioni del messaggio SOAP e WS-Addressing usate o previste.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-128">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1f3ce-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1f3ce-129">Child Elements</span></span>  
  
|<span data-ttu-id="1f3ce-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="1f3ce-130">Element</span></span>|<span data-ttu-id="1f3ce-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f3ce-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f3ce-132">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="1f3ce-132">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="1f3ce-133">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="1f3ce-134">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1f3ce-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1f3ce-135">Parent Elements</span></span>  
  
|<span data-ttu-id="1f3ce-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="1f3ce-136">Element</span></span>|<span data-ttu-id="1f3ce-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1f3ce-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f3ce-138">\<binding></span><span class="sxs-lookup"><span data-stu-id="1f3ce-138">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="1f3ce-139">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f3ce-140">Note</span><span class="sxs-lookup"><span data-stu-id="1f3ce-140">Remarks</span></span>  
 <span data-ttu-id="1f3ce-141">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="1f3ce-142">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-142">Decoding is the reverse process.</span></span> <span data-ttu-id="1f3ce-143">Windows Communication Foundation (WCF) include tre tipi di codifica per i messaggi SOAP: Testo, binaria e MTOM (MTOM).</span><span class="sxs-lookup"><span data-stu-id="1f3ce-143">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="1f3ce-144">L'elemento `binaryMessageEncoding` specifica il formato binario .NET per XML e dispone delle opzioni che consentono di specificare la codifica dei caratteri e le versioni SOAP e WS-Addressing da usare.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-144">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="1f3ce-145">Il codificatore di messaggi binario codifica messaggi di Windows Communication Foundation (WCF) in transito in formato binario.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-145">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="1f3ce-146">Se da un lato questa codifica comporta una trasmissione molto veloce dei messaggi, dall'altro si perde l'interoperabilità basata sugli standard WS - \*.</span><span class="sxs-lookup"><span data-stu-id="1f3ce-146">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f3ce-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="1f3ce-147">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="1f3ce-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f3ce-148">See also</span></span>
- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="1f3ce-149">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="1f3ce-149">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="1f3ce-150">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="1f3ce-150">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="1f3ce-151">Associazioni</span><span class="sxs-lookup"><span data-stu-id="1f3ce-151">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="1f3ce-152">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="1f3ce-152">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="1f3ce-153">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="1f3ce-153">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="1f3ce-154">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1f3ce-154">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
