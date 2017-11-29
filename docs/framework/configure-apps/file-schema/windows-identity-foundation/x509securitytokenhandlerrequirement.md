---
title: '&lt;x509SecurityTokenHandlerRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 66d4e0d6a121f807f5f372b3f39577b0bb3c4ca6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltx509securitytokenhandlerrequirementgt"></a><span data-ttu-id="c8121-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="c8121-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="c8121-103">Fornisce la configurazione facoltativa per il <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> classe o classi derivate.</span><span class="sxs-lookup"><span data-stu-id="c8121-103">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="c8121-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="c8121-104">\<system.identityModel></span></span>  
<span data-ttu-id="c8121-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="c8121-105">\<identityConfiguration></span></span>  
<span data-ttu-id="c8121-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="c8121-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="c8121-107">\<add></span><span class="sxs-lookup"><span data-stu-id="c8121-107">\<add></span></span>  
<span data-ttu-id="c8121-108">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="c8121-108">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8121-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8121-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8121-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c8121-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c8121-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c8121-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8121-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="c8121-112">Attributes</span></span>  
  
|<span data-ttu-id="c8121-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="c8121-113">Attribute</span></span>|<span data-ttu-id="c8121-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8121-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c8121-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="c8121-115">certificateValidationMode</span></span>|<span data-ttu-id="c8121-116">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valore che specifica la modalità di convalida da utilizzare per il certificato x. 509.</span><span class="sxs-lookup"><span data-stu-id="c8121-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="c8121-117">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="c8121-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="c8121-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="c8121-118">mapToWindows</span></span>|<span data-ttu-id="c8121-119">Specifica se il gestore dei token deve mappare il token di convalida a un account di Windows utilizzando l'attestazione UPN in ingresso.</span><span class="sxs-lookup"><span data-stu-id="c8121-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="c8121-120">Il valore predefinito è "false".</span><span class="sxs-lookup"><span data-stu-id="c8121-120">The default is "false".</span></span>|  
|<span data-ttu-id="c8121-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="c8121-121">revocationMode</span></span>|<span data-ttu-id="c8121-122">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valore che specifica la modalità di revoche di certificati da utilizzare per il certificato x. 509.</span><span class="sxs-lookup"><span data-stu-id="c8121-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="c8121-123">Il valore predefinito è "Online".</span><span class="sxs-lookup"><span data-stu-id="c8121-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="c8121-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="c8121-124">trustedStoreLocation</span></span>|<span data-ttu-id="c8121-125">Oggetto <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valore che specifica l'archivio certificati x. 509.</span><span class="sxs-lookup"><span data-stu-id="c8121-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="c8121-126">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="c8121-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="c8121-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="c8121-127">certificateValidator</span></span>|<span data-ttu-id="c8121-128">Un tipo personalizzato che deriva da <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="c8121-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="c8121-129">Se il `certificateValidationMode` attributo è "Custom", un'istanza di questo tipo viene usata per la convalida dei certificati dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="c8121-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8121-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c8121-130">Child Elements</span></span>  
 <span data-ttu-id="c8121-131">None</span><span class="sxs-lookup"><span data-stu-id="c8121-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8121-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c8121-132">Parent Elements</span></span>  
  
|<span data-ttu-id="c8121-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="c8121-133">Element</span></span>|<span data-ttu-id="c8121-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8121-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8121-135">\<add></span><span class="sxs-lookup"><span data-stu-id="c8121-135">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="c8121-136">Aggiunge il gestore di token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="c8121-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c8121-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8121-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
