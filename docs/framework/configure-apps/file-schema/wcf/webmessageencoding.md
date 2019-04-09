---
title: <webMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: 7221f19dd131dbd60ef1a61625633d54dfdbe85a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191744"
---
# <a name="webmessageencoding"></a><span data-ttu-id="4ee7f-101">\<webMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="4ee7f-101">\<webMessageEncoding></span></span>
<span data-ttu-id="4ee7f-102">Consente alle codifiche di messaggi XML di testo normale e JSON (JavaScript Object Notation) e al contenuto binario "non elaborato" di essere letti e scritti quando vengono usati in un'associazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4ee7f-102">Enables plain-text XML, JavaScript Object Notation (JSON) message encodings and "raw" binary content to be read and written when used in a Windows Communication Foundation (WCF) binding.</span></span>  
  
 <span data-ttu-id="4ee7f-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4ee7f-103">\<system.serviceModel></span></span>  
<span data-ttu-id="4ee7f-104">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="4ee7f-104">\<bindings></span></span>  
<span data-ttu-id="4ee7f-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4ee7f-105">\<customBinding></span></span>  
<span data-ttu-id="4ee7f-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="4ee7f-106">\<binding></span></span>  
<span data-ttu-id="4ee7f-107">\<webMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="4ee7f-107">\<webMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ee7f-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ee7f-108">Syntax</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="Integer"
                    maxWritePoolSize="Integer"
                    writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ee7f-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4ee7f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4ee7f-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ee7f-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="4ee7f-111">Attributes</span></span>  
  
|<span data-ttu-id="4ee7f-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="4ee7f-112">Attribute</span></span>|<span data-ttu-id="4ee7f-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ee7f-113">Description</span></span>|  
|---------------|-----------------|  
|`maxReadPoolSize`|<span data-ttu-id="4ee7f-114">Numero di messaggi che è possibile leggere contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-114">The amount of messages that can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="4ee7f-115">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-115">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4ee7f-116">L'impostazione predefinita è 64 lettori per ogni codificatore interno (testo, JSON e "non elaborato").</span><span class="sxs-lookup"><span data-stu-id="4ee7f-116">The default is 64 readers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="4ee7f-117">Sebbene l'aumento di questo numero determini un maggiore consumo di memoria, in questo modo il codificatore sarà in grado di gestire picchi improvvisi di messaggi in arrivo usando i lettori del pool già creati anziché crearne di nuovi.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-117">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of incoming messages because it is able to use readers from the pool that are already created instead of creating new ones.</span></span>|  
|`maxWritePoolSize`|<span data-ttu-id="4ee7f-118">Numero di messaggi che è possibile inviare contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-118">The amount of messages that can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="4ee7f-119">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4ee7f-120">L'impostazione predefinita è 16 writer per ogni codificatore interno (testo, JSON e "non elaborato").</span><span class="sxs-lookup"><span data-stu-id="4ee7f-120">The default is 16 writers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="4ee7f-121">Sebbene l'aumento di questo numero determini un maggiore consumo di memoria, in questo modo il codificatore sarà in grado di gestire picchi improvvisi di messaggi in uscita usando i writer del pool già creati anziché crearne di nuovi.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-121">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of outgoing messages because it is able to use writers from the pool that are already created instead of creating new ones.</span></span>|  
|`writeEncoding`|<span data-ttu-id="4ee7f-122">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-122">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="4ee7f-123">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="4ee7f-123">Valid values are:</span></span><br /><br /> <span data-ttu-id="4ee7f-124">-UnicodeFffeTextEncoding: Codifica Unicode bigEndian.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-124">-   UnicodeFffeTextEncoding: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="4ee7f-125">-   Utf16TextEncoding: Codifica Unicode.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-125">-   Utf16TextEncoding: Unicode encoding.</span></span><br /><span data-ttu-id="4ee7f-126">-   Utf8TextEncoding: codifica a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-126">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="4ee7f-127">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-127">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="4ee7f-128">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-128">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ee7f-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4ee7f-129">Child Elements</span></span>  
  
|<span data-ttu-id="4ee7f-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ee7f-130">Element</span></span>|<span data-ttu-id="4ee7f-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ee7f-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ee7f-132">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="4ee7f-132">\<readerQuotas></span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="4ee7f-133">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="4ee7f-134">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4ee7f-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4ee7f-135">Parent Elements</span></span>  
  
|<span data-ttu-id="4ee7f-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="4ee7f-136">Element</span></span>|<span data-ttu-id="4ee7f-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ee7f-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ee7f-138">\<binding></span><span class="sxs-lookup"><span data-stu-id="4ee7f-138">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="4ee7f-139">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ee7f-140">Note</span><span class="sxs-lookup"><span data-stu-id="4ee7f-140">Remarks</span></span>  
 <span data-ttu-id="4ee7f-141">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="4ee7f-142">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-142">Decoding is the reverse process.</span></span> <span data-ttu-id="4ee7f-143">Questi processi richiedono la specifica di una codifica caratteri.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-143">These processes require the specification of a character encoding.</span></span>  
  
 <span data-ttu-id="4ee7f-144">L'elemento `webMessageEncoding` delega a una serie di codificatori interni la gestione di codifiche XML di testo normale e JSON e dati binari non elaborati.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-144">The `webMessageEncoding` element works by delegating to a series of inner encoders to handle the plain-text XML and JSON encodings, and "raw" binary data.</span></span> <span data-ttu-id="4ee7f-145">Questa delega viene eseguita mediante un codificatore di messaggi composto.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-145">This delegation is done by a composite message encoder.</span></span>  
  
 <span data-ttu-id="4ee7f-146">Questo elemento di associazione e il relativo codificatore composto vengono usati per controllare la codifica in scenari che non usano la messaggistica SOAP usata dall'elemento `webHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-146">This binding element and its composite encoder are used to control the encoding in scenarios that do not use SOAP messaging used by the `webHttpBinding` element.</span></span> <span data-ttu-id="4ee7f-147">Questi scenari includono POX (Plain Old XML), REST (Representational State Transfer), RSS (Really Simple Syndication ) e AJAX (Atom syndication and Asynchronous JavaScript and XML).</span><span class="sxs-lookup"><span data-stu-id="4ee7f-147">These scenarios include "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) and Atom syndication, and Asynchronous JavaScript and XML (AJAX).</span></span> <span data-ttu-id="4ee7f-148">Il codificatore di messaggi composto non supporta SOAP o WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-148">The composite message encoder does not support SOAP or WS-Addressing.</span></span>  
  
 <span data-ttu-id="4ee7f-149">L'elemento di associazione può essere configurato con una codifica dei caratteri di scrittura mediante l'attributo `writeEncoding`.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-149">The binding element can be configured with a write character encoding by using the `writeEncoding` attribute.</span></span> <span data-ttu-id="4ee7f-150">Il valore <xref:System.Text.Encoding> fornito specifica il comportamento in scrittura per le codifiche JSON e XML di testo.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-150">The supplied <xref:System.Text.Encoding> value specifies the behavior on write for the JSON and Textual XML cases.</span></span> <span data-ttu-id="4ee7f-151">In lettura viene interpretata qualsiasi codifica di messaggi e codifica di testo valida.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-151">On read, any valid message encoding and text encoding is understood.</span></span>  
  
 `maxReadPoolSize` <span data-ttu-id="4ee7f-152">e `maxWritePoolSize` consente inoltre di impostare il numero massimo di lettori e writer da allocare rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-152">and `maxWritePoolSize` can also be used to set the maximum number of readers and writers to be allocated respectively.</span></span> <span data-ttu-id="4ee7f-153">Per impostazione predefinita vengono allocati 64 lettori e 16 writer.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-153">By default 64 readers and 16 writers are allocated.</span></span>  
  
 <span data-ttu-id="4ee7f-154">Vincoli di complessità predefiniti vengono inoltre impostati usando il [ \<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) elemento per la protezione da una classe di tipo denial of service (DOS) attacchi che tentano di utilizzare la complessità dei messaggi per bloccare l'elaborazione di endpoint risorse.</span><span class="sxs-lookup"><span data-stu-id="4ee7f-154">Default complexity constraints are also set using the [\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) element to protect against a class of denial of service (DOS) attacks that attempt to use message complexity to tie up endpoint processing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ee7f-155">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ee7f-155">Example</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="256"
                    maxWritePoolSize="128"
                    messageVersion="None"
                    textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="4ee7f-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ee7f-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [<span data-ttu-id="4ee7f-157">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="4ee7f-157">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="4ee7f-158">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="4ee7f-158">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="4ee7f-159">Associazioni</span><span class="sxs-lookup"><span data-stu-id="4ee7f-159">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="4ee7f-160">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="4ee7f-160">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4ee7f-161">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="4ee7f-161">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4ee7f-162">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4ee7f-162">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
