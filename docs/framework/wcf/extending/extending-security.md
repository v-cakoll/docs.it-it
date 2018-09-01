---
title: Estensione della protezione
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: a16416e580dabd6a9057e11a8183437529ca83e8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43384412"
---
# <a name="extending-security"></a><span data-ttu-id="5d9d0-102">Estensione della protezione</span><span class="sxs-lookup"><span data-stu-id="5d9d0-102">Extending Security</span></span>
<span data-ttu-id="5d9d0-103">Per supportare nuovi tipi di attestazioni e token personalizzati, è possibile estendere l'infrastruttura di sicurezza di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5d9d0-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="5d9d0-104">Questa operazione viene descritta negli argomenti di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="5d9d0-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d9d0-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="5d9d0-105">In This Section</span></span>  
 [<span data-ttu-id="5d9d0-106">Architettura di sicurezza</span><span class="sxs-lookup"><span data-stu-id="5d9d0-106">Security Architecture</span></span>](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)  
 <span data-ttu-id="5d9d0-107">Illustra in dettaglio l'architettura di sistema di sicurezza di WCF.</span><span class="sxs-lookup"><span data-stu-id="5d9d0-107">Walks through the architecture of the WCF security system.</span></span>  
  
 [<span data-ttu-id="5d9d0-108">Credenziali personalizzate e convalida delle credenziali</span><span class="sxs-lookup"><span data-stu-id="5d9d0-108">Custom Credential and Credential Validation</span></span>](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 <span data-ttu-id="5d9d0-109">Viene spiegato il modo in cui il modello di identità viene utilizzato durante la convalida di credenziali personalizzate.</span><span class="sxs-lookup"><span data-stu-id="5d9d0-109">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="5d9d0-110">Token personalizzati</span><span class="sxs-lookup"><span data-stu-id="5d9d0-110">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 <span data-ttu-id="5d9d0-111">I token rilasciati da un servizio token di sicurezza (STS) sono in genere token SAML.</span><span class="sxs-lookup"><span data-stu-id="5d9d0-111">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="5d9d0-112">In questo argomento viene spiegato come creare un tipo di token personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5d9d0-112">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="5d9d0-113">Autorizzazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="5d9d0-113">Custom Authorization</span></span>](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 <span data-ttu-id="5d9d0-114">Viene spiegato come implementare un'autorizzazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5d9d0-114">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="5d9d0-115">Override dell'identità di un servizio per l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="5d9d0-115">Overriding the Identity of a Service for Authentication</span></span>](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="5d9d0-116">Viene descritto come eseguire l'override dell'identità di un servizio per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="5d9d0-116">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="5d9d0-117">Procedura: Creare un verificatore di identità client personalizzato</span><span class="sxs-lookup"><span data-stu-id="5d9d0-117">How to: Create a Custom Client Identity Verifier</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="5d9d0-118">Viene dimostrato come convalidare l'identità di un endpoint personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5d9d0-118">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="5d9d0-119">Procedura: Usare certificati X.509 separati per la firma e la crittografia</span><span class="sxs-lookup"><span data-stu-id="5d9d0-119">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="5d9d0-120">I messaggi vengono in genere firmati e crittografati con un solo certificato.</span><span class="sxs-lookup"><span data-stu-id="5d9d0-120">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="5d9d0-121">In questo argomento viene spiegato come sia possibile utilizzare due certificati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="5d9d0-121">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="5d9d0-122">Procedura: Modificare il provider di crittografia per la chiave privata di un certificato X.509</span><span class="sxs-lookup"><span data-stu-id="5d9d0-122">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="5d9d0-123">Viene illustrato come modificare il provider di crittografia utilizzato per fornire la chiave privata di un certificato X.509 e come integrare il provider nel framework di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5d9d0-123">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5d9d0-124">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="5d9d0-124">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="5d9d0-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="5d9d0-125">Related Sections</span></span>  
 [<span data-ttu-id="5d9d0-126">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5d9d0-126">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="5d9d0-127">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="5d9d0-127">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="5d9d0-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d9d0-128">See Also</span></span>  
 [<span data-ttu-id="5d9d0-129">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="5d9d0-129">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
