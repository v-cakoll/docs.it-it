---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152632"
---
# \<samlSecurityTokenRequirement>
<span data-ttu-id="dffb3-101">Fornisce la configurazione per la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> classe, la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> classe o una classe derivata di una di queste classi.</span><span class="sxs-lookup"><span data-stu-id="dffb3-101">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="dffb3-102">Rappresentata dalla <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> classe.</span><span class="sxs-lookup"><span data-stu-id="dffb3-102">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="dffb3-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dffb3-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dffb3-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dffb3-104">Attributes and Elements</span></span>  
 <span data-ttu-id="dffb3-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dffb3-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dffb3-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="dffb3-106">Attributes</span></span>  
  
|<span data-ttu-id="dffb3-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="dffb3-107">Attribute</span></span>|<span data-ttu-id="dffb3-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dffb3-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dffb3-109">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="dffb3-109">mapToWindows</span></span>|<span data-ttu-id="dffb3-110">Specifica se il gestore di token deve eseguire il mapping del token di convalida a un account di Windows tramite l'attestazione UPN in ingresso.</span><span class="sxs-lookup"><span data-stu-id="dffb3-110">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="dffb3-111">Il valore predefinito è "false".</span><span class="sxs-lookup"><span data-stu-id="dffb3-111">The default is "false".</span></span>|  
|<span data-ttu-id="dffb3-112">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="dffb3-112">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="dffb3-113"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Valore che specifica la modalità di revoca da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="dffb3-113">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="dffb3-114">Il valore predefinito è "online".</span><span class="sxs-lookup"><span data-stu-id="dffb3-114">The default value is "Online".</span></span>|  
|<span data-ttu-id="dffb3-115">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="dffb3-115">issuerCertificateValidationMode</span></span>|<span data-ttu-id="dffb3-116"><xref:System.ServiceModel.Security.X509CertificateValidationMode>Valore che specifica la modalità di convalida da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="dffb3-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="dffb3-117">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="dffb3-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="dffb3-118">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="dffb3-118">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="dffb3-119"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Valore che specifica l'archivio certificati X. 509.</span><span class="sxs-lookup"><span data-stu-id="dffb3-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="dffb3-120">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="dffb3-120">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="dffb3-121">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="dffb3-121">issuerCertificateValidator</span></span>|<span data-ttu-id="dffb3-122">Tipo personalizzato che deriva da <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="dffb3-122">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="dffb3-123">Se l' `issuerCertificateValidationMode` attributo è "Custom", un'istanza di questo tipo viene utilizzata per la convalida del certificato dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="dffb3-123">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dffb3-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dffb3-124">Child Elements</span></span>  
  
|<span data-ttu-id="dffb3-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="dffb3-125">Element</span></span>|<span data-ttu-id="dffb3-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dffb3-126">Description</span></span>|  
|-------------|-----------------|  
|[\<nameClaimType>](nameclaimtype.md)|<span data-ttu-id="dffb3-127">Imposta il tipo di attestazione che specifica la <xref:System.Security.Principal.IIdentity.Name%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="dffb3-127">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[\<roleClaimType>](roleclaimtype.md)|<span data-ttu-id="dffb3-128">Specifica il tipo di attestazione che definisce le attestazioni del tipo di ruolo nella raccolta di <xref:System.Security.Claims.ClaimsIdentity> oggetti restituiti dal <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> metodo del gestore del token.</span><span class="sxs-lookup"><span data-stu-id="dffb3-128">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dffb3-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dffb3-129">Parent Elements</span></span>  
  
|<span data-ttu-id="dffb3-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="dffb3-130">Element</span></span>|<span data-ttu-id="dffb3-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dffb3-131">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="dffb3-132">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="dffb3-132">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dffb3-133">Commenti</span><span class="sxs-lookup"><span data-stu-id="dffb3-133">Remarks</span></span>  
 <span data-ttu-id="dffb3-134">L' `<samlSecurityTokenRequirement>` elemento è rappresentato dalla <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> classe nel modello a oggetti e viene usato per configurare la `SamlSecurityTokenRequirement` Proprietà in un oggetto <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> o <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> .</span><span class="sxs-lookup"><span data-stu-id="dffb3-134">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dffb3-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="dffb3-135">Example</span></span>  
  
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
