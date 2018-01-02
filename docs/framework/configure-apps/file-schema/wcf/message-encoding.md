---
title: Codifica dei messaggi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f30ee941-aca9-4c67-82a5-421568496f07
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b3040a16b6d167c4f066b2ddbd0a542741f88d62
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="message-encoding"></a><span data-ttu-id="e7564-102">Codifica dei messaggi</span><span class="sxs-lookup"><span data-stu-id="e7564-102">Message Encoding</span></span>
<span data-ttu-id="e7564-103">La codifica è il processo di trasformazione di un insieme di caratteri Unicode in una sequenza di byte.</span><span class="sxs-lookup"><span data-stu-id="e7564-103">Encoding is the process of transforming a set of Unicode characters into a sequence of bytes.</span></span> <span data-ttu-id="e7564-104">La decodifica è il processo inverso.</span><span class="sxs-lookup"><span data-stu-id="e7564-104">Decoding is the reverse process.</span></span> <span data-ttu-id="e7564-105">Windows Communication Foundation (WCF) include tre tipi di codifica per i messaggi SOAP, ovvero testo, binaria e MTOM (Message Transmission Optimization Mechanism).</span><span class="sxs-lookup"><span data-stu-id="e7564-105">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="e7564-106">La sezione di configurazione `binaryMessageEncoding` specifica la codifica dei caratteri e la versione dei messaggi usate per messaggi XML basati su un sistema binario.</span><span class="sxs-lookup"><span data-stu-id="e7564-106">The `binaryMessageEncoding` configuration section specifies the character encoding and message versioning used for binary-based XML messages.</span></span> <span data-ttu-id="e7564-107">Il codificatore di messaggi binario codifica messaggi di Windows Communication Foundation (WCF) in transito in formato binario.</span><span class="sxs-lookup"><span data-stu-id="e7564-107">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="e7564-108">Se da un lato questa codifica comporta una trasmissione molto veloce dei messaggi, dall'altro si perde l'interoperabilità basata sugli standard WS - *.</span><span class="sxs-lookup"><span data-stu-id="e7564-108">While this encoding results in very fast transmission of messages, interoperability based on the WS-* standards is lost.</span></span>  
  
 <span data-ttu-id="e7564-109">La sezione di configurazione `mtomMessageEncoding` specifica la codifica dei caratteri e il controllo di versione del messaggio usati per un messaggio che usa una codifica Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="e7564-109">The `mtomMessageEncoding` configuration section specifies the character encoding and message versioning used for a message using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="e7564-110">MTOM è una tecnologia efficiente per la trasmissione di dati binari nei messaggi di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e7564-110">(MTOM) is an efficient technology for transmitting binary data in Windows Communication Foundation (WCF) messages.</span></span> <span data-ttu-id="e7564-111">Il codificatore MTOM cerca un equilibrio tra efficienza e interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="e7564-111">The MTOM encoder attempts to strike a balance between efficiency and interoperability.</span></span> <span data-ttu-id="e7564-112">La codifica MTOM trasmette la maggior parte del codice XML in formato testo, ma ottimizza grandi blocchi di dati binari trasmettendoli senza introdurre modifiche e senza convertirli in formato testo.</span><span class="sxs-lookup"><span data-stu-id="e7564-112">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to text.</span></span>  
  
 <span data-ttu-id="e7564-113">La sezione di configurazione `textMessageEncoding` specifica un codificatore di testo usato per creare messaggi in transito basati su testo.</span><span class="sxs-lookup"><span data-stu-id="e7564-113">The `textMessageEncoding` configuration section specifies a text encoder used to create text-based messages on the wire.</span></span> <span data-ttu-id="e7564-114">I messaggi prodotti da questo codificatore sono adatti per l'interoperabilità basata su WS-*.</span><span class="sxs-lookup"><span data-stu-id="e7564-114">Messages produced by this encoder are suitable for WS-* based interop.</span></span> <span data-ttu-id="e7564-115">In genere il servizio Web o il client di tale servizio è in grado di comprendere codice XML in formato testo.</span><span class="sxs-lookup"><span data-stu-id="e7564-115">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="e7564-116">Tuttavia, la trasmissione di grandi blocchi di dati binari come testo è il metodo meno efficiente per la codifica di messaggi XML.</span><span class="sxs-lookup"><span data-stu-id="e7564-116">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7564-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7564-117">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 [<span data-ttu-id="e7564-118">Associazioni</span><span class="sxs-lookup"><span data-stu-id="e7564-118">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e7564-119">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="e7564-119">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="e7564-120">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="e7564-120">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="e7564-121">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e7564-121">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="e7564-122">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="e7564-122">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
