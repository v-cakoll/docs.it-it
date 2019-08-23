---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: 74ca031f7017d51adaa7a71593f537b64abbeae6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942897"
---
# <a name="claimsauthorizationmanager"></a><span data-ttu-id="f0915-101">\<claimsAuthorizationManager></span><span class="sxs-lookup"><span data-stu-id="f0915-101">\<claimsAuthorizationManager></span></span>
<span data-ttu-id="f0915-102">Registra un gestore autorizzazioni delle attestazioni per le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="f0915-102">Registers a claims authorization manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="f0915-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f0915-103">\<system.identityModel></span></span>  
<span data-ttu-id="f0915-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f0915-104">\<identityConfiguration></span></span>  
<span data-ttu-id="f0915-105">\<claimsAuthorizationManager></span><span class="sxs-lookup"><span data-stu-id="f0915-105">\<claimsAuthorizationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0915-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0915-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0915-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f0915-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f0915-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f0915-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0915-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="f0915-109">Attributes</span></span>  
  
|<span data-ttu-id="f0915-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="f0915-110">Attribute</span></span>|<span data-ttu-id="f0915-111">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="f0915-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f0915-112">type</span><span class="sxs-lookup"><span data-stu-id="f0915-112">type</span></span>|<span data-ttu-id="f0915-113">Tipo personalizzato che deriva dalla <xref:System.Security.Claims.ClaimsAuthorizationManager> classe.</span><span class="sxs-lookup"><span data-stu-id="f0915-113">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="f0915-114">Per ulteriori informazioni su come specificare l'attributo `type` , vedere [riferimenti ai tipi personalizzati](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="f0915-114">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0915-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f0915-115">Child Elements</span></span>  
 <span data-ttu-id="f0915-116">Se non esiste alcun `type` attributo o se l' `type` attributo fa riferimento alla <xref:System.Security.Claims.ClaimsAuthenticationManager> classe, l' `<claimsAuthorizationManager>` elemento non accetta elementi figlio. Tuttavia, le classi derivate da possono definire elementi di <xref:System.Security.Claims.ClaimsAuthorizationManager> configurazione figlio.</span><span class="sxs-lookup"><span data-stu-id="f0915-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0915-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f0915-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f0915-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0915-118">Element</span></span>|<span data-ttu-id="f0915-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0915-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0915-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f0915-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="f0915-121">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="f0915-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0915-122">Note</span><span class="sxs-lookup"><span data-stu-id="f0915-122">Remarks</span></span>  
 <span data-ttu-id="f0915-123">Il comportamento predefinito fornito tramite la <xref:System.Security.Claims.ClaimsAuthorizationManager> classe autorizza sempre le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="f0915-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="f0915-124">Se non `type` è specificato alcun attributo o se `type` l'attributo specifica <xref:System.Security.Claims.ClaimsAuthorizationManager> la classe, `<claimsAuthorizationManager>` l'elemento non accetta gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="f0915-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="f0915-125">È possibile specificare l' `type` attributo per registrare un tipo derivato <xref:System.Security.Claims.ClaimsAuthorizationManager> dalla classe per implementare il comportamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f0915-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="f0915-126">Le classi derivate possono supportare la configurazione tramite `<claimsAuthorizationManager>` elementi figlio dell'elemento eseguendo <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> l'override del metodo per gestire questi elementi.</span><span class="sxs-lookup"><span data-stu-id="f0915-126">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="f0915-127">Lo schema definito per gli elementi figlio dipende dalla finestra di progettazione della classe.</span><span class="sxs-lookup"><span data-stu-id="f0915-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f0915-128">Quando si usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o la <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo degli accessi in base alle attestazioni nel codice, la configurazione dell'identità a `<federationConfiguration>` cui fa riferimento l'elemento configura il gestore delle autorizzazioni delle attestazioni e i criteri usati per eseguire decisioni di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="f0915-128">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="f0915-129">Questo vale anche per gli scenari che non sono scenari Web passivi, ad esempio applicazioni Windows Communication Foundation (WCF) o un'applicazione che non è basata sul Web.</span><span class="sxs-lookup"><span data-stu-id="f0915-129">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="f0915-130">Se l'applicazione non è un'applicazione Web passiva, l' `<claimsAuthorizationManager>` elemento e i relativi elementi figlio, se presenti, della configurazione di identità a cui si fa riferimento sono le uniche impostazioni applicate.</span><span class="sxs-lookup"><span data-stu-id="f0915-130">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="f0915-131">Tutte le altre impostazioni vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="f0915-131">All other settings are ignored.</span></span> <span data-ttu-id="f0915-132">Per ulteriori informazioni, vedere l' [ \<elemento federationConfiguration >](federationconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="f0915-132">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="f0915-133">Questo elemento imposta la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="f0915-133">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0915-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="f0915-134">Example</span></span>  
 <span data-ttu-id="f0915-135">Nel codice XML seguente viene illustrata la configurazione di un gestore autorizzazioni delle attestazioni che implementa i criteri composte da coppie di azioni di risorse, ognuna delle quali specifica le combinazioni booleane delle attestazioni che un richiedente deve possedere per eseguire l'azione sulla risorsa.</span><span class="sxs-lookup"><span data-stu-id="f0915-135">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="f0915-136">Il codice che implementa il gestore autorizzazioni delle attestazioni in grado di utilizzare questo criterio è disponibile `ClaimsBasedAuthorization` nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="f0915-136">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
