---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 2851820460a34d62175929b48ad57914df557059
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945174"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="18bc3-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="18bc3-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="18bc3-102">Fornisce la configurazione facoltativa <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> per la classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="18bc3-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="18bc3-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="18bc3-103">\<system.identityModel></span></span>  
<span data-ttu-id="18bc3-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="18bc3-104">\<identityConfiguration></span></span>  
<span data-ttu-id="18bc3-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="18bc3-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="18bc3-106">\<add></span><span class="sxs-lookup"><span data-stu-id="18bc3-106">\<add></span></span>  
<span data-ttu-id="18bc3-107">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="18bc3-107">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18bc3-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18bc3-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18bc3-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="18bc3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="18bc3-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="18bc3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18bc3-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="18bc3-111">Attributes</span></span>  
  
|<span data-ttu-id="18bc3-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="18bc3-112">Attribute</span></span>|<span data-ttu-id="18bc3-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18bc3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="18bc3-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="18bc3-114">certificateValidationMode</span></span>|<span data-ttu-id="18bc3-115"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Valore che specifica la modalità di convalida da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="18bc3-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="18bc3-116">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="18bc3-116">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="18bc3-117">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="18bc3-117">mapToWindows</span></span>|<span data-ttu-id="18bc3-118">Specifica se il gestore di token deve eseguire il mapping del token di convalida a un account di Windows tramite l'attestazione UPN in ingresso.</span><span class="sxs-lookup"><span data-stu-id="18bc3-118">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="18bc3-119">Il valore predefinito è "false".</span><span class="sxs-lookup"><span data-stu-id="18bc3-119">The default is "false".</span></span>|  
|<span data-ttu-id="18bc3-120">revocationMode</span><span class="sxs-lookup"><span data-stu-id="18bc3-120">revocationMode</span></span>|<span data-ttu-id="18bc3-121"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Valore che specifica la modalità di revoca da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="18bc3-121">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="18bc3-122">Il valore predefinito è "online".</span><span class="sxs-lookup"><span data-stu-id="18bc3-122">The default value is "Online".</span></span>|  
|<span data-ttu-id="18bc3-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="18bc3-123">trustedStoreLocation</span></span>|<span data-ttu-id="18bc3-124"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valore che specifica l'archivio certificati X. 509.</span><span class="sxs-lookup"><span data-stu-id="18bc3-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="18bc3-125">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="18bc3-125">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="18bc3-126">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="18bc3-126">certificateValidator</span></span>|<span data-ttu-id="18bc3-127">Tipo personalizzato che deriva da <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="18bc3-127">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="18bc3-128">Se l' `certificateValidationMode` attributo è "Custom", un'istanza di questo tipo viene utilizzata per la convalida del certificato dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="18bc3-128">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18bc3-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="18bc3-129">Child Elements</span></span>  
 <span data-ttu-id="18bc3-130">Nessuna</span><span class="sxs-lookup"><span data-stu-id="18bc3-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18bc3-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="18bc3-131">Parent Elements</span></span>  
  
|<span data-ttu-id="18bc3-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="18bc3-132">Element</span></span>|<span data-ttu-id="18bc3-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18bc3-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18bc3-134">\<add></span><span class="sxs-lookup"><span data-stu-id="18bc3-134">\<add></span></span>](add.md)|<span data-ttu-id="18bc3-135">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="18bc3-135">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="18bc3-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="18bc3-136">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
