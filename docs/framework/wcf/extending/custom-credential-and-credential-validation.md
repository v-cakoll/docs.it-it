---
title: Credenziale personalizzata e convalida della credenziale
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3ca7726f3a6a0c5faaab1cbbd0b31125ce0c1d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="custom-credential-and-credential-validation"></a><span data-ttu-id="3d889-102">Credenziale personalizzata e convalida della credenziale</span><span class="sxs-lookup"><span data-stu-id="3d889-102">Custom Credential and Credential Validation</span></span>
<span data-ttu-id="3d889-103">La protezione in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] si basa sullo scambio di credenziali tra servizi e client.</span><span class="sxs-lookup"><span data-stu-id="3d889-103">Security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is based on the exchange of credentials between services and clients.</span></span> <span data-ttu-id="3d889-104">La maggior parte degli scenari di sicurezza può essere soddisfatta usando tipi di credenziali comuni, ad esempio Windows (Kerberos), nome utente e password e certificati.</span><span class="sxs-lookup"><span data-stu-id="3d889-104">Most security scenarios can be satisfied using common credential types, such as Windows (Kerberos), username and passwords, and certificates.</span></span> <span data-ttu-id="3d889-105">Tuttavia, se è necessario un nuovo tipo di credenziale, negli argomenti di questa sezione viene illustrato come gestire e convalidare nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="3d889-105">However, if a new type of credential is required, the topics in this section explain how to handle and validate new types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3d889-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3d889-106">In This Section</span></span>  
 [<span data-ttu-id="3d889-107">Procedura: creare un servizio che usa un Validator del certificato personalizzato</span><span class="sxs-lookup"><span data-stu-id="3d889-107">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 <span data-ttu-id="3d889-108">Viene illustrato come personalizzare la convalida [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ereditando dalla classe <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="3d889-108">Explains how to customize [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] validation by inheriting from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span>  
  
 [<span data-ttu-id="3d889-109">Procedura dettagliata: Creazione di Client personalizzate e le credenziali del servizio</span><span class="sxs-lookup"><span data-stu-id="3d889-109">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 <span data-ttu-id="3d889-110">Viene illustrato come estendere il <xref:System.ServiceModel.Description.ClientCredentials> e <xref:System.ServiceModel.Description.ServiceCredentials> classi per accogliere nuovi tipi di credenziali.</span><span class="sxs-lookup"><span data-stu-id="3d889-110">Demonstrates how to extend the <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes to accommodate new credential types.</span></span> <span data-ttu-id="3d889-111">Si tratta del primo di una serie di argomenti sulla creazione di tipi di credenziali personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3d889-111">This is first in a series of topics that enable creation of custom credential types.</span></span>  
  
 [<span data-ttu-id="3d889-112">Procedura: creare un Provider di Token di sicurezza personalizzato</span><span class="sxs-lookup"><span data-stu-id="3d889-112">How to: Create a Custom Security Token Provider</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 <span data-ttu-id="3d889-113">Viene illustrato come creare un provider di token di sicurezza per gestire nuovi tipi di credenziali e restituire nuovi token per la credenziale.</span><span class="sxs-lookup"><span data-stu-id="3d889-113">Explains how to create a security token provider to handle new credential types and return new tokens for the credential.</span></span> <span data-ttu-id="3d889-114">Si tratta del secondo argomento della serie.</span><span class="sxs-lookup"><span data-stu-id="3d889-114">This is the second topic in the series.</span></span>  
  
 [<span data-ttu-id="3d889-115">Procedura: creare un autenticatore del Token di sicurezza personalizzato</span><span class="sxs-lookup"><span data-stu-id="3d889-115">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 <span data-ttu-id="3d889-116">Viene illustrato come creare un autenticatore personalizzato per autenticare un nuovo tipo di credenziale.</span><span class="sxs-lookup"><span data-stu-id="3d889-116">Explains how to create a custom authenticator to authenticate a new credential type.</span></span> <span data-ttu-id="3d889-117">Si tratta del terzo argomento della serie.</span><span class="sxs-lookup"><span data-stu-id="3d889-117">This is the third topic in the series.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3d889-118">Riferimento</span><span class="sxs-lookup"><span data-stu-id="3d889-118">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a><span data-ttu-id="3d889-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="3d889-119">Related Sections</span></span>  
 [<span data-ttu-id="3d889-120">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="3d889-120">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="3d889-121">Federazione e token emessi</span><span class="sxs-lookup"><span data-stu-id="3d889-121">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="3d889-122">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3d889-122">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="3d889-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d889-123">See Also</span></span>  
 [<span data-ttu-id="3d889-124">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3d889-124">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
