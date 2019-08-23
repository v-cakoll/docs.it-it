---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: df259398beb242ea95efb248d6b5140b38ca3c45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942484"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="3dcce-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="3dcce-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="3dcce-102">Fornisce la configurazione per <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la classe, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="3dcce-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="3dcce-103">Rappresentata dalla <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> classe.</span><span class="sxs-lookup"><span data-stu-id="3dcce-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="3dcce-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3dcce-104">\<system.identityModel></span></span>  
<span data-ttu-id="3dcce-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3dcce-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3dcce-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3dcce-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3dcce-107">\<add></span><span class="sxs-lookup"><span data-stu-id="3dcce-107">\<add></span></span>  
<span data-ttu-id="3dcce-108">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="3dcce-108">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dcce-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3dcce-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3dcce-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3dcce-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3dcce-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3dcce-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3dcce-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="3dcce-112">Attributes</span></span>  
  
|<span data-ttu-id="3dcce-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="3dcce-113">Attribute</span></span>|<span data-ttu-id="3dcce-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3dcce-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3dcce-115">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="3dcce-115">mapToWindows</span></span>|<span data-ttu-id="3dcce-116">Specifica se il gestore di token deve eseguire il mapping del token di convalida a un account di Windows tramite l'attestazione UPN in ingresso.</span><span class="sxs-lookup"><span data-stu-id="3dcce-116">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="3dcce-117">Il valore predefinito è "false".</span><span class="sxs-lookup"><span data-stu-id="3dcce-117">The default is "false".</span></span>|  
|<span data-ttu-id="3dcce-118">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="3dcce-118">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="3dcce-119"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Valore che specifica la modalità di revoca da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="3dcce-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="3dcce-120">Il valore predefinito è "online".</span><span class="sxs-lookup"><span data-stu-id="3dcce-120">The default value is "Online".</span></span>|  
|<span data-ttu-id="3dcce-121">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="3dcce-121">issuerCertificateValidationMode</span></span>|<span data-ttu-id="3dcce-122"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Valore che specifica la modalità di convalida da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="3dcce-122">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="3dcce-123">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="3dcce-123">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="3dcce-124">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="3dcce-124">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="3dcce-125"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valore che specifica l'archivio certificati X. 509.</span><span class="sxs-lookup"><span data-stu-id="3dcce-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="3dcce-126">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="3dcce-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="3dcce-127">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="3dcce-127">issuerCertificateValidator</span></span>|<span data-ttu-id="3dcce-128">Tipo personalizzato che deriva da <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="3dcce-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="3dcce-129">Se l' `issuerCertificateValidationMode` attributo è "Custom", un'istanza di questo tipo viene utilizzata per la convalida del certificato dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="3dcce-129">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3dcce-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3dcce-130">Child Elements</span></span>  
  
|<span data-ttu-id="3dcce-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="3dcce-131">Element</span></span>|<span data-ttu-id="3dcce-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3dcce-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3dcce-133">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="3dcce-133">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="3dcce-134">Imposta il tipo di attestazione che <xref:System.Security.Principal.IIdentity.Name%2A> specifica la proprietà.</span><span class="sxs-lookup"><span data-stu-id="3dcce-134">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="3dcce-135">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="3dcce-135">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="3dcce-136">Specifica il tipo di attestazione che definisce le attestazioni del tipo di <xref:System.Security.Claims.ClaimsIdentity> ruolo nella raccolta di <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> oggetti restituiti dal metodo del gestore del token.</span><span class="sxs-lookup"><span data-stu-id="3dcce-136">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3dcce-137">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3dcce-137">Parent Elements</span></span>  
  
|<span data-ttu-id="3dcce-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="3dcce-138">Element</span></span>|<span data-ttu-id="3dcce-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3dcce-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3dcce-140">\<add></span><span class="sxs-lookup"><span data-stu-id="3dcce-140">\<add></span></span>](add.md)|<span data-ttu-id="3dcce-141">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="3dcce-141">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dcce-142">Note</span><span class="sxs-lookup"><span data-stu-id="3dcce-142">Remarks</span></span>  
 <span data-ttu-id="3dcce-143">L' `<samlSecurityTokenRequirement>` elemento è rappresentato <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> dalla classe nel modello a oggetti e viene usato per configurare la `SamlSecurityTokenRequirement` proprietà in un <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> oggetto o <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="3dcce-143">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dcce-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="3dcce-144">Example</span></span>  
  
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
