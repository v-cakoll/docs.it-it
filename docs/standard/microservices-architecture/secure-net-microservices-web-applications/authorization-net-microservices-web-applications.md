---
title: Sull'autorizzazione nelle applicazioni web e microservizi .NET
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Sull'autorizzazione nelle applicazioni web e microservizi .NET
keywords: Docker, microservizi, ASP.NET, contenitore
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 51adda4f5bdb28154f17b9a988ee2d887bf1d461
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="about-authorization-in-net-microservices-and-web-applications"></a><span data-ttu-id="d7ced-104">Sull'autorizzazione nelle applicazioni web e microservizi .NET</span><span class="sxs-lookup"><span data-stu-id="d7ced-104">About authorization in .NET microservices and web applications</span></span>

<span data-ttu-id="d7ced-105">Dopo l'autenticazione, è necessario autorizzare l'accesso API Web di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="d7ced-105">After authentication, ASP.NET Core Web APIs need to authorize access.</span></span> <span data-ttu-id="d7ced-106">Questo processo consente a un servizio eseguire le API disponibili per alcuni utenti autenticati, ma non a tutti.</span><span class="sxs-lookup"><span data-stu-id="d7ced-106">This process allows a service to make APIs available to some authenticated users, but not to all.</span></span> <span data-ttu-id="d7ced-107">[Autorizzazione](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) può essere eseguita in base ai ruoli degli utenti o in base ai criteri personalizzati, che potrebbero includere l'analisi basata sulle attestazioni o altre regole euristiche.</span><span class="sxs-lookup"><span data-stu-id="d7ced-107">[Authorization](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) can be done based on users’ roles or based on custom policy, which might include inspecting claims or other heuristics.</span></span>

<span data-ttu-id="d7ced-108">Limitare l'accesso a una route ASP.NET MVC di base è facile quanto l'applicazione di un attributo Authorize per il metodo di azione (o classe del controller, se le azioni del controller richiedono autorizzazione), come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d7ced-108">Restricting access to an ASP.NET Core MVC route is as easy as applying an Authorize attribute to the action method (or to the controller’s class if all the controller’s actions require authorization), as shown in following example:</span></span>

```csharp
public class AccountController : Controller
{
    public ActionResult Login()
    {
    }

    [Authorize]
    public ActionResult Logout()
    {
    }
}
```

<span data-ttu-id="d7ced-109">Per impostazione predefinita, l'aggiunta di un attributo Authorize senza parametri limiteranno l'accesso agli utenti autenticati per tale controller o l'azione.</span><span class="sxs-lookup"><span data-stu-id="d7ced-109">By default, adding an Authorize attribute without parameters will limit access to authenticated users for that controller or action.</span></span> <span data-ttu-id="d7ced-110">Per limitare ulteriormente un'API che deve essere disponibile solo per specifici utenti, l'attributo può essere espanso per specificare che gli utenti devono soddisfare i criteri o i ruoli necessari.</span><span class="sxs-lookup"><span data-stu-id="d7ced-110">To further restrict an API to be available for only specific users, the attribute can be expanded to specify required roles or policies that users must satisfy.</span></span>

## <a name="implementing-role-based-authorization"></a><span data-ttu-id="d7ced-111">Implementare l'autorizzazione basata sui ruoli</span><span class="sxs-lookup"><span data-stu-id="d7ced-111">Implementing role-based authorization</span></span>

<span data-ttu-id="d7ced-112">Identità di ASP.NET Core è un concetto di ruoli predefinito.</span><span class="sxs-lookup"><span data-stu-id="d7ced-112">ASP.NET Core Identity has a built-in concept of roles.</span></span> <span data-ttu-id="d7ced-113">Oltre a utenti, ASP.NET Identity Core archivia informazioni sui diversi ruoli utilizzati dall'applicazione e tiene traccia di quali utenti vengono assegnati a determinati ruoli.</span><span class="sxs-lookup"><span data-stu-id="d7ced-113">In addition to users, ASP.NET Core Identity stores information about different roles used by the application and keeps track of which users are assigned to which roles.</span></span> <span data-ttu-id="d7ced-114">Queste assegnazioni possono essere modificate a livello di codice con il tipo RoleManager (che aggiorna i ruoli nel servizio di archiviazione persistente) e il tipo di classe UserManager (che può assegnare o annullare l'assegnazione di utenti da ruoli).</span><span class="sxs-lookup"><span data-stu-id="d7ced-114">These assignments can be changed programmatically with the RoleManager type (which updates roles in persisted storage) and UserManager type (which can assign or unassign users from roles).</span></span>

<span data-ttu-id="d7ced-115">Se si esegue l'autenticazione con token di connessione JWT, il middleware di autenticazione di connessione JWT di ASP.NET Core popolerà ruoli di un utente in base alle attestazioni di ruolo trovate nel token.</span><span class="sxs-lookup"><span data-stu-id="d7ced-115">If you are authenticating with JWT bearer tokens, the ASP.NET Core JWT bearer authentication middleware will populate a user’s roles based on role claims found in the token.</span></span> <span data-ttu-id="d7ced-116">Per limitare l'accesso a un'azione MVC o il controller per gli utenti nei ruoli specifici, è possibile includere un parametro di ruoli nell'intestazione Authorize, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d7ced-116">To limit access to an MVC action or controller to users in specific roles, you can include a Roles parameter in the Authorize header, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
public class ControlPanelController : Controller
{
    public ActionResult SetTime()
    {
    }

    [Authorize(Roles = "Administrator")]
    public ActionResult ShutDown()
    {
    }
}
```

<span data-ttu-id="d7ced-117">In questo esempio, solo gli utenti ai ruoli amministratore o PowerUser possono accedere alle API nel controller di Pannello di controllo (ad esempio, l'esecuzione dell'azione di SetTime).</span><span class="sxs-lookup"><span data-stu-id="d7ced-117">In this example, only users in the Administrator or PowerUser roles can access APIs in the ControlPanel controller (such as executing the SetTime action).</span></span> <span data-ttu-id="d7ced-118">L'API di arresto viene ulteriormente limitato per consentire l'accesso solo agli utenti nel ruolo di amministratore.</span><span class="sxs-lookup"><span data-stu-id="d7ced-118">The ShutDown API is further restricted to allow access only to users in the Administrator role.</span></span>

<span data-ttu-id="d7ced-119">Per richiedere che l'utente sia in più ruoli, utilizzare più attributi autorizza, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d7ced-119">To require a user be in multiple roles, you use multiple Authorize attributes, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

<span data-ttu-id="d7ced-120">In questo esempio, per chiamare API1, un utente è necessario:</span><span class="sxs-lookup"><span data-stu-id="d7ced-120">In this example, to call API1, a user must:</span></span>

-   <span data-ttu-id="d7ced-121">Nell'amministratore *o* ruolo PowerUser, *e*</span><span class="sxs-lookup"><span data-stu-id="d7ced-121">Be in the Adminstrator *or* PowerUser role, *and*</span></span>

-   <span data-ttu-id="d7ced-122">Il ruolo RemoteEmployee, *e*</span><span class="sxs-lookup"><span data-stu-id="d7ced-122">Be in the RemoteEmployee role, *and*</span></span>

-   <span data-ttu-id="d7ced-123">Soddisfa un gestore personalizzato per l'autorizzazione CustomPolicy.</span><span class="sxs-lookup"><span data-stu-id="d7ced-123">Satisfy a custom handler for CustomPolicy authorization.</span></span>

## <a name="implementing-policy-based-authorization"></a><span data-ttu-id="d7ced-124">Implementare l'autorizzazione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="d7ced-124">Implementing policy-based authorization</span></span>

<span data-ttu-id="d7ced-125">Le regole di autorizzazione personalizzati possono anche essere scritti utilizzando [criteri di autorizzazione](https://docs.asp.net/en/latest/security/authorization/policies.html).</span><span class="sxs-lookup"><span data-stu-id="d7ced-125">Custom authorization rules can also be written using [authorization policies](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span> <span data-ttu-id="d7ced-126">In questa sezione viene fornita una panoramica.</span><span class="sxs-lookup"><span data-stu-id="d7ced-126">In this section we provide an overview.</span></span> <span data-ttu-id="d7ced-127">È disponibile in linea di dettaglio [Workshop autorizzazione ASP.NET](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span><span class="sxs-lookup"><span data-stu-id="d7ced-127">More detail is available in the online [ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span></span>

<span data-ttu-id="d7ced-128">Criteri di autorizzazione personalizzati vengono registrati nel metodo Startup.ConfigureServices mediante il servizio. Metodo AddAuthorization.</span><span class="sxs-lookup"><span data-stu-id="d7ced-128">Custom authorization policies are registered in the Startup.ConfigureServices method using the service.AddAuthorization method.</span></span> <span data-ttu-id="d7ced-129">Questo metodo accetta un delegato che consente di configurare un argomento AuthorizationOptions.</span><span class="sxs-lookup"><span data-stu-id="d7ced-129">This method takes a delegate that configures an AuthorizationOptions argument.</span></span>

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("AdministratorsOnly", policy =>
        policy.RequireRole("Administrator"));
    options.AddPolicy("EmployeesOnly", policy =>
        policy.RequireClaim("EmployeeNumber"));
    options.AddPolicy("Over21", policy =>
        policy.Requirements.Add(new MinimumAgeRequirement(21)));
});
```

<span data-ttu-id="d7ced-130">Come illustrato nell'esempio, è possibile che i criteri possono essere associati a diversi tipi di requisiti.</span><span class="sxs-lookup"><span data-stu-id="d7ced-130">As shown in the example, policies can be associated with different types of requirements.</span></span> <span data-ttu-id="d7ced-131">Dopo che i criteri vengono registrati, possono essere applicati a un'azione o controller passando il nome del criterio come argomento dell'attributo Authorize criteri (ad esempio, \[Authorize(Policy="EmployeesOnly")\]) possono avere criteri requisiti di più, non solo uno (come illustrato in questi esempi).</span><span class="sxs-lookup"><span data-stu-id="d7ced-131">After the policies are registered, they can be applied to an action or controller by passing the policy’s name as the Policy argument of the Authorize attribute (for example, \[Authorize(Policy="EmployeesOnly")\]) Policies can have multiple requirements, not just one (as shown in these examples).</span></span>

<span data-ttu-id="d7ced-132">Nell'esempio precedente, la prima chiamata AddPolicy è un metodo alternativo di autorizzazione dal ruolo.</span><span class="sxs-lookup"><span data-stu-id="d7ced-132">In the previous example, the first AddPolicy call is just an alternative way of authorizing by role.</span></span> <span data-ttu-id="d7ced-133">Se \[Authorize(Policy="AdministratorsOnly")\] viene applicato a un'API, solo gli utenti del ruolo di amministratore sarà in grado di accedervi.</span><span class="sxs-lookup"><span data-stu-id="d7ced-133">If \[Authorize(Policy="AdministratorsOnly")\] is applied to an API, only users in the Administrator role will be able to access it.</span></span>

<span data-ttu-id="d7ced-134">La seconda chiamata AddPolicy viene illustrato un modo semplice per richiedere che una determinata attestazione deve essere presente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="d7ced-134">The second AddPolicy call demonstrates an easy way to require that a particular claim should be present for the user.</span></span> <span data-ttu-id="d7ced-135">Facoltativamente, il metodo di RequireClaim accetta i valori previsti per l'attestazione.</span><span class="sxs-lookup"><span data-stu-id="d7ced-135">The RequireClaim method also optionally takes expected values for the claim.</span></span> <span data-ttu-id="d7ced-136">Se i valori vengono specificati, il requisito viene soddisfatto solo se l'utente dispone di un'attestazione di tipo corretto sia uno dei valori specificati.</span><span class="sxs-lookup"><span data-stu-id="d7ced-136">If values are specified, the requirement is met only if the user has both a claim of the correct type and one of the specified values.</span></span> <span data-ttu-id="d7ced-137">Se si utilizza il middleware di autenticazione di connessione JWT, tutte le proprietà JWT saranno disponibili come attestazioni utente.</span><span class="sxs-lookup"><span data-stu-id="d7ced-137">If you are using the JWT bearer authentication middleware, all JWT properties will be available as user claims.</span></span>

<span data-ttu-id="d7ced-138">I criteri più interessanti illustrato di seguito sono nel terzo metodo AddPolicy, perché utilizza un requisito di autorizzazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d7ced-138">The most interesting policy shown here is in the third AddPolicy method, because it uses a custom authorization requirement.</span></span> <span data-ttu-id="d7ced-139">Con i requisiti di autorizzazione personalizzati, si può avere un notevole controllo sulla modalità di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="d7ced-139">By using custom authorization requirements, you can have a great deal of control over how authorization is performed.</span></span> <span data-ttu-id="d7ced-140">Per il funzionamento, è necessario implementare questi tipi:</span><span class="sxs-lookup"><span data-stu-id="d7ced-140">For this to work, you must implement these types:</span></span>

-   <span data-ttu-id="d7ced-141">Un tipo di requisiti che deriva da IAuthorizationRequirement e che contiene campi che specificano i dettagli del requisito.</span><span class="sxs-lookup"><span data-stu-id="d7ced-141">A Requirements type that derives from IAuthorizationRequirement and that contains fields specifying the details of the requirement.</span></span> <span data-ttu-id="d7ced-142">Nell'esempio, si tratta di un campo di validità per il tipo di MinimumAgeRequirement di esempio.</span><span class="sxs-lookup"><span data-stu-id="d7ced-142">In the example, this is an age field for the sample MinimumAgeRequirement type.</span></span>

-   <span data-ttu-id="d7ced-143">Un gestore che implementa AuthorizationHandler&lt;T&gt;, dove T è il tipo di IAuthorizationRequirement in grado di soddisfare il gestore.</span><span class="sxs-lookup"><span data-stu-id="d7ced-143">A handler that implements AuthorizationHandler&lt;T&gt;, where T is the type of IAuthorizationRequirement that the handler can satisfy.</span></span> <span data-ttu-id="d7ced-144">Il gestore deve implementare il metodo HandleRequirementAsync, che controlla se un contesto specificato che contiene informazioni sull'utente soddisfa il requisito.</span><span class="sxs-lookup"><span data-stu-id="d7ced-144">The handler must implement the HandleRequirementAsync method, which checks whether a specified context that contains information about the user satisfies the requirement.</span></span>

<span data-ttu-id="d7ced-145">Se l'utente soddisfa i requisiti, una chiamata al contesto. Esito positivo verrà indicano che l'utente è autorizzato.</span><span class="sxs-lookup"><span data-stu-id="d7ced-145">If the user meets the requirement, a call to context.Succeed will indicate that the user is authorized.</span></span> <span data-ttu-id="d7ced-146">Se sono disponibili diversi modi, che un utente potrebbe soddisfare un requisito di autorizzazione, è possono creare più gestori.</span><span class="sxs-lookup"><span data-stu-id="d7ced-146">If there are multiple ways that a user might satisfy an authorization requirement, multiple handlers can be created.</span></span>

<span data-ttu-id="d7ced-147">Oltre a registrare i requisiti dei criteri personalizzati con chiamate AddPolicy, è inoltre necessario registrare gestori requisito personalizzato tramite l'inserimento di dipendenze (servizi. AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).</span><span class="sxs-lookup"><span data-stu-id="d7ced-147">In addition to registering custom policy requirements with AddPolicy calls, you also need to register custom requirement handlers via Dependency Injection (services.AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).</span></span>

<span data-ttu-id="d7ced-148">Un esempio di un requisito di autorizzazione personalizzato e un gestore per il controllo di validità di un utente (basato su un'attestazione DateOfBirth) è disponibile in ASP.NET Core [documentazione autorizzazione](https://docs.asp.net/en/latest/security/authorization/policies.html).</span><span class="sxs-lookup"><span data-stu-id="d7ced-148">An example of a custom authorization requirement and handler for checking a user’s age (based on a DateOfBirth claim) is available in the ASP.NET Core [authorization documentation](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d7ced-149">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d7ced-149">Additional resources</span></span>

-   <span data-ttu-id="d7ced-150">**Autenticazione ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span><span class="sxs-lookup"><span data-stu-id="d7ced-150">**ASP.NET Core Authentication**
[*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span></span>

-   <span data-ttu-id="d7ced-151">**Autorizzazione ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span><span class="sxs-lookup"><span data-stu-id="d7ced-151">**ASP.NET Core Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span></span>

-   <span data-ttu-id="d7ced-152">**Autorizzazione basata sui ruoli**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span><span class="sxs-lookup"><span data-stu-id="d7ced-152">**Role based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span></span>

-   <span data-ttu-id="d7ced-153">**Autorizzazione personalizzata basata su criteri**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span><span class="sxs-lookup"><span data-stu-id="d7ced-153">**Custom Policy-Based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="d7ced-154">[Precedente] [Avanti] (developer app-segreti storage.md) (index.md)</span><span class="sxs-lookup"><span data-stu-id="d7ced-154">[Previous] (index.md) [Next] (developer-app-secrets-storage.md)</span></span>
