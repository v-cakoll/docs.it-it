---
title: '&lt;certificateValidation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 778088f2e0508f5a80c29ae027b2442a80286795
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltcertificatevalidationgt"></a><span data-ttu-id="08ca8-102">&lt;certificateValidation&gt;</span><span class="sxs-lookup"><span data-stu-id="08ca8-102">&lt;certificateValidation&gt;</span></span>
<span data-ttu-id="08ca8-103">Controlla le impostazioni che utilizzano gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="08ca8-103">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="08ca8-104">Queste impostazioni vengono ignorate se un gestore specifico è configurato con il proprio servizio di convalida.</span><span class="sxs-lookup"><span data-stu-id="08ca8-104">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="08ca8-105">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="08ca8-105">\<system.identityModel></span></span>  
<span data-ttu-id="08ca8-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="08ca8-106">\<identityConfiguration></span></span>  
<span data-ttu-id="08ca8-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="08ca8-107">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08ca8-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08ca8-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08ca8-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="08ca8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="08ca8-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="08ca8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08ca8-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="08ca8-111">Attributes</span></span>  
  
|<span data-ttu-id="08ca8-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="08ca8-112">Attribute</span></span>|<span data-ttu-id="08ca8-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08ca8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="08ca8-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="08ca8-114">certificateValidationMode</span></span>|<span data-ttu-id="08ca8-115">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valore che specifica la modalità di convalida da utilizzare per il certificato x. 509.</span><span class="sxs-lookup"><span data-stu-id="08ca8-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="08ca8-116">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="08ca8-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="08ca8-117">Per specificare un validator personalizzato, impostare questo attributo su "Custom" e specificare il servizio di convalida utilizzando il [ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="08ca8-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="08ca8-118">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="08ca8-118">Optional.</span></span>|  
|<span data-ttu-id="08ca8-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="08ca8-119">revocationMode</span></span>|<span data-ttu-id="08ca8-120">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valore che specifica la modalità di revoche di certificati da utilizzare per il certificato x. 509.</span><span class="sxs-lookup"><span data-stu-id="08ca8-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="08ca8-121">Il valore predefinito è "Online".</span><span class="sxs-lookup"><span data-stu-id="08ca8-121">The default value is "Online".</span></span> <span data-ttu-id="08ca8-122">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="08ca8-122">Optional.</span></span>|  
|<span data-ttu-id="08ca8-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="08ca8-123">trustedStoreLocation</span></span>|<span data-ttu-id="08ca8-124">Oggetto <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valore che specifica l'archivio certificati x. 509.</span><span class="sxs-lookup"><span data-stu-id="08ca8-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="08ca8-125">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="08ca8-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="08ca8-126">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="08ca8-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08ca8-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="08ca8-127">Child Elements</span></span>  
  
|<span data-ttu-id="08ca8-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="08ca8-128">Element</span></span>|<span data-ttu-id="08ca8-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08ca8-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08ca8-130">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="08ca8-130">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="08ca8-131">Specifica un tipo personalizzato per la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="08ca8-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="08ca8-132">Questo tipo viene utilizzato solo se il `certificateValidationMode` attributo del [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) viene impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="08ca8-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="08ca8-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="08ca8-133">Parent Elements</span></span>  
  
|<span data-ttu-id="08ca8-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="08ca8-134">Element</span></span>|<span data-ttu-id="08ca8-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08ca8-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08ca8-136">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="08ca8-136">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="08ca8-137">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="08ca8-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="08ca8-138">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="08ca8-138">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="08ca8-139">Fornisce la configurazione per una raccolta di sicurezza gestori di token.</span><span class="sxs-lookup"><span data-stu-id="08ca8-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08ca8-140">Note</span><span class="sxs-lookup"><span data-stu-id="08ca8-140">Remarks</span></span>  
 <span data-ttu-id="08ca8-141">A `<certificateValidation>` elemento può essere specificato a livello di servizio sotto il `<identityConfiguration>` elemento o a livello di raccolta gestore dei token di sicurezza nel `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="08ca8-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="08ca8-142">Le impostazioni in una raccolta di gestore del token sostituiscono quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="08ca8-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="08ca8-143">Alcuni gestori di token consentono di specificare impostazioni di convalida dei certificati nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="08ca8-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="08ca8-144">Le impostazioni ai gestori di token singoli sostituiscono quelle specificate a livello di servizio e la raccolta di gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="08ca8-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08ca8-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="08ca8-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
