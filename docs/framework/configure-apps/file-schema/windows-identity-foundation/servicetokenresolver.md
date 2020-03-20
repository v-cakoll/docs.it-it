---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152580"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="443d4-101">\<> serviceTokenResolver</span><span class="sxs-lookup"><span data-stu-id="443d4-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="443d4-102">Registra il resolver di token del servizio utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="443d4-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="443d4-103">Il resolver del token del servizio viene utilizzato per risolvere il token di crittografia nei token e nei messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="443d4-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="443d4-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="443d4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="443d4-105">&nbsp;&nbsp;[**\<>system.identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="443d4-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="443d4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di identitàConfigurazione**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="443d4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="443d4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="443d4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="443d4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="443d4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="443d4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span><span class="sxs-lookup"><span data-stu-id="443d4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="443d4-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="443d4-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="443d4-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="443d4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="443d4-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="443d4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="443d4-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="443d4-113">Attributes</span></span>  
  
|<span data-ttu-id="443d4-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="443d4-114">Attribute</span></span>|<span data-ttu-id="443d4-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="443d4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="443d4-116">type</span><span class="sxs-lookup"><span data-stu-id="443d4-116">type</span></span>|<span data-ttu-id="443d4-117">Specifica il tipo di resolver del token del servizio.</span><span class="sxs-lookup"><span data-stu-id="443d4-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="443d4-118">Il <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo che <xref:System.IdentityModel.Selectors.SecurityTokenResolver> deriva dalla classe.</span><span class="sxs-lookup"><span data-stu-id="443d4-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="443d4-119">Per ulteriori informazioni su `type` come specificare l'attributo, vedere [Riferimenti ai tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="443d4-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="443d4-120">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="443d4-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="443d4-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="443d4-121">Child Elements</span></span>  
 <span data-ttu-id="443d4-122">nessuno</span><span class="sxs-lookup"><span data-stu-id="443d4-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="443d4-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="443d4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="443d4-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="443d4-124">Element</span></span>|<span data-ttu-id="443d4-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="443d4-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="443d4-126">\<>securityTokenHandlerConfiguration</span><span class="sxs-lookup"><span data-stu-id="443d4-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="443d4-127">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="443d4-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="443d4-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="443d4-128">Remarks</span></span>  
 <span data-ttu-id="443d4-129">Il resolver del token del servizio può essere utilizzato per risolvere il token di crittografia nei token e nei messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="443d4-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="443d4-130">Viene utilizzato per recuperare la chiave che deve essere utilizzata per decrittografare i token in ingresso.</span><span class="sxs-lookup"><span data-stu-id="443d4-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="443d4-131">È necessario `type` specificare l'attributo.</span><span class="sxs-lookup"><span data-stu-id="443d4-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="443d4-132">Il tipo specificato <xref:System.IdentityModel.Selectors.SecurityTokenResolver> può essere o un tipo <xref:System.IdentityModel.Selectors.SecurityTokenResolver> personalizzato che deriva dalla classe .</span><span class="sxs-lookup"><span data-stu-id="443d4-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="443d4-133">Alcuni gestori di token consentono di specificare le impostazioni del resolver del token del servizio nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="443d4-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="443d4-134">Le impostazioni nei singoli gestori di token eseguono l'override di quelle specificate nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="443d4-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="443d4-135">Specificare `<serviceTokenResolver>` l'elemento come elemento figlio dell'elemento [ \<identityConfiguration>](identityconfiguration.md) è deprecato, ma è comunque supportato per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="443d4-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="443d4-136">Le impostazioni `<securityTokenHandlerConfiguration>` dell'elemento `<identityConfiguration>` sostituiscono quelle dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="443d4-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="443d4-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="443d4-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
