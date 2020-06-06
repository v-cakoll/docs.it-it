---
title: <webMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: 4aa87acaf9080959ba8b53e3ec3216314dc745b6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732576"
---
# \<webMessageEncoding>
<span data-ttu-id="b2759-101">Consente alle codifiche di messaggi XML di testo normale e JSON (JavaScript Object Notation) e al contenuto binario "non elaborato" di essere letti e scritti quando vengono usati in un'associazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="b2759-101">Enables plain-text XML, JavaScript Object Notation (JSON) message encodings and "raw" binary content to be read and written when used in a Windows Communication Foundation (WCF) binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="b2759-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2759-102">Syntax</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="Integer"
                    maxWritePoolSize="Integer"
                    writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2759-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b2759-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b2759-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b2759-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2759-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="b2759-105">Attributes</span></span>  
  
|<span data-ttu-id="b2759-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="b2759-106">Attribute</span></span>|<span data-ttu-id="b2759-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2759-107">Description</span></span>|  
|---------------|-----------------|  
|`maxReadPoolSize`|<span data-ttu-id="b2759-108">Numero di messaggi che è possibile leggere contemporaneamente senza allocare nuovi lettori.</span><span class="sxs-lookup"><span data-stu-id="b2759-108">The amount of messages that can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="b2759-109">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="b2759-109">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="b2759-110">L'impostazione predefinita è 64 lettori per ogni codificatore interno (testo, JSON e "non elaborato").</span><span class="sxs-lookup"><span data-stu-id="b2759-110">The default is 64 readers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="b2759-111">Sebbene l'aumento di questo numero determini un maggiore consumo di memoria, in questo modo il codificatore sarà in grado di gestire picchi improvvisi di messaggi in arrivo usando i lettori del pool già creati anziché crearne di nuovi.</span><span class="sxs-lookup"><span data-stu-id="b2759-111">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of incoming messages because it is able to use readers from the pool that are already created instead of creating new ones.</span></span>|  
|`maxWritePoolSize`|<span data-ttu-id="b2759-112">Numero di messaggi che è possibile inviare contemporaneamente senza allocare nuovi writer.</span><span class="sxs-lookup"><span data-stu-id="b2759-112">The amount of messages that can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="b2759-113">Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore.</span><span class="sxs-lookup"><span data-stu-id="b2759-113">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="b2759-114">L'impostazione predefinita è 16 writer per ogni codificatore interno (testo, JSON e "non elaborato").</span><span class="sxs-lookup"><span data-stu-id="b2759-114">The default is 16 writers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="b2759-115">Sebbene l'aumento di questo numero determini un maggiore consumo di memoria, in questo modo il codificatore sarà in grado di gestire picchi improvvisi di messaggi in uscita usando i writer del pool già creati anziché crearne di nuovi.</span><span class="sxs-lookup"><span data-stu-id="b2759-115">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of outgoing messages because it is able to use writers from the pool that are already created instead of creating new ones.</span></span>|  
|`writeEncoding`|<span data-ttu-id="b2759-116">Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="b2759-116">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="b2759-117">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="b2759-117">Valid values are:</span></span><br /><br /> <span data-ttu-id="b2759-118">-UnicodeFffeTextEncoding: codifica Unicode big endian.</span><span class="sxs-lookup"><span data-stu-id="b2759-118">-   UnicodeFffeTextEncoding: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="b2759-119">-Utf16TextEncoding: codifica Unicode.</span><span class="sxs-lookup"><span data-stu-id="b2759-119">-   Utf16TextEncoding: Unicode encoding.</span></span><br /><span data-ttu-id="b2759-120">-Utf8TextEncoding: codifica a 8 bit.</span><span class="sxs-lookup"><span data-stu-id="b2759-120">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="b2759-121">L'impostazione predefinita è Utf8TextEncoding.</span><span class="sxs-lookup"><span data-stu-id="b2759-121">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="b2759-122">L'attributo è di tipo <xref:System.Text.Encoding>.</span><span class="sxs-lookup"><span data-stu-id="b2759-122">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2759-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b2759-123">Child Elements</span></span>  
  
|<span data-ttu-id="b2759-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b2759-124">Element</span></span>|<span data-ttu-id="b2759-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2759-125">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="b2759-126">Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione.</span><span class="sxs-lookup"><span data-stu-id="b2759-126">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="b2759-127">L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="b2759-127">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2759-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b2759-128">Parent Elements</span></span>  
  
|<span data-ttu-id="b2759-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="b2759-129">Element</span></span>|<span data-ttu-id="b2759-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2759-130">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="b2759-131">Definisce tutte le funzionalità di associazione dell'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b2759-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2759-132">Commenti</span><span class="sxs-lookup"><span data-stu-id="b2759-132">Remarks</span></span>  
 <span data-ttu-id="b2759-133">La codifica è il processo di trasformazione di un messaggio in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="b2759-133">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="b2759-134">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="b2759-134">Decoding is the reverse process.</span></span> <span data-ttu-id="b2759-135">Questi processi richiedono la specifica di una codifica caratteri.</span><span class="sxs-lookup"><span data-stu-id="b2759-135">These processes require the specification of a character encoding.</span></span>  
  
 <span data-ttu-id="b2759-136">L'elemento `webMessageEncoding` delega a una serie di codificatori interni la gestione di codifiche XML di testo normale e JSON e dati binari non elaborati.</span><span class="sxs-lookup"><span data-stu-id="b2759-136">The `webMessageEncoding` element works by delegating to a series of inner encoders to handle the plain-text XML and JSON encodings, and "raw" binary data.</span></span> <span data-ttu-id="b2759-137">Questa delega viene eseguita mediante un codificatore di messaggi composto.</span><span class="sxs-lookup"><span data-stu-id="b2759-137">This delegation is done by a composite message encoder.</span></span>  
  
 <span data-ttu-id="b2759-138">Questo elemento di associazione e il relativo codificatore composto vengono usati per controllare la codifica in scenari che non usano la messaggistica SOAP usata dall'elemento `webHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="b2759-138">This binding element and its composite encoder are used to control the encoding in scenarios that do not use SOAP messaging used by the `webHttpBinding` element.</span></span> <span data-ttu-id="b2759-139">Questi scenari includono POX (Plain Old XML), REST (Representational State Transfer), RSS (Really Simple Syndication ) e AJAX (Atom syndication and Asynchronous JavaScript and XML).</span><span class="sxs-lookup"><span data-stu-id="b2759-139">These scenarios include "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) and Atom syndication, and Asynchronous JavaScript and XML (AJAX).</span></span> <span data-ttu-id="b2759-140">Il codificatore di messaggi composto non supporta SOAP o WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="b2759-140">The composite message encoder does not support SOAP or WS-Addressing.</span></span>  
  
 <span data-ttu-id="b2759-141">L'elemento di associazione può essere configurato con una codifica dei caratteri di scrittura mediante l'attributo `writeEncoding`.</span><span class="sxs-lookup"><span data-stu-id="b2759-141">The binding element can be configured with a write character encoding by using the `writeEncoding` attribute.</span></span> <span data-ttu-id="b2759-142">Il valore <xref:System.Text.Encoding> fornito specifica il comportamento in scrittura per le codifiche JSON e XML di testo.</span><span class="sxs-lookup"><span data-stu-id="b2759-142">The supplied <xref:System.Text.Encoding> value specifies the behavior on write for the JSON and Textual XML cases.</span></span> <span data-ttu-id="b2759-143">In lettura viene interpretata qualsiasi codifica di messaggi e codifica di testo valida.</span><span class="sxs-lookup"><span data-stu-id="b2759-143">On read, any valid message encoding and text encoding is understood.</span></span>  
  
 <span data-ttu-id="b2759-144">Le proprietà `maxReadPoolSize` e `maxWritePoolSize` possono inoltre essere usate per impostare rispettivamente il numero massimo di lettori e il numero massimo di writer da allocare.</span><span class="sxs-lookup"><span data-stu-id="b2759-144">`maxReadPoolSize` and `maxWritePoolSize` can also be used to set the maximum number of readers and writers to be allocated respectively.</span></span> <span data-ttu-id="b2759-145">Per impostazione predefinita vengono allocati 64 lettori e 16 writer.</span><span class="sxs-lookup"><span data-stu-id="b2759-145">By default 64 readers and 16 writers are allocated.</span></span>  
  
 <span data-ttu-id="b2759-146">I vincoli di complessità predefiniti vengono inoltre impostati utilizzando l' [\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) elemento per proteggersi da una classe di attacchi Denial of Service (DOS) che tentano di utilizzare la complessità dei messaggi per bloccare le risorse di elaborazione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="b2759-146">Default complexity constraints are also set using the [\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) element to protect against a class of denial of service (DOS) attacks that attempt to use message complexity to tie up endpoint processing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2759-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2759-147">Example</span></span>  
  
```xml  
<webMessageEncoding maxReadPoolSize="256"
                    maxWritePoolSize="128"
                    messageVersion="None"
                    textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="b2759-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2759-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [<span data-ttu-id="b2759-149">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="b2759-149">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="b2759-150">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="b2759-150">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="b2759-151">Binding</span><span class="sxs-lookup"><span data-stu-id="b2759-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b2759-152">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="b2759-152">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b2759-153">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="b2759-153">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
