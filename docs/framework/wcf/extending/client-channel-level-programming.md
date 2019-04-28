---
title: Programmazione a livello di canale client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3b787719-4e77-4e77-96a6-5b15a11b995a
ms.openlocfilehash: ea56c99d7d122dd20fc217f8ecb2937bcf81bec3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923266"
---
# <a name="client-channel-level-programming"></a><span data-ttu-id="df35b-102">Programmazione a livello di canale client</span><span class="sxs-lookup"><span data-stu-id="df35b-102">Client Channel-Level Programming</span></span>
<span data-ttu-id="df35b-103">In questo argomento viene descritto come scrivere un'applicazione client Windows Communication Foundation (WCF) senza usare il <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> classe e il modello a oggetti associato.</span><span class="sxs-lookup"><span data-stu-id="df35b-103">This topic describes how to write a Windows Communication Foundation (WCF) client application without using the <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> class and its associated object model.</span></span>  
  
## <a name="sending-messages"></a><span data-ttu-id="df35b-104">Invio di messaggi</span><span class="sxs-lookup"><span data-stu-id="df35b-104">Sending Messages</span></span>  
 <span data-ttu-id="df35b-105">Per l'invio di messaggi e la ricezione e l'elaborazione di risposte è necessario eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="df35b-105">To be ready to send messages and receive and process replies, the following steps are required:</span></span>  
  
1. <span data-ttu-id="df35b-106">Creare un'associazione.</span><span class="sxs-lookup"><span data-stu-id="df35b-106">Create a binding.</span></span>  
  
2. <span data-ttu-id="df35b-107">Generare una channel factory.</span><span class="sxs-lookup"><span data-stu-id="df35b-107">Build a channel factory.</span></span>  
  
3. <span data-ttu-id="df35b-108">Creare un canale.</span><span class="sxs-lookup"><span data-stu-id="df35b-108">Create a channel.</span></span>  
  
4. <span data-ttu-id="df35b-109">Inviare una richiesta e leggere la riposta.</span><span class="sxs-lookup"><span data-stu-id="df35b-109">Send a request and read the reply.</span></span>  
  
5. <span data-ttu-id="df35b-110">Chiudere tutti gli oggetti canale.</span><span class="sxs-lookup"><span data-stu-id="df35b-110">Close all channel objects.</span></span>  
  
#### <a name="creating-a-binding"></a><span data-ttu-id="df35b-111">Creazione di un'associazione</span><span class="sxs-lookup"><span data-stu-id="df35b-111">Creating a Binding</span></span>  
 <span data-ttu-id="df35b-112">Analogamente al caso di ricezione (vedere [canale del servizio a livello di programmazione](../../../../docs/framework/wcf/extending/service-channel-level-programming.md)), l'invio di messaggi inizia creando un'associazione.</span><span class="sxs-lookup"><span data-stu-id="df35b-112">Similar to the receiving case (see [Service Channel-Level Programming](../../../../docs/framework/wcf/extending/service-channel-level-programming.md)), sending messages starts by creating a binding.</span></span> <span data-ttu-id="df35b-113">In questo esempio viene creato un nuovo <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> e viene aggiunto un <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> alla rispettiva raccolta di elementi.</span><span class="sxs-lookup"><span data-stu-id="df35b-113">This example creates a new <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> and adds an <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> to its Elements collection.</span></span>  
  
#### <a name="building-a-channelfactory"></a><span data-ttu-id="df35b-114">Generare una channel factory.</span><span class="sxs-lookup"><span data-stu-id="df35b-114">Building a ChannelFactory</span></span>  
 <span data-ttu-id="df35b-115">Anziché creare un <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType>, questa volta è necessario creare una <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> chiamando <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType> nell'associazione dove il parametro del tipo è <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="df35b-115">Instead of creating a <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType>, this time we create a <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> by calling <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType> on the binding where the type parameter is <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>.</span></span> <span data-ttu-id="df35b-116">Mentre i listener del canale vengono utilizzati dalla parte in attesa di messaggi in arrivo, le channel factory vengono utilizzate dalla parte che inizia la comunicazione per creare un canale.</span><span class="sxs-lookup"><span data-stu-id="df35b-116">While channel listeners are used by the side that waits for incoming messages, channel factories are used by the side that initiates the communication to create a channel.</span></span> <span data-ttu-id="df35b-117">Esattamente come i listener del canale, le channel factory devono essere aperte prima di poter essere utilizzate.</span><span class="sxs-lookup"><span data-stu-id="df35b-117">Just like channel listeners, channel factories must be opened first before they can be used.</span></span>  
  
#### <a name="creating-a-channel"></a><span data-ttu-id="df35b-118">Creazione di un canale</span><span class="sxs-lookup"><span data-stu-id="df35b-118">Creating a Channel</span></span>  
 <span data-ttu-id="df35b-119">È necessario quindi chiamare <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> per creare un <xref:System.ServiceModel.Channels.IRequestChannel>.</span><span class="sxs-lookup"><span data-stu-id="df35b-119">We then call <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> to create an <xref:System.ServiceModel.Channels.IRequestChannel>.</span></span> <span data-ttu-id="df35b-120">Questa chiamata prende l'indirizzo dell'endpoint con il quale si vuole comunicare utilizzando il nuovo canale creato.</span><span class="sxs-lookup"><span data-stu-id="df35b-120">This call takes the address of the endpoint with which we want to communicate using the new channel being created.</span></span> <span data-ttu-id="df35b-121">Quando viene ottenuto un canale, è necessario chiamare Open su di esso per renderlo pronto per la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="df35b-121">Once we have a channel, we call Open on it to put it in a state ready for communication.</span></span> <span data-ttu-id="df35b-122">A seconda della natura del trasporto, con questa chiamata a Open viene avviata una connessione con l'endpoint di destinazione oppure non viene eseguita alcuna operazione nella rete.</span><span class="sxs-lookup"><span data-stu-id="df35b-122">Depending on the nature of the transport, this call to Open may initiate a connection with the target endpoint or may do nothing at all on the network.</span></span>  
  
#### <a name="sending-a-request-and-reading-the-reply"></a><span data-ttu-id="df35b-123">Invio di una richiesta e lettura della risposta</span><span class="sxs-lookup"><span data-stu-id="df35b-123">Sending a Request and Reading the Reply</span></span>  
 <span data-ttu-id="df35b-124">Dopo che un canale è stato aperto, è possibile creare un messaggio e utilizzare il metodo di richiesta del canale per inviare la richiesta e attendere la risposta.</span><span class="sxs-lookup"><span data-stu-id="df35b-124">Once we have an opened channel, we can create a message and use the channel’s Request method to send the request and wait for the reply to come back.</span></span> <span data-ttu-id="df35b-125">Questo metodo restituisce un messaggio di risposta che è possibile leggere per scoprire quale è stata la risposta dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="df35b-125">When this method returns, we have a reply message that we can read to find out what the endpoint’s reply was.</span></span>  
  
#### <a name="closing-objects"></a><span data-ttu-id="df35b-126">Chiusura di oggetti</span><span class="sxs-lookup"><span data-stu-id="df35b-126">Closing Objects</span></span>  
 <span data-ttu-id="df35b-127">Per evitare la perdita di risorse, è necessario chiudere gli oggetti utilizzati nelle comunicazioni quando non sono più necessari.</span><span class="sxs-lookup"><span data-stu-id="df35b-127">To avoid leaking resources, we close objects used in communications when they are no longer required.</span></span>  
  
 <span data-ttu-id="df35b-128">Nell'esempio di codice seguente viene illustrato un client di base che utilizza la channel factory per inviare un messaggio e leggere la risposta.</span><span class="sxs-lookup"><span data-stu-id="df35b-128">The following code example shows a basic client using the channel factory to send a message and read the reply.</span></span>  
  
 [!code-csharp[ChannelProgrammingBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/clientprogram.cs#2)]
 [!code-vb[ChannelProgrammingBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/clientprogram.vb#2)]
