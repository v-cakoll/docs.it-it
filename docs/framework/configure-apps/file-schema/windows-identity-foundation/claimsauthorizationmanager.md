---
title: '&lt;claimsAuthorizationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: a745339cffdada56a9b7f27f3f879b9d437c2da2
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48032101"
---
# <a name="ltclaimsauthorizationmanagergt"></a><span data-ttu-id="22011-102">&lt;claimsAuthorizationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="22011-102">&lt;claimsAuthorizationManager&gt;</span></span>
<span data-ttu-id="22011-103">Registra un gestore di autorizzazione delle attestazioni per le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="22011-103">Registers a claims authorization manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="22011-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="22011-104">\<system.identityModel></span></span>  
<span data-ttu-id="22011-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="22011-105">\<identityConfiguration></span></span>  
<span data-ttu-id="22011-106">\<claimsAuthorizationManager ></span><span class="sxs-lookup"><span data-stu-id="22011-106">\<claimsAuthorizationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22011-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22011-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22011-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="22011-108">Attributes and Elements</span></span>  
 <span data-ttu-id="22011-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="22011-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22011-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="22011-110">Attributes</span></span>  
  
|<span data-ttu-id="22011-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="22011-111">Attribute</span></span>|<span data-ttu-id="22011-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22011-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22011-113">tipo</span><span class="sxs-lookup"><span data-stu-id="22011-113">type</span></span>|<span data-ttu-id="22011-114">Un tipo personalizzato che deriva dal <xref:System.Security.Claims.ClaimsAuthorizationManager> classe.</span><span class="sxs-lookup"><span data-stu-id="22011-114">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="22011-115">Per altre informazioni su come specificare il `type` dell'attributo, vedere [riferimenti a tipi personalizzati](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="22011-115">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22011-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="22011-116">Child Elements</span></span>  
 <span data-ttu-id="22011-117">Se è presente alcun `type` attributo, oppure se il `type` i riferimenti dell'attributo le <xref:System.Security.Claims.ClaimsAuthenticationManager> (classe), il `<claimsAuthorizationManager>` elemento non accetta elementi figlio; tuttavia, le classi derivate da <xref:System.Security.Claims.ClaimsAuthorizationManager> possono definire elementi di configurazione figlio.</span><span class="sxs-lookup"><span data-stu-id="22011-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22011-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="22011-118">Parent Elements</span></span>  
  
|<span data-ttu-id="22011-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="22011-119">Element</span></span>|<span data-ttu-id="22011-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22011-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22011-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="22011-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="22011-122">Specifica le impostazioni di identità a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="22011-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22011-123">Note</span><span class="sxs-lookup"><span data-stu-id="22011-123">Remarks</span></span>  
 <span data-ttu-id="22011-124">Il comportamento predefinito fornito tramite il <xref:System.Security.Claims.ClaimsAuthorizationManager> classe autorizza sempre le attestazioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="22011-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="22011-125">Se nessun `type` attributo è specificato o se il `type` attributo specifica il <xref:System.Security.Claims.ClaimsAuthorizationManager> (classe), il `<claimsAuthorizationManager>` elemento non accetta elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="22011-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="22011-126">È possibile specificare il `type` attributo per registrare un tipo derivato dal <xref:System.Security.Claims.ClaimsAuthorizationManager> classe per implementare il comportamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="22011-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="22011-127">Le classi derivate possono supportano la configurazione tramite gli elementi figlio del `<claimsAuthorizationManager>` elemento eseguendo l'override di <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> metodo per gestire questi elementi.</span><span class="sxs-lookup"><span data-stu-id="22011-127">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="22011-128">Lo schema definito per gli elementi figlio dipende dalla finestra di progettazione della classe.</span><span class="sxs-lookup"><span data-stu-id="22011-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="22011-129">Quando si usa la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o il <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> classe per fornire il controllo di accesso basato sulle attestazioni nel codice, la configurazione di identità che fa riferimento il `<federationConfiguration>` elemento consente di configurare il gestore di autorizzazione delle attestazioni e i criteri utilizzati per rendere decisioni di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="22011-129">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="22011-130">Ciò è vero, anche in scenari non Web gli scenari passivi, ad esempio le applicazioni di Windows Communication Foundation (WCF) o un'applicazione che non è basata sul Web.</span><span class="sxs-lookup"><span data-stu-id="22011-130">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="22011-131">Se l'applicazione non è un'applicazione Web passiva, il `<claimsAuthorizationManager>` elemento (e gli elementi di criteri figlio, se presente) della configurazione dell'identità cui viene fatto riferimento sono le uniche impostazioni applicate.</span><span class="sxs-lookup"><span data-stu-id="22011-131">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="22011-132">Tutte le altre impostazioni vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="22011-132">All other settings are ignored.</span></span> <span data-ttu-id="22011-133">Per altre informazioni, vedere la [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="22011-133">For more information, see the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="22011-134">Questo elemento viene impostata la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> proprietà.</span><span class="sxs-lookup"><span data-stu-id="22011-134">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22011-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="22011-135">Example</span></span>  
 <span data-ttu-id="22011-136">Il codice XML seguente viene illustrata la configurazione per un'autorizzazione delle attestazioni gestore che implementa criteri composto da coppie risorsa-azione di ognuno dei quali specifica combinazioni booleane le attestazioni che un richiedente deve disporre del privilegio per eseguire l'operazione sulla risorsa.</span><span class="sxs-lookup"><span data-stu-id="22011-136">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="22011-137">Il codice che implementa il gestore di autorizzazione delle attestazioni in grado di utilizzare questo criterio è reperibile nel `ClaimsBasedAuthorization` esempio.</span><span class="sxs-lookup"><span data-stu-id="22011-137">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
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
