---
title: Estensione della protezione
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 45216493a3afa23f24a085964a2c43e19b197d4b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797127"
---
# <a name="extending-security"></a><span data-ttu-id="8e5b4-102">Estensione della protezione</span><span class="sxs-lookup"><span data-stu-id="8e5b4-102">Extending Security</span></span>
<span data-ttu-id="8e5b4-103">Per supportare nuovi tipi di attestazione e token personalizzati, è possibile estendere l'infrastruttura di sicurezza di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8e5b4-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="8e5b4-104">Questa operazione viene descritta negli argomenti di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="8e5b4-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8e5b4-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="8e5b4-105">In This Section</span></span>  
  
 [<span data-ttu-id="8e5b4-106">Credenziali personalizzate e convalida delle credenziali</span><span class="sxs-lookup"><span data-stu-id="8e5b4-106">Custom Credential and Credential Validation</span></span>](custom-credential-and-credential-validation.md)  
 <span data-ttu-id="8e5b4-107">Viene spiegato il modo in cui il modello di identità viene utilizzato durante la convalida di credenziali personalizzate.</span><span class="sxs-lookup"><span data-stu-id="8e5b4-107">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="8e5b4-108">Token personalizzati</span><span class="sxs-lookup"><span data-stu-id="8e5b4-108">Custom Tokens</span></span>](custom-tokens.md)  
 <span data-ttu-id="8e5b4-109">I token rilasciati da un servizio token di sicurezza (STS) sono in genere token SAML.</span><span class="sxs-lookup"><span data-stu-id="8e5b4-109">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="8e5b4-110">In questo argomento viene spiegato come creare un tipo di token personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8e5b4-110">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="8e5b4-111">Autorizzazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="8e5b4-111">Custom Authorization</span></span>](custom-authorization.md)  
 <span data-ttu-id="8e5b4-112">Viene spiegato come implementare un'autorizzazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="8e5b4-112">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="8e5b4-113">Override dell'identità di un servizio per l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="8e5b4-113">Overriding the Identity of a Service for Authentication</span></span>](overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="8e5b4-114">Viene descritto come eseguire l'override dell'identità di un servizio per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="8e5b4-114">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="8e5b4-115">Procedura: Creare un verificatore di identità client personalizzato</span><span class="sxs-lookup"><span data-stu-id="8e5b4-115">How to: Create a Custom Client Identity Verifier</span></span>](how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="8e5b4-116">Viene dimostrato come convalidare l'identità di un endpoint personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8e5b4-116">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="8e5b4-117">Procedura: Usare certificati X. 509 distinti per la firma e la crittografia</span><span class="sxs-lookup"><span data-stu-id="8e5b4-117">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="8e5b4-118">I messaggi vengono in genere firmati e crittografati con un solo certificato.</span><span class="sxs-lookup"><span data-stu-id="8e5b4-118">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="8e5b4-119">In questo argomento viene spiegato come sia possibile utilizzare due certificati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="8e5b4-119">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="8e5b4-120">Procedura: Modificare il provider di crittografia per la chiave privata di un certificato X. 509</span><span class="sxs-lookup"><span data-stu-id="8e5b4-120">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="8e5b4-121">Viene illustrato come modificare il provider di crittografia utilizzato per fornire la chiave privata di un certificato X. 509 e come integrare il provider nel Framework Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8e5b4-121">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8e5b4-122">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="8e5b4-122">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="8e5b4-123">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="8e5b4-123">Related Sections</span></span>  
 [<span data-ttu-id="8e5b4-124">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8e5b4-124">Security</span></span>](../feature-details/security.md)  
  
 [<span data-ttu-id="8e5b4-125">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="8e5b4-125">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="8e5b4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e5b4-126">See also</span></span>

- [<span data-ttu-id="8e5b4-127">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="8e5b4-127">Security Overview</span></span>](../feature-details/security-overview.md)
