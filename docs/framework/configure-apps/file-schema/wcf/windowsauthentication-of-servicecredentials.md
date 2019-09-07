---
title: <windowsAuthentication> di <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: ded04f6e87fce2e12dac8f681ba2d4178f8fd204
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399105"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="2176c-102">\<WindowsAuthentication > di \<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="2176c-102">\<windowsAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="2176c-103">Specifica le impostazioni della credenziale di un servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="2176c-103">Specifies the settings of a Windows service credential.</span></span>  
  
<span data-ttu-id="2176c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2176c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2176c-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2176c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2176c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2176c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="2176c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceBehaviors**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2176c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="2176c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2176c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="2176c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di serviceCredentials**](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="2176c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="2176c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> windowsAuthentication**</span><span class="sxs-lookup"><span data-stu-id="2176c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2176c-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2176c-111">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2176c-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2176c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2176c-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2176c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2176c-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="2176c-114">Attributes</span></span>  
  
|<span data-ttu-id="2176c-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="2176c-115">Attribute</span></span>|<span data-ttu-id="2176c-116">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="2176c-116">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="2176c-117">Attributo booleano facoltativo che specifica se il sistema include gruppi Windows nel contesto di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2176c-117">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="2176c-118">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="2176c-118">The default is `true`.</span></span><br /><br /> <span data-ttu-id="2176c-119">L'impostazione di questo attributo su `true` determina un effetto sulle prestazioni in quanto comporta un'espansione completa del gruppo.</span><span class="sxs-lookup"><span data-stu-id="2176c-119">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="2176c-120">Impostare questo attributo su `false` se non è necessario stabilire l'elenco di gruppi a cui appartiene un utente.</span><span class="sxs-lookup"><span data-stu-id="2176c-120">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="2176c-121">Attributo booleano facoltativo che specifica se sono consentiti chiamanti anonimi, non autenticati.</span><span class="sxs-lookup"><span data-stu-id="2176c-121">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="2176c-122">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="2176c-122">The default is `false`.</span></span><br /><br /> <span data-ttu-id="2176c-123">Quando l'attributo `clientCredentialType` di un'associazione è impostato su `Windows`, il sistema non consente i chiamanti anonimi.</span><span class="sxs-lookup"><span data-stu-id="2176c-123">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="2176c-124">Questo significa che l'accesso al sistema è consentito solo ai chiamanti autenticati del dominio o del gruppo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2176c-124">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="2176c-125">È possibile eseguire l'override di questo comportamento usando questo attributo.</span><span class="sxs-lookup"><span data-stu-id="2176c-125">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="2176c-126">Usare questa impostazione con estrema cautela.</span><span class="sxs-lookup"><span data-stu-id="2176c-126">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2176c-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2176c-127">Child Elements</span></span>  
 <span data-ttu-id="2176c-128">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2176c-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2176c-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2176c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="2176c-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="2176c-130">Element</span></span>|<span data-ttu-id="2176c-131">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="2176c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2176c-132">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="2176c-132">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="2176c-133">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="2176c-133">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2176c-134">Note</span><span class="sxs-lookup"><span data-stu-id="2176c-134">Remarks</span></span>  
 <span data-ttu-id="2176c-135">Usare questo elemento per specificare se consentire l'accesso a utenti di Windows anonimi mediante l'impostazione dell'attributo `allowAnonymousLogons`.</span><span class="sxs-lookup"><span data-stu-id="2176c-135">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="2176c-136">È inoltre possibile specificare se includere le informazioni sul gruppo al quale appartengono gli utenti in AuthorizationContext mediante l'impostazione dell'attributo `includeWindowsGroups`.</span><span class="sxs-lookup"><span data-stu-id="2176c-136">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="2176c-137">Se l'attributo viene impostato su `true` (impostazione predefinita), il servizio sarà in grado di determinare i gruppi di Windows ai quali appartiene il client.</span><span class="sxs-lookup"><span data-stu-id="2176c-137">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2176c-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2176c-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
