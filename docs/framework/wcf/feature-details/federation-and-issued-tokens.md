---
title: Federazione e token emessi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 017d3e51022ad9980dc8f058415697c80a2a6b35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="federation-and-issued-tokens"></a><span data-ttu-id="2314d-102">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="2314d-102">Federation and Issued Tokens</span></span>
<span data-ttu-id="2314d-103">Con [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] è possibile creare client che comunicano in modo protetto con servizi che implementano le specifiche di WS-Federation e WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="2314d-103">With [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], you can create clients that communicate securely with services that implement the WS-Federation and WS-Trust specifications.</span></span> <span data-ttu-id="2314d-104">Le specifiche utilizzano XML, SOAP e Web Services Description Language (WSDL) per fornire meccanismi che consentano l'autenticazione e l'autorizzazione in diverse aree di attendibilità.</span><span class="sxs-lookup"><span data-stu-id="2314d-104">The specifications use XML, SOAP, and Web Services Description Language (WSDL) to provide mechanisms that enable authentication and authorization across different trust realms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2314d-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="2314d-105">In This Section</span></span>  
 [<span data-ttu-id="2314d-106">Federazione</span><span class="sxs-lookup"><span data-stu-id="2314d-106">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 <span data-ttu-id="2314d-107">Fornisce una panoramica della federazione.</span><span class="sxs-lookup"><span data-stu-id="2314d-107">Provides an overview of federation.</span></span>  
  
 [<span data-ttu-id="2314d-108">Federazione e attendibilità</span><span class="sxs-lookup"><span data-stu-id="2314d-108">Federation and Trust</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)  
 <span data-ttu-id="2314d-109">Elenca i problemi di progettazione da tenere in considerazione durante la creazione di servizi o di client federati.</span><span class="sxs-lookup"><span data-stu-id="2314d-109">Lists the design issues to be aware of when creating federated services or clients.</span></span>  
  
 [<span data-ttu-id="2314d-110">Procedura: Creare un client federato</span><span class="sxs-lookup"><span data-stu-id="2314d-110">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 <span data-ttu-id="2314d-111">Descrive le nozioni fondamentali sulla creazione di un client federato con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2314d-111">Describes the basics of creating a federated client with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="2314d-112">Procedura: Configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="2314d-112">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 <span data-ttu-id="2314d-113">Descrive i passaggi necessari per la creazione di un servizio federato.</span><span class="sxs-lookup"><span data-stu-id="2314d-113">Describes the steps of creating a federated service.</span></span>  
  
 [<span data-ttu-id="2314d-114">Procedura: Creare una classe WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="2314d-114">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="2314d-115">Descrive come configurare client e servizi che utilizzano `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="2314d-115">Describes how to configure clients and services that use the `WSFederationHttpBinding`.</span></span>  
  
 [<span data-ttu-id="2314d-116">Procedura: Creare un servizio token di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2314d-116">How to: Create a Security Token Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-token-service.md)  
 <span data-ttu-id="2314d-117">Descrive i passaggi necessari per la creazione di un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2314d-117">Describes the steps of creating a security token service.</span></span>  
  
 [<span data-ttu-id="2314d-118">Attestazioni e token SAML (Security Assertions Markup Language)</span><span class="sxs-lookup"><span data-stu-id="2314d-118">Security Assertions Markup Language (SAML) Tokens and Claims</span></span>](../../../../docs/framework/wcf/feature-details/saml-tokens-and-claims.md)  
 <span data-ttu-id="2314d-119">Descrive i token Security Assertions Markup Language (SAML) che sono flessibili e consentono di creare tipi di attestazione dettagliati.</span><span class="sxs-lookup"><span data-stu-id="2314d-119">Describes Security Assertions Markup Language (SAML) tokens, which are extensible and enable you to create rich claim types.</span></span>  
  
 [<span data-ttu-id="2314d-120">Procedura: Configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="2314d-120">How to: Configure a Local Issuer</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 <span data-ttu-id="2314d-121">Descrive come creare un emittente locale di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2314d-121">Describes how to create a local issuer of security tokens.</span></span>  
  
 [<span data-ttu-id="2314d-122">Procedura: Disabilitare sessioni sicure in un'associazione WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="2314d-122">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="2314d-123">Descrive come disattivare sessioni protette in `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="2314d-123">Describes how to disable secure sessions on a `WSFederationHttpBinding`.</span></span> <span data-ttu-id="2314d-124">La disattivazione di sessioni protette è necessaria in caso di creazione di una Web farm che richiede una sessione per ogni client.</span><span class="sxs-lookup"><span data-stu-id="2314d-124">Disabling secure sessions is necessary when creating a Web farm that requires a session for each client.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2314d-125">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="2314d-125">Reference</span></span>  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a><span data-ttu-id="2314d-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2314d-126">See Also</span></span>  
 [<span data-ttu-id="2314d-127">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2314d-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="2314d-128">Token personalizzati</span><span class="sxs-lookup"><span data-stu-id="2314d-128">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 [<span data-ttu-id="2314d-129">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="2314d-129">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
