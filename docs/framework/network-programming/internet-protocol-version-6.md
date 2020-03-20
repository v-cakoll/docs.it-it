---
title: protocollo IPv6
ms.date: 03/30/2017
helpviewer_keywords:
- IPv6, improvements
- IPv4
- IPv6
- Internet Protocol version 6, improvements
- Internet Protocol version 6
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
ms.openlocfilehash: 367db4fa4e585d6066009dbd1afacb154829319a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047872"
---
# <a name="internet-protocol-version-6"></a><span data-ttu-id="88351-102">protocollo IPv6</span><span class="sxs-lookup"><span data-stu-id="88351-102">Internet Protocol Version 6</span></span>
<span data-ttu-id="88351-103">IPv6 (Internet Protocol version 6) è una nuova famiglia di protocolli standard per il livello di rete di Internet.</span><span class="sxs-lookup"><span data-stu-id="88351-103">The Internet Protocol version 6 (IPv6) is a new suite of standard protocols for the network layer of the Internet.</span></span> <span data-ttu-id="88351-104">IPv6 è progettato per risolvere molti dei problemi riscontrati nell'attuale versione della famiglia di protocolli IP (chiamata IPv4), relativi a esaurimento di indirizzi, sicurezza, configurazione automatica, estendibilità e così via.</span><span class="sxs-lookup"><span data-stu-id="88351-104">IPv6 is designed to solve many of the problems of the current version of the Internet Protocol suite (known as IPv4) with regard to address depletion, security, auto-configuration, extensibility, and so on.</span></span> <span data-ttu-id="88351-105">IPv6 estende le funzionalità di Internet in modo da permettere nuovi tipi di applicazioni, tra cui applicazioni peer-to-peer e per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="88351-105">IPv6 expands the capabilities of the Internet to enable new kinds of applications, including peer-to-peer and mobile applications.</span></span> <span data-ttu-id="88351-106">Di seguito sono elencati i problemi principali dell'attuale protocollo IPv4:</span><span class="sxs-lookup"><span data-stu-id="88351-106">The following are the main issues of the current IPv4 protocol:</span></span>  
  
- <span data-ttu-id="88351-107">Esaurimento rapido dello spazio di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="88351-107">Rapid depletion of the address space.</span></span>  
  
     <span data-ttu-id="88351-108">Questo problema ha comportato l'uso di convertitori NAT (Network Address Translator) che eseguono il mapping di più indirizzi privati in un unico indirizzo IP pubblico.</span><span class="sxs-lookup"><span data-stu-id="88351-108">This has led to the use of Network Address Translators (NATs) that map multiple private addresses to a single public IP address.</span></span> <span data-ttu-id="88351-109">I problemi principali creati da questo meccanismo sono il sovraccarico di elaborazione e la mancanza di connettività end-to-end.</span><span class="sxs-lookup"><span data-stu-id="88351-109">The main problems created by this mechanism are processing overhead and lack of end-to-end connectivity.</span></span>  
  
- <span data-ttu-id="88351-110">Mancanza di supporto delle gerarchie.</span><span class="sxs-lookup"><span data-stu-id="88351-110">Lack of hierarchy support.</span></span>  
  
     <span data-ttu-id="88351-111">A causa della sua tipica organizzazione predefinita delle classi, il protocollo IPv4 è privo di vero supporto delle gerarchie.</span><span class="sxs-lookup"><span data-stu-id="88351-111">Because of its inherent predefined class organization, IPv4 lacks true hierarchical support.</span></span> <span data-ttu-id="88351-112">È impossibile strutturare gli indirizzi IP in modo da eseguire un mapping effettivo della topologia di rete.</span><span class="sxs-lookup"><span data-stu-id="88351-112">It is impossible to structure the IP addresses in a way that truly maps the network topology.</span></span> <span data-ttu-id="88351-113">Questo notevole difetto di progettazione crea la necessità di tabelle di routing di grandi dimensioni per distribuire pacchetti IPv4 in qualsiasi posizione in Internet.</span><span class="sxs-lookup"><span data-stu-id="88351-113">This crucial design flaw creates the need for large routing tables to deliver IPv4 packets to any location on the Internet.</span></span>  
  
- <span data-ttu-id="88351-114">Configurazione di rete complessa.</span><span class="sxs-lookup"><span data-stu-id="88351-114">Complex network configuration.</span></span>  
  
     <span data-ttu-id="88351-115">Con IPv4, gli indirizzi devono essere assegnati in modo statico o tramite un protocollo di configurazione come DHCP.</span><span class="sxs-lookup"><span data-stu-id="88351-115">With IPv4, addresses must be assigned statically or using a configuration protocol such as DHCP.</span></span> <span data-ttu-id="88351-116">In una situazione ideale, gli host non dovrebbero dipendere dall'amministrazione di un'infrastruttura DHCP.</span><span class="sxs-lookup"><span data-stu-id="88351-116">In an ideal situation, hosts would not have to rely on the administration of a DHCP infrastructure.</span></span> <span data-ttu-id="88351-117">Al contrario, dovrebbero essere in grado di configurare se stessi in base al segmento di rete in cui si trovano.</span><span class="sxs-lookup"><span data-stu-id="88351-117">Instead, they would be able to configure themselves based on the network segment in which they are located.</span></span>  
  
- <span data-ttu-id="88351-118">Mancanza di autenticazione e riservatezza integrate.</span><span class="sxs-lookup"><span data-stu-id="88351-118">Lack of built-in authentication and confidentiality.</span></span>  
  
     <span data-ttu-id="88351-119">IPv4 non richiede il supporto di meccanismi che forniscono l'autenticazione o la crittografia dei dati scambiati.</span><span class="sxs-lookup"><span data-stu-id="88351-119">IPv4 does not require the support for any mechanism that provides authentication or encryption of the exchanged data.</span></span> <span data-ttu-id="88351-120">Questo problema è stato risolto con IPv6.</span><span class="sxs-lookup"><span data-stu-id="88351-120">This changes with IPv6.</span></span> <span data-ttu-id="88351-121">Internet Protocol security (IPSec) è un requisito del supporto di IPv6.</span><span class="sxs-lookup"><span data-stu-id="88351-121">Internet Protocol security (IPSec) is an IPv6 support requirement.</span></span>  
  
 <span data-ttu-id="88351-122">Una nuova famiglia di protocolli deve soddisfare i requisiti di base seguenti:</span><span class="sxs-lookup"><span data-stu-id="88351-122">A new protocol suite must satisfy the following basic requirements:</span></span>  
  
- <span data-ttu-id="88351-123">Routing e indirizzamento su larga scala con sovraccarico ridotto.</span><span class="sxs-lookup"><span data-stu-id="88351-123">Large-scale routing and addressing with low overhead.</span></span>  
  
- <span data-ttu-id="88351-124">Configurazione automatica per diverse situazione di connessione.</span><span class="sxs-lookup"><span data-stu-id="88351-124">Auto-configuration for various connecting situations.</span></span>  
  
- <span data-ttu-id="88351-125">Autenticazione e riservatezza integrate.</span><span class="sxs-lookup"><span data-stu-id="88351-125">Built-in authentication and confidentiality.</span></span>  
  
 <span data-ttu-id="88351-126">Per altre informazioni, vedere [Indirizzamento IPv6](ipv6-addressing.md), [Routing IPv6](ipv6-routing.md), [Configurazione automatica di IPv6](ipv6-auto-configuration.md), [Abilitazione e disabilitazione di IPv6](enabling-and-disabling-ipv6.md) e [Procedura: Modificare il file di configurazione del computer per abilitare il supporto IPv6](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span><span class="sxs-lookup"><span data-stu-id="88351-126">For more information, see [IPv6 Addressing](ipv6-addressing.md), [IPv6 Routing](ipv6-routing.md), [IPv6 Auto-Configuration](ipv6-auto-configuration.md), [Enabling and Disabling IPv6](enabling-and-disabling-ipv6.md), and [How to: Modify the Computer Configuration File to Enable IPv6 Support](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="88351-127">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="88351-127">References</span></span>  
 <span data-ttu-id="88351-128">Di seguito sono elencati alcuni documenti RFC selezionati disponibili nel sito Web [Internet Engineering Task Force (IETF)](https://www.ietf.org/):</span><span class="sxs-lookup"><span data-stu-id="88351-128">The following are selected RFC documents that you can find at the [Internet Engineering Task Force (IETF)](https://www.ietf.org/) website:</span></span>  
  
- <span data-ttu-id="88351-129">RFC 1287, Towards the Future Internet Architecture (Verso il futuro dell'architettura di Internet).</span><span class="sxs-lookup"><span data-stu-id="88351-129">RFC 1287, Towards the Future Internet Architecture.</span></span>  
  
- <span data-ttu-id="88351-130">RFC 1454, Comparison of Proposals for Next Version of IP (Confronto tra proposte per la prossima versione di IP).</span><span class="sxs-lookup"><span data-stu-id="88351-130">RFC 1454, Comparison of Proposals for Next Version of IP.</span></span>  
  
- <span data-ttu-id="88351-131">RFC 2373, IP Version 6 Addressing Architecture (Architettura di indirizzamento di IPv6).</span><span class="sxs-lookup"><span data-stu-id="88351-131">RFC 2373, IP Version 6 Addressing Architecture.</span></span>  
  
- <span data-ttu-id="88351-132">RFC 2374, An IPv6 Aggregatable Global Unicast Address Format (Formato di indirizzi unicast globali aggregabile a IPv6).</span><span class="sxs-lookup"><span data-stu-id="88351-132">RFC 2374, An IPv6 Aggregatable Global Unicast Address Format.</span></span>  
  
 <span data-ttu-id="88351-133">Le informazioni relative a IPv6 sono disponibili anche in [IP Version 6 (IPv6)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd379498%28v=ws.10%29) (IP versione 6 - IPv6).</span><span class="sxs-lookup"><span data-stu-id="88351-133">You can also find IPv6-related information on the [IP Version 6 (IPv6)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd379498%28v=ws.10%29).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88351-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88351-134">See also</span></span>

- [<span data-ttu-id="88351-135">Esempio di socket IPv6</span><span class="sxs-lookup"><span data-stu-id="88351-135">IPv6 Sockets Sample</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms180981%28v=vs.85%29)
- [<span data-ttu-id="88351-136">Esempi di programmazione di rete</span><span class="sxs-lookup"><span data-stu-id="88351-136">Network Programming Samples</span></span>](network-programming-samples.md)
- [<span data-ttu-id="88351-137">socket</span><span class="sxs-lookup"><span data-stu-id="88351-137">Sockets</span></span>](sockets.md)
