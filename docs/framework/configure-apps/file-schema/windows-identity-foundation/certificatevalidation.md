---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: c2d1a5d36cb5616ef06eedc093dd70a68a164a81
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252128"
---
# \<certificateValidation>
<span data-ttu-id="46ba0-101">Controlla le impostazioni utilizzate dai gestori di token per convalidare i certificati.</span><span class="sxs-lookup"><span data-stu-id="46ba0-101">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="46ba0-102">Queste impostazioni vengono sostituite se un gestore specifico è configurato con il proprio validator.</span><span class="sxs-lookup"><span data-stu-id="46ba0-102">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**  
  
## <a name="syntax"></a><span data-ttu-id="46ba0-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46ba0-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46ba0-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="46ba0-104">Attributes and Elements</span></span>  
 <span data-ttu-id="46ba0-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="46ba0-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46ba0-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="46ba0-106">Attributes</span></span>  
  
|<span data-ttu-id="46ba0-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="46ba0-107">Attribute</span></span>|<span data-ttu-id="46ba0-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46ba0-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46ba0-109">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="46ba0-109">certificateValidationMode</span></span>|<span data-ttu-id="46ba0-110"><xref:System.ServiceModel.Security.X509CertificateValidationMode>Valore che specifica la modalità di convalida da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="46ba0-110">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="46ba0-111">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="46ba0-111">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="46ba0-112">Per specificare un validator personalizzato, impostare questo attributo su "Custom" e specificare il validator usando l' [\<certificateValidator>](certificatevalidator.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="46ba0-112">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="46ba0-113">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="46ba0-113">Optional.</span></span>|  
|<span data-ttu-id="46ba0-114">revocationMode</span><span class="sxs-lookup"><span data-stu-id="46ba0-114">revocationMode</span></span>|<span data-ttu-id="46ba0-115"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Valore che specifica la modalità di revoca da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="46ba0-115">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="46ba0-116">Il valore predefinito è "online".</span><span class="sxs-lookup"><span data-stu-id="46ba0-116">The default value is "Online".</span></span> <span data-ttu-id="46ba0-117">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="46ba0-117">Optional.</span></span>|  
|<span data-ttu-id="46ba0-118">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="46ba0-118">trustedStoreLocation</span></span>|<span data-ttu-id="46ba0-119"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Valore che specifica l'archivio certificati X. 509.</span><span class="sxs-lookup"><span data-stu-id="46ba0-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="46ba0-120">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="46ba0-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="46ba0-121">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="46ba0-121">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46ba0-122">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="46ba0-122">Child Elements</span></span>  
  
|<span data-ttu-id="46ba0-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="46ba0-123">Element</span></span>|<span data-ttu-id="46ba0-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46ba0-124">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidator>](certificatevalidator.md)|<span data-ttu-id="46ba0-125">Specifica un tipo personalizzato per la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="46ba0-125">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="46ba0-126">Questo tipo viene utilizzato solo se l' `certificateValidationMode` attributo dell' [\<certificateValidation>](certificatevalidation.md) elemento è impostato su "Custom".</span><span class="sxs-lookup"><span data-stu-id="46ba0-126">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="46ba0-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="46ba0-127">Parent Elements</span></span>  
  
|<span data-ttu-id="46ba0-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="46ba0-128">Element</span></span>|<span data-ttu-id="46ba0-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46ba0-129">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="46ba0-130">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="46ba0-130">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="46ba0-131">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="46ba0-131">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46ba0-132">Commenti</span><span class="sxs-lookup"><span data-stu-id="46ba0-132">Remarks</span></span>  
 <span data-ttu-id="46ba0-133">Un `<certificateValidation>` elemento può essere specificato a livello di servizio nell' `<identityConfiguration>` elemento o nel livello di raccolta del gestore del token di sicurezza sotto l' `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="46ba0-133">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="46ba0-134">Le impostazioni in una raccolta di gestori di token eseguono l'override di quelle specificate nel servizio.</span><span class="sxs-lookup"><span data-stu-id="46ba0-134">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="46ba0-135">Alcuni gestori di token consentono di specificare le impostazioni di convalida del certificato nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="46ba0-135">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="46ba0-136">Le impostazioni nei singoli gestori di token eseguono l'override di quelle specificate sia a livello di servizio che nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="46ba0-136">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46ba0-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="46ba0-137">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
