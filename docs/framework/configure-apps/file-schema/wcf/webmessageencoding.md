---
title: '&lt;webMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: fc1f83128dacb588d8179dea95c132da1ab2be91
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltwebmessageencodinggt"></a><span data-ttu-id="5d0a6-102">&lt;webMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="5d0a6-102">&lt;webMessageEncoding&gt;</span></span>
<span data-ttu-id="5d0a6-103">Consente alle codifiche di messaggi XML di testo normale e JSON (JavaScript Object Notation) e al contenuto binario "non elaborato" di essere letti e scritti quando vengono usati in un'associazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5d0a6-103">Enables plain-text XML, JavaScript Object Notation (JSON) message encodings and "raw" binary content to be read and written when used in a Windows Communication Foundation (WCF) binding.</span></span>  
  
 <span data-ttu-id="5d0a6-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5d0a6-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5d0a6-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="5d0a6-105">\<bindings></span></span>  
<span data-ttu-id="5d0a6-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5d0a6-106">\<customBinding></span></span>  
<span data-ttu-id="5d0a6-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5d0a6-107">\<binding></span></span>  
<span data-ttu-id="5d0a6-108">\<webMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="5d0a6-108">\<webMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d0a6-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d0a6-109">Syntax</span></span>  
  
```xml  
<webMessageEncoding   
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
  
writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d0a6-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5d0a6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5d0a6-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d0a6-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="5d0a6-112">Attributes</span></span>  
  
|<span data-ttu-id="5d0a6-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="5d0a6-113">Attribute</span></span>|<span data-ttu-id="5d0a6-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d0a6-114">Description</span></span>|  
|---------------|-----------------|  
|`maxReadPoolSize`|<span data-ttu-id="5d0a6-115">Numero di messaggi che è possibile leggere contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-115">The amount of messages that can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="5d0a6-116">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="5d0a6-117">L'impostazione predefinita è 64 lettori per ogni codificatore interno (testo, JSON e "non elaborato").</span><span class="sxs-lookup"><span data-stu-id="5d0a6-117">The default is 64 readers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="5d0a6-118">Sebbene l'aumento di questo numero determini un maggiore consumo di memoria, in questo modo il codificatore sarà in grado di gestire picchi improvvisi di messaggi in arrivo usando i lettori del pool già creati anziché crearne di nuovi.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-118">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of incoming messages because it is able to use readers from the pool that are already created instead of creating new ones.</span></span>|  
|`maxWritePoolSize`|<span data-ttu-id="5d0a6-119">Numero di messaggi che è possibile inviare contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-119">The amount of messages that can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="5d0a6-120">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="5d0a6-121">L'impostazione predefinita è 16 writer per ogni codificatore interno (testo, JSON e "non elaborato").</span><span class="sxs-lookup"><span data-stu-id="5d0a6-121">The default is 16 writers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="5d0a6-122">Sebbene l'aumento di questo numero determini un maggiore consumo di memoria, in questo modo il codificatore sarà in grado di gestire picchi improvvisi di messaggi in uscita usando i writer del pool già creati anziché crearne di nuovi.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-122">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of outgoing messages because it is able to use writers from the pool that are already created instead of creating new ones.</span></span>|  
|`writeEncoding`|<span data-ttu-id="5d0a6-123">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-123">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="5d0a6-124">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="5d0a6-124">Valid values are:</span></span><br /><br /> <span data-ttu-id="5d0a6-125">-UnicodeFffeTextEncoding: Codifica Unicode Big Endian.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-125">-   UnicodeFffeTextEncoding: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="5d0a6-126">-Utf16TextEncoding: Codifica Unicode.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-126">-   Utf16TextEncoding: Unicode encoding.</span></span><br /><span data-ttu-id="5d0a6-127">-Utf8TextEncoding: codifica a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-127">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="5d0a6-128">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-128">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="5d0a6-129">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-129">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d0a6-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5d0a6-130">Child Elements</span></span>  
  
|<span data-ttu-id="5d0a6-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d0a6-131">Element</span></span>|<span data-ttu-id="5d0a6-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d0a6-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d0a6-133">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="5d0a6-133">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="5d0a6-134">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-134">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="5d0a6-135">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-135">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d0a6-136">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5d0a6-136">Parent Elements</span></span>  
  
|<span data-ttu-id="5d0a6-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d0a6-137">Element</span></span>|<span data-ttu-id="5d0a6-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d0a6-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d0a6-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="5d0a6-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="5d0a6-140">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-140">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d0a6-141">Note</span><span class="sxs-lookup"><span data-stu-id="5d0a6-141">Remarks</span></span>  
 <span data-ttu-id="5d0a6-142">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-142">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="5d0a6-143">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-143">Decoding is the reverse process.</span></span> <span data-ttu-id="5d0a6-144">Questi processi richiedono la specifica di una codifica caratteri.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-144">These processes require the specification of a character encoding.</span></span>  
  
 <span data-ttu-id="5d0a6-145">L'elemento `webMessageEncoding` delega a una serie di codificatori interni la gestione di codifiche XML di testo normale e JSON e dati binari non elaborati.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-145">The `webMessageEncoding` element works by delegating to a series of inner encoders to handle the plain-text XML and JSON encodings, and "raw" binary data.</span></span> <span data-ttu-id="5d0a6-146">Questa delega viene eseguita mediante un codificatore di messaggi composto.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-146">This delegation is done by a composite message encoder.</span></span>  
  
 <span data-ttu-id="5d0a6-147">Questo elemento di associazione e il relativo codificatore composto vengono usati per controllare la codifica in scenari che non usano la messaggistica SOAP usata dall'elemento `webHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-147">This binding element and its composite encoder are used to control the encoding in scenarios that do not use SOAP messaging used by the `webHttpBinding` element.</span></span> <span data-ttu-id="5d0a6-148">Questi scenari includono POX (Plain Old XML), REST (Representational State Transfer), RSS (Really Simple Syndication ) e AJAX (Atom syndication and Asynchronous JavaScript and XML).</span><span class="sxs-lookup"><span data-stu-id="5d0a6-148">These scenarios include "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) and Atom syndication, and Asynchronous JavaScript and XML (AJAX).</span></span> <span data-ttu-id="5d0a6-149">Il codificatore di messaggi composto non supporta SOAP o WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-149">The composite message encoder does not support SOAP or WS-Addressing.</span></span>  
  
 <span data-ttu-id="5d0a6-150">L'elemento di associazione può essere configurato con una codifica dei caratteri di scrittura mediante l'attributo `writeEncoding`.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-150">The binding element can be configured with a write character encoding by using the `writeEncoding` attribute.</span></span> <span data-ttu-id="5d0a6-151">Il valore <xref:System.Text.Encoding> fornito specifica il comportamento in scrittura per le codifiche JSON e XML di testo.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-151">The supplied <xref:System.Text.Encoding> value specifies the behavior on write for the JSON and Textual XML cases.</span></span> <span data-ttu-id="5d0a6-152">In lettura viene interpretata qualsiasi codifica di messaggi e codifica di testo valida.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-152">On read, any valid message encoding and text encoding is understood.</span></span>  
  
 <span data-ttu-id="5d0a6-153">Le proprietà `maxReadPoolSize` e `maxWritePoolSize` possono inoltre essere usate per impostare rispettivamente il numero massimo di lettori e il numero massimo di writer da allocare.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-153">`maxReadPoolSize` and `maxWritePoolSize` can also be used to set the maximum number of readers and writers to be allocated respectively.</span></span> <span data-ttu-id="5d0a6-154">Per impostazione predefinita vengono allocati 64 lettori e 16 writer.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-154">By default 64 readers and 16 writers are allocated.</span></span>  
  
 <span data-ttu-id="5d0a6-155">Vincoli di complessità predefiniti vengono inoltre impostati utilizzando il [ \<readerQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) elemento per la protezione da una classe di tipo denial of service (DOS) attacchi che tentano di utilizzare la complessità dei messaggi per bloccare l'elaborazione di endpoint risorse.</span><span class="sxs-lookup"><span data-stu-id="5d0a6-155">Default complexity constraints are also set using the [\<readerQuotas>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) element to protect against a class of denial of service (DOS) attacks that attempt to use message complexity to tie up endpoint processing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d0a6-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="5d0a6-156">Example</span></span>  
  
```xml  
<webMessageEncoding   
    maxReadPoolSize="256"  
    maxWritePoolSize="128"  
    messageVersion="None"  
    textEncoding="utf-8"   
/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d0a6-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d0a6-157">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>  
 [<span data-ttu-id="5d0a6-158">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="5d0a6-158">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="5d0a6-159">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="5d0a6-159">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="5d0a6-160">Associazioni</span><span class="sxs-lookup"><span data-stu-id="5d0a6-160">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="5d0a6-161">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="5d0a6-161">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="5d0a6-162">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="5d0a6-162">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="5d0a6-163">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5d0a6-163">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
