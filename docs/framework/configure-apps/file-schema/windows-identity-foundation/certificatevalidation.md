---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 7b8823d792e3f15846a9483d670994be4b368980
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273897"
---
# <a name="certificatevalidation"></a><span data-ttu-id="401ed-101">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="401ed-101">\<certificateValidation></span></span>
<span data-ttu-id="401ed-102">Controllare le impostazioni che utilizzano i gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="401ed-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="401ed-103">Queste impostazioni vengono ignorate se un gestore specifico è configurato con il proprio validator.</span><span class="sxs-lookup"><span data-stu-id="401ed-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="401ed-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="401ed-104">\<system.identityModel></span></span>  
<span data-ttu-id="401ed-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="401ed-105">\<identityConfiguration></span></span>  
<span data-ttu-id="401ed-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="401ed-106">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="401ed-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="401ed-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="401ed-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="401ed-108">Attributes and Elements</span></span>  
 <span data-ttu-id="401ed-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="401ed-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="401ed-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="401ed-110">Attributes</span></span>  
  
|<span data-ttu-id="401ed-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="401ed-111">Attribute</span></span>|<span data-ttu-id="401ed-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="401ed-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="401ed-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="401ed-113">certificateValidationMode</span></span>|<span data-ttu-id="401ed-114">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valore che specifica la modalità di convalida da utilizzare per il certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="401ed-114">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="401ed-115">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="401ed-115">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="401ed-116">Per specificare un validator personalizzato, impostare questo attributo su "Custom" e specificare il validator mediante la [ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="401ed-116">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="401ed-117">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="401ed-117">Optional.</span></span>|  
|<span data-ttu-id="401ed-118">revocationMode</span><span class="sxs-lookup"><span data-stu-id="401ed-118">revocationMode</span></span>|<span data-ttu-id="401ed-119">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valore che specifica la modalità di revoche di certificati da utilizzare per il certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="401ed-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="401ed-120">Il valore predefinito è "Online".</span><span class="sxs-lookup"><span data-stu-id="401ed-120">The default value is "Online".</span></span> <span data-ttu-id="401ed-121">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="401ed-121">Optional.</span></span>|  
|<span data-ttu-id="401ed-122">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="401ed-122">trustedStoreLocation</span></span>|<span data-ttu-id="401ed-123">Oggetto <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valore che specifica l'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="401ed-123">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="401ed-124">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="401ed-124">The default value is "LocalMachine".</span></span> <span data-ttu-id="401ed-125">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="401ed-125">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="401ed-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="401ed-126">Child Elements</span></span>  
  
|<span data-ttu-id="401ed-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="401ed-127">Element</span></span>|<span data-ttu-id="401ed-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="401ed-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="401ed-129">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="401ed-129">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="401ed-130">Specifica un tipo personalizzato per la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="401ed-130">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="401ed-131">Questo tipo viene usato solo se il `certificateValidationMode` attributo del [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) elemento è impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="401ed-131">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="401ed-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="401ed-132">Parent Elements</span></span>  
  
|<span data-ttu-id="401ed-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="401ed-133">Element</span></span>|<span data-ttu-id="401ed-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="401ed-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="401ed-135">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="401ed-135">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="401ed-136">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="401ed-136">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="401ed-137">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="401ed-137">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="401ed-138">Fornisce la configurazione per una raccolta di sicurezza i gestori di token.</span><span class="sxs-lookup"><span data-stu-id="401ed-138">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="401ed-139">Note</span><span class="sxs-lookup"><span data-stu-id="401ed-139">Remarks</span></span>  
 <span data-ttu-id="401ed-140">Oggetto `<certificateValidation>` elemento può essere specificato a livello di servizio con il `<identityConfiguration>` elemento o a livello di raccolta gestori di token di sicurezza nel `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="401ed-140">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="401ed-141">Le impostazioni in una raccolta di gestori di token sostituiscono quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="401ed-141">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="401ed-142">Alcuni gestori di token consentono di specificare le impostazioni di convalida di certificati nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="401ed-142">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="401ed-143">Le impostazioni ai singoli gestori di token sostituiscono quelle specificate a livello di servizio e la raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="401ed-143">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="401ed-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="401ed-144">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
