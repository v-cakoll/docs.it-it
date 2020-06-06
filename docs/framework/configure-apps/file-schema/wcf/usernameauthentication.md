---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: dc5c00a2204646863ae2570bb97b8d70e22a72d4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399194"
---
# \<userNameAuthentication>
<span data-ttu-id="402e1-101">Specifica le credenziali di un servizio in base a nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="402e1-101">Specifies a service's credentials based on user name and password.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="402e1-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="402e1-102">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="402e1-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="402e1-103">Attributes and Elements</span></span>  
 <span data-ttu-id="402e1-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="402e1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="402e1-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="402e1-105">Attributes</span></span>  
  
|<span data-ttu-id="402e1-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="402e1-106">Attribute</span></span>|<span data-ttu-id="402e1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="402e1-107">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="402e1-108"><xref:System.TimeSpan> specifica il periodo massimo di tempo durante il quale un token è memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="402e1-108">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="402e1-109">L'impostazione predefinita è 00:15:00.</span><span class="sxs-lookup"><span data-stu-id="402e1-109">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="402e1-110">Valore booleano che specifica se i token di accesso vengono memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="402e1-110">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="402e1-111">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="402e1-111">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="402e1-112">Stringa che specifica il tipo di convalida personalizzata della password nome utente da usare.</span><span class="sxs-lookup"><span data-stu-id="402e1-112">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="402e1-113">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="402e1-113">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="402e1-114">Valore booleano che specifica se i gruppi di Windows sono inclusi nel contesto di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="402e1-114">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="402e1-115">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="402e1-115">The default is `true`.</span></span><br /><br /> <span data-ttu-id="402e1-116">L'impostazione di questo attributo su `true` determina un effetto sulle prestazioni in quanto comporta un'espansione completa del gruppo.</span><span class="sxs-lookup"><span data-stu-id="402e1-116">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="402e1-117">Impostare questa proprietà su `false` se non è necessario stabilire l'elenco di gruppi a cui appartiene un utente.</span><span class="sxs-lookup"><span data-stu-id="402e1-117">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="402e1-118">Numero intero che specifica il numero massimo di token di accesso da memorizzare nella cache.</span><span class="sxs-lookup"><span data-stu-id="402e1-118">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="402e1-119">Questo valore deve essere maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="402e1-119">This value should be larger than zero.</span></span> <span data-ttu-id="402e1-120">Il valore predefinito è 128.</span><span class="sxs-lookup"><span data-stu-id="402e1-120">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="402e1-121">Quando l'attributo `clientCredentialType` di un'associazione viene impostato su `username`, viene eseguito il mapping del nome utente sugli account di Windows.</span><span class="sxs-lookup"><span data-stu-id="402e1-121">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="402e1-122">È possibile eseguire l'override di questo comportamento usando questo attributo, il quale è una stringa che contiene il nome del valore <xref:System.Web.Security.MembershipProvider> che fornisce il meccanismo di convalida della password appropriato.</span><span class="sxs-lookup"><span data-stu-id="402e1-122">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="402e1-123">Specifica il modo in cui viene convalidata la password del nome utente.</span><span class="sxs-lookup"><span data-stu-id="402e1-123">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="402e1-124">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="402e1-124">Valid values are:</span></span><br /><br /> <span data-ttu-id="402e1-125">-Windows</span><span class="sxs-lookup"><span data-stu-id="402e1-125">-   Windows</span></span><br /><span data-ttu-id="402e1-126">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="402e1-126">-   MembershipProvider</span></span><br /><span data-ttu-id="402e1-127">-Personalizzato</span><span class="sxs-lookup"><span data-stu-id="402e1-127">-   Custom</span></span><br /><br /> <span data-ttu-id="402e1-128">L'impostazione predefinita è Windows.</span><span class="sxs-lookup"><span data-stu-id="402e1-128">The default is Windows.</span></span> <span data-ttu-id="402e1-129">L'attributo è di tipo <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="402e1-129">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="402e1-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="402e1-130">Child Elements</span></span>  
 <span data-ttu-id="402e1-131">No.</span><span class="sxs-lookup"><span data-stu-id="402e1-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="402e1-132">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="402e1-132">Parent Elements</span></span>  
  
|<span data-ttu-id="402e1-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="402e1-133">Element</span></span>|<span data-ttu-id="402e1-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="402e1-134">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="402e1-135">Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.</span><span class="sxs-lookup"><span data-stu-id="402e1-135">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="402e1-136">Commenti</span><span class="sxs-lookup"><span data-stu-id="402e1-136">Remarks</span></span>  
 <span data-ttu-id="402e1-137">Se nessuna delle associazioni usate da un servizio viene configurata per l'autenticazione basata su nome utente/password, gli attributi rilevanti per questo elemento vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="402e1-137">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="402e1-138">Tali attributi includono `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` e `userNamePasswordValidationMode`.</span><span class="sxs-lookup"><span data-stu-id="402e1-138">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="402e1-139">Se nessuna delle associazioni usate da un servizio viene configurata per usare l'autenticazione di Windows per nome utente/password, le impostazioni relative alla memorizzazione nella cache dei token di accesso vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="402e1-139">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="402e1-140">Tali impostazioni includono `cacheLogonTokenLifetime`, `cacheLogonTokens` e `maxCacheLogonTokens`.</span><span class="sxs-lookup"><span data-stu-id="402e1-140">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="402e1-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="402e1-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
