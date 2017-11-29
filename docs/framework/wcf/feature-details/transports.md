---
title: Trasporti in Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 115e2a69c7d990c7d4c59634644fb557e83ad405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="d5818-102">Trasporti in Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="d5818-102">Transports in Windows Communication Foundation</span></span>
<span data-ttu-id="d5818-103">Il livello di trasporto è al livello più basso dello stack dei canali.</span><span class="sxs-lookup"><span data-stu-id="d5818-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="d5818-104">I trasporti principali utilizzati in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sono HTTP, Https, TCP e named pipe.</span><span class="sxs-lookup"><span data-stu-id="d5818-104">The main transports used in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="d5818-105">Negli argomenti di questa sezione vengono fornite informazioni sulla scelta fra questi trasporti, la configurazione del trasporto e l'impostazione delle proprietà di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="d5818-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 <span data-ttu-id="d5818-106">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sono inclusi trasporti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="d5818-106">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] includes additional transports.</span></span> <span data-ttu-id="d5818-107">Per informazioni sul trasporto di Accodamento messaggi (noto anche come MSMQ), vedere [code e sessioni affidabili](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="d5818-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="d5818-108">Per informazioni sul trasporto peer-to-peer, vedere [rete Peer-to-Peer](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="d5818-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5818-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d5818-109">In This Section</span></span>  
 [<span data-ttu-id="d5818-110">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="d5818-110">Choosing a Transport</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 <span data-ttu-id="d5818-111">Descrive i tre trasporti principali con gli aspetti da considerare in fase di selezione.</span><span class="sxs-lookup"><span data-stu-id="d5818-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="d5818-112">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="d5818-112">Choosing a Message Encoder</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 <span data-ttu-id="d5818-113">Descrive i fattori da considerare nella scelta di un elemento di associazione di codifica dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="d5818-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="d5818-114">Trasferimento dei messaggi di flusso</span><span class="sxs-lookup"><span data-stu-id="d5818-114">Streaming Message Transfer</span></span>](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 <span data-ttu-id="d5818-115">Descrive come configurare il livello del trasporto per l'esecuzione del flusso.</span><span class="sxs-lookup"><span data-stu-id="d5818-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="d5818-116">Configurazione di HTTP e HTTPS</span><span class="sxs-lookup"><span data-stu-id="d5818-116">Configuring HTTP and HTTPS</span></span>](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 <span data-ttu-id="d5818-117">Descrive come configurare gli elementi di associazione del trasporto HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d5818-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="d5818-118">Procedura: sostituire la prenotazione URL WCF con una prenotazione limitata</span><span class="sxs-lookup"><span data-stu-id="d5818-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="d5818-119">Descrive come utilizzare le prenotazioni limitate URL di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5818-119">Describes how to use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]URL restricted reservations.</span></span>  
  
 [<span data-ttu-id="d5818-120">Quote del trasporto</span><span class="sxs-lookup"><span data-stu-id="d5818-120">Transport Quotas</span></span>](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 <span data-ttu-id="d5818-121">Vengono fornite considerazioni per l'impostazione delle quote disponibili nel livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d5818-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="d5818-122">Utilizzo di NAT e firewall</span><span class="sxs-lookup"><span data-stu-id="d5818-122">Working with NATs and Firewalls</span></span>](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 <span data-ttu-id="d5818-123">Descrive come configurare il livello di trasporto quando i messaggi vengono inviati o ricevuti attraverso un firewall o quando si utilizza la conversione degli indirizzi di rete (NAT).</span><span class="sxs-lookup"><span data-stu-id="d5818-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="d5818-124">Condivisione porta Net. TCP</span><span class="sxs-lookup"><span data-stu-id="d5818-124">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 <span data-ttu-id="d5818-125">Descrive come utilizzare il componente di condivisione porte Net.TCP di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5818-125">Describes how to use the Net.TCP Port Sharing component of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d5818-126">Riferimento</span><span class="sxs-lookup"><span data-stu-id="d5818-126">Reference</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="d5818-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="d5818-127">Related Sections</span></span>  
 [<span data-ttu-id="d5818-128">Associazioni</span><span class="sxs-lookup"><span data-stu-id="d5818-128">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [<span data-ttu-id="d5818-129">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="d5818-129">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
