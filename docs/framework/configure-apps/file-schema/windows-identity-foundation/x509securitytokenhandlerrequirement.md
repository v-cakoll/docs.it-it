---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 30ce69a35cfdd34e0dfea5c682347eb9187e04ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152450"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="b4c5a-101">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="b4c5a-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="b4c5a-102">Fornisce una configurazione <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> facoltativa per la classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="b4c5a-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="b4c5a-103">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b4c5a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b4c5a-104">&nbsp;&nbsp;[**\<>system.identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="b4c5a-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="b4c5a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di identitàConfigurazione**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b4c5a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="b4c5a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="b4c5a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="b4c5a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<aggiungere>**](add.md)</span><span class="sxs-lookup"><span data-stu-id="b4c5a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="b4c5a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span><span class="sxs-lookup"><span data-stu-id="b4c5a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4c5a-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4c5a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4c5a-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b4c5a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b4c5a-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b4c5a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4c5a-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="b4c5a-112">Attributes</span></span>  
  
|<span data-ttu-id="b4c5a-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="b4c5a-113">Attribute</span></span>|<span data-ttu-id="b4c5a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4c5a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b4c5a-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="b4c5a-115">certificateValidationMode</span></span>|<span data-ttu-id="b4c5a-116">Valore <xref:System.ServiceModel.Security.X509CertificateValidationMode> che specifica la modalità di convalida da utilizzare per il certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="b4c5a-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="b4c5a-117">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="b4c5a-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="b4c5a-118">MapToWindows (finestra di lavoro su MapToWindows</span><span class="sxs-lookup"><span data-stu-id="b4c5a-118">mapToWindows</span></span>|<span data-ttu-id="b4c5a-119">Specifica se il gestore di token deve eseguire il mapping del token di convalida a un account Windows utilizzando l'attestazione UPN in ingresso.</span><span class="sxs-lookup"><span data-stu-id="b4c5a-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="b4c5a-120">Il valore predefinito è "false".</span><span class="sxs-lookup"><span data-stu-id="b4c5a-120">The default is "false".</span></span>|  
|<span data-ttu-id="b4c5a-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="b4c5a-121">revocationMode</span></span>|<span data-ttu-id="b4c5a-122">Valore <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> che specifica la modalità di revoca da utilizzare per il certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="b4c5a-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="b4c5a-123">Il valore predefinito è "Online".</span><span class="sxs-lookup"><span data-stu-id="b4c5a-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="b4c5a-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="b4c5a-124">trustedStoreLocation</span></span>|<span data-ttu-id="b4c5a-125">Valore <xref:System.Security.Cryptography.X509Certificates.StoreLocation> che specifica l'archivio certificati X.509.</span><span class="sxs-lookup"><span data-stu-id="b4c5a-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="b4c5a-126">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="b4c5a-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="b4c5a-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="b4c5a-127">certificateValidator</span></span>|<span data-ttu-id="b4c5a-128">Tipo personalizzato che deriva <xref:System.IdentityModel.Selectors.X509CertificateValidator>da .</span><span class="sxs-lookup"><span data-stu-id="b4c5a-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="b4c5a-129">Se `certificateValidationMode` l'attributo è "Custom", un'istanza di questo tipo viene utilizzata per la convalida del certificato dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="b4c5a-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4c5a-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b4c5a-130">Child Elements</span></span>  
 <span data-ttu-id="b4c5a-131">nessuno</span><span class="sxs-lookup"><span data-stu-id="b4c5a-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4c5a-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b4c5a-132">Parent Elements</span></span>  
  
|<span data-ttu-id="b4c5a-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="b4c5a-133">Element</span></span>|<span data-ttu-id="b4c5a-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4c5a-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4c5a-135">\<aggiungere></span><span class="sxs-lookup"><span data-stu-id="b4c5a-135">\<add></span></span>](add.md)|<span data-ttu-id="b4c5a-136">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="b4c5a-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b4c5a-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4c5a-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
