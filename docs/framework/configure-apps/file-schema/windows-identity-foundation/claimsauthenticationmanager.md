---
title: '&lt;claimsAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 0ec7e44363f87e54eae97b70352f520fe87540be
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47235270"
---
# <a name="ltclaimsauthenticationmanagergt"></a><span data-ttu-id="4a369-102">&lt;claimsAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="4a369-102">&lt;claimsAuthenticationManager&gt;</span></span>
<span data-ttu-id="4a369-103">Registra un gestore di autenticazione delle attestazioni per le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="4a369-103">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="4a369-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="4a369-104">\<system.identityModel></span></span>  
<span data-ttu-id="4a369-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="4a369-105">\<identityConfiguration></span></span>  
<span data-ttu-id="4a369-106">\<claimsAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="4a369-106">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a369-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a369-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a369-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4a369-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4a369-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4a369-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a369-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="4a369-110">Attributes</span></span>  
  
|<span data-ttu-id="4a369-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="4a369-111">Attribute</span></span>|<span data-ttu-id="4a369-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a369-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a369-113">tipo</span><span class="sxs-lookup"><span data-stu-id="4a369-113">type</span></span>|<span data-ttu-id="4a369-114">Specifica un tipo personalizzato che deriva dal <xref:System.Security.Claims.ClaimsAuthenticationManager> classe.</span><span class="sxs-lookup"><span data-stu-id="4a369-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="4a369-115">Per altre informazioni su come specificare il `type` attributo, vedere [riferimenti a tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="4a369-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a369-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4a369-116">Child Elements</span></span>  
 <span data-ttu-id="4a369-117">Se è presente alcun `type` attributo, oppure se il `type` i riferimenti dell'attributo le <xref:System.Security.Claims.ClaimsAuthenticationManager> (classe), il `<claimsAuthenticationManager>` elemento non accetta elementi figlio; tuttavia, le classi derivate da <xref:System.Security.Claims.ClaimsAuthenticationManager> possono definire elementi di configurazione figlio.</span><span class="sxs-lookup"><span data-stu-id="4a369-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4a369-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4a369-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4a369-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="4a369-119">Element</span></span>|<span data-ttu-id="4a369-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a369-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a369-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="4a369-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="4a369-122">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="4a369-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a369-123">Note</span><span class="sxs-lookup"><span data-stu-id="4a369-123">Remarks</span></span>  
 <span data-ttu-id="4a369-124">Il comportamento predefinito fornito tramite il <xref:System.Security.Claims.ClaimsAuthenticationManager> classe restituisce le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="4a369-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="4a369-125">Se nessun `type` attributo è specificato o se il `type` attributo specifica il <xref:System.Security.Claims.ClaimsAuthenticationManager> (classe), il `<claimsAuthenticationManager>` elemento non accetta elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="4a369-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="4a369-126">È possibile specificare il `type` attributo per registrare un tipo derivato dal <xref:System.Security.Claims.ClaimsAuthenticationManager> classe per implementare il comportamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4a369-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="4a369-127">Le classi derivate possono supportano la configurazione tramite gli elementi figlio del `<claimsAuthenticationManager>` elemento eseguendo l'override di <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> metodo per gestire questi elementi.</span><span class="sxs-lookup"><span data-stu-id="4a369-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="4a369-128">Lo schema definito per gli elementi figlio dipende dalla finestra di progettazione della classe.</span><span class="sxs-lookup"><span data-stu-id="4a369-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="4a369-129">Il `<claimsAuthenticationManager>` set di elementi di <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="4a369-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a369-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="4a369-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```
