---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.date: 03/30/2017
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
ms.openlocfilehash: ce97eaa2ad5c9dbd5f4d6f81186960c489eb4b85
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596077"
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a><span data-ttu-id="0191c-102">System.ServiceModel.Channels.PeerMaintainerActivity</span><span class="sxs-lookup"><span data-stu-id="0191c-102">System.ServiceModel.Channels.PeerMaintainerActivity</span></span>
<span data-ttu-id="0191c-103">Il modulo PeerMaintainer sta eseguendo un'operazione specifica (i dettagli sono contenuti nel corpo del messaggio di traccia).</span><span class="sxs-lookup"><span data-stu-id="0191c-103">The PeerMaintainer module is performing a specific operation (details contained within the trace message body).</span></span>  
  
## <a name="description"></a><span data-ttu-id="0191c-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0191c-104">Description</span></span>  
 <span data-ttu-id="0191c-105">Questa traccia si verifica durante varie operazioni PeerMaintainer.</span><span class="sxs-lookup"><span data-stu-id="0191c-105">This trace occurs during various PeerMaintainer operations.</span></span>  
  
 <span data-ttu-id="0191c-106">PeerMaintainer è un componente interno di PeerNode.</span><span class="sxs-lookup"><span data-stu-id="0191c-106">PeerMaintainer is an internal component of PeerNode.</span></span> <span data-ttu-id="0191c-107">Ogni minuto o ogni 32 messaggi ricevuti, invia un messaggio LinkUtility ai router adiacenti con le statistiche sulla quantità di messaggi scambiati e su quanti di essi sono utili (non duplicati, non manomessi).</span><span class="sxs-lookup"><span data-stu-id="0191c-107">Every minute, or every 32 messages received, it sends a LinkUtility message to its neighbors with statistics about how many messages are exchanged and how many are useful (non-duplicates, untampered).</span></span> <span data-ttu-id="0191c-108">Ciò consente di determinare l'utilità di collegamento di un determinato router adiacente.</span><span class="sxs-lookup"><span data-stu-id="0191c-108">This helps determine a particular neighbor's Link Utility.</span></span> <span data-ttu-id="0191c-109">Ogni cinque minuti circa, il componente Maintener verifica l'integrità delle connessioni al router adiacente.</span><span class="sxs-lookup"><span data-stu-id="0191c-109">Approximately every five minutes, the maintainer checks the health of neighbor connections.</span></span> <span data-ttu-id="0191c-110">Se il numero di connessioni al router adiacente supera il valore ideale, il componente elimina le connessioni meno utili.</span><span class="sxs-lookup"><span data-stu-id="0191c-110">If the number of neighbor connections exceeds the ideal amount, the maintainer prunes off the least useful connections.</span></span> <span data-ttu-id="0191c-111">Se il numero di connessioni non è sufficiente, il componente ne acquisisce di nuove.</span><span class="sxs-lookup"><span data-stu-id="0191c-111">If there are not enough connections, the maintainer acquires new connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0191c-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0191c-112">See also</span></span>

- [<span data-ttu-id="0191c-113">Traccia</span><span class="sxs-lookup"><span data-stu-id="0191c-113">Tracing</span></span>](index.md)
- [<span data-ttu-id="0191c-114">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="0191c-114">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="0191c-115">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="0191c-115">Administration and Diagnostics</span></span>](../index.md)
