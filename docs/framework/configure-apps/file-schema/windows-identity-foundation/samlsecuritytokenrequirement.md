---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: cab7572518a7a6dc26f8bbcf67cd424fa1c01085
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251895"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="33936-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="33936-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="33936-102">Fornisce la configurazione per <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la classe, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="33936-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="33936-103">Rappresentata dalla <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> classe.</span><span class="sxs-lookup"><span data-stu-id="33936-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
<span data-ttu-id="33936-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="33936-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="33936-105">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="33936-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="33936-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="33936-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="33936-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="33936-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="33936-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Aggiungi >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="33936-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="33936-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> samlSecurityTokenRequirement**</span><span class="sxs-lookup"><span data-stu-id="33936-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33936-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33936-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement   
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33936-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="33936-111">Attributes and Elements</span></span>  
 <span data-ttu-id="33936-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="33936-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33936-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="33936-113">Attributes</span></span>  
  
|<span data-ttu-id="33936-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="33936-114">Attribute</span></span>|<span data-ttu-id="33936-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33936-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33936-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="33936-116">mapToWindows</span></span>|<span data-ttu-id="33936-117">Specifica se il gestore di token deve eseguire il mapping del token di convalida a un account di Windows tramite l'attestazione UPN in ingresso.</span><span class="sxs-lookup"><span data-stu-id="33936-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="33936-118">Il valore predefinito è "false".</span><span class="sxs-lookup"><span data-stu-id="33936-118">The default is "false".</span></span>|  
|<span data-ttu-id="33936-119">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="33936-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="33936-120"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Valore che specifica la modalità di revoca da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="33936-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="33936-121">Il valore predefinito è "online".</span><span class="sxs-lookup"><span data-stu-id="33936-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="33936-122">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="33936-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="33936-123"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Valore che specifica la modalità di convalida da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="33936-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="33936-124">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="33936-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="33936-125">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="33936-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="33936-126"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valore che specifica l'archivio certificati X. 509.</span><span class="sxs-lookup"><span data-stu-id="33936-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="33936-127">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="33936-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="33936-128">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="33936-128">issuerCertificateValidator</span></span>|<span data-ttu-id="33936-129">Tipo personalizzato che deriva da <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="33936-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="33936-130">Se l' `issuerCertificateValidationMode` attributo è "Custom", un'istanza di questo tipo viene utilizzata per la convalida del certificato dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="33936-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33936-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="33936-131">Child Elements</span></span>  
  
|<span data-ttu-id="33936-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="33936-132">Element</span></span>|<span data-ttu-id="33936-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33936-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33936-134">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="33936-134">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="33936-135">Imposta il tipo di attestazione che <xref:System.Security.Principal.IIdentity.Name%2A> specifica la proprietà.</span><span class="sxs-lookup"><span data-stu-id="33936-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="33936-136">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="33936-136">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="33936-137">Specifica il tipo di attestazione che definisce le attestazioni del tipo di <xref:System.Security.Claims.ClaimsIdentity> ruolo nella raccolta di <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> oggetti restituiti dal metodo del gestore del token.</span><span class="sxs-lookup"><span data-stu-id="33936-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33936-138">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="33936-138">Parent Elements</span></span>  
  
|<span data-ttu-id="33936-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="33936-139">Element</span></span>|<span data-ttu-id="33936-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="33936-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33936-141">\<add></span><span class="sxs-lookup"><span data-stu-id="33936-141">\<add></span></span>](add.md)|<span data-ttu-id="33936-142">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="33936-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33936-143">Note</span><span class="sxs-lookup"><span data-stu-id="33936-143">Remarks</span></span>  
 <span data-ttu-id="33936-144">L' `<samlSecurityTokenRequirement>` elemento è rappresentato <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> dalla classe nel modello a oggetti e viene usato per configurare la `SamlSecurityTokenRequirement` proprietà in un <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> oggetto o <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="33936-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33936-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="33936-145">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```
