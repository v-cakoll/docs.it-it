---
title: Attestazioni e negazioni di accesso alle risorse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- claims [WCF], denying access to resources
ms.assetid: 145ebb41-680e-4256-b14c-1efb4af1e982
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 156856ddd1a4c3b1d8f77a8a61f7e0336f993839
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="claims-and-denying-access-to-resources"></a><span data-ttu-id="c9bd1-102">Attestazioni e negazioni di accesso alle risorse</span><span class="sxs-lookup"><span data-stu-id="c9bd1-102">Claims and Denying Access to Resources</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="c9bd1-103"> supporta un meccanismo di autorizzazione basato su attestazioni.</span><span class="sxs-lookup"><span data-stu-id="c9bd1-103"> supports a claims-based authorization mechanism.</span></span> <span data-ttu-id="c9bd1-104">Così come consentono l'accesso alle risorse in base alla presenza di attestazioni, i sistemi spesso negano l'accesso alle risorse in base alla presenza di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="c9bd1-104">As well as allowing access to resources based on the presence of claims, systems often deny access to resources based on the presence of claims.</span></span> <span data-ttu-id="c9bd1-105">Tali sistemi devono esaminare la classe <xref:System.IdentityModel.Policy.AuthorizationContext> per rilevare la presenza di attestazioni che causano la negazione dell'accesso prima di ricercare le attestazioni che causano la concessione dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="c9bd1-105">Such systems should examine the <xref:System.IdentityModel.Policy.AuthorizationContext> for claims that result in access being denied before looking for claims that result in access being allowed.</span></span>  
  
 <span data-ttu-id="c9bd1-106">Ad esempio, un sistema potrebbe negare l'accesso a una risorsa a chiunque disponga di un'attestazione di tipo `Age`, un diritto <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> e un valore di risorsa `Under 21` solo quando tale identità dispone anche di un'attestazione di tipo `Name`, un diritto <xref:System.IdentityModel.Claims.Rights.Identity%2A> e un valore di risorsa `Mallory`.</span><span class="sxs-lookup"><span data-stu-id="c9bd1-106">For example, a system might deny access to a resource to anyone who has a claim with a type of `Age`, a right of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, and a resource value of `Under 21` only when that identity also has a claim of type `Name`, a right of <xref:System.IdentityModel.Claims.Rights.Identity%2A>, and a resource value of `Mallory`.</span></span> <span data-ttu-id="c9bd1-107">In altri termini, il sistema nega l'accesso a chiunque abbia meno di 21 anni e lo concede quando il nome è Mallory.</span><span class="sxs-lookup"><span data-stu-id="c9bd1-107">Put another way, the system denies access to anyone who is under 21 years old and grants access when the name is Mallory.</span></span> <span data-ttu-id="c9bd1-108">Per implementare correttamente questa semantica, è importante ricercare prima l'attestazione `Age` e determinare se l'età è inferiore ai 21 anni.</span><span class="sxs-lookup"><span data-stu-id="c9bd1-108">To correctly implement this semantic, it is important to look for the `Age` claim first and determine whether the age is under 21 years old.</span></span> <span data-ttu-id="c9bd1-109">In caso contrario, se Mallory ha meno di 21 anni, l'accesso alla risorsa potrebbe essere concesso unicamente sulla base dell'attestazione `Name`.</span><span class="sxs-lookup"><span data-stu-id="c9bd1-109">Otherwise, if Mallory is under 21, then the resource may be granted access solely on the basis of the `Name` claim.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bd1-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9bd1-110">See Also</span></span>  
 [<span data-ttu-id="c9bd1-111">Gestione delle attestazioni e dell'autorizzazione con il modello di identità</span><span class="sxs-lookup"><span data-stu-id="c9bd1-111">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="c9bd1-112">Attestazioni e token</span><span class="sxs-lookup"><span data-stu-id="c9bd1-112">Claims and Tokens</span></span>](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)
