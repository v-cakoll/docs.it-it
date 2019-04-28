---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 5a4cf8d429198b889f2bb362294ba3841c814b26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788700"
---
# <a name="usernameauthentication"></a><span data-ttu-id="9c26e-101">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="9c26e-101">\<userNameAuthentication></span></span>
<span data-ttu-id="9c26e-102">Specifica le credenziali di un servizio in base a nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="9c26e-102">Specifies a service's credentials based on user name and password.</span></span>  
  
 <span data-ttu-id="9c26e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9c26e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="9c26e-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="9c26e-104">\<behaviors></span></span>  
<span data-ttu-id="9c26e-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9c26e-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="9c26e-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9c26e-106">\<behavior></span></span>  
<span data-ttu-id="9c26e-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="9c26e-107">\<serviceCredentials></span></span>  
<span data-ttu-id="9c26e-108">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="9c26e-108">\<userNameAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c26e-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c26e-109">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c26e-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9c26e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9c26e-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9c26e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c26e-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="9c26e-112">Attributes</span></span>  
  
|<span data-ttu-id="9c26e-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="9c26e-113">Attribute</span></span>|<span data-ttu-id="9c26e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c26e-114">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="9c26e-115"><xref:System.TimeSpan> specifica il periodo massimo di tempo durante il quale un token è memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="9c26e-115">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="9c26e-116">L'impostazione predefinita è 00:15:00.</span><span class="sxs-lookup"><span data-stu-id="9c26e-116">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="9c26e-117">Valore booleano che specifica se i token di accesso vengono memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="9c26e-117">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="9c26e-118">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="9c26e-118">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="9c26e-119">Stringa che specifica il tipo di convalida personalizzata della password nome utente da usare.</span><span class="sxs-lookup"><span data-stu-id="9c26e-119">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="9c26e-120">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="9c26e-120">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="9c26e-121">Valore booleano che specifica se i gruppi di Windows sono inclusi nel contesto di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9c26e-121">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="9c26e-122">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="9c26e-122">The default is `true`.</span></span><br /><br /> <span data-ttu-id="9c26e-123">L'impostazione di questo attributo su `true` determina un effetto sulle prestazioni in quanto comporta un'espansione completa del gruppo.</span><span class="sxs-lookup"><span data-stu-id="9c26e-123">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="9c26e-124">Impostare questa proprietà su `false` se non è necessario stabilire l'elenco di gruppi a cui appartiene un utente.</span><span class="sxs-lookup"><span data-stu-id="9c26e-124">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="9c26e-125">Numero intero che specifica il numero massimo di token di accesso da memorizzare nella cache.</span><span class="sxs-lookup"><span data-stu-id="9c26e-125">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="9c26e-126">Questo valore deve essere maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="9c26e-126">This value should be larger than zero.</span></span> <span data-ttu-id="9c26e-127">Il valore predefinito è 128.</span><span class="sxs-lookup"><span data-stu-id="9c26e-127">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="9c26e-128">Quando l'attributo `clientCredentialType` di un'associazione viene impostato su `username`, viene eseguito il mapping del nome utente sugli account di Windows.</span><span class="sxs-lookup"><span data-stu-id="9c26e-128">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="9c26e-129">È possibile eseguire l'override di questo comportamento usando questo attributo, il quale è una stringa che contiene il nome del valore <xref:System.Web.Security.MembershipProvider> che fornisce il meccanismo di convalida della password appropriato.</span><span class="sxs-lookup"><span data-stu-id="9c26e-129">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="9c26e-130">Specifica il modo in cui viene convalidata la password del nome utente.</span><span class="sxs-lookup"><span data-stu-id="9c26e-130">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="9c26e-131">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="9c26e-131">Valid values are:</span></span><br /><br /> <span data-ttu-id="9c26e-132">-   Windows</span><span class="sxs-lookup"><span data-stu-id="9c26e-132">-   Windows</span></span><br /><span data-ttu-id="9c26e-133">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="9c26e-133">-   MembershipProvider</span></span><br /><span data-ttu-id="9c26e-134">-Custom</span><span class="sxs-lookup"><span data-stu-id="9c26e-134">-   Custom</span></span><br /><br /> <span data-ttu-id="9c26e-135">L'impostazione predefinita è Windows.</span><span class="sxs-lookup"><span data-stu-id="9c26e-135">The default is Windows.</span></span> <span data-ttu-id="9c26e-136">L'attributo è di tipo <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="9c26e-136">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c26e-137">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9c26e-137">Child Elements</span></span>  
 <span data-ttu-id="9c26e-138">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9c26e-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c26e-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9c26e-139">Parent Elements</span></span>  
  
|<span data-ttu-id="9c26e-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c26e-140">Element</span></span>|<span data-ttu-id="9c26e-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9c26e-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c26e-142">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="9c26e-142">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="9c26e-143">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="9c26e-143">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c26e-144">Note</span><span class="sxs-lookup"><span data-stu-id="9c26e-144">Remarks</span></span>  
 <span data-ttu-id="9c26e-145">Se nessuna delle associazioni usate da un servizio viene configurata per l'autenticazione basata su nome utente/password, gli attributi rilevanti per questo elemento vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="9c26e-145">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="9c26e-146">Tali attributi includono `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` e `userNamePasswordValidationMode`.</span><span class="sxs-lookup"><span data-stu-id="9c26e-146">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="9c26e-147">Se nessuna delle associazioni usate da un servizio viene configurata per usare l'autenticazione di Windows per nome utente/password, le impostazioni relative alla memorizzazione nella cache dei token di accesso vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="9c26e-147">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="9c26e-148">Tali impostazioni includono `cacheLogonTokenLifetime`, `cacheLogonTokens` e `maxCacheLogonTokens`.</span><span class="sxs-lookup"><span data-stu-id="9c26e-148">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c26e-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c26e-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
