---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152749"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="b32be-101">\<> di claimsAuthenticationManager</span><span class="sxs-lookup"><span data-stu-id="b32be-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="b32be-102">Registra un gestore di autenticazione delle attestazioni per le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="b32be-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
<span data-ttu-id="b32be-103">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b32be-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b32be-104">&nbsp;&nbsp;[**\<>system.identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="b32be-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="b32be-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>di identitàConfigurazione**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b32be-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="b32be-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span><span class="sxs-lookup"><span data-stu-id="b32be-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b32be-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b32be-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b32be-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b32be-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b32be-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b32be-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b32be-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="b32be-110">Attributes</span></span>  
  
|<span data-ttu-id="b32be-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="b32be-111">Attribute</span></span>|<span data-ttu-id="b32be-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b32be-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b32be-113">type</span><span class="sxs-lookup"><span data-stu-id="b32be-113">type</span></span>|<span data-ttu-id="b32be-114">Specifica un tipo personalizzato che <xref:System.Security.Claims.ClaimsAuthenticationManager> deriva dalla classe.</span><span class="sxs-lookup"><span data-stu-id="b32be-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="b32be-115">Per ulteriori informazioni su `type` come specificare l'attributo, vedere [Riferimenti ai tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="b32be-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b32be-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b32be-116">Child Elements</span></span>  
 <span data-ttu-id="b32be-117">Se non `type` è presente alcun `type` attributo <xref:System.Security.Claims.ClaimsAuthenticationManager> o `<claimsAuthenticationManager>` se l'attributo fa riferimento alla classe, l'elemento non accetta elementi figlio; tuttavia, le <xref:System.Security.Claims.ClaimsAuthenticationManager> classi derivate da possono definire elementi di configurazione figlio.</span><span class="sxs-lookup"><span data-stu-id="b32be-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b32be-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b32be-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b32be-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="b32be-119">Element</span></span>|<span data-ttu-id="b32be-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b32be-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b32be-121">\<>di identitàConfigurazione</span><span class="sxs-lookup"><span data-stu-id="b32be-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="b32be-122">Specifica le impostazioni dell'identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="b32be-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b32be-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b32be-123">Remarks</span></span>  
 <span data-ttu-id="b32be-124">Il comportamento predefinito <xref:System.Security.Claims.ClaimsAuthenticationManager> fornito tramite la classe fa eco alle attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="b32be-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="b32be-125">Se `type` non viene specificato `type` alcun attributo <xref:System.Security.Claims.ClaimsAuthenticationManager> o `<claimsAuthenticationManager>` se l'attributo specifica la classe , l'elemento non accetta elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="b32be-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="b32be-126">È possibile `type` specificare l'attributo <xref:System.Security.Claims.ClaimsAuthenticationManager> per registrare un tipo derivato dalla classe per implementare il comportamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b32be-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="b32be-127">Le classi derivate possono supportare la configurazione tramite gli elementi figlio dell'elemento `<claimsAuthenticationManager>` eseguendo l'override del <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> metodo per gestire questi elementi.</span><span class="sxs-lookup"><span data-stu-id="b32be-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="b32be-128">Lo schema definito per gli elementi figlio è all'utente della finestra di progettazione della classe.</span><span class="sxs-lookup"><span data-stu-id="b32be-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="b32be-129">L'elemento `<claimsAuthenticationManager>` <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> imposta la proprietà .</span><span class="sxs-lookup"><span data-stu-id="b32be-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b32be-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="b32be-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
