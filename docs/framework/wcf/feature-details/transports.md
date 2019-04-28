---
title: Trasporti in Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 6bb8e8b90c26533661684bd403b9ec439f1bb37e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61933731"
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="46246-102">Trasporti in Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="46246-102">Transports in Windows Communication Foundation</span></span>
<span data-ttu-id="46246-103">Il livello di trasporto è al livello più basso dello stack dei canali.</span><span class="sxs-lookup"><span data-stu-id="46246-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="46246-104">I trasporti principali usati in Windows Communication Foundation (WCF) sono HTTP, HTTPS, TCP e named pipe.</span><span class="sxs-lookup"><span data-stu-id="46246-104">The main transports used in Windows Communication Foundation (WCF) are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="46246-105">Negli argomenti di questa sezione vengono fornite informazioni sulla scelta fra questi trasporti, la configurazione del trasporto e l'impostazione delle proprietà di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="46246-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 <span data-ttu-id="46246-106">WCF sono inclusi trasporti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="46246-106">WCF includes additional transports.</span></span> <span data-ttu-id="46246-107">Per informazioni sul trasporto Accodamento messaggi (noto anche come MSMQ), vedere [code e sessioni affidabili](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="46246-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="46246-108">Per informazioni sul trasporto peer-to-peer, vedere [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="46246-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="46246-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="46246-109">In This Section</span></span>  
 [<span data-ttu-id="46246-110">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="46246-110">Choosing a Transport</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 <span data-ttu-id="46246-111">Descrive i tre trasporti principali con gli aspetti da considerare in fase di selezione.</span><span class="sxs-lookup"><span data-stu-id="46246-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="46246-112">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="46246-112">Choosing a Message Encoder</span></span>](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 <span data-ttu-id="46246-113">Descrive i fattori da considerare nella scelta di un elemento di associazione di codifica dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="46246-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="46246-114">Trasferimento di messaggi di flusso</span><span class="sxs-lookup"><span data-stu-id="46246-114">Streaming Message Transfer</span></span>](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 <span data-ttu-id="46246-115">Descrive come configurare il livello del trasporto per l'esecuzione del flusso.</span><span class="sxs-lookup"><span data-stu-id="46246-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="46246-116">Configurazione di HTTP e HTTPS</span><span class="sxs-lookup"><span data-stu-id="46246-116">Configuring HTTP and HTTPS</span></span>](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 <span data-ttu-id="46246-117">Descrive come configurare gli elementi di associazione del trasporto HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="46246-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="46246-118">Procedura: Sostituire la prenotazione URL WCF con una prenotazione limitata</span><span class="sxs-lookup"><span data-stu-id="46246-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="46246-119">Viene descritto come utilizzare le prenotazioni WCFURL limitato.</span><span class="sxs-lookup"><span data-stu-id="46246-119">Describes how to use WCFURL restricted reservations.</span></span>  
  
 [<span data-ttu-id="46246-120">Quote dei trasporti</span><span class="sxs-lookup"><span data-stu-id="46246-120">Transport Quotas</span></span>](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 <span data-ttu-id="46246-121">Vengono fornite considerazioni per l'impostazione delle quote disponibili nel livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="46246-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="46246-122">Uso di NAT e firewall</span><span class="sxs-lookup"><span data-stu-id="46246-122">Working with NATs and Firewalls</span></span>](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 <span data-ttu-id="46246-123">Descrive come configurare il livello di trasporto quando i messaggi vengono inviati o ricevuti attraverso un firewall o quando si utilizza la conversione degli indirizzi di rete (NAT).</span><span class="sxs-lookup"><span data-stu-id="46246-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="46246-124">Condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="46246-124">Net.TCP Port Sharing</span></span>](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 <span data-ttu-id="46246-125">Viene descritto come utilizzare il componente di condivisione delle porte Net. TCP di WCF.</span><span class="sxs-lookup"><span data-stu-id="46246-125">Describes how to use the Net.TCP Port Sharing component of WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="46246-126">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="46246-126">Reference</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="46246-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="46246-127">Related Sections</span></span>  
 [<span data-ttu-id="46246-128">Associazioni</span><span class="sxs-lookup"><span data-stu-id="46246-128">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [<span data-ttu-id="46246-129">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="46246-129">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
