---
title: Protocollo PNRP (Peer Name Resolution Protocol)
ms.date: 03/30/2017
ms.assetid: 11940511-c124-4d91-ae31-d4ed6e81ee58
ms.openlocfilehash: c8b7b2190349323bf212d816a77f5f7810f6ca2c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74428219"
---
# <a name="peer-name-resolution-protocol"></a><span data-ttu-id="22a8e-102">Protocollo PNRP (Peer Name Resolution Protocol)</span><span class="sxs-lookup"><span data-stu-id="22a8e-102">Peer Name Resolution Protocol</span></span>
<span data-ttu-id="22a8e-103">Negli ambienti peer-to-peer, i peer usano sistemi di risoluzione dei nomi specifici per dedurre l'ubicazione di rete reciproca (indirizzi, protocolli e porte) dai nomi o altri tipi di identificatori.</span><span class="sxs-lookup"><span data-stu-id="22a8e-103">In peer-to-peer environments, peers use specific name resolution systems to resolve each other's network locations (addresses, protocols, and ports) from names or other types of identifiers.</span></span> <span data-ttu-id="22a8e-104">Nel passato, la risoluzione dei nomi peer era complicata dalla transitorietà intrinseca della connettività e da altri inconvenienti nel sistema DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="22a8e-104">In the past, peer name resolution has been complicated by the inherently transient connectivity as well as other shortcomings within the Domain Name System (DNS).</span></span>  
  
 <span data-ttu-id="22a8e-105">La piattaforma di rete Microsoft® Windows® Peer-to-Peer Networking risolve il problema relativo al protocollo di risoluzione del nome del peer (PNRP), offrendo un protocollo sicuro, scalabile e dinamico di registrazione e risoluzione dei nomi sviluppato per la prima volta per Windows XP e quindi aggiornato in Windows Vista™.</span><span class="sxs-lookup"><span data-stu-id="22a8e-105">The Microsoft® Windows® Peer-to-Peer Networking platform solves this problem with the Peer Name Resolution Protocol (PNRP), a secure, scalable, and dynamic name registration and name resolution protocol first developed for Windows XP and then upgraded in Windows Vista™.</span></span> <span data-ttu-id="22a8e-106">PNRP funziona in modo molto diverso dai tradizionali sistemi di risoluzione dei nomi, aprendo nuove ed entusiasmanti possibilità per gli sviluppatori di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="22a8e-106">PNRP works very differently from traditional name resolution systems, opening up exciting new possibilities for application developers.</span></span>  
  
 <span data-ttu-id="22a8e-107">Con PNRP, i nomi di peer possono essere applicati al computer oppure ad applicazioni o servizi singoli nel computer.</span><span class="sxs-lookup"><span data-stu-id="22a8e-107">With PNRP, peer names can be applied to the machine, or individual applications or services on the machine.</span></span> <span data-ttu-id="22a8e-108">Una risoluzione dei nomi peer contiene un indirizzo, una porta e probabilmente anche un payload esteso.</span><span class="sxs-lookup"><span data-stu-id="22a8e-108">A peer name resolution includes an address, port, and possibly an extended payload.</span></span> <span data-ttu-id="22a8e-109">I vantaggi di questo sistema includono la tolleranza di errore, l'assenza di colli di bottiglia e risoluzioni dei nomi che non restituiranno mai indirizzi non aggiornati. Il protocollo è quindi una soluzione eccellente per l'individuazione degli utenti mobili.</span><span class="sxs-lookup"><span data-stu-id="22a8e-109">Benefits of this system include fault tolerance, no bottlenecks, and name resolutions that will never return stale addresses; making the protocol an excellent solution for locating mobile users.</span></span>  
  
 <span data-ttu-id="22a8e-110">A livello di sicurezza, i nomi di peer possono essere pubblicati come protetti o non protetti.</span><span class="sxs-lookup"><span data-stu-id="22a8e-110">In terms of security, peer names can be published as secured (protected) or unsecured (unprotected).</span></span> <span data-ttu-id="22a8e-111">PNRP usa la crittografia a chiave pubblica per proteggere i nomi di peer sicuri dallo spoofing. Con PNRP si possono assegnare nomi sia ai computer che ai servizi.</span><span class="sxs-lookup"><span data-stu-id="22a8e-111">PNRP uses public key cryptography to protect secure peer names against spoofing; both computers and services can be named with PNRP.</span></span>  
  
<span data-ttu-id="22a8e-112">Il protocollo PNRP (Peer Name Resolution Protocol) ha le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="22a8e-112">The Peer Name Resolution Protocol demonstrates the following properties:</span></span>  
  
- <span data-ttu-id="22a8e-113">È un protocollo distribuito e quasi del tutto senza server.</span><span class="sxs-lookup"><span data-stu-id="22a8e-113">Distributed and almost entirely serverless.</span></span> <span data-ttu-id="22a8e-114">I server sono necessari solo per il processo di bootstrap.</span><span class="sxs-lookup"><span data-stu-id="22a8e-114">Servers are only required for the bootstrapping process.</span></span>  
  
- <span data-ttu-id="22a8e-115">Protezione della pubblicazione dei nomi senza il coinvolgimento di terze parti.</span><span class="sxs-lookup"><span data-stu-id="22a8e-115">Secure name publication without the involvement of third parties.</span></span> <span data-ttu-id="22a8e-116">Diversamente dalla pubblicazione dei nomi DNS, la pubblicazione dei nomi PNRP è istantanea e non comporta costi finanziari.</span><span class="sxs-lookup"><span data-stu-id="22a8e-116">Unlike DNS name publication, PNRP name publication is instantaneous and without financial cost.</span></span>  
  
- <span data-ttu-id="22a8e-117">PNRP implementa gli aggiornamenti in tempo reale e ciò impedisce la risoluzione di indirizzi non aggiornati.</span><span class="sxs-lookup"><span data-stu-id="22a8e-117">PNRP updates in real-time, which prevents the resolution of stale addresses.</span></span>  
  
- <span data-ttu-id="22a8e-118">La risoluzione dei nomi tramite PNRP si estende oltre i computer, consentendo anche la risoluzione dei nomi per i servizi.</span><span class="sxs-lookup"><span data-stu-id="22a8e-118">The resolution of names via PNRP extends beyond computers by also allowing name resolution for services.</span></span>  
  
## <a name="the-systemnetpeertopeer-namespace"></a><span data-ttu-id="22a8e-119">Spazio dei nomi System.Net.PeerToPeer</span><span class="sxs-lookup"><span data-stu-id="22a8e-119">The System.Net.PeerToPeer namespace</span></span>  
  
- <span data-ttu-id="22a8e-120">Le funzionalità del protocollo PNRP sono definite dallo spazio dei nomi <xref:System.Net.PeerToPeer> all'interno di .NET Framework versione 3.5.</span><span class="sxs-lookup"><span data-stu-id="22a8e-120">PNRP functionality is defined by the <xref:System.Net.PeerToPeer> namespace within the .NET Framework version 3.5.</span></span> <span data-ttu-id="22a8e-121">È disponibile un set di tipi che può essere usato per registrare e risolvere i nomi di peer con un servizio PNRP disponibile.</span><span class="sxs-lookup"><span data-stu-id="22a8e-121">It provides a set of types that can be used to register and resolve peer names with an available PNRP service.</span></span>  
  
- <span data-ttu-id="22a8e-122">(È possibile creare e inizializzare resolver PNRP e resolver di peer personalizzati usando i tipi forniti dallo spazio dei nomi <xref:System.ServiceModel.PeerResolvers>.)</span><span class="sxs-lookup"><span data-stu-id="22a8e-122">(PNRP and custom peer resolvers can be created and instantiated using the types provided in the <xref:System.ServiceModel.PeerResolvers> namespace.)</span></span>  
  
- <span data-ttu-id="22a8e-123">I tipi di base usati per registrare e risolvere i nomi con un servizio PNRP disponibile sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="22a8e-123">The basic types used to register and resolve names with an available PNRP service are as follows:</span></span>  
  
- <span data-ttu-id="22a8e-124"><xref:System.Net.PeerToPeer.Cloud>: definisce le informazioni che descrivono un cloud PNRP disponibile, incluso il relativo ambito.</span><span class="sxs-lookup"><span data-stu-id="22a8e-124"><xref:System.Net.PeerToPeer.Cloud>: Defines the information describing an available PNRP cloud, including its scope.</span></span>  
  
- <span data-ttu-id="22a8e-125"><xref:System.Net.PeerToPeer.PeerName>: definisce un nome di peer che può essere usato per registrare e risolvere successivamente un peer all'interno di un cloud.</span><span class="sxs-lookup"><span data-stu-id="22a8e-125"><xref:System.Net.PeerToPeer.PeerName>: Defines a peer name that can be used to register and subsequently resolve a peer within a cloud.</span></span>  
  
- <span data-ttu-id="22a8e-126"><xref:System.Net.PeerToPeer.PeerNameRecord>: definisce il record nel cloud PNRP che contiene le informazioni di registrazione per un peer, che include gli endpoint di rete in cui è possibile contattare il peer.</span><span class="sxs-lookup"><span data-stu-id="22a8e-126"><xref:System.Net.PeerToPeer.PeerNameRecord>: Defines the record in PNRP cloud that contains the registration information for a peer, which includes the network endpoints at which the peer can be contacted.</span></span>  
  
- <span data-ttu-id="22a8e-127"><xref:System.Net.PeerToPeer.PeerNameRegistration>: definisce il processo di registrazione per un nome di peer, inclusi i metodi per avviare e arrestare la registrazione dei nomi di peer.</span><span class="sxs-lookup"><span data-stu-id="22a8e-127"><xref:System.Net.PeerToPeer.PeerNameRegistration>: Defines the registration process for a peer name, including methods to start and stop peer name registration.</span></span>  
  
- <span data-ttu-id="22a8e-128"><xref:System.Net.PeerToPeer.PeerNameResolver>: definisce il processo per la risoluzione di un nome di peer negli endpoint di rete corrispondenti, inclusi sia i metodi sincroni che quelli asincroni per la risoluzione.</span><span class="sxs-lookup"><span data-stu-id="22a8e-128"><xref:System.Net.PeerToPeer.PeerNameResolver>: Defines the process for resolving a peer name to its network endpoint(s), including both synchronous and asynchronous methods for resolution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22a8e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22a8e-129">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers>
- <xref:System.Net.PeerToPeer>
- [<span data-ttu-id="22a8e-130">Esempi di programmazione di rete</span><span class="sxs-lookup"><span data-stu-id="22a8e-130">Network Programming Samples</span></span>](network-programming-samples.md)

<!-- to-do: review sample links
- [PeerToPeer Technology Sample](https://go.microsoft.com/fwlink/?LinkID=179571)
-->
