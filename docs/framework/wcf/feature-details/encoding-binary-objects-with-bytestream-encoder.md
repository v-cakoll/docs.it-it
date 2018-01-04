---
title: Codifica di oggetti binari con il codificatore ByteStream
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2cf68356ffa5fe20de7bd417c77388cd214ca718
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a><span data-ttu-id="88031-102">Codifica di oggetti binari con il codificatore ByteStream</span><span class="sxs-lookup"><span data-stu-id="88031-102">Encoding Binary Objects with ByteStream Encoder</span></span>
<span data-ttu-id="88031-103">L'invio e la ricezione di dati binari non elaborati con [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] vengono configurati utilizzando <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="88031-103">Sending and receiving raw binary data with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is configured using <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>.</span></span>  
  
## <a name="byte-stream-message-encoder-architecture"></a><span data-ttu-id="88031-104">Architettura del codificatore di messaggi del flusso di byte</span><span class="sxs-lookup"><span data-stu-id="88031-104">Byte Stream Message Encoder Architecture</span></span>  
 <span data-ttu-id="88031-105">Il codificatore di messaggi binario utilizzato da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non dispone di funzionalità per l'elaborazione, la convalida o l'identificazione dei dati binari sottostanti nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="88031-105">The binary message encoder used by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] has no facility for processing, validating, or identifying the underlying binary data in the message.</span></span> <span data-ttu-id="88031-106">Il pacchetto dei dati viene codificato in XML, inviato, ricevuto e decodificato.</span><span class="sxs-lookup"><span data-stu-id="88031-106">The data package is encoded into XML, sent, received, and decoded.</span></span> <span data-ttu-id="88031-107">Il codificatore elabora i dati dopo essere passati al trasporto e prima che il messaggio venga inviato alla coda di messaggi.</span><span class="sxs-lookup"><span data-stu-id="88031-107">The encoder processes the data after being passed to the transport and before the message is sent to the message queue.</span></span> <span data-ttu-id="88031-108">A livello funzionale, il codificatore binario esegue il wrapping dei dati del messaggio negli elementi `<binary>` per l'invio e rimuove gli elementi in seguito alla ricezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="88031-108">Functionally, the binary encoder wraps the message data in `<binary>` elements for sending and removes the elements after the message is received.</span></span>  
  
## <a name="using-the-byte-stream-message-encoder"></a><span data-ttu-id="88031-109">Utilizzo del codificatore di messaggi del flusso di byte</span><span class="sxs-lookup"><span data-stu-id="88031-109">Using the Byte Stream Message Encoder</span></span>  
 <span data-ttu-id="88031-110">Nell'esempio seguente viene mostrato un contratto di servizio che implementa il codificatore di messaggi del flusso di byte.</span><span class="sxs-lookup"><span data-stu-id="88031-110">The following example shows a service contract that implements the byte stream message encoder.</span></span>  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 <span data-ttu-id="88031-111">Nell'esempio riportato di seguito viene illustrato il servizio richiamato.</span><span class="sxs-lookup"><span data-stu-id="88031-111">The following example shows the service being invoked.</span></span>  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 <span data-ttu-id="88031-112">In caso di utilizzo di un servizio che implementa un'infrastruttura di messaggi (ad esempio, un router), il messaggio viene elaborato senza controllo, convalida o interazione con il messaggio, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="88031-112">In the case of using a service that implements a message infrastructure (such as a router), the message is processed without inspecting, validating, or otherwise interacting with the message, as shown in the following example.</span></span>  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a><span data-ttu-id="88031-113">Scenari</span><span class="sxs-lookup"><span data-stu-id="88031-113">Scenarios</span></span>  
 <span data-ttu-id="88031-114">Il codificatore del flusso di byte è utile negli scenari seguenti.</span><span class="sxs-lookup"><span data-stu-id="88031-114">The Byte Stream Encoder is useful in the following scenarios.</span></span>  
  
-   <span data-ttu-id="88031-115">Trasferimento di un'immagine JPEG tra computer mediante [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88031-115">Transferring a JPEG image between computers using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="88031-116">In questo scenario l'immagine arriva tramite il trasporto da un'origine esterna e i dati inviati saranno i byte non elaborati che costituiscono l'immagine.</span><span class="sxs-lookup"><span data-stu-id="88031-116">In this scenario, the image will arrive through the transport from an outside source, and the data sent will be the raw bytes that make up the image.</span></span> <span data-ttu-id="88031-117">Un servizio riceverà i dati binari e visualizzerà l'immagine.</span><span class="sxs-lookup"><span data-stu-id="88031-117">A service will receive the binary data and display the image.</span></span>  
  
-   <span data-ttu-id="88031-118">Lettura delle informazioni al di fuori di una coda di messaggi ed elaborazione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="88031-118">Reading information out of a message queue and processing it.</span></span> <span data-ttu-id="88031-119">Il messaggio verrà letto da un gestore delle code di messaggi e verrà passato al canale della coda di messaggi per essere gestito.</span><span class="sxs-lookup"><span data-stu-id="88031-119">The message will be read from a message queue manager, and passed up the message queue channel to be handled.</span></span> <span data-ttu-id="88031-120">Il canale della coda di messaggi fungerà da gestore delle code nello stack di canali di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88031-120">The message queue channel will act as a queue manager in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] channel stack.</span></span>  
  
 <span data-ttu-id="88031-121">In caso di invio di un messaggio tramite un canale della coda di messaggi, il mittente non avrà alcun controllo sui byte ricevuti dal gestore delle code.</span><span class="sxs-lookup"><span data-stu-id="88031-121">In the case of sending a message over a message queue channel, the sender has no control over the bytes received from the queue manager.</span></span> <span data-ttu-id="88031-122">Se il processo di ricezione non è in grado di leggere i byte non elaborati, il messaggio verrà ricevuto in un formato non corretto e non verrà elaborato. Si presuppone che il processo di ricezione sia in grado di convertire i byte ricevuti in un formato utilizzabile.</span><span class="sxs-lookup"><span data-stu-id="88031-122">If the receiving process has no capability to read raw bytes, the message will be received as badly formatted and will not be processed; it is assumed that the receiving process will have the capability of translating the received bytes back into a usable format.</span></span>
