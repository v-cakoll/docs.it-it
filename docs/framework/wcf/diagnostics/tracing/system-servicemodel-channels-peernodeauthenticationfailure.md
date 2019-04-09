---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.date: 03/30/2017
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
ms.openlocfilehash: 315122914ebcb3e8e4d72c8d976026a126306168
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219005"
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a><span data-ttu-id="130f7-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span><span class="sxs-lookup"><span data-stu-id="130f7-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span></span>
<span data-ttu-id="130f7-103">L’handshake di sicurezza con un router adiacente potenziale non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="130f7-103">The security handshake with a potential neighbor was not successful.</span></span>  
  
## <a name="description"></a><span data-ttu-id="130f7-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="130f7-104">Description</span></span>  
 <span data-ttu-id="130f7-105">Questa traccia si verifica quando si tenta di stabilire una connessione protetta con un router adiacente.</span><span class="sxs-lookup"><span data-stu-id="130f7-105">This trace occurs while attempting to establish a secure neighbor connection.</span></span> <span data-ttu-id="130f7-106">Tale situazione può verificarsi a causa di credenziali insufficienti o incorrette.</span><span class="sxs-lookup"><span data-stu-id="130f7-106">This can happen due to insufficient or incorrect credentials.</span></span>  
  
 <span data-ttu-id="130f7-107">PeerChannel riconosce un solo tipo di token per identificazione sicura, i certificati X.509 che offrono un modello sicuro di identità basato sul tipo di autenticazione e di autorizzazione che può essere implementato.</span><span class="sxs-lookup"><span data-stu-id="130f7-107">PeerChannel recognizes a single token type for strong identification, X.509 certificates, which provide a strong identity model based on the type of authentication and authorization that can be implemented.</span></span> <span data-ttu-id="130f7-108">PeerChannel fornisce inoltre il supporto per applicazioni semplici tramite l'utilizzo di password.</span><span class="sxs-lookup"><span data-stu-id="130f7-108">PeerChannel also provides support for simple applications through the use of passwords.</span></span> <span data-ttu-id="130f7-109">Le password possono essere utilizzate solo per consentire l'accesso alla sessione, non per eseguire l'autenticazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="130f7-109">Passwords can be used only to allow entry to the session; they cannot be used to perform message authentication.</span></span> <span data-ttu-id="130f7-110">Ciò è dovuto al fatto che è difficile e inappropriato utilizzare per l'autenticazione dell'origine un token simmetrico condiviso da un gruppo di peer.</span><span class="sxs-lookup"><span data-stu-id="130f7-110">This is because a symmetric token that a group of peers share is difficult and inappropriate to use for source authentication.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="130f7-111">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="130f7-111">Troubleshooting</span></span>  
 <span data-ttu-id="130f7-112">Assicurarsi che tutti i router adiacenti abbiano le credenziali di sicurezza appropriate.</span><span class="sxs-lookup"><span data-stu-id="130f7-112">Ensure that all neighbors have the appropriate security credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="130f7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="130f7-113">See also</span></span>

- [<span data-ttu-id="130f7-114">Protezione del canale peer</span><span class="sxs-lookup"><span data-stu-id="130f7-114">Peer Channel Security</span></span>](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)
- [<span data-ttu-id="130f7-115">Traccia</span><span class="sxs-lookup"><span data-stu-id="130f7-115">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="130f7-116">Utilizzo delle tracce per risolvere i problemi di un'applicazione</span><span class="sxs-lookup"><span data-stu-id="130f7-116">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="130f7-117">Amministrazione e diagnostica</span><span class="sxs-lookup"><span data-stu-id="130f7-117">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
