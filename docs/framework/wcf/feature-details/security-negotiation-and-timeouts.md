---
title: Negoziazione di sicurezza e timeout
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: 1b5fb15b4ea00ba33b741c96bcb423aefe9890fa
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600997"
---
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="8fa5e-102">Negoziazione di sicurezza e timeout</span><span class="sxs-lookup"><span data-stu-id="8fa5e-102">Security Negotiation and Timeouts</span></span>
<span data-ttu-id="8fa5e-103">Quando si esegue l'autenticazione di client e servizi, Windows Communication Foundation (WCF) supporta una modalità in cui la credenziale del servizio viene negoziata come parte dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="8fa5e-103">When clients and services authenticate, Windows Communication Foundation (WCF) supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="8fa5e-104">In scenari di questo tipo, può verificarsi uno scambio di autenticazione multifase tra il client e il servizio al fine di propagare la credenziale del servizio al client.</span><span class="sxs-lookup"><span data-stu-id="8fa5e-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="8fa5e-105">La proprietà <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> controlla il tempo di completamento richiesto per tale scambio multifase.</span><span class="sxs-lookup"><span data-stu-id="8fa5e-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="8fa5e-106">Questo timeout viene tuttavia applicato solo se lo scambio impiega effettivamente più tempo di una singola richiesta-risposta.</span><span class="sxs-lookup"><span data-stu-id="8fa5e-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="8fa5e-107">Nel caso in cui la negoziazione venga completata in un singolo round trip, il timeout non viene applicato.</span><span class="sxs-lookup"><span data-stu-id="8fa5e-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fa5e-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fa5e-108">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [<span data-ttu-id="8fa5e-109">Procedura: impostare lo sfasamento massimo dei segnali di clock</span><span class="sxs-lookup"><span data-stu-id="8fa5e-109">How to: Set a Max Clock Skew</span></span>](how-to-set-a-max-clock-skew.md)
