---
title: '&lt;userNameAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cea18a2c8c2244f384b87b48f195b77da4eb5dfd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltusernameauthenticationgt"></a><span data-ttu-id="a4ade-102">&lt;userNameAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="a4ade-102">&lt;userNameAuthentication&gt;</span></span>
<span data-ttu-id="a4ade-103">Specifica le credenziali di un servizio in base a nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="a4ade-103">Specifies a service's credentials based on user name and password.</span></span>  
  
 <span data-ttu-id="a4ade-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a4ade-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a4ade-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="a4ade-105">\<behaviors></span></span>  
<span data-ttu-id="a4ade-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a4ade-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="a4ade-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="a4ade-107">\<behavior></span></span>  
<span data-ttu-id="a4ade-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="a4ade-108">\<serviceCredentials></span></span>  
<span data-ttu-id="a4ade-109">\<userNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="a4ade-109">\<userNameAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4ade-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4ade-110">Syntax</span></span>  
  
```xml  
<userNameAuthentication  
   cacheLogonTokenLifetime="TimeSpan"  
   cacheLogonTokens="Boolean"   
   customUserNamePasswordValidatorType="String"  
   includeWindowsGroups="Boolean"   
   maxCacheLogonTokens="Integer"  
   membershipProviderName="String"  
   userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4ade-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a4ade-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a4ade-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a4ade-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4ade-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="a4ade-113">Attributes</span></span>  
  
|<span data-ttu-id="a4ade-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="a4ade-114">Attribute</span></span>|<span data-ttu-id="a4ade-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4ade-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="a4ade-116"><xref:System.TimeSpan> specifica il periodo massimo di tempo durante il quale un token è memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="a4ade-116">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="a4ade-117">L'impostazione predefinita è 00:15:00.</span><span class="sxs-lookup"><span data-stu-id="a4ade-117">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="a4ade-118">Valore booleano che specifica se i token di accesso vengono memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="a4ade-118">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="a4ade-119">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="a4ade-119">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="a4ade-120">Stringa che specifica il tipo di convalida personalizzata della password nome utente da usare.</span><span class="sxs-lookup"><span data-stu-id="a4ade-120">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="a4ade-121">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="a4ade-121">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="a4ade-122">Valore booleano che specifica se i gruppi di Windows sono inclusi nel contesto di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a4ade-122">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="a4ade-123">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="a4ade-123">The default is `true`.</span></span><br /><br /> <span data-ttu-id="a4ade-124">L'impostazione di questo attributo su `true` determina un effetto sulle prestazioni in quanto comporta un'espansione completa del gruppo.</span><span class="sxs-lookup"><span data-stu-id="a4ade-124">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="a4ade-125">Impostare questa proprietà su `false` se non è necessario stabilire l'elenco di gruppi a cui appartiene un utente.</span><span class="sxs-lookup"><span data-stu-id="a4ade-125">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="a4ade-126">Numero intero che specifica il numero massimo di token di accesso da memorizzare nella cache.</span><span class="sxs-lookup"><span data-stu-id="a4ade-126">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="a4ade-127">Questo valore deve essere maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="a4ade-127">This value should be larger than zero.</span></span> <span data-ttu-id="a4ade-128">Il valore predefinito è 128.</span><span class="sxs-lookup"><span data-stu-id="a4ade-128">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="a4ade-129">Quando l'attributo `clientCredentialType` di un'associazione viene impostato su `username`, viene eseguito il mapping del nome utente sugli account di Windows.</span><span class="sxs-lookup"><span data-stu-id="a4ade-129">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="a4ade-130">È possibile eseguire l'override di questo comportamento usando questo attributo, il quale è una stringa che contiene il nome del valore <xref:System.Web.Security.MembershipProvider> che fornisce il meccanismo di convalida della password appropriato.</span><span class="sxs-lookup"><span data-stu-id="a4ade-130">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="a4ade-131">Specifica il modo in cui viene convalidata la password del nome utente.</span><span class="sxs-lookup"><span data-stu-id="a4ade-131">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="a4ade-132">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="a4ade-132">Valid values are:</span></span><br /><br /> <span data-ttu-id="a4ade-133">-Windows</span><span class="sxs-lookup"><span data-stu-id="a4ade-133">-   Windows</span></span><br /><span data-ttu-id="a4ade-134">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="a4ade-134">-   MembershipProvider</span></span><br /><span data-ttu-id="a4ade-135">-Custom</span><span class="sxs-lookup"><span data-stu-id="a4ade-135">-   Custom</span></span><br /><br /> <span data-ttu-id="a4ade-136">L'impostazione predefinita è Windows.</span><span class="sxs-lookup"><span data-stu-id="a4ade-136">The default is Windows.</span></span> <span data-ttu-id="a4ade-137">L'attributo è di tipo <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="a4ade-137">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4ade-138">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a4ade-138">Child Elements</span></span>  
 <span data-ttu-id="a4ade-139">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a4ade-139">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4ade-140">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a4ade-140">Parent Elements</span></span>  
  
|<span data-ttu-id="a4ade-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="a4ade-141">Element</span></span>|<span data-ttu-id="a4ade-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4ade-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4ade-143">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="a4ade-143">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="a4ade-144">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="a4ade-144">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4ade-145">Note</span><span class="sxs-lookup"><span data-stu-id="a4ade-145">Remarks</span></span>  
 <span data-ttu-id="a4ade-146">Se nessuna delle associazioni usate da un servizio viene configurata per l'autenticazione basata su nome utente/password, gli attributi rilevanti per questo elemento vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="a4ade-146">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="a4ade-147">Tali attributi includono `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` e `userNamePasswordValidationMode`.</span><span class="sxs-lookup"><span data-stu-id="a4ade-147">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="a4ade-148">Se nessuna delle associazioni usate da un servizio viene configurata per usare l'autenticazione di Windows per nome utente/password, le impostazioni relative alla memorizzazione nella cache dei token di accesso vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="a4ade-148">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="a4ade-149">Tali impostazioni includono `cacheLogonTokenLifetime`, `cacheLogonTokens` e `maxCacheLogonTokens`.</span><span class="sxs-lookup"><span data-stu-id="a4ade-149">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ade-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4ade-150">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UserNameServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
