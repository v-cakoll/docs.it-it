---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: c901daf4d442a206345301795c7a4bdc076329cd
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252097"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="4de2f-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="4de2f-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="4de2f-102">Registra un gestore di autenticazione delle attestazioni per le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="4de2f-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
<span data-ttu-id="4de2f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4de2f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4de2f-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="4de2f-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="4de2f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="4de2f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="4de2f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> claimsAuthenticationManager**</span><span class="sxs-lookup"><span data-stu-id="4de2f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4de2f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4de2f-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4de2f-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4de2f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4de2f-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4de2f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4de2f-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="4de2f-110">Attributes</span></span>  
  
|<span data-ttu-id="4de2f-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="4de2f-111">Attribute</span></span>|<span data-ttu-id="4de2f-112">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="4de2f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4de2f-113">type</span><span class="sxs-lookup"><span data-stu-id="4de2f-113">type</span></span>|<span data-ttu-id="4de2f-114">Specifica un tipo personalizzato che deriva dalla <xref:System.Security.Claims.ClaimsAuthenticationManager> classe.</span><span class="sxs-lookup"><span data-stu-id="4de2f-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="4de2f-115">Per ulteriori informazioni su come specificare l'attributo `type` , vedere [riferimenti ai tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="4de2f-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4de2f-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4de2f-116">Child Elements</span></span>  
 <span data-ttu-id="4de2f-117">Se non esiste alcun `type` attributo o se l' `type` attributo fa riferimento alla <xref:System.Security.Claims.ClaimsAuthenticationManager> classe, l' `<claimsAuthenticationManager>` elemento non accetta elementi figlio. Tuttavia, le classi derivate da possono definire elementi di <xref:System.Security.Claims.ClaimsAuthenticationManager> configurazione figlio.</span><span class="sxs-lookup"><span data-stu-id="4de2f-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4de2f-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4de2f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4de2f-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="4de2f-119">Element</span></span>|<span data-ttu-id="4de2f-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4de2f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4de2f-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="4de2f-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="4de2f-122">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="4de2f-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4de2f-123">Note</span><span class="sxs-lookup"><span data-stu-id="4de2f-123">Remarks</span></span>  
 <span data-ttu-id="4de2f-124">Il comportamento predefinito fornito tramite la <xref:System.Security.Claims.ClaimsAuthenticationManager> classe restituisce le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="4de2f-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="4de2f-125">Se non `type` è specificato alcun attributo o se `type` l'attributo specifica <xref:System.Security.Claims.ClaimsAuthenticationManager> la classe, `<claimsAuthenticationManager>` l'elemento non accetta gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="4de2f-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="4de2f-126">È possibile specificare l' `type` attributo per registrare un tipo derivato <xref:System.Security.Claims.ClaimsAuthenticationManager> dalla classe per implementare il comportamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4de2f-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="4de2f-127">Le classi derivate possono supportare la configurazione tramite `<claimsAuthenticationManager>` elementi figlio dell'elemento eseguendo <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> l'override del metodo per gestire questi elementi.</span><span class="sxs-lookup"><span data-stu-id="4de2f-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="4de2f-128">Lo schema definito per gli elementi figlio dipende dalla finestra di progettazione della classe.</span><span class="sxs-lookup"><span data-stu-id="4de2f-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="4de2f-129">L' `<claimsAuthenticationManager>` elemento imposta la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="4de2f-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4de2f-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="4de2f-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
