---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 6e8267f170dbb26381564be7b66df5f617156885
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790442"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="eebc4-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="eebc4-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="eebc4-102">Fornisce una configurazione facoltativa per il <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="eebc4-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="eebc4-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="eebc4-103">\<system.identityModel></span></span>  
<span data-ttu-id="eebc4-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="eebc4-104">\<identityConfiguration></span></span>  
<span data-ttu-id="eebc4-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="eebc4-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="eebc4-106">\<add></span><span class="sxs-lookup"><span data-stu-id="eebc4-106">\<add></span></span>  
<span data-ttu-id="eebc4-107">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="eebc4-107">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eebc4-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eebc4-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eebc4-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="eebc4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="eebc4-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="eebc4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eebc4-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="eebc4-111">Attributes</span></span>  
  
|<span data-ttu-id="eebc4-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="eebc4-112">Attribute</span></span>|<span data-ttu-id="eebc4-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eebc4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eebc4-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="eebc4-114">certificateValidationMode</span></span>|<span data-ttu-id="eebc4-115">Un <xref:System.ServiceModel.Security.X509CertificateValidationMode> valore che specifica la modalità di convalida da utilizzare per il certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="eebc4-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="eebc4-116">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="eebc4-116">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="eebc4-117">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="eebc4-117">mapToWindows</span></span>|<span data-ttu-id="eebc4-118">Specifica se il gestore di token deve mappare il token di convalida a un account di Windows usando l'attestazione UPN in ingresso.</span><span class="sxs-lookup"><span data-stu-id="eebc4-118">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="eebc4-119">Il valore predefinito è "false".</span><span class="sxs-lookup"><span data-stu-id="eebc4-119">The default is "false".</span></span>|  
|<span data-ttu-id="eebc4-120">revocationMode</span><span class="sxs-lookup"><span data-stu-id="eebc4-120">revocationMode</span></span>|<span data-ttu-id="eebc4-121">Un <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> valore che specifica la modalità di revoche di certificati da utilizzare per il certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="eebc4-121">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="eebc4-122">Il valore predefinito è "Online".</span><span class="sxs-lookup"><span data-stu-id="eebc4-122">The default value is "Online".</span></span>|  
|<span data-ttu-id="eebc4-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="eebc4-123">trustedStoreLocation</span></span>|<span data-ttu-id="eebc4-124">Oggetto <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valore che specifica l'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="eebc4-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="eebc4-125">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="eebc4-125">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="eebc4-126">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="eebc4-126">certificateValidator</span></span>|<span data-ttu-id="eebc4-127">Un tipo personalizzato che deriva da <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="eebc4-127">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="eebc4-128">Se il `certificateValidationMode` attributo è "Custom", un'istanza di questo tipo viene usata per la convalida del certificato dell'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="eebc4-128">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eebc4-129">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="eebc4-129">Child Elements</span></span>  
 <span data-ttu-id="eebc4-130">nessuno</span><span class="sxs-lookup"><span data-stu-id="eebc4-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eebc4-131">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="eebc4-131">Parent Elements</span></span>  
  
|<span data-ttu-id="eebc4-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="eebc4-132">Element</span></span>|<span data-ttu-id="eebc4-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eebc4-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eebc4-134">\<add></span><span class="sxs-lookup"><span data-stu-id="eebc4-134">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="eebc4-135">Aggiunge il gestore di token di sicurezza specificato nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="eebc4-135">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eebc4-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="eebc4-136">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
