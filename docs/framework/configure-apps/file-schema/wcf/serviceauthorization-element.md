---
title: Elemento <serviceAuthorization>
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: f476f754a340f52859be2986e42754cba0ef3771
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "71834014"
---
# <a name="serviceauthorization-element"></a><span data-ttu-id="fc8f1-102">Elemento \<serviceAuthorization></span><span class="sxs-lookup"><span data-stu-id="fc8f1-102">\<serviceAuthorization> element</span></span>

<span data-ttu-id="fc8f1-103">Specifica impostazioni che autorizzano accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="fc8f1-103">Specifies settings that authorize access to service operations</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthorization>**  

## <a name="syntax"></a><span data-ttu-id="fc8f1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc8f1-104">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="fc8f1-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fc8f1-105">Attributes and elements</span></span>

<span data-ttu-id="fc8f1-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre:</span><span class="sxs-lookup"><span data-stu-id="fc8f1-106">The following sections describe attributes, child elements, and parent elements:</span></span>

### <a name="attributes"></a><span data-ttu-id="fc8f1-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="fc8f1-107">Attributes</span></span>

|<span data-ttu-id="fc8f1-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="fc8f1-108">Attribute</span></span>|<span data-ttu-id="fc8f1-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc8f1-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc8f1-110">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="fc8f1-110">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="fc8f1-111">Valore booleano che specifica se tutte le operazioni nel servizio rappresentano il chiamante.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-111">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="fc8f1-112">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-112">The default is `false`.</span></span><br /><br /> <span data-ttu-id="fc8f1-113">Quando un'operazione del servizio specifica rappresenta il chiamante, il contesto del thread viene commutato nel contesto del chiamante prima dell'esecuzione del servizio specificato.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-113">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="fc8f1-114">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="fc8f1-114">principalPermissionMode</span></span>|<span data-ttu-id="fc8f1-115">Imposta l'entità di sicurezza usata per eseguire operazioni nel server.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-115">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="fc8f1-116">Sono inclusi i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc8f1-116">Values include the following:</span></span><br /><br /> <span data-ttu-id="fc8f1-117">-Nessuno</span><span class="sxs-lookup"><span data-stu-id="fc8f1-117">-   None</span></span><br /><span data-ttu-id="fc8f1-118">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="fc8f1-118">-   UseWindowsGroups</span></span><br /><span data-ttu-id="fc8f1-119">-UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="fc8f1-119">-   UseAspNetRoles</span></span><br /><span data-ttu-id="fc8f1-120">-Personalizzato</span><span class="sxs-lookup"><span data-stu-id="fc8f1-120">-   Custom</span></span><br /><br /> <span data-ttu-id="fc8f1-121">Il valore predefinito è UseWindowsGroups.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-121">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="fc8f1-122">Il valore è di tipo <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-122">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="fc8f1-123">Per altre informazioni sull'uso di questo attributo, vedere [procedura: limitare l'accesso con la classe PrincipalPermissionAttribute](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="fc8f1-123">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="fc8f1-124">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="fc8f1-124">roleProviderName</span></span>|<span data-ttu-id="fc8f1-125">Una stringa che specifica il nome del provider di ruoli che fornisce informazioni sui ruoli per un'applicazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fc8f1-125">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="fc8f1-126">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="fc8f1-127">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="fc8f1-127">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="fc8f1-128">Stringa che contiene il tipo di gestione autorizzazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-128">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="fc8f1-129">Per altre informazioni, vedere <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-129">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  

### <a name="child-elements"></a><span data-ttu-id="fc8f1-130">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fc8f1-130">Child elements</span></span>

|<span data-ttu-id="fc8f1-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc8f1-131">Element</span></span>|<span data-ttu-id="fc8f1-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc8f1-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc8f1-133">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="fc8f1-133">authorizationPolicies</span></span>|<span data-ttu-id="fc8f1-134">Contiene una raccolta di tipi di criteri di autorizzazione che possono essere aggiunti mediante la parola chiave `add`.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-134">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="fc8f1-135">Ciascun criterio di autorizzazione contiene un solo attributo `policyType` obbligatorio che è una stringa.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-135">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="fc8f1-136">L'attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-136">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="fc8f1-137">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-137">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="fc8f1-138">Per altre informazioni, vedere <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-138">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  

### <a name="parent-elements"></a><span data-ttu-id="fc8f1-139">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fc8f1-139">Parent elements</span></span>

|<span data-ttu-id="fc8f1-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc8f1-140">Element</span></span>|<span data-ttu-id="fc8f1-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc8f1-141">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="fc8f1-142">Contiene una raccolta di impostazioni per il comportamento di un servizio.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-142">Contains a collection of settings for the behavior of a service.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="fc8f1-143">Commenti</span><span class="sxs-lookup"><span data-stu-id="fc8f1-143">Remarks</span></span>

<span data-ttu-id="fc8f1-144">Questa sezione contiene elementi che influiscono su autorizzazioni, provider del ruolo personalizzati e rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-144">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
<span data-ttu-id="fc8f1-145">L'attributo `principalPermissionMode` specifica i gruppi di utenti da usare quando si autorizza l'uso di un metodo protetto.</span><span class="sxs-lookup"><span data-stu-id="fc8f1-145">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="fc8f1-146">Il valore predefinito è `UseWindowsGroups` e specifica che la ricerca degli ID che tentano di accedere a una determinata risorsa viene eseguita nei gruppi di Windows, ad esempio "Administrators" o "Users".</span><span class="sxs-lookup"><span data-stu-id="fc8f1-146">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="fc8f1-147">È inoltre possibile specificare l' `UseAspNetRoles` utilizzo di un provider di ruoli personalizzato configurato nell' \<system.web> elemento, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fc8f1-147">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code:</span></span>

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
  
<span data-ttu-id="fc8f1-148">Il codice seguente illustra l'oggetto `roleProviderName` usato con l' `principalPermissionMode` attributo:</span><span class="sxs-lookup"><span data-stu-id="fc8f1-148">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute:</span></span>
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

<span data-ttu-id="fc8f1-149">Per un esempio dettagliato dell'uso di questo elemento di configurazione, vedere [autorizzazione dell'accesso alle operazioni del servizio](../../../wcf/samples/authorizing-access-to-service-operations.md) e ai [criteri di autorizzazione](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="fc8f1-149">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fc8f1-150">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="fc8f1-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [<span data-ttu-id="fc8f1-151">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="fc8f1-151">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="fc8f1-152">Autorizzazione dell'accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="fc8f1-152">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="fc8f1-153">Procedura: Creare un gestore autorizzazioni personalizzato per un servizio</span><span class="sxs-lookup"><span data-stu-id="fc8f1-153">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="fc8f1-154">Procedura: Limitare l'accesso con la classe PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="fc8f1-154">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [<span data-ttu-id="fc8f1-155">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="fc8f1-155">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
