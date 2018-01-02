---
title: Elemento &lt;serviceAuthorization&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9572cea14b7c15893459133aa75e9fa62b10d4f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltserviceauthorizationgt-element"></a><span data-ttu-id="b31fa-102">Elemento &lt;serviceAuthorization&gt;</span><span class="sxs-lookup"><span data-stu-id="b31fa-102">&lt;serviceAuthorization&gt; element</span></span>
<span data-ttu-id="b31fa-103">Specifica impostazioni che autorizzano accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="b31fa-103">Specifies settings that authorize access to service operations</span></span>  
  
 <span data-ttu-id="b31fa-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b31fa-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b31fa-105">\<i comportamenti ></span><span class="sxs-lookup"><span data-stu-id="b31fa-105">\<behaviors></span></span>  
<span data-ttu-id="b31fa-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="b31fa-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b31fa-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="b31fa-107">\<behavior></span></span>  
<span data-ttu-id="b31fa-108">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="b31fa-108">\<serviceAuthorization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b31fa-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b31fa-109">Syntax</span></span>  
  
```xml  
<serviceAuthorization  
     impersonateCallerForAllOperations="Boolean"  
      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"  
      roleProviderName="String"  
      serviceAuthorizationManagerType="String" />  
      <authorizationPolicies>  
         <add policyType="String" />  
      </authorizationPolicies>  
</serviceAuthorization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b31fa-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="b31fa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b31fa-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="b31fa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b31fa-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="b31fa-112">Attributes</span></span>  
  
|<span data-ttu-id="b31fa-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="b31fa-113">Attribute</span></span>|<span data-ttu-id="b31fa-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b31fa-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b31fa-115">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="b31fa-115">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="b31fa-116">Valore booleano che specifica se tutte le operazioni nel servizio rappresentano il chiamante.</span><span class="sxs-lookup"><span data-stu-id="b31fa-116">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="b31fa-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="b31fa-117">The default is `false`.</span></span><br /><br /> <span data-ttu-id="b31fa-118">Quando un'operazione del servizio specifica rappresenta il chiamante, il contesto del thread viene commutato nel contesto del chiamante prima dell'esecuzione del servizio specificato.</span><span class="sxs-lookup"><span data-stu-id="b31fa-118">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="b31fa-119">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="b31fa-119">principalPermissionMode</span></span>|<span data-ttu-id="b31fa-120">Imposta l'entità di sicurezza usata per eseguire operazioni nel server.</span><span class="sxs-lookup"><span data-stu-id="b31fa-120">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="b31fa-121">Sono inclusi i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b31fa-121">Values include the following:</span></span><br /><br /> <span data-ttu-id="b31fa-122">-Nessuno</span><span class="sxs-lookup"><span data-stu-id="b31fa-122">-   None</span></span><br /><span data-ttu-id="b31fa-123">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="b31fa-123">-   UseWindowsGroups</span></span><br /><span data-ttu-id="b31fa-124">-UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="b31fa-124">-   UseAspNetRoles</span></span><br /><span data-ttu-id="b31fa-125">-Custom</span><span class="sxs-lookup"><span data-stu-id="b31fa-125">-   Custom</span></span><br /><br /> <span data-ttu-id="b31fa-126">Il valore predefinito è UseWindowsGroups.</span><span class="sxs-lookup"><span data-stu-id="b31fa-126">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="b31fa-127">Il valore è di tipo <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="b31fa-127">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="b31fa-128">Per ulteriori informazioni sull'utilizzo di questo attributo, vedere [procedura: limitare l'accesso con la classe PrincipalPermissionAttribute](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="b31fa-128">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="b31fa-129">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="b31fa-129">roleProviderName</span></span>|<span data-ttu-id="b31fa-130">Una stringa che specifica il nome del provider di ruoli che fornisce informazioni sui ruoli per un'applicazione di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="b31fa-130">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="b31fa-131">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="b31fa-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="b31fa-132">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="b31fa-132">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="b31fa-133">Stringa che contiene il tipo di gestione autorizzazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="b31fa-133">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="b31fa-134">Per altre informazioni, vedere <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="b31fa-134">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b31fa-135">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b31fa-135">Child Elements</span></span>  
  
|<span data-ttu-id="b31fa-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="b31fa-136">Element</span></span>|<span data-ttu-id="b31fa-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b31fa-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b31fa-138">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="b31fa-138">authorizationPolicies</span></span>|<span data-ttu-id="b31fa-139">Contiene una raccolta di tipi di criteri di autorizzazione che possono essere aggiunti mediante la parola chiave `add`.</span><span class="sxs-lookup"><span data-stu-id="b31fa-139">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="b31fa-140">Ciascun criterio di autorizzazione contiene un solo attributo `policyType` obbligatorio che è una stringa.</span><span class="sxs-lookup"><span data-stu-id="b31fa-140">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="b31fa-141">L'attributo specifica un criterio di autorizzazione che consente la trasformazione di un set di attestazioni di input in un altro set di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="b31fa-141">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="b31fa-142">Su questa base può essere concesso o negato il controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="b31fa-142">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="b31fa-143">Per altre informazioni, vedere <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="b31fa-143">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b31fa-144">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b31fa-144">Parent Elements</span></span>  
  
|<span data-ttu-id="b31fa-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="b31fa-145">Element</span></span>|<span data-ttu-id="b31fa-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b31fa-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b31fa-147">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="b31fa-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="b31fa-148">Contiene una raccolta di impostazioni per il comportamento di un servizio.</span><span class="sxs-lookup"><span data-stu-id="b31fa-148">Contains a collection of settings for the behavior of a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b31fa-149">Note</span><span class="sxs-lookup"><span data-stu-id="b31fa-149">Remarks</span></span>  
 <span data-ttu-id="b31fa-150">Questa sezione contiene elementi che influiscono su autorizzazioni, provider del ruolo personalizzati e rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="b31fa-150">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
 <span data-ttu-id="b31fa-151">L'attributo `principalPermissionMode` specifica i gruppi di utenti da usare quando si autorizza l'uso di un metodo protetto.</span><span class="sxs-lookup"><span data-stu-id="b31fa-151">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="b31fa-152">Il valore predefinito è `UseWindowsGroups` e specifica che la ricerca degli ID che tentano di accedere a una determinata risorsa viene eseguita nei gruppi di Windows, ad esempio "Administrators" o "Users".</span><span class="sxs-lookup"><span data-stu-id="b31fa-152">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="b31fa-153">È inoltre possibile specificare `UseAspNetRoles` per utilizzare un provider di ruoli personalizzato configurato nel \<System. Web > elemento, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b31fa-153">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code.</span></span>  
  
```xml  
<system.web>  
  <membership defaultProvider="SqlProvider"   
   userIsOnlineTimeWindow="15">  
     <providers>  
       <clear />  
       <add   
          name="SqlProvider"   
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
  <!-- Other configuration code not shown.-->  
</system.web>  
```  
  
 <span data-ttu-id="b31fa-154">Nell'esempio di codice seguente viene illustrato l'uso di un elemento `roleProviderName` con l'attributo `principalPermissionMode`.</span><span class="sxs-lookup"><span data-stu-id="b31fa-154">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute.</span></span>  
  
```xml  
<behaviors>  
   <behavior name="ServiceBehaviour">  
     <serviceAuthorization principalPermissionMode ="UseAspNetRoles"   
                           roleProviderName ="SqlProvider" />  
   </behavior>   
<!-- Other configuration code not shown. -->  
</behaviors>  
```  
  
 <span data-ttu-id="b31fa-155">Per un esempio dettagliato dell'utilizzo di questo elemento di configurazione, vedere [autorizzare l'accesso alle operazioni del servizio](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) e [criteri di autorizzazione](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b31fa-155">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b31fa-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b31fa-156">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 [<span data-ttu-id="b31fa-157">Comportamenti di sicurezza</span><span class="sxs-lookup"><span data-stu-id="b31fa-157">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="b31fa-158">Autorizzazione dell'accesso alle operazioni del servizio</span><span class="sxs-lookup"><span data-stu-id="b31fa-158">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="b31fa-159">Procedura: Creare un gestore autorizzazioni personalizzato per un servizio</span><span class="sxs-lookup"><span data-stu-id="b31fa-159">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [<span data-ttu-id="b31fa-160">Procedura: Limitare l'accesso con la classe PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="b31fa-160">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 [<span data-ttu-id="b31fa-161">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="b31fa-161">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)
