---
title: '&lt;x509SecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 8af4a718fc9f4ba7f674d98e13424bb443693c6c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755942"
---
# <a name="ltx509securitytokenhandlerrequirementgt"></a><span data-ttu-id="028cf-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="028cf-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="028cf-103">Fornisce la configurazione facoltativa per il <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> classe o classi derivate.</span><span class="sxs-lookup"><span data-stu-id="028cf-103">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="028cf-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="028cf-104">\<system.identityModel></span></span>  
<span data-ttu-id="028cf-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="028cf-105">\<identityConfiguration></span></span>  
<span data-ttu-id="028cf-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="028cf-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="028cf-107">\<add></span><span class="sxs-lookup"><span data-stu-id="028cf-107">\<add></span></span>  
<span data-ttu-id="028cf-108">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="028cf-108">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="028cf-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="028cf-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="028cf-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="028cf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="028cf-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="028cf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="028cf-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="028cf-112">Attributes</span></span>  
  
|<span data-ttu-id="028cf-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="028cf-113">Attribute</span></span>|<span data-ttu-id="028cf-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="028cf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="028cf-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="028cf-115">certificateValidationMode</span></span>|<span data-ttu-id="028cf-116">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valore che specifica la modalità di convalida da utilizzare per il certificato x. 509.</span><span class="sxs-lookup"><span data-stu-id="028cf-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="028cf-117">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="028cf-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="028cf-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="028cf-118">mapToWindows</span></span>|<span data-ttu-id="028cf-119">Specifica se il gestore dei token deve mappare il token di convalida a un account di Windows utilizzando l'attestazione UPN in ingresso.</span><span class="sxs-lookup"><span data-stu-id="028cf-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="028cf-120">Il valore predefinito è "false".</span><span class="sxs-lookup"><span data-stu-id="028cf-120">The default is "false".</span></span>|  
|<span data-ttu-id="028cf-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="028cf-121">revocationMode</span></span>|<span data-ttu-id="028cf-122">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valore che specifica la modalità di revoche di certificati da utilizzare per il certificato x. 509.</span><span class="sxs-lookup"><span data-stu-id="028cf-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="028cf-123">Il valore predefinito è "Online".</span><span class="sxs-lookup"><span data-stu-id="028cf-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="028cf-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="028cf-124">trustedStoreLocation</span></span>|<span data-ttu-id="028cf-125">Oggetto <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valore che specifica l'archivio certificati x. 509.</span><span class="sxs-lookup"><span data-stu-id="028cf-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="028cf-126">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="028cf-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="028cf-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="028cf-127">certificateValidator</span></span>|<span data-ttu-id="028cf-128">Un tipo personalizzato che deriva da <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="028cf-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="028cf-129">Se il `certificateValidationMode` attributo è "Custom", un'istanza di questo tipo viene usata per la convalida dei certificati dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="028cf-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="028cf-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="028cf-130">Child Elements</span></span>  
 <span data-ttu-id="028cf-131">Nessuno</span><span class="sxs-lookup"><span data-stu-id="028cf-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="028cf-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="028cf-132">Parent Elements</span></span>  
  
|<span data-ttu-id="028cf-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="028cf-133">Element</span></span>|<span data-ttu-id="028cf-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="028cf-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="028cf-135">\<add></span><span class="sxs-lookup"><span data-stu-id="028cf-135">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="028cf-136">Aggiunge il gestore di token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="028cf-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="028cf-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="028cf-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
