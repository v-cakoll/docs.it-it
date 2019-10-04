---
title: Elemento <serviceAuthorization>
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: f476f754a340f52859be2986e42754cba0ef3771
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834014"
---
# <a name="serviceauthorization-element"></a><span data-ttu-id="f1d95-102">elemento > \<serviceAuthorization</span><span class="sxs-lookup"><span data-stu-id="f1d95-102">\<serviceAuthorization> element</span></span>

<span data-ttu-id="f1d95-103">Specifica impostazioni che autorizzano accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="f1d95-103">Specifies settings that authorize access to service operations</span></span>

<span data-ttu-id="f1d95-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f1d95-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f1d95-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f1d95-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f1d95-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<behaviors >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f1d95-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="f1d95-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f1d95-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="f1d95-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0behavior >** ](behavior-of-servicebehaviors.md)1</span><span class="sxs-lookup"><span data-stu-id="f1d95-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\</span></span>
<span data-ttu-id="f1d95-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 **&nbsp;1serviceAuthorization >**</span><span class="sxs-lookup"><span data-stu-id="f1d95-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthorization>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="f1d95-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1d95-110">Syntax</span></span>

```xml
<serviceAuthorization impersonateCallerForAllOperations="Boolean"
                      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"
                      roleProviderName="String"
                      serviceAuthorizationManagerType="String">
  <authorizationPolicies>
    <add policyType="String" />
  </authorizationPolicies>
</serviceAuthorization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f1d95-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f1d95-111">Attributes and elements</span></span>

<span data-ttu-id="f1d95-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre:</span><span class="sxs-lookup"><span data-stu-id="f1d95-112">The following sections describe attributes, child elements, and parent elements:</span></span>

### <a name="attributes"></a><span data-ttu-id="f1d95-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="f1d95-113">Attributes</span></span>

|<span data-ttu-id="f1d95-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="f1d95-114">Attribute</span></span>|<span data-ttu-id="f1d95-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1d95-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f1d95-116">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="f1d95-116">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="f1d95-117">Valore booleano che specifica se tutte le operazioni nel servizio rappresentano il chiamante.</span><span class="sxs-lookup"><span data-stu-id="f1d95-117">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="f1d95-118">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="f1d95-118">The default is `false`.</span></span><br /><br /> <span data-ttu-id="f1d95-119">Quando un'operazione del servizio specifica rappresenta il chiamante, il contesto del thread viene commutato nel contesto del chiamante prima dell'esecuzione del servizio specificato.</span><span class="sxs-lookup"><span data-stu-id="f1d95-119">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="f1d95-120">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="f1d95-120">principalPermissionMode</span></span>|<span data-ttu-id="f1d95-121">Imposta l'entità di sicurezza usata per eseguire operazioni nel server.</span><span class="sxs-lookup"><span data-stu-id="f1d95-121">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="f1d95-122">Sono inclusi i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1d95-122">Values include the following:</span></span><br /><br /> <span data-ttu-id="f1d95-123">-Nessuno</span><span class="sxs-lookup"><span data-stu-id="f1d95-123">-   None</span></span><br /><span data-ttu-id="f1d95-124">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="f1d95-124">-   UseWindowsGroups</span></span><br /><span data-ttu-id="f1d95-125">-UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="f1d95-125">-   UseAspNetRoles</span></span><br /><span data-ttu-id="f1d95-126">-Personalizzato</span><span class="sxs-lookup"><span data-stu-id="f1d95-126">-   Custom</span></span><br /><br /> <span data-ttu-id="f1d95-127">Il valore predefinito è UseWindowsGroups.</span><span class="sxs-lookup"><span data-stu-id="f1d95-127">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="f1d95-128">Il valore è di tipo <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="f1d95-128">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="f1d95-129">Per ulteriori informazioni sull'utilizzo di questo attributo, vedere [How per: Limitare l'accesso con la classe PrincipalPermissionAttribute @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="f1d95-129">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="f1d95-130">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="f1d95-130">roleProviderName</span></span>|<span data-ttu-id="f1d95-131">Una stringa che specifica il nome del provider di ruoli che fornisce informazioni sui ruoli per un'applicazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f1d95-131">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="f1d95-132">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="f1d95-132">The default is an empty string.</span></span>|  
|<span data-ttu-id="f1d95-133">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="f1d95-133">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="f1d95-134">Stringa che contiene il tipo di gestione autorizzazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="f1d95-134">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="f1d95-135">Per altre informazioni, vedere <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="f1d95-135">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="f1d95-136">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f1d95-136">Child elements</span></span>

|<span data-ttu-id="f1d95-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1d95-137">Element</span></span>|<span data-ttu-id="f1d95-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1d95-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f1d95-139">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="f1d95-139">authorizationPolicies</span></span>|<span data-ttu-id="f1d95-140">Contiene una raccolta di tipi di criteri di autorizzazione che possono essere aggiunti mediante la parola chiave `add`.</span><span class="sxs-lookup"><span data-stu-id="f1d95-140">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="f1d95-141">Ciascun criterio di autorizzazione contiene un solo attributo `policyType` obbligatorio che è una stringa.</span><span class="sxs-lookup"><span data-stu-id="f1d95-141">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="f1d95-142">L'attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="f1d95-142">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="f1d95-143">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="f1d95-143">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="f1d95-144">Per altre informazioni, vedere <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="f1d95-144">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  

### <a name="parent-elements"></a><span data-ttu-id="f1d95-145">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f1d95-145">Parent elements</span></span>

|<span data-ttu-id="f1d95-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1d95-146">Element</span></span>|<span data-ttu-id="f1d95-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1d95-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1d95-148">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f1d95-148">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="f1d95-149">Contiene una raccolta di impostazioni per il comportamento di un servizio.</span><span class="sxs-lookup"><span data-stu-id="f1d95-149">Contains a collection of settings for the behavior of a service.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="f1d95-150">Note</span><span class="sxs-lookup"><span data-stu-id="f1d95-150">Remarks</span></span>

<span data-ttu-id="f1d95-151">Questa sezione contiene elementi che influiscono su autorizzazioni, provider del ruolo personalizzati e rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="f1d95-151">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
<span data-ttu-id="f1d95-152">L'attributo `principalPermissionMode` specifica i gruppi di utenti da usare quando si autorizza l'uso di un metodo protetto.</span><span class="sxs-lookup"><span data-stu-id="f1d95-152">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="f1d95-153">Il valore predefinito è `UseWindowsGroups` e specifica che la ricerca degli ID che tentano di accedere a una determinata risorsa viene eseguita nei gruppi di Windows, ad esempio "Administrators" o "Users".</span><span class="sxs-lookup"><span data-stu-id="f1d95-153">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="f1d95-154">È anche possibile specificare `UseAspNetRoles` per usare un provider di ruoli personalizzato configurato nell'elemento > di @no__t -1system. Web, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f1d95-154">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code:</span></span>

```xml
<system.web>
  <membership defaultProvider="SqlProvider"
              userIsOnlineTimeWindow="15">
    <providers>
      <clear />
      <add name="SqlProvider"
           type="System.Web.Security.SqlMembershipProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipProvider"
           enablePasswordRetrieval="false"
           enablePasswordReset="false"
           requiresQuestionAndAnswer="false"
           requiresUniqueEmail="true"
           passwordFormat="Hashed" />
    </providers>
  </membership>
  <!-- Other configuration code not shown. -->
</system.web>
```
  
<span data-ttu-id="f1d95-155">Il codice seguente mostra il `roleProviderName` usato con l'attributo `principalPermissionMode`:</span><span class="sxs-lookup"><span data-stu-id="f1d95-155">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute:</span></span>
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

<span data-ttu-id="f1d95-156">Per un esempio dettagliato dell'uso di questo elemento di configurazione, vedere [autorizzazione dell'accesso alle operazioni del servizio](../../../wcf/samples/authorizing-access-to-service-operations.md) e ai [criteri di autorizzazione](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f1d95-156">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f1d95-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1d95-157">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="f1d95-158">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f1d95-158">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f1d95-159">Autorizzazione dell'accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="f1d95-159">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- <span data-ttu-id="f1d95-160">[Procedura: Creare un gestore autorizzazioni personalizzato per un servizio @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="f1d95-160">[How to: Create a Custom Authorization Manager for a Service](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)</span></span>
- <span data-ttu-id="f1d95-161">[Procedura: Limitazione dell'accesso con la classe PrincipalPermissionAttribute @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="f1d95-161">[How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)</span></span>
- [<span data-ttu-id="f1d95-162">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="f1d95-162">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
