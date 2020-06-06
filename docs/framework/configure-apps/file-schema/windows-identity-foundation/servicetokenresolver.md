---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152580"
---
# \<serviceTokenResolver>
<span data-ttu-id="9938d-101">Registra il resolver del token di servizio utilizzato dai gestori nella raccolta di gestori di token.</span><span class="sxs-lookup"><span data-stu-id="9938d-101">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="9938d-102">Il resolver del token del servizio viene usato per risolvere il token di crittografia sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="9938d-102">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="9938d-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9938d-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9938d-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9938d-104">Attributes and Elements</span></span>  
 <span data-ttu-id="9938d-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9938d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9938d-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="9938d-106">Attributes</span></span>  
  
|<span data-ttu-id="9938d-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="9938d-107">Attribute</span></span>|<span data-ttu-id="9938d-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9938d-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9938d-109">type</span><span class="sxs-lookup"><span data-stu-id="9938d-109">type</span></span>|<span data-ttu-id="9938d-110">Specifica il tipo del resolver del token del servizio.</span><span class="sxs-lookup"><span data-stu-id="9938d-110">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="9938d-111"><xref:System.IdentityModel.Selectors.SecurityTokenResolver>Tipo o un tipo che deriva dalla <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="9938d-111">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="9938d-112">Per ulteriori informazioni su come specificare l' `type` attributo, vedere [riferimenti ai tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="9938d-112">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="9938d-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9938d-113">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9938d-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9938d-114">Child Elements</span></span>  
 <span data-ttu-id="9938d-115">nessuno</span><span class="sxs-lookup"><span data-stu-id="9938d-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9938d-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9938d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="9938d-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="9938d-117">Element</span></span>|<span data-ttu-id="9938d-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9938d-118">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="9938d-119">Fornisce la configurazione per una raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9938d-119">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9938d-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="9938d-120">Remarks</span></span>  
 <span data-ttu-id="9938d-121">Il resolver del token del servizio può essere usato per risolvere il token di crittografia sui token e i messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="9938d-121">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="9938d-122">Viene usato per recuperare la chiave che deve essere usata per decrittografare i token in ingresso.</span><span class="sxs-lookup"><span data-stu-id="9938d-122">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="9938d-123">È necessario specificare l' `type` attributo.</span><span class="sxs-lookup"><span data-stu-id="9938d-123">You must specify the `type` attribute.</span></span> <span data-ttu-id="9938d-124">Il tipo specificato può essere <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizzato che deriva dalla <xref:System.IdentityModel.Selectors.SecurityTokenResolver> classe.</span><span class="sxs-lookup"><span data-stu-id="9938d-124">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="9938d-125">Alcuni gestori di token consentono di specificare le impostazioni del resolver del token del servizio nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="9938d-125">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="9938d-126">Le impostazioni sui singoli gestori di token eseguono l'override di quelle specificate nella raccolta di gestori di token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9938d-126">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9938d-127">Specificare l' `<serviceTokenResolver>` elemento come elemento figlio dell' [\<identityConfiguration>](identityconfiguration.md) elemento è stato deprecato, ma è ancora supportato per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="9938d-127">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="9938d-128">Le impostazioni sull' `<securityTokenHandlerConfiguration>` elemento eseguono l'override di quelle nell' `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="9938d-128">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9938d-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="9938d-129">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
