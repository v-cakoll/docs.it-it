---
title: Attestazioni e token SAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
- issued tokens
- SAML token
ms.assetid: 930b6e34-9eab-4e95-826c-4e06659bb977
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2b35ba4da503663a2bb92597ed193c408e7c99b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="saml-tokens-and-claims"></a><span data-ttu-id="d4d73-102">Attestazioni e token SAML</span><span class="sxs-lookup"><span data-stu-id="d4d73-102">SAML Tokens and Claims</span></span>
<span data-ttu-id="d4d73-103">Sicurezza asserzioni Markup Language (SAML) *token* sono rappresentazioni XML di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="d4d73-103">Security Assertions Markup Language (SAML) *tokens* are XML representations of claims.</span></span> <span data-ttu-id="d4d73-104">Per impostazione predefinita, i token SAML [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] viene usato negli scenari di sicurezza federata *i token rilasciati*.</span><span class="sxs-lookup"><span data-stu-id="d4d73-104">By default, SAML tokens [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] uses in federated security scenarios are *issued tokens*.</span></span>  
  
 <span data-ttu-id="d4d73-105">I token SAML contengono istruzioni che si configurano come attestazioni elaborate da un'entità su un'altra entità.</span><span class="sxs-lookup"><span data-stu-id="d4d73-105">SAML tokens carry statements that are sets of claims made by one entity about another entity.</span></span> <span data-ttu-id="d4d73-106">Negli scenari di sicurezza federati, ad esempio, le istruzioni sono elaborate da un servizio token di sicurezza su un utente del sistema.</span><span class="sxs-lookup"><span data-stu-id="d4d73-106">For example, in federated security scenarios, the statements are made by a security token service about a user in the system.</span></span> <span data-ttu-id="d4d73-107">Il servizio token di sicurezza firma il token SAML per indicare la veridicità delle istruzioni contenute nel token.</span><span class="sxs-lookup"><span data-stu-id="d4d73-107">The security token service signs the SAML token to indicate the veracity of the statements contained in the token.</span></span> <span data-ttu-id="d4d73-108">Il token SAML, inoltre, è associato a chiavi crittografiche di cui l'utente del token SAML dimostra di essere a conoscenza.</span><span class="sxs-lookup"><span data-stu-id="d4d73-108">In addition, the SAML token is associated with cryptographic key material that the user of the SAML token proves knowledge of.</span></span> <span data-ttu-id="d4d73-109">La prova dimostra al componente che il token SAML è stato, infatti, rilasciato a quell'utente.</span><span class="sxs-lookup"><span data-stu-id="d4d73-109">This proof satisfies the relying party that the SAML token was, in fact, issued to that user.</span></span> <span data-ttu-id="d4d73-110">In uno scenario tipico, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d4d73-110">For example, in a typical scenario:</span></span>  
  
1.  <span data-ttu-id="d4d73-111">Un client chiede un token SAML a un servizio token di sicurezza, autenticandosi al servizio mediante le credenziali di Windows.</span><span class="sxs-lookup"><span data-stu-id="d4d73-111">A client requests a SAML token from a security token service, authenticating to that security token service by using Windows credentials.</span></span>  
  
2.  <span data-ttu-id="d4d73-112">Il servizio token di sicurezza rilascia un token SAML al cliente.</span><span class="sxs-lookup"><span data-stu-id="d4d73-112">The security token service issues a SAML token to the client.</span></span> <span data-ttu-id="d4d73-113">Il token SAML viene firmato con un certificato associato al servizio token di sicurezza e contiene una chiave di prova crittografata per il servizio di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d4d73-113">The SAML token is signed with a certificate associated with the security token service and contains a proof key encrypted for the target service.</span></span>  
  
3.  <span data-ttu-id="d4d73-114">Il client riceve inoltre una copia del *chiave di prova*.</span><span class="sxs-lookup"><span data-stu-id="d4d73-114">The client also receives a copy of the *proof key*.</span></span> <span data-ttu-id="d4d73-115">Il client presenta quindi il token SAML al servizio dell'applicazione (il *relying party*) e firma il messaggio con tale chiave di prova.</span><span class="sxs-lookup"><span data-stu-id="d4d73-115">The client then presents the SAML token to the application service (the *relying party*) and signs the message with that proof key.</span></span>  
  
4.  <span data-ttu-id="d4d73-116">La firma sul token SAML dimostra al componente che il servizio token di sicurezza ha rilasciato il token.</span><span class="sxs-lookup"><span data-stu-id="d4d73-116">The signature over the SAML token tells the relying party that the security token service issued the token.</span></span> <span data-ttu-id="d4d73-117">La firma del messaggio creata con la chiave di prova dimostra al componente che il token è stato rilasciato al client.</span><span class="sxs-lookup"><span data-stu-id="d4d73-117">The message signature created with the proof key tells the relying party that the token was issued to the client.</span></span>  
  
## <a name="from-claims-to-samlattributes"></a><span data-ttu-id="d4d73-118">Da attestazioni a SamlAttributes</span><span class="sxs-lookup"><span data-stu-id="d4d73-118">From Claims to SamlAttributes</span></span>  
 <span data-ttu-id="d4d73-119">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] le istruzioni contenute nei token SAML sono modellate come oggetti <xref:System.IdentityModel.Tokens.SamlAttribute> che possono essere popolati direttamente da oggetti <xref:System.IdentityModel.Claims.Claim> purché l'oggetto <xref:System.IdentityModel.Claims.Claim> disponga di una proprietà <xref:System.IdentityModel.Claims.Claim.Right%2A> di <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> e la proprietà <xref:System.IdentityModel.Claims.Claim.Resource%2A> sia di tipo <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="d4d73-119">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], statements in SAML tokens are modeled as <xref:System.IdentityModel.Tokens.SamlAttribute> objects, which can be populated directly from <xref:System.IdentityModel.Claims.Claim> objects, provided the <xref:System.IdentityModel.Claims.Claim> object has a <xref:System.IdentityModel.Claims.Claim.Right%2A> property of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> and the <xref:System.IdentityModel.Claims.Claim.Resource%2A> property is of type <xref:System.String>.</span></span> <span data-ttu-id="d4d73-120">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d4d73-120">For example:</span></span>  
  
 [!code-csharp[c_CreateSTS#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#8)]
 [!code-vb[c_CreateSTS#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#8)]  
  
> [!NOTE]
>  <span data-ttu-id="d4d73-121">Quando i token SAML vengono serializzati nei messaggi, quando sono rilasciati da un servizio token di sicurezza o quando sono presentati dai client ai servizi nell'ambito dell'autenticazione, la quota della dimensione massima del messaggio deve essere sufficientemente grande da contenere il token SAML e le altre parti del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d4d73-121">When SAML tokens are serialized in messages, either when they are issued by a security token service or when they are presented by clients to services as part of authentication, the maximum message size quota must be sufficiently large to accommodate the SAML token and the other message parts.</span></span> <span data-ttu-id="d4d73-122">Normalmente la quota della dimensione predefinita del messaggio è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="d4d73-122">In normal cases, the default message size quotas are sufficient.</span></span> <span data-ttu-id="d4d73-123">È tuttavia possibile, nei casi in cui un token SAML sia di grandi dimensioni perché contiene centinaia di attestazioni, che risulti necessario aumentare le quote per contenere il token serializzato.</span><span class="sxs-lookup"><span data-stu-id="d4d73-123">However, in cases where a SAML token is large because it contains hundreds of claims, you may need to increase the quotas to accommodate the serialized token.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="d4d73-124">[Considerazioni sulla sicurezza per i dati](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).</span><span class="sxs-lookup"><span data-stu-id="d4d73-124"> [Security Considerations for Data](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).</span></span>  
  
## <a name="from-samlattributes-to-claims"></a><span data-ttu-id="d4d73-125">Da SamlAttributes ad attestazioni</span><span class="sxs-lookup"><span data-stu-id="d4d73-125">From SamlAttributes to Claims</span></span>  
 <span data-ttu-id="d4d73-126">Quando i token SAML vengono ricevuti nei messaggi, le varie istruzioni contenute nel token SAML vengono trasformate in oggetti <xref:System.IdentityModel.Policy.IAuthorizationPolicy> inseriti in <xref:System.IdentityModel.Policy.AuthorizationContext>.</span><span class="sxs-lookup"><span data-stu-id="d4d73-126">When SAML tokens are received in messages, the various statements in the SAML token are turned into <xref:System.IdentityModel.Policy.IAuthorizationPolicy> objects that are placed into the <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span> <span data-ttu-id="d4d73-127">Le attestazioni di ogni istruzione SAML sono restituite dalla proprietà <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> di <xref:System.IdentityModel.Policy.AuthorizationContext> e possono essere esaminate per determinare se autenticare e autorizzare l'utente.</span><span class="sxs-lookup"><span data-stu-id="d4d73-127">The claims from each SAML statement are returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> and can be examined to determine whether to authenticate and authorize the user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4d73-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4d73-128">See Also</span></span>  
 <xref:System.IdentityModel.Policy.AuthorizationContext>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 <xref:System.IdentityModel.Claims.ClaimSet>  
 [<span data-ttu-id="d4d73-129">Federazione</span><span class="sxs-lookup"><span data-stu-id="d4d73-129">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 [<span data-ttu-id="d4d73-130">Procedura: Creare un client federato</span><span class="sxs-lookup"><span data-stu-id="d4d73-130">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="d4d73-131">Procedura: Configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="d4d73-131">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="d4d73-132">Gestione delle attestazioni e dell'autorizzazione con il modello di identità</span><span class="sxs-lookup"><span data-stu-id="d4d73-132">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="d4d73-133">Attestazioni e token</span><span class="sxs-lookup"><span data-stu-id="d4d73-133">Claims and Tokens</span></span>](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)  
 [<span data-ttu-id="d4d73-134">Creazione di attestazioni e valori delle risorse</span><span class="sxs-lookup"><span data-stu-id="d4d73-134">Claim Creation and Resource Values</span></span>](../../../../docs/framework/wcf/feature-details/claim-creation-and-resource-values.md)  
 [<span data-ttu-id="d4d73-135">Procedura: Creare un'attestazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="d4d73-135">How to: Create a Custom Claim</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)
