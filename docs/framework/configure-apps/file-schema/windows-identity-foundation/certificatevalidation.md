---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: c2d1a5d36cb5616ef06eedc093dd70a68a164a81
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252128"
---
# <a name="certificatevalidation"></a><span data-ttu-id="ff235-101">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="ff235-101">\<certificateValidation></span></span>
<span data-ttu-id="ff235-102">Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="ff235-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="ff235-103">Queste impostazioni vengono sostituite se un gestore specifico è configurato con il proprio validator.</span><span class="sxs-lookup"><span data-stu-id="ff235-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
<span data-ttu-id="ff235-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ff235-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ff235-105">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="ff235-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="ff235-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="ff235-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="ff235-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> certificateValidation**</span><span class="sxs-lookup"><span data-stu-id="ff235-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff235-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff235-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff235-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ff235-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ff235-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ff235-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff235-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="ff235-111">Attributes</span></span>  
  
|<span data-ttu-id="ff235-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="ff235-112">Attribute</span></span>|<span data-ttu-id="ff235-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff235-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ff235-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="ff235-114">certificateValidationMode</span></span>|<span data-ttu-id="ff235-115"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Valore che specifica la modalità di convalida da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="ff235-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ff235-116">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="ff235-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="ff235-117">Per specificare un validator personalizzato, impostare questo attributo su "Custom" e specificare il validator usando l' [ \<elemento CertificateValidator >](certificatevalidator.md) .</span><span class="sxs-lookup"><span data-stu-id="ff235-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="ff235-118">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ff235-118">Optional.</span></span>|  
|<span data-ttu-id="ff235-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="ff235-119">revocationMode</span></span>|<span data-ttu-id="ff235-120"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Valore che specifica la modalità di revoca da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="ff235-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ff235-121">Il valore predefinito è "online".</span><span class="sxs-lookup"><span data-stu-id="ff235-121">The default value is "Online".</span></span> <span data-ttu-id="ff235-122">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ff235-122">Optional.</span></span>|  
|<span data-ttu-id="ff235-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="ff235-123">trustedStoreLocation</span></span>|<span data-ttu-id="ff235-124"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valore che specifica l'archivio certificati X. 509.</span><span class="sxs-lookup"><span data-stu-id="ff235-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="ff235-125">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="ff235-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="ff235-126">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ff235-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff235-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ff235-127">Child Elements</span></span>  
  
|<span data-ttu-id="ff235-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff235-128">Element</span></span>|<span data-ttu-id="ff235-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ff235-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff235-130">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="ff235-130">\<certificateValidator></span></span>](certificatevalidator.md)|<span data-ttu-id="ff235-131">Specifica un tipo personalizzato per la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="ff235-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="ff235-132">Questo tipo viene utilizzato solo se l' `certificateValidationMode` attributo [ \<dell'elemento > CertificateValidation](certificatevalidation.md) è impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="ff235-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ff235-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ff235-133">Parent Elements</span></span>  
  
|<span data-ttu-id="ff235-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff235-134">Element</span></span>|<span data-ttu-id="ff235-135">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="ff235-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff235-136">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ff235-136">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="ff235-137">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="ff235-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="ff235-138">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="ff235-138">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="ff235-139">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ff235-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff235-140">Note</span><span class="sxs-lookup"><span data-stu-id="ff235-140">Remarks</span></span>  
 <span data-ttu-id="ff235-141">Un `<certificateValidation>` elemento può essere specificato a livello di servizio `<identityConfiguration>` nell'elemento o nel livello di raccolta del gestore del token di sicurezza `<securityTokenHandlerConfiguration>` sotto l'elemento.</span><span class="sxs-lookup"><span data-stu-id="ff235-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="ff235-142">Le impostazioni in una raccolta di gestori di token eseguono l'override di quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="ff235-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="ff235-143">Alcuni gestori di token consentono di specificare le impostazioni di convalida del certificato nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="ff235-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="ff235-144">Le impostazioni nei singoli gestori di token eseguono l'override di quelle specificate sia a livello di servizio che nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ff235-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff235-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="ff235-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
