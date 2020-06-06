---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152749"
---
# \<claimsAuthenticationManager>
<span data-ttu-id="cae17-101">Registra un gestore di autenticazione delle attestazioni per le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="cae17-101">Registers a claims authentication manager for the incoming claims.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="cae17-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cae17-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cae17-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cae17-103">Attributes and Elements</span></span>  
 <span data-ttu-id="cae17-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cae17-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cae17-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="cae17-105">Attributes</span></span>  
  
|<span data-ttu-id="cae17-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="cae17-106">Attribute</span></span>|<span data-ttu-id="cae17-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cae17-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cae17-108">type</span><span class="sxs-lookup"><span data-stu-id="cae17-108">type</span></span>|<span data-ttu-id="cae17-109">Specifica un tipo personalizzato che deriva dalla <xref:System.Security.Claims.ClaimsAuthenticationManager> classe.</span><span class="sxs-lookup"><span data-stu-id="cae17-109">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="cae17-110">Per ulteriori informazioni su come specificare l' `type` attributo, vedere [riferimenti ai tipi personalizzati].</span><span class="sxs-lookup"><span data-stu-id="cae17-110">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cae17-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cae17-111">Child Elements</span></span>  
 <span data-ttu-id="cae17-112">Se non esiste alcun `type` attributo o se l' `type` attributo fa riferimento alla <xref:System.Security.Claims.ClaimsAuthenticationManager> classe, l' `<claimsAuthenticationManager>` elemento non accetta elementi figlio. Tuttavia, le classi derivate da <xref:System.Security.Claims.ClaimsAuthenticationManager> possono definire elementi di configurazione figlio.</span><span class="sxs-lookup"><span data-stu-id="cae17-112">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cae17-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cae17-113">Parent Elements</span></span>  
  
|<span data-ttu-id="cae17-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="cae17-114">Element</span></span>|<span data-ttu-id="cae17-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cae17-115">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="cae17-116">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="cae17-116">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cae17-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="cae17-117">Remarks</span></span>  
 <span data-ttu-id="cae17-118">Il comportamento predefinito fornito tramite la <xref:System.Security.Claims.ClaimsAuthenticationManager> classe restituisce le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="cae17-118">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="cae17-119">Se non `type` è specificato alcun attributo o se l' `type` attributo specifica la <xref:System.Security.Claims.ClaimsAuthenticationManager> classe, l' `<claimsAuthenticationManager>` elemento non accetta gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="cae17-119">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="cae17-120">È possibile specificare l' `type` attributo per registrare un tipo derivato dalla <xref:System.Security.Claims.ClaimsAuthenticationManager> classe per implementare il comportamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="cae17-120">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="cae17-121">Le classi derivate possono supportare la configurazione tramite elementi figlio dell' `<claimsAuthenticationManager>` elemento eseguendo l'override del <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> metodo per gestire questi elementi.</span><span class="sxs-lookup"><span data-stu-id="cae17-121">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="cae17-122">Lo schema definito per gli elementi figlio dipende dalla finestra di progettazione della classe.</span><span class="sxs-lookup"><span data-stu-id="cae17-122">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="cae17-123">L' `<claimsAuthenticationManager>` elemento imposta la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="cae17-123">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cae17-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="cae17-124">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
