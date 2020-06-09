---
title: Federazione e token emessi
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
ms.openlocfilehash: aeffc1e2a7b61dfd9406b9f06678064533ea61ec
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595505"
---
# <a name="federation-and-issued-tokens"></a><span data-ttu-id="d7d5e-102">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="d7d5e-102">Federation and Issued Tokens</span></span>
<span data-ttu-id="d7d5e-103">Con Windows Communication Foundation (WCF) è possibile creare client che comunicano in modo sicuro con servizi che implementano le specifiche WS-Federation e WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="d7d5e-103">With Windows Communication Foundation (WCF), you can create clients that communicate securely with services that implement the WS-Federation and WS-Trust specifications.</span></span> <span data-ttu-id="d7d5e-104">Le specifiche utilizzano XML, SOAP e Web Services Description Language (WSDL) per fornire meccanismi che consentano l'autenticazione e l'autorizzazione in diverse aree di attendibilità.</span><span class="sxs-lookup"><span data-stu-id="d7d5e-104">The specifications use XML, SOAP, and Web Services Description Language (WSDL) to provide mechanisms that enable authentication and authorization across different trust realms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7d5e-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d7d5e-105">In This Section</span></span>  
 [<span data-ttu-id="d7d5e-106">Federazione</span><span class="sxs-lookup"><span data-stu-id="d7d5e-106">Federation</span></span>](federation.md)  
 <span data-ttu-id="d7d5e-107">Fornisce una panoramica della federazione.</span><span class="sxs-lookup"><span data-stu-id="d7d5e-107">Provides an overview of federation.</span></span>  
  
 [<span data-ttu-id="d7d5e-108">Federazione e attendibilità</span><span class="sxs-lookup"><span data-stu-id="d7d5e-108">Federation and Trust</span></span>](federation-and-trust.md)  
 <span data-ttu-id="d7d5e-109">Elenca i problemi di progettazione da tenere in considerazione durante la creazione di servizi o di client federati.</span><span class="sxs-lookup"><span data-stu-id="d7d5e-109">Lists the design issues to be aware of when creating federated services or clients.</span></span>  
  
 [<span data-ttu-id="d7d5e-110">Procedura: creare un client federato</span><span class="sxs-lookup"><span data-stu-id="d7d5e-110">How to: Create a Federated Client</span></span>](how-to-create-a-federated-client.md)  
 <span data-ttu-id="d7d5e-111">Vengono descritte le nozioni di base sulla creazione di un client federato con WCF.</span><span class="sxs-lookup"><span data-stu-id="d7d5e-111">Describes the basics of creating a federated client with WCF.</span></span>  
  
 [<span data-ttu-id="d7d5e-112">Procedura: configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="d7d5e-112">How to: Configure Credentials on a Federation Service</span></span>](how-to-configure-credentials-on-a-federation-service.md)  
 <span data-ttu-id="d7d5e-113">Descrive i passaggi necessari per la creazione di un servizio federato.</span><span class="sxs-lookup"><span data-stu-id="d7d5e-113">Describes the steps of creating a federated service.</span></span>  
  
 [<span data-ttu-id="d7d5e-114">Procedura: Creare una classe WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d7d5e-114">How to: Create a WSFederationHttpBinding</span></span>](how-to-create-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="d7d5e-115">Descrive come configurare client e servizi che utilizzano `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="d7d5e-115">Describes how to configure clients and services that use the `WSFederationHttpBinding`.</span></span>  
  
 [<span data-ttu-id="d7d5e-116">Procedura: creare un servizio token di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d7d5e-116">How to: Create a Security Token Service</span></span>](how-to-create-a-security-token-service.md)  
 <span data-ttu-id="d7d5e-117">Descrive i passaggi necessari per la creazione di un servizio token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d7d5e-117">Describes the steps of creating a security token service.</span></span>  
  
 [<span data-ttu-id="d7d5e-118">Attestazioni e token SAML (Security Assertions Markup Language)</span><span class="sxs-lookup"><span data-stu-id="d7d5e-118">Security Assertions Markup Language (SAML) Tokens and Claims</span></span>](saml-tokens-and-claims.md)  
 <span data-ttu-id="d7d5e-119">Descrive i token Security Assertions Markup Language (SAML) che sono flessibili e consentono di creare tipi di attestazione dettagliati.</span><span class="sxs-lookup"><span data-stu-id="d7d5e-119">Describes Security Assertions Markup Language (SAML) tokens, which are extensible and enable you to create rich claim types.</span></span>  
  
 [<span data-ttu-id="d7d5e-120">Procedura: configurare un emittente locale</span><span class="sxs-lookup"><span data-stu-id="d7d5e-120">How to: Configure a Local Issuer</span></span>](how-to-configure-a-local-issuer.md)  
 <span data-ttu-id="d7d5e-121">Descrive come creare un emittente locale di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d7d5e-121">Describes how to create a local issuer of security tokens.</span></span>  
  
 [<span data-ttu-id="d7d5e-122">Procedura: disattivare sessioni protette in un'associazione WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d7d5e-122">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="d7d5e-123">Descrive come disattivare sessioni protette in `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="d7d5e-123">Describes how to disable secure sessions on a `WSFederationHttpBinding`.</span></span> <span data-ttu-id="d7d5e-124">La disattivazione di sessioni protette è necessaria in caso di creazione di una Web farm che richiede una sessione per ogni client.</span><span class="sxs-lookup"><span data-stu-id="d7d5e-124">Disabling secure sessions is necessary when creating a Web farm that requires a session for each client.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d7d5e-125">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="d7d5e-125">Reference</span></span>  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a><span data-ttu-id="d7d5e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7d5e-126">See also</span></span>

- [<span data-ttu-id="d7d5e-127">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="d7d5e-127">Authorization</span></span>](authorization-in-wcf.md)
- [<span data-ttu-id="d7d5e-128">Token personalizzati</span><span class="sxs-lookup"><span data-stu-id="d7d5e-128">Custom Tokens</span></span>](../extending/custom-tokens.md)
- <span data-ttu-id="d7d5e-129">[Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d7d5e-129">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
