---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 8185153eb02c5794b0f6ac02a6837806f2073c07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941913"
---
# <a name="certificatevalidation"></a><span data-ttu-id="ef3bf-101">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="ef3bf-101">\<certificateValidation></span></span>
<span data-ttu-id="ef3bf-102">Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="ef3bf-103">Queste impostazioni vengono sostituite se un gestore specifico è configurato con il proprio validator.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="ef3bf-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="ef3bf-104">\<system.identityModel></span></span>  
<span data-ttu-id="ef3bf-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ef3bf-105">\<identityConfiguration></span></span>  
<span data-ttu-id="ef3bf-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="ef3bf-106">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef3bf-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef3bf-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef3bf-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ef3bf-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ef3bf-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef3bf-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="ef3bf-110">Attributes</span></span>  
  
|<span data-ttu-id="ef3bf-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="ef3bf-111">Attribute</span></span>|<span data-ttu-id="ef3bf-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="ef3bf-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef3bf-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="ef3bf-113">certificateValidationMode</span></span>|<span data-ttu-id="ef3bf-114"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Valore che specifica la modalità di convalida da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-114">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ef3bf-115">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="ef3bf-115">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="ef3bf-116">Per specificare un validator personalizzato, impostare questo attributo su "Custom" e specificare il validator usando l' [ \<elemento CertificateValidator >](certificatevalidator.md) .</span><span class="sxs-lookup"><span data-stu-id="ef3bf-116">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="ef3bf-117">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-117">Optional.</span></span>|  
|<span data-ttu-id="ef3bf-118">revocationMode</span><span class="sxs-lookup"><span data-stu-id="ef3bf-118">revocationMode</span></span>|<span data-ttu-id="ef3bf-119"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Valore che specifica la modalità di revoca da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ef3bf-120">Il valore predefinito è "online".</span><span class="sxs-lookup"><span data-stu-id="ef3bf-120">The default value is "Online".</span></span> <span data-ttu-id="ef3bf-121">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-121">Optional.</span></span>|  
|<span data-ttu-id="ef3bf-122">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="ef3bf-122">trustedStoreLocation</span></span>|<span data-ttu-id="ef3bf-123"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valore che specifica l'archivio certificati X. 509.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-123">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="ef3bf-124">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="ef3bf-124">The default value is "LocalMachine".</span></span> <span data-ttu-id="ef3bf-125">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-125">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef3bf-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ef3bf-126">Child Elements</span></span>  
  
|<span data-ttu-id="ef3bf-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef3bf-127">Element</span></span>|<span data-ttu-id="ef3bf-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef3bf-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef3bf-129">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="ef3bf-129">\<certificateValidator></span></span>](certificatevalidator.md)|<span data-ttu-id="ef3bf-130">Specifica un tipo personalizzato per la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-130">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="ef3bf-131">Questo tipo viene utilizzato solo se l' `certificateValidationMode` attributo [ \<dell'elemento > CertificateValidation](certificatevalidation.md) è impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="ef3bf-131">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef3bf-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ef3bf-132">Parent Elements</span></span>  
  
|<span data-ttu-id="ef3bf-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef3bf-133">Element</span></span>|<span data-ttu-id="ef3bf-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef3bf-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef3bf-135">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ef3bf-135">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="ef3bf-136">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-136">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="ef3bf-137">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="ef3bf-137">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="ef3bf-138">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-138">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef3bf-139">Note</span><span class="sxs-lookup"><span data-stu-id="ef3bf-139">Remarks</span></span>  
 <span data-ttu-id="ef3bf-140">Un `<certificateValidation>` elemento può essere specificato a livello di servizio `<identityConfiguration>` nell'elemento o nel livello di raccolta del gestore del token di sicurezza `<securityTokenHandlerConfiguration>` sotto l'elemento.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-140">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="ef3bf-141">Le impostazioni in una raccolta di gestori di token eseguono l'override di quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-141">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="ef3bf-142">Alcuni gestori di token consentono di specificare le impostazioni di convalida del certificato nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-142">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="ef3bf-143">Le impostazioni nei singoli gestori di token eseguono l'override di quelle specificate sia a livello di servizio che nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ef3bf-143">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef3bf-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="ef3bf-144">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
