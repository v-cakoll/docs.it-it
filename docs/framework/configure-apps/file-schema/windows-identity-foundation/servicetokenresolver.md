---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 30a53c11b551623311f7ca3f957143fc702568a1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251841"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="0c82b-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="0c82b-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="0c82b-102">Registra il resolver del token di servizio utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="0c82b-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="0c82b-103">Il resolver del token del servizio viene usato per risolvere il token di crittografia sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="0c82b-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="0c82b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0c82b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0c82b-105">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="0c82b-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="0c82b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="0c82b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="0c82b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="0c82b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="0c82b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="0c82b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="0c82b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> serviceTokenResolver**</span><span class="sxs-lookup"><span data-stu-id="0c82b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c82b-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c82b-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c82b-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0c82b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0c82b-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0c82b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c82b-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="0c82b-113">Attributes</span></span>  
  
|<span data-ttu-id="0c82b-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="0c82b-114">Attribute</span></span>|<span data-ttu-id="0c82b-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="0c82b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0c82b-116">type</span><span class="sxs-lookup"><span data-stu-id="0c82b-116">type</span></span>|<span data-ttu-id="0c82b-117">Specifica il tipo del resolver del token del servizio.</span><span class="sxs-lookup"><span data-stu-id="0c82b-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="0c82b-118">Tipo o un tipo che deriva <xref:System.IdentityModel.Selectors.SecurityTokenResolver> dalla classe. <xref:System.IdentityModel.Selectors.SecurityTokenResolver></span><span class="sxs-lookup"><span data-stu-id="0c82b-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="0c82b-119">Per ulteriori informazioni su come specificare l'attributo `type` , vedere [riferimenti ai tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="0c82b-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="0c82b-120">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="0c82b-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c82b-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0c82b-121">Child Elements</span></span>  
 <span data-ttu-id="0c82b-122">Nessuna</span><span class="sxs-lookup"><span data-stu-id="0c82b-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0c82b-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0c82b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0c82b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c82b-124">Element</span></span>|<span data-ttu-id="0c82b-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c82b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c82b-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="0c82b-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="0c82b-127">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0c82b-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c82b-128">Note</span><span class="sxs-lookup"><span data-stu-id="0c82b-128">Remarks</span></span>  
 <span data-ttu-id="0c82b-129">Il resolver del token del servizio può essere usato per risolvere il token di crittografia sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="0c82b-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="0c82b-130">Viene usato per recuperare la chiave che deve essere usata per decrittografare i token in ingresso.</span><span class="sxs-lookup"><span data-stu-id="0c82b-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="0c82b-131">È necessario specificare l' `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="0c82b-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="0c82b-132">Il tipo specificato può essere <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizzato che deriva <xref:System.IdentityModel.Selectors.SecurityTokenResolver> dalla classe.</span><span class="sxs-lookup"><span data-stu-id="0c82b-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="0c82b-133">Alcuni gestori di token consentono di specificare le impostazioni del resolver del token del servizio nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="0c82b-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="0c82b-134">Le impostazioni sui singoli gestori di token eseguono l'override di quelle specificate nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0c82b-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c82b-135">Specificare l' `<serviceTokenResolver>` elemento come elemento figlio [ \<dell'elemento > IdentityConfiguration](identityconfiguration.md) è stato deprecato, ma è ancora supportato per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="0c82b-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="0c82b-136">Le impostazioni sull' `<securityTokenHandlerConfiguration>` elemento eseguono l'override `<identityConfiguration>` di quelle nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="0c82b-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c82b-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="0c82b-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
 