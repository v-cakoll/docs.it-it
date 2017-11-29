---
title: Negoziazione di sicurezza e timeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: b4d0b2953a91040c37afe88d9499fd4be1970f31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="83558-102">Negoziazione di sicurezza e timeout</span><span class="sxs-lookup"><span data-stu-id="83558-102">Security Negotiation and Timeouts</span></span>
<span data-ttu-id="83558-103">Quando viene eseguita l'autenticazione di client e servizi, in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] è supportata una modalità in base alla quale la credenziale del servizio viene negoziata nell'ambito dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="83558-103">When clients and services authenticate, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="83558-104">In scenari di questo tipo, può verificarsi uno scambio di autenticazione multifase tra il client e il servizio al fine di propagare la credenziale del servizio al client.</span><span class="sxs-lookup"><span data-stu-id="83558-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="83558-105">La proprietà <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> controlla il tempo di completamento richiesto per tale scambio multifase.</span><span class="sxs-lookup"><span data-stu-id="83558-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="83558-106">Questo timeout viene tuttavia applicato solo se lo scambio impiega effettivamente più tempo di una singola richiesta-risposta.</span><span class="sxs-lookup"><span data-stu-id="83558-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="83558-107">Nel caso in cui la negoziazione venga completata in un singolo round trip, il timeout non viene applicato.</span><span class="sxs-lookup"><span data-stu-id="83558-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83558-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83558-108">See Also</span></span>  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 [<span data-ttu-id="83558-109">Procedura: impostare un numero massimo di sfasamento</span><span class="sxs-lookup"><span data-stu-id="83558-109">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
