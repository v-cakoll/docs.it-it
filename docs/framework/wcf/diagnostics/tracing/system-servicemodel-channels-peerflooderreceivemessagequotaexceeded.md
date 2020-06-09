---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 93afa0b495e20c02c58ac1fa75c31715eaa0e8dc
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596090"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="db705-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="db705-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>
<span data-ttu-id="db705-103">La velocità di ricezione dei messaggi in ingresso è troppo elevata.</span><span class="sxs-lookup"><span data-stu-id="db705-103">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="db705-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db705-104">Description</span></span>  
 <span data-ttu-id="db705-105">Questa traccia si verifica quando si tenta di elaborare messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="db705-105">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="db705-106">Non è possibile inoltrare un messaggio a un elemento adiacente poiché la quota impostata per tale elemento è stata superata.</span><span class="sxs-lookup"><span data-stu-id="db705-106">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="db705-107">Questo problema si verifica quando un elemento adiacente che non risponde non riesce a cancellare un backlog di messaggi in sospeso per tale elemento adiacente.</span><span class="sxs-lookup"><span data-stu-id="db705-107">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="db705-108">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="db705-108">Troubleshooting</span></span>  
 <span data-ttu-id="db705-109">Ridurre la velocità di invio dei messaggi all'interno della rete.</span><span class="sxs-lookup"><span data-stu-id="db705-109">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db705-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db705-110">See also</span></span>

- [<span data-ttu-id="db705-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="db705-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="db705-112">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="db705-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="db705-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="db705-113">Administration and Diagnostics</span></span>](../index.md)
