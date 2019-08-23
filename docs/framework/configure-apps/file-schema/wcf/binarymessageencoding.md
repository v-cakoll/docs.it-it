---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: 9b6b74200c807e6523ed3f7250945040bd12658d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919801"
---
# <a name="binarymessageencoding"></a><span data-ttu-id="e127e-101">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="e127e-101">\<binaryMessageEncoding></span></span>
<span data-ttu-id="e127e-102">Definisce un codificatore di messaggi binario che codifica messaggi di Windows Communication Foundation (WCF) in transito in formato binario.</span><span class="sxs-lookup"><span data-stu-id="e127e-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="e127e-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e127e-103">\<system.serviceModel></span></span>  
<span data-ttu-id="e127e-104">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="e127e-104">\<bindings></span></span>  
<span data-ttu-id="e127e-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e127e-105">\<customBinding></span></span>  
<span data-ttu-id="e127e-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="e127e-106">\<binding></span></span>  
<span data-ttu-id="e127e-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="e127e-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e127e-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e127e-108">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e127e-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e127e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e127e-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e127e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e127e-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="e127e-111">Attributes</span></span>  
  
|<span data-ttu-id="e127e-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="e127e-112">Attribute</span></span>|<span data-ttu-id="e127e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e127e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e127e-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="e127e-114">maxReadPoolSize</span></span>|<span data-ttu-id="e127e-115">Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="e127e-115">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="e127e-116">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="e127e-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e127e-117">Il valore predefinito è 64.</span><span class="sxs-lookup"><span data-stu-id="e127e-117">The default is 64.</span></span>|  
|<span data-ttu-id="e127e-118">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="e127e-118">maxSessionSize</span></span>|<span data-ttu-id="e127e-119">Numero intero positivo che imposta la dimensione, in byte, del buffer usato per la codifica.</span><span class="sxs-lookup"><span data-stu-id="e127e-119">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="e127e-120">Un buffer più grande aumenta la velocità di codifica a spese della dimensione del working set.</span><span class="sxs-lookup"><span data-stu-id="e127e-120">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="e127e-121">Il valore predefinito è 2048.</span><span class="sxs-lookup"><span data-stu-id="e127e-121">The default is 2048.</span></span>|  
|<span data-ttu-id="e127e-122">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="e127e-122">maxWritePoolSize</span></span>|<span data-ttu-id="e127e-123">Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="e127e-123">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="e127e-124">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="e127e-124">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e127e-125">Il valore predefinito è 16.</span><span class="sxs-lookup"><span data-stu-id="e127e-125">The default is 16.</span></span>|  
|<span data-ttu-id="e127e-126">messageVersion</span><span class="sxs-lookup"><span data-stu-id="e127e-126">messageVersion</span></span>|<span data-ttu-id="e127e-127">Specifica le versioni del messaggio SOAP e WS-Addressing usate o previste.</span><span class="sxs-lookup"><span data-stu-id="e127e-127">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e127e-128">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e127e-128">Child Elements</span></span>  
  
|<span data-ttu-id="e127e-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="e127e-129">Element</span></span>|<span data-ttu-id="e127e-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e127e-130">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e127e-131">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e127e-131">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="e127e-132">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="e127e-132">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="e127e-133">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="e127e-133">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e127e-134">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e127e-134">Parent Elements</span></span>  
  
|<span data-ttu-id="e127e-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="e127e-135">Element</span></span>|<span data-ttu-id="e127e-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e127e-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e127e-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="e127e-137">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="e127e-138">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e127e-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e127e-139">Note</span><span class="sxs-lookup"><span data-stu-id="e127e-139">Remarks</span></span>  
 <span data-ttu-id="e127e-140">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="e127e-140">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="e127e-141">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="e127e-141">Decoding is the reverse process.</span></span> <span data-ttu-id="e127e-142">Windows Communication Foundation (WCF) include tre tipi di codifica per i messaggi SOAP: Testo, binario e MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="e127e-142">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="e127e-143">L'elemento `binaryMessageEncoding` specifica il formato binario .NET per XML e dispone delle opzioni che consentono di specificare la codifica dei caratteri e le versioni SOAP e WS-Addressing da usare.</span><span class="sxs-lookup"><span data-stu-id="e127e-143">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="e127e-144">Il codificatore di messaggi binario codifica messaggi di Windows Communication Foundation (WCF) in transito in formato binario.</span><span class="sxs-lookup"><span data-stu-id="e127e-144">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="e127e-145">Se da un lato questa codifica comporta una trasmissione molto veloce dei messaggi, dall'altro si perde l'interoperabilità basata sugli standard WS - \*.</span><span class="sxs-lookup"><span data-stu-id="e127e-145">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e127e-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="e127e-146">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="e127e-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e127e-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="e127e-148">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="e127e-148">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="e127e-149">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="e127e-149">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="e127e-150">Associazioni</span><span class="sxs-lookup"><span data-stu-id="e127e-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e127e-151">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="e127e-151">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e127e-152">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="e127e-152">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e127e-153">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e127e-153">\<customBinding></span></span>](custombinding.md)
