---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ffca9a587bdb32afc252f9719eb35e3139dd3f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a><span data-ttu-id="711fd-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span><span class="sxs-lookup"><span data-stu-id="711fd-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span></span>
<span data-ttu-id="711fd-103">L’handshake di sicurezza con un router adiacente potenziale non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="711fd-103">The security handshake with a potential neighbor was not successful.</span></span>  
  
## <a name="description"></a><span data-ttu-id="711fd-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="711fd-104">Description</span></span>  
 <span data-ttu-id="711fd-105">Questa traccia si verifica quando si tenta di stabilire una connessione protetta con un router adiacente.</span><span class="sxs-lookup"><span data-stu-id="711fd-105">This trace occurs while attempting to establish a secure neighbor connection.</span></span> <span data-ttu-id="711fd-106">Tale situazione può verificarsi a causa di credenziali insufficienti o incorrette.</span><span class="sxs-lookup"><span data-stu-id="711fd-106">This can happen due to insufficient or incorrect credentials.</span></span>  
  
 <span data-ttu-id="711fd-107">PeerChannel riconosce un solo tipo di token per identificazione sicura, i certificati X.509 che offrono un modello sicuro di identità basato sul tipo di autenticazione e di autorizzazione che può essere implementato.</span><span class="sxs-lookup"><span data-stu-id="711fd-107">PeerChannel recognizes a single token type for strong identification, X.509 certificates, which provide a strong identity model based on the type of authentication and authorization that can be implemented.</span></span> <span data-ttu-id="711fd-108">PeerChannel fornisce inoltre il supporto per applicazioni semplici tramite l'utilizzo di password.</span><span class="sxs-lookup"><span data-stu-id="711fd-108">PeerChannel also provides support for simple applications through the use of passwords.</span></span> <span data-ttu-id="711fd-109">Le password possono essere utilizzate solo per consentire l'accesso alla sessione, non per eseguire l'autenticazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="711fd-109">Passwords can be used only to allow entry to the session; they cannot be used to perform message authentication.</span></span> <span data-ttu-id="711fd-110">Ciò è dovuto al fatto che è difficile e inappropriato utilizzare per l'autenticazione dell'origine un token simmetrico condiviso da un gruppo di peer.</span><span class="sxs-lookup"><span data-stu-id="711fd-110">This is because a symmetric token that a group of peers share is difficult and inappropriate to use for source authentication.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="711fd-111">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="711fd-111">Troubleshooting</span></span>  
 <span data-ttu-id="711fd-112">Assicurarsi che tutti i router adiacenti abbiano le credenziali di sicurezza appropriate.</span><span class="sxs-lookup"><span data-stu-id="711fd-112">Ensure that all neighbors have the appropriate security credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="711fd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="711fd-113">See Also</span></span>  
 [<span data-ttu-id="711fd-114">Sicurezza del canale peer</span><span class="sxs-lookup"><span data-stu-id="711fd-114">Peer Channel Security</span></span>](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)  
 [<span data-ttu-id="711fd-115">Traccia</span><span class="sxs-lookup"><span data-stu-id="711fd-115">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="711fd-116">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="711fd-116">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="711fd-117">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="711fd-117">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
