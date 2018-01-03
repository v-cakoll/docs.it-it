---
title: Informazioni sullo spazio dei nomi System.Net.PeerToPeer.Collaboration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5d8c1c1-6844-4947-9759-c7f1b564bded
caps.latest.revision: "4"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 24571209673d7706955bdb9ffbe21ad6da98e18a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="about-the-systemnetpeertopeercollaboration-namespace"></a><span data-ttu-id="70a85-102">Informazioni sullo spazio dei nomi System.Net.PeerToPeer.Collaboration</span><span class="sxs-lookup"><span data-stu-id="70a85-102">About the System.Net.PeerToPeer.Collaboration Namespace</span></span>
<span data-ttu-id="70a85-103">Lo spazio dei nomi <xref:System.Net.PeerToPeer.Collaboration> offre classi e API che consentono di implementare attività di collaborazione peer usando l'infrastruttura di collaborazione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="70a85-103">The <xref:System.Net.PeerToPeer.Collaboration> namespace provides classes and APIs that are used to implement peer collaboration activities using the Peer-to-Peer Collaboration Infrastructure.</span></span>  
  
## <a name="classes"></a><span data-ttu-id="70a85-104">Classi</span><span class="sxs-lookup"><span data-stu-id="70a85-104">Classes</span></span>  
 <span data-ttu-id="70a85-105">Le principali classi usate nell'implementazione di un'attività di collaborazione peer-to-peer sono:</span><span class="sxs-lookup"><span data-stu-id="70a85-105">The main classes used in the implementation of a Peer-to-Peer Collaboration activity are:</span></span>  
  
-   <span data-ttu-id="70a85-106"><xref:System.Net.PeerToPeer.Collaboration.ContactManager>, che consente di archiviare i contatti peer.</span><span class="sxs-lookup"><span data-stu-id="70a85-106">The <xref:System.Net.PeerToPeer.Collaboration.ContactManager>, which can be used to store peer contacts.</span></span>  
  
-   <span data-ttu-id="70a85-107"><xref:System.Net.PeerToPeer.Collaboration.PeerApplication>, in cui è possibile collaborare, ad esempio un gioco, un client di chat o una soluzione di gestione delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="70a85-107">The <xref:System.Net.PeerToPeer.Collaboration.PeerApplication> in which to collaborate, such as a game, chat client, or conferencing solution.</span></span>  
  
-   <span data-ttu-id="70a85-108">I peer che collaboreranno in un'attività</span><span class="sxs-lookup"><span data-stu-id="70a85-108">The peers that will be collaborating in an activity.</span></span>  <span data-ttu-id="70a85-109">e che possono essere rappresentati come <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe> o oggetti <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint>.</span><span class="sxs-lookup"><span data-stu-id="70a85-109">These peers can be represented as <xref:System.Net.PeerToPeer.Collaboration.PeerContact>, <xref:System.Net.PeerToPeer.Collaboration.PeerNearMe>, or <xref:System.Net.PeerToPeer.Collaboration.PeerEndPoint> objects.</span></span>  
  
-   <span data-ttu-id="70a85-110">La stessa classe statica <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration>, che specifica le applicazioni disponibili e i peer partecipanti ad ognuna di esse.</span><span class="sxs-lookup"><span data-stu-id="70a85-110">The static <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> class itself, which specifies which applications are available and which peers are participating in them.</span></span>  
  
 <span data-ttu-id="70a85-111">Per invitare i peer a una sessione di collaborazione vengono usati i metodi <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A>.</span><span class="sxs-lookup"><span data-stu-id="70a85-111">The <xref:System.Net.PeerToPeer.Collaboration.PeerContact.Invite%2A> methods are used to invite peers to a collaboration session.</span></span>  <span data-ttu-id="70a85-112">Un peer chiamante può sottoscrivere un altro peer a eventi che segnalano aggiornamenti a un oggetto o a un'applicazione o forniscono informazioni di presenza associate alla sessione di collaborazione.</span><span class="sxs-lookup"><span data-stu-id="70a85-112">A calling peer can subscribe to another peer for events that signal updates to application, object, or presence information affiliated with the collaboration session.</span></span> <span data-ttu-id="70a85-113">Le classi di presenza specificano se un <xref:System.Net.PeerToPeer.Collaboration.Peer> è disponibile per la collaborazione, mentre la classe <xref:System.Net.PeerToPeer.Collaboration.PeerScope> consente di specificare il tipo partecipazione consentita per un peer: <xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet> (globale), <xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe>, (subnet) o <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None>.</span><span class="sxs-lookup"><span data-stu-id="70a85-113">Presence classes specify whether a <xref:System.Net.PeerToPeer.Collaboration.Peer> is available for collaboration, and the <xref:System.Net.PeerToPeer.Collaboration.PeerScope> class is used to specify how much participation is allowed for a peer:  <xref:System.Net.PeerToPeer.Collaboration.PeerScope.Internet> (global), <xref:System.Net.PeerToPeer.Collaboration.PeerScope.NearMe>, (subnet) or <xref:System.Net.PeerToPeer.Collaboration.PeerScope.None>.</span></span>  
  
 <span data-ttu-id="70a85-114">Una sessione di collaborazione si articola in quattro passaggi:</span><span class="sxs-lookup"><span data-stu-id="70a85-114">A collaboration session is comprised of four steps:</span></span>  
  
-   <span data-ttu-id="70a85-115">Individuazione.</span><span class="sxs-lookup"><span data-stu-id="70a85-115">Discovery.</span></span> <span data-ttu-id="70a85-116">Individuare o pubblicare le applicazioni, i peer e le informazioni di presenza.</span><span class="sxs-lookup"><span data-stu-id="70a85-116">Discover or publish applications, peers, and presence information.</span></span>  <span data-ttu-id="70a85-117">Ad esempio, trovare altre persone nella subnet locale con lo stesso gioco installato.</span><span class="sxs-lookup"><span data-stu-id="70a85-117">For instance, find other people on the local subnet that have the same games installed.</span></span>  
  
-   <span data-ttu-id="70a85-118">Invito.</span><span class="sxs-lookup"><span data-stu-id="70a85-118">Invitation.</span></span> <span data-ttu-id="70a85-119">Inviare e accettare inviti protetti a peer remoti per avviare o partecipare a sessioni <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration>.</span><span class="sxs-lookup"><span data-stu-id="70a85-119">Send and accept secure invitations for remote peer(s) to start or join <xref:System.Net.PeerToPeer.Collaboration.PeerCollaboration> sessions.</span></span>  
  
-   <span data-ttu-id="70a85-120">Gestione dei contatti.</span><span class="sxs-lookup"><span data-stu-id="70a85-120">Contact Management.</span></span> <span data-ttu-id="70a85-121">Aggiungere i peer individuati come contatti a <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.</span><span class="sxs-lookup"><span data-stu-id="70a85-121">Add discovered peers as a contact to a <xref:System.Net.PeerToPeer.Collaboration.ContactManager>.</span></span>  
  
-   <span data-ttu-id="70a85-122">Comunicazione.</span><span class="sxs-lookup"><span data-stu-id="70a85-122">Communication.</span></span> <span data-ttu-id="70a85-123">Quando viene stabilita la comunicazione, usare le API <xref:System.Net>, l'API <xref:System.Net.PeerToPeer> o le classi del canale peer di Windows Communication Foundation per le comunicazioni a più parti.</span><span class="sxs-lookup"><span data-stu-id="70a85-123">When communication is established, use the <xref:System.Net> APIs, the <xref:System.Net.PeerToPeer> API, or the Windows Communication Foundation Peer Channel classes for multiparty communications.</span></span>  
  
 <span data-ttu-id="70a85-124">Il peer host, ad esempio, avvia una sessione di collaborazione e usa il metodo <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> per aggiungere un peer remoto e uno relativi dei peer locali a Gestione contatti del peer host.</span><span class="sxs-lookup"><span data-stu-id="70a85-124">For example, the host peer starts a collaboration session, and utilizes the <xref:System.Net.PeerToPeer.Collaboration.ContactManager.CreateContact%2A> method to add a remote peer and one of its local peers to the Contact Manager of the host peer.</span></span>  <span data-ttu-id="70a85-125">In questo caso, i tre utenti parteciperanno nella rispettiva sessione di collaborazione privata.</span><span class="sxs-lookup"><span data-stu-id="70a85-125">The three users will then participate in their own private collaboration session.</span></span>  
  
 <span data-ttu-id="70a85-126">Le tipiche applicazioni P2P sono: conferenze telefoniche per la gestione collaborativa degli appunti, applicazioni chat senza server, annunci pubblicitari interattivi e sessioni di giochi online.</span><span class="sxs-lookup"><span data-stu-id="70a85-126">Typical P2P applications are: conference calls for collaborative note-taking or whiteboarding, serverless chat applications, interactive advertisements, and online gaming sessions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70a85-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70a85-127">See Also</span></span>  
 <xref:System.Net.PeerToPeer.Collaboration>
