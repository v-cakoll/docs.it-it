---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 3ce6b3021f47708c222c3ec5a88d474d17106748
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500991"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a><span data-ttu-id="ef700-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span><span class="sxs-lookup"><span data-stu-id="ef700-102">System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded</span></span>
<span data-ttu-id="ef700-103">La velocità di ricezione dei messaggi in ingresso è troppo elevata.</span><span class="sxs-lookup"><span data-stu-id="ef700-103">The inbound receive rate of messages is too high.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ef700-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef700-104">Description</span></span>  
 <span data-ttu-id="ef700-105">Questa traccia si verifica quando si tenta di elaborare messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="ef700-105">This trace occurs when attempting to process inbound messages.</span></span> <span data-ttu-id="ef700-106">Non è possibile inoltrare un messaggio a un elemento adiacente poiché la quota impostata per tale elemento è stata superata.</span><span class="sxs-lookup"><span data-stu-id="ef700-106">A message could not be forwarded to a specific neighbor because the quota set for that neighbor has been exceeded.</span></span> <span data-ttu-id="ef700-107">Questo problema si verifica quando un elemento adiacente che non risponde non riesce a cancellare un backlog di messaggi in sospeso per tale elemento adiacente.</span><span class="sxs-lookup"><span data-stu-id="ef700-107">This occurs when an unresponsive neighbor fails to clear a backlog of messages pending for that neighbor.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ef700-108">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="ef700-108">Troubleshooting</span></span>  
 <span data-ttu-id="ef700-109">Ridurre la velocità di invio dei messaggi all'interno della rete.</span><span class="sxs-lookup"><span data-stu-id="ef700-109">Reduce the rate at which messages are sent within the mesh.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef700-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef700-110">See also</span></span>
- [<span data-ttu-id="ef700-111">Traccia</span><span class="sxs-lookup"><span data-stu-id="ef700-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="ef700-112">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="ef700-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ef700-113">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="ef700-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
