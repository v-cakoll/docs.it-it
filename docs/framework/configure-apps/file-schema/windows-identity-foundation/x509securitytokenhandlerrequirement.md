---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 30ce69a35cfdd34e0dfea5c682347eb9187e04ed
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152450"
---
# \<x509SecurityTokenHandlerRequirement>
<span data-ttu-id="f5dcd-101">Fornisce la configurazione facoltativa per la <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> classe o le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-101">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="f5dcd-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5dcd-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5dcd-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f5dcd-103">Attributes and Elements</span></span>  
 <span data-ttu-id="f5dcd-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5dcd-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="f5dcd-105">Attributes</span></span>  
  
|<span data-ttu-id="f5dcd-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="f5dcd-106">Attribute</span></span>|<span data-ttu-id="f5dcd-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5dcd-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5dcd-108">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="f5dcd-108">certificateValidationMode</span></span>|<span data-ttu-id="f5dcd-109"><xref:System.ServiceModel.Security.X509CertificateValidationMode>Valore che specifica la modalità di convalida da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-109">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="f5dcd-110">Il valore predefinito è "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="f5dcd-110">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="f5dcd-111">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="f5dcd-111">mapToWindows</span></span>|<span data-ttu-id="f5dcd-112">Specifica se il gestore di token deve eseguire il mapping del token di convalida a un account di Windows tramite l'attestazione UPN in ingresso.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-112">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="f5dcd-113">Il valore predefinito è "false".</span><span class="sxs-lookup"><span data-stu-id="f5dcd-113">The default is "false".</span></span>|  
|<span data-ttu-id="f5dcd-114">revocationMode</span><span class="sxs-lookup"><span data-stu-id="f5dcd-114">revocationMode</span></span>|<span data-ttu-id="f5dcd-115"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>Valore che specifica la modalità di revoca da utilizzare per il certificato X. 509.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-115">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="f5dcd-116">Il valore predefinito è "online".</span><span class="sxs-lookup"><span data-stu-id="f5dcd-116">The default value is "Online".</span></span>|  
|<span data-ttu-id="f5dcd-117">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="f5dcd-117">trustedStoreLocation</span></span>|<span data-ttu-id="f5dcd-118"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Valore che specifica l'archivio certificati X. 509.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="f5dcd-119">Il valore predefinito è "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="f5dcd-119">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="f5dcd-120">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="f5dcd-120">certificateValidator</span></span>|<span data-ttu-id="f5dcd-121">Tipo personalizzato che deriva da <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="f5dcd-121">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="f5dcd-122">Se l' `certificateValidationMode` attributo è "Custom", un'istanza di questo tipo viene utilizzata per la convalida del certificato dell'autorità emittente.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-122">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5dcd-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f5dcd-123">Child Elements</span></span>  
 <span data-ttu-id="f5dcd-124">nessuno</span><span class="sxs-lookup"><span data-stu-id="f5dcd-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5dcd-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f5dcd-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f5dcd-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5dcd-126">Element</span></span>|<span data-ttu-id="f5dcd-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5dcd-127">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="f5dcd-128">Aggiunge il gestore del token di sicurezza specificato alla raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="f5dcd-128">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f5dcd-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5dcd-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
