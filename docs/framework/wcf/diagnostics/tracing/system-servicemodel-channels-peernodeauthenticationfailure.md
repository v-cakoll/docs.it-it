---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.date: 03/30/2017
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
ms.openlocfilehash: 633f497950ab14d7715537eed8f5cc80e7a350a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33479853"
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a><span data-ttu-id="018fa-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span><span class="sxs-lookup"><span data-stu-id="018fa-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span></span>
<span data-ttu-id="018fa-103">L’handshake di sicurezza con un router adiacente potenziale non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="018fa-103">The security handshake with a potential neighbor was not successful.</span></span>  
  
## <a name="description"></a><span data-ttu-id="018fa-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="018fa-104">Description</span></span>  
 <span data-ttu-id="018fa-105">Questa traccia si verifica quando si tenta di stabilire una connessione protetta con un router adiacente.</span><span class="sxs-lookup"><span data-stu-id="018fa-105">This trace occurs while attempting to establish a secure neighbor connection.</span></span> <span data-ttu-id="018fa-106">Tale situazione può verificarsi a causa di credenziali insufficienti o incorrette.</span><span class="sxs-lookup"><span data-stu-id="018fa-106">This can happen due to insufficient or incorrect credentials.</span></span>  
  
 <span data-ttu-id="018fa-107">PeerChannel riconosce un solo tipo di token per identificazione sicura, i certificati X.509 che offrono un modello sicuro di identità basato sul tipo di autenticazione e di autorizzazione che può essere implementato.</span><span class="sxs-lookup"><span data-stu-id="018fa-107">PeerChannel recognizes a single token type for strong identification, X.509 certificates, which provide a strong identity model based on the type of authentication and authorization that can be implemented.</span></span> <span data-ttu-id="018fa-108">PeerChannel fornisce inoltre il supporto per applicazioni semplici tramite l'utilizzo di password.</span><span class="sxs-lookup"><span data-stu-id="018fa-108">PeerChannel also provides support for simple applications through the use of passwords.</span></span> <span data-ttu-id="018fa-109">Le password possono essere utilizzate solo per consentire l'accesso alla sessione, non per eseguire l'autenticazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="018fa-109">Passwords can be used only to allow entry to the session; they cannot be used to perform message authentication.</span></span> <span data-ttu-id="018fa-110">Ciò è dovuto al fatto che è difficile e inappropriato utilizzare per l'autenticazione dell'origine un token simmetrico condiviso da un gruppo di peer.</span><span class="sxs-lookup"><span data-stu-id="018fa-110">This is because a symmetric token that a group of peers share is difficult and inappropriate to use for source authentication.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="018fa-111">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="018fa-111">Troubleshooting</span></span>  
 <span data-ttu-id="018fa-112">Assicurarsi che tutti i router adiacenti abbiano le credenziali di sicurezza appropriate.</span><span class="sxs-lookup"><span data-stu-id="018fa-112">Ensure that all neighbors have the appropriate security credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="018fa-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="018fa-113">See Also</span></span>  
 [<span data-ttu-id="018fa-114">Sicurezza del canale peer</span><span class="sxs-lookup"><span data-stu-id="018fa-114">Peer Channel Security</span></span>](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)  
 [<span data-ttu-id="018fa-115">Traccia</span><span class="sxs-lookup"><span data-stu-id="018fa-115">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="018fa-116">Uso delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="018fa-116">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="018fa-117">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="018fa-117">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
