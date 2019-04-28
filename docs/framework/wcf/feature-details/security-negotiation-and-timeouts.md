---
title: Negoziazione di sicurezza e timeout
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: a02c9d7b42eadf9a5ce9af8022fe292d6c23249c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61748291"
---
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="f8282-102">Negoziazione di sicurezza e timeout</span><span class="sxs-lookup"><span data-stu-id="f8282-102">Security Negotiation and Timeouts</span></span>
<span data-ttu-id="f8282-103">Quando l'autenticazione client e servizi, Windows Communication Foundation (WCF) supporta una modalità in cui la credenziale del servizio viene negoziata nell'ambito dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f8282-103">When clients and services authenticate, Windows Communication Foundation (WCF) supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="f8282-104">In scenari di questo tipo, può verificarsi uno scambio di autenticazione multifase tra il client e il servizio al fine di propagare la credenziale del servizio al client.</span><span class="sxs-lookup"><span data-stu-id="f8282-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="f8282-105">La proprietà <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> controlla il tempo di completamento richiesto per tale scambio multifase.</span><span class="sxs-lookup"><span data-stu-id="f8282-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="f8282-106">Questo timeout viene tuttavia applicato solo se lo scambio impiega effettivamente più tempo di una singola richiesta-risposta.</span><span class="sxs-lookup"><span data-stu-id="f8282-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="f8282-107">Nel caso in cui la negoziazione venga completata in un singolo round trip, il timeout non viene applicato.</span><span class="sxs-lookup"><span data-stu-id="f8282-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8282-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8282-108">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [<span data-ttu-id="f8282-109">Procedura: Set un'inclinazione di Clock massima</span><span class="sxs-lookup"><span data-stu-id="f8282-109">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
