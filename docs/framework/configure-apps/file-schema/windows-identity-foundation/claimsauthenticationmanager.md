---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: ecf26263bf47e8b4609e7adc208f0a59a2fa795b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667327"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="ea2fc-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="ea2fc-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="ea2fc-102">Registra un gestore di autenticazione delle attestazioni per le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="ea2fc-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="ea2fc-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="ea2fc-103">\<system.identityModel></span></span>  
<span data-ttu-id="ea2fc-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ea2fc-104">\<identityConfiguration></span></span>  
<span data-ttu-id="ea2fc-105">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="ea2fc-105">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea2fc-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea2fc-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea2fc-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ea2fc-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ea2fc-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ea2fc-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea2fc-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="ea2fc-109">Attributes</span></span>  
  
|<span data-ttu-id="ea2fc-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="ea2fc-110">Attribute</span></span>|<span data-ttu-id="ea2fc-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea2fc-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ea2fc-112">tipo</span><span class="sxs-lookup"><span data-stu-id="ea2fc-112">type</span></span>|<span data-ttu-id="ea2fc-113">Specifica un tipo personalizzato che deriva dal <xref:System.Security.Claims.ClaimsAuthenticationManager> classe.</span><span class="sxs-lookup"><span data-stu-id="ea2fc-113">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="ea2fc-114">Per altre informazioni su come specificare il `type` attributo, vedere [riferimenti a tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="ea2fc-114">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea2fc-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ea2fc-115">Child Elements</span></span>  
 <span data-ttu-id="ea2fc-116">Se è presente alcun `type` attributo, oppure se il `type` i riferimenti dell'attributo le <xref:System.Security.Claims.ClaimsAuthenticationManager> (classe), il `<claimsAuthenticationManager>` elemento non accetta elementi figlio; tuttavia, le classi derivate da <xref:System.Security.Claims.ClaimsAuthenticationManager> possono definire elementi di configurazione figlio.</span><span class="sxs-lookup"><span data-stu-id="ea2fc-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea2fc-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ea2fc-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ea2fc-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea2fc-118">Element</span></span>|<span data-ttu-id="ea2fc-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ea2fc-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea2fc-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="ea2fc-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="ea2fc-121">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="ea2fc-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea2fc-122">Note</span><span class="sxs-lookup"><span data-stu-id="ea2fc-122">Remarks</span></span>  
 <span data-ttu-id="ea2fc-123">Il comportamento predefinito fornito tramite il <xref:System.Security.Claims.ClaimsAuthenticationManager> classe restituisce le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="ea2fc-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="ea2fc-124">Se nessun `type` attributo è specificato o se il `type` attributo specifica il <xref:System.Security.Claims.ClaimsAuthenticationManager> (classe), il `<claimsAuthenticationManager>` elemento non accetta elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="ea2fc-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="ea2fc-125">È possibile specificare il `type` attributo per registrare un tipo derivato dal <xref:System.Security.Claims.ClaimsAuthenticationManager> classe per implementare il comportamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ea2fc-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="ea2fc-126">Le classi derivate possono supportano la configurazione tramite gli elementi figlio del `<claimsAuthenticationManager>` elemento eseguendo l'override di <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> metodo per gestire questi elementi.</span><span class="sxs-lookup"><span data-stu-id="ea2fc-126">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="ea2fc-127">Lo schema definito per gli elementi figlio dipende dalla finestra di progettazione della classe.</span><span class="sxs-lookup"><span data-stu-id="ea2fc-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="ea2fc-128">Il `<claimsAuthenticationManager>` set di elementi di <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="ea2fc-128">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea2fc-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="ea2fc-129">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
