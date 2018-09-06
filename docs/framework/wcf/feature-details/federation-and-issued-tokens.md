---
title: Federazione e token emessi
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
ms.openlocfilehash: bdbd5c49197b65816da9b0f2c87d97afb893d79f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43788104"
---
# <a name="federation-and-issued-tokens"></a><span data-ttu-id="cc907-102">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="cc907-102">Federation and Issued Tokens</span></span>
<span data-ttu-id="cc907-103">Con Windows Communication Foundation (WCF), è possibile creare i client che comunicano in modo sicuro con i servizi che implementano le specifiche WS-Federation e WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="cc907-103">With Windows Communication Foundation (WCF), you can create clients that communicate securely with services that implement the WS-Federation and WS-Trust specifications.</span></span> <span data-ttu-id="cc907-104">Le specifiche utilizzano XML, SOAP e Web Services Description Language (WSDL) per fornire meccanismi che consentano l'autenticazione e l'autorizzazione in diverse aree di attendibilità.</span><span class="sxs-lookup"><span data-stu-id="cc907-104">The specifications use XML, SOAP, and Web Services Description Language (WSDL) to provide mechanisms that enable authentication and authorization across different trust realms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc907-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="cc907-105">In This Section</span></span>  
 [<span data-ttu-id="cc907-106">Federazione</span><span class="sxs-lookup"><span data-stu-id="cc907-106">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 <span data-ttu-id="cc907-107">Fornisce una panoramica della federazione.</span><span class="sxs-lookup"><span data-stu-id="cc907-107">Provides an overview of federation.</span></span>  
  
 [<span data-ttu-id="cc907-108">Federazione e attendibilità</span><span class="sxs-lookup"><span data-stu-id="cc907-108">Federation and Trust</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)  
 <span data-ttu-id="cc907-109">Elenca i problemi di progettazione da tenere in considerazione durante la creazione di servizi o di client federati.</span><span class="sxs-lookup"><span data-stu-id="cc907-109">Lists the design issues to be aware of when creating federated services or clients.</span></span>  
  
 [<span data-ttu-id="cc907-110">Procedura: Creare un client federato</span><span class="sxs-lookup"><span data-stu-id="cc907-110">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 <span data-ttu-id="cc907-111">Descrive i concetti fondamentali della creazione di un client federato con WCF.</span><span class="sxs-lookup"><span data-stu-id="cc907-111">Describes the basics of creating a federated client with WCF.</span></span>  
  
 [<span data-ttu-id="cc907-112">Procedura: Configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="cc907-112">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 <span data-ttu-id="cc907-113">Descrive i passaggi necessari per la creazione di un servizio federato.</span><span class="sxs-lookup"><span data-stu-id="cc907-113">Describes the steps of creating a federated service.</span></span>  
  
 [<span data-ttu-id="cc907-114">Procedura: Creare una classe WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="cc907-114">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="cc907-115">Descrive come configurare client e servizi che utilizzano `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="cc907-115">Describes how to configure clients and services that use the `WSFederationHttpBinding`.</span></span>  
  
 [<span data-ttu-id="cc907-116">Procedura: Creare un servizio token di sicurezza</span><span class="sxs-lookup"><span data-stu-id="cc907-116">How to: Create a Security Token Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-token-service.md)  
 <span data-ttu-id="cc907-117">Descrive i passaggi necessari per la creazione di un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cc907-117">Describes the steps of creating a security token service.</span></span>  
  
 [<span data-ttu-id="cc907-118">Attestazioni e token SAML (Security Assertions Markup Language)</span><span class="sxs-lookup"><span data-stu-id="cc907-118">Security Assertions Markup Language (SAML) Tokens and Claims</span></span>](../../../../docs/framework/wcf/feature-details/saml-tokens-and-claims.md)  
 <span data-ttu-id="cc907-119">Descrive i token Security Assertions Markup Language (SAML) che sono flessibili e consentono di creare tipi di attestazione dettagliati.</span><span class="sxs-lookup"><span data-stu-id="cc907-119">Describes Security Assertions Markup Language (SAML) tokens, which are extensible and enable you to create rich claim types.</span></span>  
  
 [<span data-ttu-id="cc907-120">Procedura: Configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="cc907-120">How to: Configure a Local Issuer</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 <span data-ttu-id="cc907-121">Descrive come creare un emittente locale di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cc907-121">Describes how to create a local issuer of security tokens.</span></span>  
  
 [<span data-ttu-id="cc907-122">Procedura: Disabilitare sessioni sicure in un'associazione WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="cc907-122">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="cc907-123">Descrive come disattivare sessioni protette in `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="cc907-123">Describes how to disable secure sessions on a `WSFederationHttpBinding`.</span></span> <span data-ttu-id="cc907-124">La disattivazione di sessioni protette è necessaria in caso di creazione di una Web farm che richiede una sessione per ogni client.</span><span class="sxs-lookup"><span data-stu-id="cc907-124">Disabling secure sessions is necessary when creating a Web farm that requires a session for each client.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cc907-125">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="cc907-125">Reference</span></span>  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a><span data-ttu-id="cc907-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc907-126">See Also</span></span>  
 [<span data-ttu-id="cc907-127">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="cc907-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="cc907-128">Token personalizzati</span><span class="sxs-lookup"><span data-stu-id="cc907-128">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 [<span data-ttu-id="cc907-129">Modello di sicurezza per Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="cc907-129">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
