---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 76eeea635fd65486a1c16bea15a49018876dae99
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251686"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="7432d-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="7432d-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="7432d-102">Fornisce la configurazione facoltativa <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> per la classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="7432d-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="7432d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7432d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7432d-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="7432d-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="7432d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="7432d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="7432d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="7432d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="7432d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Aggiungi >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="7432d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="7432d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> x509SecurityTokenHandlerRequirement**</span><span class="sxs-lookup"><span data-stu-id="7432d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7432d-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7432d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7432d-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7432d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7432d-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7432d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7432d-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="7432d-112">Attributes</span></span>  
  
|<span data-ttu-id="7432d-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="7432d-113">Attribute</span></span>|<span data-ttu-id="7432d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7432d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7432d-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="7432d-115">certificateValidationMode</span></span>|<span data-ttu-id="7432d-116"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Valore che specifica la modalità di convalida da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="7432d-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="7432d-117">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="7432d-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="7432d-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="7432d-118">mapToWindows</span></span>|<span data-ttu-id="7432d-119">Specifica se il gestore di token deve eseguire il mapping del token di convalida a un account di Windows tramite l'attestazione UPN in ingresso.</span><span class="sxs-lookup"><span data-stu-id="7432d-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="7432d-120">Il valore predefinito è "false".</span><span class="sxs-lookup"><span data-stu-id="7432d-120">The default is "false".</span></span>|  
|<span data-ttu-id="7432d-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="7432d-121">revocationMode</span></span>|<span data-ttu-id="7432d-122"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Valore che specifica la modalità di revoca da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="7432d-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="7432d-123">Il valore predefinito è "online".</span><span class="sxs-lookup"><span data-stu-id="7432d-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="7432d-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="7432d-124">trustedStoreLocation</span></span>|<span data-ttu-id="7432d-125"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valore che specifica l'archivio certificati X. 509.</span><span class="sxs-lookup"><span data-stu-id="7432d-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="7432d-126">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="7432d-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="7432d-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="7432d-127">certificateValidator</span></span>|<span data-ttu-id="7432d-128">Tipo personalizzato che deriva da <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="7432d-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="7432d-129">Se l' `certificateValidationMode` attributo è "Custom", un'istanza di questo tipo viene utilizzata per la convalida del certificato dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="7432d-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7432d-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7432d-130">Child Elements</span></span>  
 <span data-ttu-id="7432d-131">Nessuna</span><span class="sxs-lookup"><span data-stu-id="7432d-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7432d-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7432d-132">Parent Elements</span></span>  
  
|<span data-ttu-id="7432d-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="7432d-133">Element</span></span>|<span data-ttu-id="7432d-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7432d-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7432d-135">\<add></span><span class="sxs-lookup"><span data-stu-id="7432d-135">\<add></span></span>](add.md)|<span data-ttu-id="7432d-136">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="7432d-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7432d-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="7432d-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
