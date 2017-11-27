---
title: Estensione della protezione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
caps.latest.revision: "23"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: a3950b156ede806382bbe4e013db5d94a8b20a23
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="extending-security"></a><span data-ttu-id="19146-102">Estensione della protezione</span><span class="sxs-lookup"><span data-stu-id="19146-102">Extending Security</span></span>
<span data-ttu-id="19146-103">Per contenere nuovi tipi di attestazione e nuovi token personalizzati, è possibile estendere l'infrastruttura di sicurezza di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19146-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="19146-104">Questa operazione viene descritta negli argomenti di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="19146-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="19146-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="19146-105">In This Section</span></span>  
 [<span data-ttu-id="19146-106">Architettura di sicurezza</span><span class="sxs-lookup"><span data-stu-id="19146-106">Security Architecture</span></span>](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)  
 <span data-ttu-id="19146-107">Viene illustrata l'architettura del sistema della protezione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19146-107">Walks through the architecture of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security system.</span></span>  
  
 [<span data-ttu-id="19146-108">Credenziale personalizzata e convalida delle credenziali</span><span class="sxs-lookup"><span data-stu-id="19146-108">Custom Credential and Credential Validation</span></span>](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 <span data-ttu-id="19146-109">Viene spiegato il modo in cui il modello di identità viene utilizzato durante la convalida di credenziali personalizzate.</span><span class="sxs-lookup"><span data-stu-id="19146-109">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="19146-110">Token personalizzati</span><span class="sxs-lookup"><span data-stu-id="19146-110">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 <span data-ttu-id="19146-111">I token rilasciati da un servizio token di sicurezza (STS) sono in genere token SAML.</span><span class="sxs-lookup"><span data-stu-id="19146-111">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="19146-112">In questo argomento viene spiegato come creare un tipo di token personalizzato.</span><span class="sxs-lookup"><span data-stu-id="19146-112">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="19146-113">Autorizzazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="19146-113">Custom Authorization</span></span>](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 <span data-ttu-id="19146-114">Viene spiegato come implementare un'autorizzazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="19146-114">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="19146-115">Override dell'identità di un servizio per l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="19146-115">Overriding the Identity of a Service for Authentication</span></span>](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="19146-116">Viene descritto come eseguire l'override dell'identità di un servizio per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="19146-116">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="19146-117">Procedura: creare un verificatore di identità Client personalizzato</span><span class="sxs-lookup"><span data-stu-id="19146-117">How to: Create a Custom Client Identity Verifier</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="19146-118">Viene dimostrato come convalidare l'identità di un endpoint personalizzato.</span><span class="sxs-lookup"><span data-stu-id="19146-118">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="19146-119">Procedura: usare i certificati x. 509 separati per la firma e crittografia</span><span class="sxs-lookup"><span data-stu-id="19146-119">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="19146-120">I messaggi vengono in genere firmati e crittografati con un solo certificato.</span><span class="sxs-lookup"><span data-stu-id="19146-120">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="19146-121">In questo argomento viene spiegato come sia possibile utilizzare due certificati, se necessario.</span><span class="sxs-lookup"><span data-stu-id="19146-121">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="19146-122">Procedura: modificare il Provider di crittografia per la chiave privata del certificato x. 509</span><span class="sxs-lookup"><span data-stu-id="19146-122">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="19146-123">Viene illustrato come modificare il provider di crittografia utilizzato per fornire la chiave privata di un certificato X.509 e come integrare il provider nel framework di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19146-123">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="19146-124">Riferimento</span><span class="sxs-lookup"><span data-stu-id="19146-124">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="19146-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="19146-125">Related Sections</span></span>  
 [<span data-ttu-id="19146-126">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="19146-126">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="19146-127">Programmazione WCF di base</span><span class="sxs-lookup"><span data-stu-id="19146-127">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="19146-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19146-128">See Also</span></span>  
 [<span data-ttu-id="19146-129">Cenni preliminari sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="19146-129">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
