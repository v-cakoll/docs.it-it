---
title: Trasporti in Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 077d63d8038b245a68083611897c1e6c68971071
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598671"
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="96f99-102">Trasporti in Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="96f99-102">Transports in Windows Communication Foundation</span></span>
<span data-ttu-id="96f99-103">Il livello di trasporto è al livello più basso dello stack dei canali.</span><span class="sxs-lookup"><span data-stu-id="96f99-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="96f99-104">I trasporti principali utilizzati in Windows Communication Foundation (WCF) sono HTTP, HTTPS, TCP e named pipe.</span><span class="sxs-lookup"><span data-stu-id="96f99-104">The main transports used in Windows Communication Foundation (WCF) are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="96f99-105">Negli argomenti di questa sezione vengono fornite informazioni sulla scelta fra questi trasporti, la configurazione del trasporto e l'impostazione delle proprietà di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="96f99-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 <span data-ttu-id="96f99-106">WCF include trasporti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="96f99-106">WCF includes additional transports.</span></span> <span data-ttu-id="96f99-107">Per informazioni sul trasporto di Accodamento messaggi (noto anche come MSMQ), vedere [code e sessioni affidabili](queues-and-reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="96f99-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="96f99-108">Per informazioni sul trasporto peer-to-peer, vedere la pagina relativa [alla rete peer-to-peer](peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="96f99-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96f99-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="96f99-109">In This Section</span></span>  
 [<span data-ttu-id="96f99-110">Scelta di un trasporto</span><span class="sxs-lookup"><span data-stu-id="96f99-110">Choosing a Transport</span></span>](choosing-a-transport.md)  
 <span data-ttu-id="96f99-111">Descrive i tre trasporti principali con gli aspetti da considerare in fase di selezione.</span><span class="sxs-lookup"><span data-stu-id="96f99-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="96f99-112">Scelta di un codificatore di messaggi</span><span class="sxs-lookup"><span data-stu-id="96f99-112">Choosing a Message Encoder</span></span>](choosing-a-message-encoder.md)  
 <span data-ttu-id="96f99-113">Descrive i fattori da considerare nella scelta di un elemento di associazione di codifica dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="96f99-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="96f99-114">Trasferimento dei messaggi di flusso</span><span class="sxs-lookup"><span data-stu-id="96f99-114">Streaming Message Transfer</span></span>](streaming-message-transfer.md)  
 <span data-ttu-id="96f99-115">Descrive come configurare il livello del trasporto per l'esecuzione del flusso.</span><span class="sxs-lookup"><span data-stu-id="96f99-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="96f99-116">Configurazione di HTTP e HTTPS</span><span class="sxs-lookup"><span data-stu-id="96f99-116">Configuring HTTP and HTTPS</span></span>](configuring-http-and-https.md)  
 <span data-ttu-id="96f99-117">Descrive come configurare gli elementi di associazione del trasporto HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="96f99-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="96f99-118">Procedura: Sostituire la prenotazione URL WCF con una prenotazione limitata</span><span class="sxs-lookup"><span data-stu-id="96f99-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="96f99-119">Viene descritto come usare le prenotazioni con restrizioni WCFURL.</span><span class="sxs-lookup"><span data-stu-id="96f99-119">Describes how to use WCFURL restricted reservations.</span></span>  
  
 [<span data-ttu-id="96f99-120">Quote dei trasporti</span><span class="sxs-lookup"><span data-stu-id="96f99-120">Transport Quotas</span></span>](transport-quotas.md)  
 <span data-ttu-id="96f99-121">Vengono fornite considerazioni per l'impostazione delle quote disponibili nel livello di trasporto.</span><span class="sxs-lookup"><span data-stu-id="96f99-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="96f99-122">Uso di conversioni NAT e firewall</span><span class="sxs-lookup"><span data-stu-id="96f99-122">Working with NATs and Firewalls</span></span>](working-with-nats-and-firewalls.md)  
 <span data-ttu-id="96f99-123">Descrive come configurare il livello di trasporto quando i messaggi vengono inviati o ricevuti attraverso un firewall o quando si utilizza la conversione degli indirizzi di rete (NAT).</span><span class="sxs-lookup"><span data-stu-id="96f99-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="96f99-124">Condivisione delle porte Net.TCP</span><span class="sxs-lookup"><span data-stu-id="96f99-124">Net.TCP Port Sharing</span></span>](net-tcp-port-sharing.md)  
 <span data-ttu-id="96f99-125">Viene descritto come utilizzare il componente di condivisione delle porte net. TCP di WCF.</span><span class="sxs-lookup"><span data-stu-id="96f99-125">Describes how to use the Net.TCP Port Sharing component of WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="96f99-126">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="96f99-126">Reference</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="96f99-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="96f99-127">Related Sections</span></span>  
 [<span data-ttu-id="96f99-128">Binding</span><span class="sxs-lookup"><span data-stu-id="96f99-128">Bindings</span></span>](bindings.md)  
  
 [<span data-ttu-id="96f99-129">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="96f99-129">Extending Bindings</span></span>](../extending/extending-bindings.md)
