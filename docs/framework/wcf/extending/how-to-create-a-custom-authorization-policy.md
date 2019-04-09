---
title: 'Procedura: Creare un criterio di autorizzazione personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 05b0549b-882d-4660-b6f0-5678543e5475
ms.openlocfilehash: 78cc77a5491e50d718a53efff1c6f99acf23cf27
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115388"
---
# <a name="how-to-create-a-custom-authorization-policy"></a><span data-ttu-id="1df79-102">Procedura: Creare un criterio di autorizzazione personalizzato</span><span class="sxs-lookup"><span data-stu-id="1df79-102">How to: Create a Custom Authorization Policy</span></span>
<span data-ttu-id="1df79-103">L'infrastruttura del modello di identità in Windows Communication Foundation (WCF) supporta un modello di autorizzazione basata sulle attestazioni.</span><span class="sxs-lookup"><span data-stu-id="1df79-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) supports a claim-based authorization model.</span></span> <span data-ttu-id="1df79-104">Le attestazioni vengono estratte dai token, elaborate facoltativamente dal criterio di autorizzazione personalizzato e poi collocate nella classe <xref:System.IdentityModel.Policy.AuthorizationContext> che può quindi essere esaminata per prendere decisioni in merito alle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="1df79-104">Claims are extracted from tokens, optionally processed by custom authorization policy, and then placed into an <xref:System.IdentityModel.Policy.AuthorizationContext> that can then be examined to make authorization decisions.</span></span> <span data-ttu-id="1df79-105">È possibile utilizzare un criterio personalizzato per trasformare le attestazioni ottenute dai token in ingresso in attestazioni previste dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1df79-105">A custom policy can be used to transform claims from incoming tokens into claims expected by the application.</span></span> <span data-ttu-id="1df79-106">In questo modo, il livello dell'applicazione può essere isolato dai dettagli alle differenti attestazioni fornite dai diversi tipi di token supportati da WCF.</span><span class="sxs-lookup"><span data-stu-id="1df79-106">In this way, the application layer can be insulated from the details on the differing claims served up by the different token types that WCF supports.</span></span> <span data-ttu-id="1df79-107">In questo argomento viene illustrato come implementare un criterio di autorizzazione personalizzato e come aggiungerlo alla raccolta di criteri utilizzati da un servizio.</span><span class="sxs-lookup"><span data-stu-id="1df79-107">This topic shows how to implement a custom authorization policy and how to add that policy to the collection of policies used by a service.</span></span>  
  
### <a name="to-implement-a-custom-authorization-policy"></a><span data-ttu-id="1df79-108">Per implementare un criterio di autorizzazione personalizzato</span><span class="sxs-lookup"><span data-stu-id="1df79-108">To implement a custom authorization policy</span></span>  
  
1.  <span data-ttu-id="1df79-109">Definire una nuova classe che deriva dall'interfaccia <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span><span class="sxs-lookup"><span data-stu-id="1df79-109">Define a new class that derives from <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>  
  
2.  <span data-ttu-id="1df79-110">Implementare la proprietà di sola lettura <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> generando una stringa univoca nel costruttore per la classe e restituendo tale stringa ogni volta che viene eseguito l'accesso alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="1df79-110">Implement the read-only <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> property by generating a unique string in the constructor for the class and returning that string whenever the property is accessed.</span></span>  
  
3.  <span data-ttu-id="1df79-111">Implementare la proprietà di sola lettura <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A> restituendo una classe <xref:System.IdentityModel.Claims.ClaimSet> che rappresenta l'emittente del criterio.</span><span class="sxs-lookup"><span data-stu-id="1df79-111">Implement the read-only <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A> property by returning a <xref:System.IdentityModel.Claims.ClaimSet> that represents the policy issuer.</span></span> <span data-ttu-id="1df79-112">Può trattarsi di una classe `ClaimSet` che rappresenta l'applicazione o di una classe `ClaimSet` incorporata (ad esempio, la classe `ClaimSet` restituita dalla proprietà statica <xref:System.IdentityModel.Claims.ClaimSet.System%2A>.</span><span class="sxs-lookup"><span data-stu-id="1df79-112">This could be a `ClaimSet` that represents the application or a built-in `ClaimSet` (for example, the `ClaimSet` returned by the static <xref:System.IdentityModel.Claims.ClaimSet.System%2A> property.</span></span>  
  
4.  <span data-ttu-id="1df79-113">Implementare il metodo <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> come descritto nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="1df79-113">Implement the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method as described in the following procedure.</span></span>  
  
### <a name="to-implement-the-evaluate-method"></a><span data-ttu-id="1df79-114">Per implementare il metodo Evaluate</span><span class="sxs-lookup"><span data-stu-id="1df79-114">To implement the Evaluate method</span></span>  
  
1.  <span data-ttu-id="1df79-115">A questo metodo vengono passati due parametri: un'istanza della classe <xref:System.IdentityModel.Policy.EvaluationContext> e un riferimento all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="1df79-115">Two parameters are passed to this method: an instance of the <xref:System.IdentityModel.Policy.EvaluationContext> class and an object reference.</span></span>  
  
2.  <span data-ttu-id="1df79-116">Se il criterio di autorizzazione personalizzato aggiunge <xref:System.IdentityModel.Claims.ClaimSet> istanze indipendentemente dal contenuto corrente del <xref:System.IdentityModel.Policy.EvaluationContext>, aggiungere ogni `ClaimSet` chiamando il <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> metodo e restituire `true` dal <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="1df79-116">If the custom authorization policy adds <xref:System.IdentityModel.Claims.ClaimSet> instances without regard to the current content of the <xref:System.IdentityModel.Policy.EvaluationContext>, then add each `ClaimSet` by calling the <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> method and return `true` from the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> method.</span></span> <span data-ttu-id="1df79-117">La restituzione di `true` indica all'infrastruttura di autorizzazione che il criterio di autorizzazione ha eseguito la sua funzione e che non occorre chiamarlo nuovamente.</span><span class="sxs-lookup"><span data-stu-id="1df79-117">Returning `true` indicates to the authorization infrastructure that the authorization policy has performed its work and does not need to be called again.</span></span>  
  
3.  <span data-ttu-id="1df79-118">Se il criterio di autorizzazione personalizzato aggiunge set di attestazioni solo quando determinate attestazioni sono già presenti in `EvaluationContext`, ricercare tali attestazioni esaminando le istanze di `ClaimSet` restituite dalla proprietà <xref:System.IdentityModel.Policy.EvaluationContext.ClaimSets%2A>.</span><span class="sxs-lookup"><span data-stu-id="1df79-118">If the custom authorization policy adds claim sets only if certain claims are already present in the `EvaluationContext`, then look for those claims by examining the `ClaimSet` instances returned by the <xref:System.IdentityModel.Policy.EvaluationContext.ClaimSets%2A> property.</span></span> <span data-ttu-id="1df79-119">Se le attestazioni sono presenti, aggiungere i nuovi set di attestazioni chiamando il metodo <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> e, se non devono essere aggiunti altri set di attestazioni, restituire `true` per indicare all'infrastruttura di autorizzazione che il criterio di autorizzazione ha completato la sua funzione.</span><span class="sxs-lookup"><span data-stu-id="1df79-119">If the claims are present, then add the new claim sets by calling the <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> method and, if no more claim sets are to be added, return `true`, indicating to the authorization infrastructure that the authorization policy has completed its work.</span></span> <span data-ttu-id="1df79-120">Se le attestazioni non sono presenti, restituire `false` per indicare che il criterio di autorizzazione deve essere chiamato nuovamente nel caso in cui altri criteri di autorizzazione aggiungano altri set di attestazioni a `EvaluationContext`.</span><span class="sxs-lookup"><span data-stu-id="1df79-120">If the claims are not present, return `false`, indicating that the authorization policy should be called again if other authorization policies add more claim sets to the `EvaluationContext`.</span></span>  
  
4.  <span data-ttu-id="1df79-121">Negli scenari di elaborazione più complessi, si utilizza il secondo parametro del metodo <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> per archiviare una variabile di stato che l'infrastruttura di autorizzazione passerà nuovamente durante ogni chiamata successiva al metodo <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> per una particolare valutazione.</span><span class="sxs-lookup"><span data-stu-id="1df79-121">In more complex processing scenarios, the second parameter of the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method is used to store a state variable that the authorization infrastructure will pass back during each subsequent call to the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method for a particular evaluation.</span></span>  
  
### <a name="to-specify-a-custom-authorization-policy-through-configuration"></a><span data-ttu-id="1df79-122">Per specificare un criterio di autorizzazione personalizzato tramite configurazione</span><span class="sxs-lookup"><span data-stu-id="1df79-122">To specify a custom authorization policy through configuration</span></span>  
  
1.  <span data-ttu-id="1df79-123">Specificare il tipo del criterio di autorizzazione personalizzato nell'attributo `policyType` dell'elemento `add` dell'elemento `authorizationPolicies` dell'elemento `serviceAuthorization`.</span><span class="sxs-lookup"><span data-stu-id="1df79-123">Specify the type of the custom authorization policy in the `policyType` attribute in the `add` element in the `authorizationPolicies` element in the `serviceAuthorization` element.</span></span>  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
        <serviceAuthorization serviceAuthorizationManagerType=  
                  "Samples.MyServiceAuthorizationManager" >  
          <authorizationPolicies>  
            <add policyType="Samples.MyAuthorizationPolicy" />  
          </authorizationPolicies>  
        </serviceAuthorization>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="to-specify-a-custom-authorization-policy-through-code"></a><span data-ttu-id="1df79-124">Per specificare un criterio di autorizzazione personalizzato tramite codice</span><span class="sxs-lookup"><span data-stu-id="1df79-124">To specify a custom authorization policy through code</span></span>  
  
1.  <span data-ttu-id="1df79-125">Creare una classe <xref:System.Collections.Generic.List%601> dell'interfaccia <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span><span class="sxs-lookup"><span data-stu-id="1df79-125">Create a <xref:System.Collections.Generic.List%601> of <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>  
  
2.  <span data-ttu-id="1df79-126">Creare un'istanza del criterio di autorizzazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1df79-126">Create an instance of the custom authorization policy.</span></span>  
  
3.  <span data-ttu-id="1df79-127">Aggiungere l'istanza del criterio di autorizzazione all'elenco.</span><span class="sxs-lookup"><span data-stu-id="1df79-127">Add the authorization policy instance to the list.</span></span>  
  
4.  <span data-ttu-id="1df79-128">Ripetere i passaggi 2 e 3 per ogni criterio di autorizzazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1df79-128">Repeat steps 2 and 3 for each custom authorization policy.</span></span>  
  
5.  <span data-ttu-id="1df79-129">Assegnare una versione in sola lettura dell'elenco alla proprietà <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>.</span><span class="sxs-lookup"><span data-stu-id="1df79-129">Assign a read-only version of the list to the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A> property.</span></span>  
  
     [!code-csharp[c_CustomAuthPol#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#8)]
     [!code-vb[c_CustomAuthPol#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="1df79-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="1df79-130">Example</span></span>  
 <span data-ttu-id="1df79-131">Nell'esempio seguente viene illustrata un'implementazione completa dell'interfaccia <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span><span class="sxs-lookup"><span data-stu-id="1df79-131">The following example shows a complete <xref:System.IdentityModel.Policy.IAuthorizationPolicy> implementation.</span></span>  
  
 [!code-csharp[c_CustomAuthPol#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#5)]
 [!code-vb[c_CustomAuthPol#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="1df79-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1df79-132">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [<span data-ttu-id="1df79-133">Procedura: Confrontare le attestazioni</span><span class="sxs-lookup"><span data-stu-id="1df79-133">How to: Compare Claims</span></span>](../../../../docs/framework/wcf/extending/how-to-compare-claims.md)
- [<span data-ttu-id="1df79-134">Procedura: Creare un gestore autorizzazioni personalizzato per un servizio</span><span class="sxs-lookup"><span data-stu-id="1df79-134">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="1df79-135">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1df79-135">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)
