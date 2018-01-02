---
title: '&lt;windowsAuthentication&gt; di &lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b6043b35ea9dbed1e1e6e170035436038334b34
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltwindowsauthenticationgt-of-ltservicecredentialsgt"></a><span data-ttu-id="da776-102">&lt;windowsAuthentication&gt; di &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="da776-102">&lt;windowsAuthentication&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="da776-103">Specifica le impostazioni della credenziale di un servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="da776-103">Specifies the settings of a Windows service credential.</span></span>  
  
 <span data-ttu-id="da776-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="da776-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="da776-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="da776-105">\<behaviors></span></span>  
<span data-ttu-id="da776-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="da776-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="da776-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="da776-107">\<behavior></span></span>  
<span data-ttu-id="da776-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="da776-108">\<serviceCredentials></span></span>  
<span data-ttu-id="da776-109">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="da776-109">\<windowsAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da776-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da776-110">Syntax</span></span>  
  
```xml  
<windowsAuthentication  
      allowAnonymousLogons="Boolean"  
      includeWindowsGroups="Boolean" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da776-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="da776-111">Attributes and Elements</span></span>  
 <span data-ttu-id="da776-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="da776-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da776-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="da776-113">Attributes</span></span>  
  
|<span data-ttu-id="da776-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="da776-114">Attribute</span></span>|<span data-ttu-id="da776-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da776-115">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="da776-116">Attributo booleano facoltativo che specifica se il sistema include gruppi Windows nel contesto di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="da776-116">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="da776-117">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="da776-117">The default is `true`.</span></span><br /><br /> <span data-ttu-id="da776-118">L'impostazione di questo attributo su `true` determina un effetto sulle prestazioni in quanto comporta un'espansione completa del gruppo.</span><span class="sxs-lookup"><span data-stu-id="da776-118">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="da776-119">Impostare questo attributo su `false` se non è necessario stabilire l'elenco di gruppi a cui appartiene un utente.</span><span class="sxs-lookup"><span data-stu-id="da776-119">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="da776-120">Attributo booleano facoltativo che specifica se sono consentiti chiamanti anonimi, non autenticati.</span><span class="sxs-lookup"><span data-stu-id="da776-120">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="da776-121">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="da776-121">The default is `false`.</span></span><br /><br /> <span data-ttu-id="da776-122">Quando l'attributo `clientCredentialType` di un'associazione è impostato su `Windows`, il sistema non consente i chiamanti anonimi.</span><span class="sxs-lookup"><span data-stu-id="da776-122">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="da776-123">Questo significa che l'accesso al sistema è consentito solo ai chiamanti autenticati del dominio o del gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="da776-123">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="da776-124">È possibile eseguire l'override di questo comportamento usando questo attributo.</span><span class="sxs-lookup"><span data-stu-id="da776-124">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="da776-125">Usare questa impostazione con estrema cautela.</span><span class="sxs-lookup"><span data-stu-id="da776-125">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da776-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="da776-126">Child Elements</span></span>  
 <span data-ttu-id="da776-127">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="da776-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da776-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="da776-128">Parent Elements</span></span>  
  
|<span data-ttu-id="da776-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="da776-129">Element</span></span>|<span data-ttu-id="da776-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da776-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da776-131">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="da776-131">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="da776-132">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="da776-132">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da776-133">Note</span><span class="sxs-lookup"><span data-stu-id="da776-133">Remarks</span></span>  
 <span data-ttu-id="da776-134">Usare questo elemento per specificare se consentire l'accesso a utenti di Windows anonimi mediante l'impostazione dell'attributo `allowAnonymousLogons`.</span><span class="sxs-lookup"><span data-stu-id="da776-134">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="da776-135">È inoltre possibile specificare se includere le informazioni sul gruppo al quale appartengono gli utenti in AuthorizationContext mediante l'impostazione dell'attributo `includeWindowsGroups`.</span><span class="sxs-lookup"><span data-stu-id="da776-135">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="da776-136">Se l'attributo viene impostato su `true` (impostazione predefinita), il servizio sarà in grado di determinare i gruppi di Windows ai quali appartiene il client.</span><span class="sxs-lookup"><span data-stu-id="da776-136">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da776-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da776-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WindowsServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>  
 <xref:System.ServiceModel.Security.WindowsServiceCredential>
