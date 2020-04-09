---
title: Informazioni sull'autorizzazione in microservizi .NET e applicazioni Web
description: Sicurezza nei microservizi .NET e nelle applicazioni Web - Panoramica delle principali opzioni di autorizzazione nelle applicazioni ASP.NET Core, sia basate sui ruoli che basate sui criteri.
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: 27936a33ea2bb46cedb9d10ee47a2117e1843e14
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988206"
---
# <a name="about-authorization-in-net-microservices-and-web-applications"></a><span data-ttu-id="d15d0-103">Informazioni sull'autorizzazione in microservizi .NET e applicazioni Web</span><span class="sxs-lookup"><span data-stu-id="d15d0-103">About authorization in .NET microservices and web applications</span></span>

<span data-ttu-id="d15d0-104">Dopo l'autenticazione, le API Web di ASP.NET Core devono autorizzare l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d15d0-104">After authentication, ASP.NET Core Web APIs need to authorize access.</span></span> <span data-ttu-id="d15d0-105">Questo processo, ad esempio, consente a un servizio di rendere le API disponibili per alcuni utenti autenticati, ma non per tutti.</span><span class="sxs-lookup"><span data-stu-id="d15d0-105">This process allows a service to make APIs available to some authenticated users, but not to all.</span></span> <span data-ttu-id="d15d0-106">[L'autorizzazione](/aspnet/core/security/authorization/introduction) può essere eseguita in base ai ruoli degli utenti o in base a criteri personalizzati, che possono includere l'ispezione di attestazioni o altre euristiche.</span><span class="sxs-lookup"><span data-stu-id="d15d0-106">[Authorization](/aspnet/core/security/authorization/introduction) can be done based on users' roles or based on custom policy, which might include inspecting claims or other heuristics.</span></span>

<span data-ttu-id="d15d0-107">Limitare l'accesso a una route MVC di ASP.NET Core è semplice come applicare un attributo Authorize al metodo di azione (o alla classe del controller se tutte le azioni del controller richiedono l'autorizzazione), come illustrato nell'esempio seguente:Restricting access to an ASP.NET Core MVC route is easy as applying an Authorize attribute to the action method (or to the controller's class if all the controller's actions require authorization), as shown in following example:</span><span class="sxs-lookup"><span data-stu-id="d15d0-107">Restricting access to an ASP.NET Core MVC route is as easy as applying an Authorize attribute to the action method (or to the controller's class if all the controller's actions require authorization), as shown in following example:</span></span>

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

<span data-ttu-id="d15d0-108">Per impostazione predefinita, l'aggiunta di un attributo Authorize senza parametri limita l'accesso agli utenti autenticati per tale controller o azione.</span><span class="sxs-lookup"><span data-stu-id="d15d0-108">By default, adding an Authorize attribute without parameters will limit access to authenticated users for that controller or action.</span></span> <span data-ttu-id="d15d0-109">Per limitare ulteriormente un'API e renderla disponibile solo per specifici utenti, l'attributo può essere espanso per specificare i criteri o i ruoli richiesti che gli utenti devono soddisfare.</span><span class="sxs-lookup"><span data-stu-id="d15d0-109">To further restrict an API to be available for only specific users, the attribute can be expanded to specify required roles or policies that users must satisfy.</span></span>

## <a name="implement-role-based-authorization"></a><span data-ttu-id="d15d0-110">Implementare l'autorizzazione basata sui ruoli</span><span class="sxs-lookup"><span data-stu-id="d15d0-110">Implement role-based authorization</span></span>

<span data-ttu-id="d15d0-111">ASP.NET Core Identity offre funzionalità integrate per i ruoli.</span><span class="sxs-lookup"><span data-stu-id="d15d0-111">ASP.NET Core Identity has a built-in concept of roles.</span></span> <span data-ttu-id="d15d0-112">Oltre agli utenti, ASP.NET Core Identity archivia informazioni sui diversi ruoli usati dall'applicazione e tiene traccia degli utenti a cui sono assegnati i vari ruoli.</span><span class="sxs-lookup"><span data-stu-id="d15d0-112">In addition to users, ASP.NET Core Identity stores information about different roles used by the application and keeps track of which users are assigned to which roles.</span></span> <span data-ttu-id="d15d0-113">Queste assegnazioni possono essere modificate a livello di codice con il tipo `RoleManager`, che aggiorna i ruoli nell'archiviazione persistente e con il tipo `UserManager`, che può concedere o revocare i ruoli degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d15d0-113">These assignments can be changed programmatically with the `RoleManager` type that updates roles in persisted storage, and the `UserManager` type that can grant or revoke roles from users.</span></span>

<span data-ttu-id="d15d0-114">Se si esegue l'autenticazione con i token di portatore JWT, il middleware di autenticazione del portatore JWT di ASP.NET base popolerà i ruoli di un utente in base alle attestazioni di ruolo presenti nel token.</span><span class="sxs-lookup"><span data-stu-id="d15d0-114">If you're authenticating with JWT bearer tokens, the ASP.NET Core JWT bearer authentication middleware will populate a user's roles based on role claims found in the token.</span></span> <span data-ttu-id="d15d0-115">Per limitare l'accesso a un'azione o un controller MVC a utenti con ruoli specifici, è possibile includere un parametro Roles nell'annotazione (attributo) Authorize, come illustrato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d15d0-115">To limit access to an MVC action or controller to users in specific roles, you can include a Roles parameter in the Authorize annotation (attribute), as shown in the following code fragment:</span></span>

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

<span data-ttu-id="d15d0-116">In questo esempio, solo gli utenti con i ruoli Administrator o PowerUser possono accedere alle API nel controller ControlPanel (ad esempio, l'esecuzione dell'azione SetTime).</span><span class="sxs-lookup"><span data-stu-id="d15d0-116">In this example, only users in the Administrator or PowerUser roles can access APIs in the ControlPanel controller (such as executing the SetTime action).</span></span> <span data-ttu-id="d15d0-117">L'API ShutDown è ulteriormente limitata in modo da consentire l'accesso solo agli utenti con il ruolo Administrator.</span><span class="sxs-lookup"><span data-stu-id="d15d0-117">The ShutDown API is further restricted to allow access only to users in the Administrator role.</span></span>

<span data-ttu-id="d15d0-118">Per richiedere l'appartenenza di un utente a più ruoli, è possibile usare più attributi Authorize, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d15d0-118">To require a user be in multiple roles, you use multiple Authorize attributes, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

<span data-ttu-id="d15d0-119">In questo esempio, per chiamare API1, un utente deve:</span><span class="sxs-lookup"><span data-stu-id="d15d0-119">In this example, to call API1, a user must:</span></span>

- <span data-ttu-id="d15d0-120">Appartenere al ruolo Administrator *o* PowerUser *e*</span><span class="sxs-lookup"><span data-stu-id="d15d0-120">Be in the Administrator *or* PowerUser role, *and*</span></span>

- <span data-ttu-id="d15d0-121">Appartenere al ruolo RemoteEmployee *e*</span><span class="sxs-lookup"><span data-stu-id="d15d0-121">Be in the RemoteEmployee role, *and*</span></span>

- <span data-ttu-id="d15d0-122">Soddisfare un gestore personalizzato per l'autorizzazione CustomPolicy.</span><span class="sxs-lookup"><span data-stu-id="d15d0-122">Satisfy a custom handler for CustomPolicy authorization.</span></span>

## <a name="implement-policy-based-authorization"></a><span data-ttu-id="d15d0-123">Implementare l'autorizzazione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="d15d0-123">Implement policy-based authorization</span></span>

<span data-ttu-id="d15d0-124">È anche possibile scrivere regole di autorizzazione personalizzate usando i [criteri di autorizzazione](https://docs.asp.net/en/latest/security/authorization/policies.html).</span><span class="sxs-lookup"><span data-stu-id="d15d0-124">Custom authorization rules can also be written using [authorization policies](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span> <span data-ttu-id="d15d0-125">Questa sezione offre una panoramica.</span><span class="sxs-lookup"><span data-stu-id="d15d0-125">This section provides an overview.</span></span> <span data-ttu-id="d15d0-126">Per altre informazioni, vedere [AspNetAuthorizationWorkshop
](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span><span class="sxs-lookup"><span data-stu-id="d15d0-126">For more information, see the [ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span></span>

<span data-ttu-id="d15d0-127">I criteri di autorizzazione personalizzati vengono registrati nel metodo Startup.ConfigureServices mediante il metodo service.AddAuthorization.</span><span class="sxs-lookup"><span data-stu-id="d15d0-127">Custom authorization policies are registered in the Startup.ConfigureServices method using the service.AddAuthorization method.</span></span> <span data-ttu-id="d15d0-128">Questo metodo accetta un delegato che configura un argomento AuthorizationOptions.</span><span class="sxs-lookup"><span data-stu-id="d15d0-128">This method takes a delegate that configures an AuthorizationOptions argument.</span></span>

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

<span data-ttu-id="d15d0-129">Come illustrato nell'esempio, i criteri possono essere associati a diversi tipi di requisiti.</span><span class="sxs-lookup"><span data-stu-id="d15d0-129">As shown in the example, policies can be associated with different types of requirements.</span></span> <span data-ttu-id="d15d0-130">Dopo la registrazione, i criteri possono essere applicati a un'azione o a un controller passando il `[Authorize(Policy="EmployeesOnly")]`nome del criterio come argomento Policy dell'attributo Authorize (ad esempio, ) I criteri possono avere più requisiti, non solo uno (come illustrato in questi esempi).</span><span class="sxs-lookup"><span data-stu-id="d15d0-130">After the policies are registered, they can be applied to an action or controller by passing the policy's name as the Policy argument of the Authorize attribute (for example, `[Authorize(Policy="EmployeesOnly")]`) Policies can have multiple requirements, not just one (as shown in these examples).</span></span>

<span data-ttu-id="d15d0-131">Nell'esempio precedente, la prima chiamata AddPolicy è un metodo alternativo per eseguire l'autorizzazione in base al ruolo.</span><span class="sxs-lookup"><span data-stu-id="d15d0-131">In the previous example, the first AddPolicy call is just an alternative way of authorizing by role.</span></span> <span data-ttu-id="d15d0-132">Se `[Authorize(Policy="AdministratorsOnly")]` viene applicato a un'API, solo gli utenti con il ruolo Administrator saranno in grado di accedervi.</span><span class="sxs-lookup"><span data-stu-id="d15d0-132">If `[Authorize(Policy="AdministratorsOnly")]` is applied to an API, only users in the Administrator role will be able to access it.</span></span>

<span data-ttu-id="d15d0-133">La seconda chiamata <xref:Microsoft.AspNetCore.Authorization.AuthorizationOptions.AddPolicy%2A> illustra un modo semplice per richiedere la presenza di una determinata attestazione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="d15d0-133">The second <xref:Microsoft.AspNetCore.Authorization.AuthorizationOptions.AddPolicy%2A> call demonstrates an easy way to require that a particular claim should be present for the user.</span></span> <span data-ttu-id="d15d0-134">Facoltativamente, il metodo <xref:Microsoft.AspNetCore.Authorization.AuthorizationPolicyBuilder.RequireClaim%2A> accetta anche i valori previsti per l'attestazione.</span><span class="sxs-lookup"><span data-stu-id="d15d0-134">The <xref:Microsoft.AspNetCore.Authorization.AuthorizationPolicyBuilder.RequireClaim%2A> method also optionally takes expected values for the claim.</span></span> <span data-ttu-id="d15d0-135">Se si specificano i valori, il requisito viene soddisfatto solo se l'utente dispone di un'attestazione di tipo corretto e di uno dei valori specificati.</span><span class="sxs-lookup"><span data-stu-id="d15d0-135">If values are specified, the requirement is met only if the user has both a claim of the correct type and one of the specified values.</span></span> <span data-ttu-id="d15d0-136">Se si usa il middleware di autenticazione del bearer token JWT, tutte le proprietà JWT sono disponibili come attestazioni utente.</span><span class="sxs-lookup"><span data-stu-id="d15d0-136">If you're using the JWT bearer authentication middleware, all JWT properties will be available as user claims.</span></span>

<span data-ttu-id="d15d0-137">I criteri più interessanti illustrati di seguito si trovano nel terzo metodo `AddPolicy`, perché usano un requisito di autorizzazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d15d0-137">The most interesting policy shown here is in the third `AddPolicy` method, because it uses a custom authorization requirement.</span></span> <span data-ttu-id="d15d0-138">Con i requisiti di autorizzazione personalizzati, è possibile avere un notevole controllo sulla modalità di esecuzione dell'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="d15d0-138">By using custom authorization requirements, you can have a great deal of control over how authorization is performed.</span></span> <span data-ttu-id="d15d0-139">Per garantirne il funzionamento, è necessario implementare questi tipi:</span><span class="sxs-lookup"><span data-stu-id="d15d0-139">For this to work, you must implement these types:</span></span>

- <span data-ttu-id="d15d0-140">Un tipo Requirements che deriva da <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> e contiene campi che specificano i dettagli del requisito.</span><span class="sxs-lookup"><span data-stu-id="d15d0-140">A Requirements type that derives from <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> and that contains fields specifying the details of the requirement.</span></span> <span data-ttu-id="d15d0-141">Nell'esempio, si tratta di un campo relativo all'età per il tipo `MinimumAgeRequirement` di esempio.</span><span class="sxs-lookup"><span data-stu-id="d15d0-141">In the example, this is an age field for the sample `MinimumAgeRequirement` type.</span></span>

- <span data-ttu-id="d15d0-142">Un gestore che implementa <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601>, dove T è il tipo di <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> che il gestore di è in grado di soddisfare.</span><span class="sxs-lookup"><span data-stu-id="d15d0-142">A handler that implements <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601>, where T is the type of <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> that the handler can satisfy.</span></span> <span data-ttu-id="d15d0-143">Il gestore deve implementare il metodo <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601.HandleRequirementAsync%2A>, che verifica se un contesto specificato contenente informazioni sull'utente soddisfa il requisito.</span><span class="sxs-lookup"><span data-stu-id="d15d0-143">The handler must implement the <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601.HandleRequirementAsync%2A> method, which checks whether a specified context that contains information about the user satisfies the requirement.</span></span>

<span data-ttu-id="d15d0-144">Se l'utente soddisfa il requisito, una chiamata a `context.Succeed` indicherà che l'utente è autorizzato.</span><span class="sxs-lookup"><span data-stu-id="d15d0-144">If the user meets the requirement, a call to `context.Succeed` will indicate that the user is authorized.</span></span> <span data-ttu-id="d15d0-145">Se esistono diversi modi in cui un utente potrebbe soddisfare un requisito di autorizzazione, è possibile creare più gestori.</span><span class="sxs-lookup"><span data-stu-id="d15d0-145">If there are multiple ways that a user might satisfy an authorization requirement, multiple handlers can be created.</span></span>

<span data-ttu-id="d15d0-146">Oltre a registrare i requisiti dei criteri personalizzati con le chiamate `AddPolicy`, è necessario registrare i gestori dei requisiti personalizzati tramite l'inserimento di dipendenze (`services.AddTransient<IAuthorizationHandler, MinimumAgeHandler>()`).</span><span class="sxs-lookup"><span data-stu-id="d15d0-146">In addition to registering custom policy requirements with `AddPolicy` calls, you also need to register custom requirement handlers via Dependency Injection (`services.AddTransient<IAuthorizationHandler, MinimumAgeHandler>()`).</span></span>

<span data-ttu-id="d15d0-147">Un esempio di un requisito di autorizzazione personalizzato e un `DateOfBirth` gestore per controllare l'età di un utente (in base a un'attestazione) è disponibile nella [documentazione](https://docs.asp.net/en/latest/security/authorization/policies.html)di autorizzazione ASP.NET Core .</span><span class="sxs-lookup"><span data-stu-id="d15d0-147">An example of a custom authorization requirement and handler for checking a user's age (based on a `DateOfBirth` claim) is available in the ASP.NET Core [authorization documentation](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d15d0-148">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d15d0-148">Additional resources</span></span>

- <span data-ttu-id="d15d0-149">**Autenticazione di base di ASP.NET** </span><span class="sxs-lookup"><span data-stu-id="d15d0-149">**ASP.NET Core Authentication** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- <span data-ttu-id="d15d0-150">**Autorizzazione ASP.NET core** </span><span class="sxs-lookup"><span data-stu-id="d15d0-150">**ASP.NET Core Authorization** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authorization/introduction](/aspnet/core/security/authorization/introduction)

- <span data-ttu-id="d15d0-151">**Autorizzazione basata sui ruoli** </span><span class="sxs-lookup"><span data-stu-id="d15d0-151">**Role-based Authorization** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authorization/roles](/aspnet/core/security/authorization/roles)

- <span data-ttu-id="d15d0-152">**Autorizzazione basata su criteri personalizzatiCustom Policy-Based Authorization** </span><span class="sxs-lookup"><span data-stu-id="d15d0-152">**Custom Policy-Based Authorization** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authorization/policies](/aspnet/core/security/authorization/policies)

>[!div class="step-by-step"]
><span data-ttu-id="d15d0-153">[Successivo](index.md)
>[precedente](developer-app-secrets-storage.md)</span><span class="sxs-lookup"><span data-stu-id="d15d0-153">[Previous](index.md)
[Next](developer-app-secrets-storage.md)</span></span>
