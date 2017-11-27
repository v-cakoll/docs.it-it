---
title: '&lt;claimsAuthenticationManager&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 48e5be23b196a24a9d3e2a1dc4639d8ca9823660
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltclaimsauthenticationmanagergt"></a><span data-ttu-id="3dee1-102">&lt;claimsAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="3dee1-102">&lt;claimsAuthenticationManager&gt;</span></span>
<span data-ttu-id="3dee1-103">Registra un gestore di autenticazione delle attestazioni per le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="3dee1-103">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="3dee1-104">\<System. IdentityModel ></span><span class="sxs-lookup"><span data-stu-id="3dee1-104">\<system.identityModel></span></span>  
<span data-ttu-id="3dee1-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3dee1-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3dee1-106">\<claimsAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="3dee1-106">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dee1-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3dee1-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3dee1-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3dee1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3dee1-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3dee1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3dee1-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="3dee1-110">Attributes</span></span>  
  
|<span data-ttu-id="3dee1-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="3dee1-111">Attribute</span></span>|<span data-ttu-id="3dee1-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3dee1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3dee1-113">tipo</span><span class="sxs-lookup"><span data-stu-id="3dee1-113">type</span></span>|<span data-ttu-id="3dee1-114">Specifica un tipo personalizzato da cui deriva il <xref:System.Security.Claims.ClaimsAuthenticationManager> classe.</span><span class="sxs-lookup"><span data-stu-id="3dee1-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="3dee1-115">Per ulteriori informazioni su come specificare il `type` attributo, vedere [riferimenti al tipo personalizzato].</span><span class="sxs-lookup"><span data-stu-id="3dee1-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3dee1-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3dee1-116">Child Elements</span></span>  
 <span data-ttu-id="3dee1-117">Se è presente alcun `type` attributo, o se il `type` riferimenti dell'attributo di <xref:System.Security.Claims.ClaimsAuthenticationManager> (classe), il `<claimsAuthenticationManager>` elemento non ha elementi figlio; tuttavia, le classi derivate da <xref:System.Security.Claims.ClaimsAuthenticationManager> possibile definire elementi di configurazione figlio.</span><span class="sxs-lookup"><span data-stu-id="3dee1-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3dee1-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3dee1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3dee1-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="3dee1-119">Element</span></span>|<span data-ttu-id="3dee1-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3dee1-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3dee1-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3dee1-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="3dee1-122">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="3dee1-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dee1-123">Note</span><span class="sxs-lookup"><span data-stu-id="3dee1-123">Remarks</span></span>  
 <span data-ttu-id="3dee1-124">Il comportamento predefinito fornito tramite la <xref:System.Security.Claims.ClaimsAuthenticationManager> classe restituisce le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="3dee1-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="3dee1-125">Se non `type` attributo specificato o se il `type` attributo specifica il <xref:System.Security.Claims.ClaimsAuthenticationManager> (classe), il `<claimsAuthenticationManager>` elemento non ha elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="3dee1-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="3dee1-126">È possibile specificare il `type` attributo per registrare un tipo derivato dalla <xref:System.Security.Claims.ClaimsAuthenticationManager> classe per implementare un comportamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3dee1-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="3dee1-127">Le classi derivate possono supportare configurazione tramite gli elementi figlio del `<claimsAuthenticationManager>` elemento eseguendo l'override di <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> metodo per gestire questi elementi.</span><span class="sxs-lookup"><span data-stu-id="3dee1-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="3dee1-128">Lo schema definito per gli elementi figlio è la finestra di progettazione della classe.</span><span class="sxs-lookup"><span data-stu-id="3dee1-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="3dee1-129">Il `<claimsAuthenticationManager>` set di elementi di <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="3dee1-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dee1-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="3dee1-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```
