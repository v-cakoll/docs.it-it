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
# <a name="about-authorization-in-net-microservices-and-web-applications"></a>Informazioni sull'autorizzazione in microservizi .NET e applicazioni Web

Dopo l'autenticazione, le API Web di ASP.NET Core devono autorizzare l'accesso. Questo processo, ad esempio, consente a un servizio di rendere le API disponibili per alcuni utenti autenticati, ma non per tutti. [L'autorizzazione](/aspnet/core/security/authorization/introduction) può essere eseguita in base ai ruoli degli utenti o in base a criteri personalizzati, che possono includere l'ispezione di attestazioni o altre euristiche.

Limitare l'accesso a una route MVC di ASP.NET Core è semplice come applicare un attributo Authorize al metodo di azione (o alla classe del controller se tutte le azioni del controller richiedono l'autorizzazione), come illustrato nell'esempio seguente:Restricting access to an ASP.NET Core MVC route is easy as applying an Authorize attribute to the action method (or to the controller's class if all the controller's actions require authorization), as shown in following example:

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

Per impostazione predefinita, l'aggiunta di un attributo Authorize senza parametri limita l'accesso agli utenti autenticati per tale controller o azione. Per limitare ulteriormente un'API e renderla disponibile solo per specifici utenti, l'attributo può essere espanso per specificare i criteri o i ruoli richiesti che gli utenti devono soddisfare.

## <a name="implement-role-based-authorization"></a>Implementare l'autorizzazione basata sui ruoli

ASP.NET Core Identity offre funzionalità integrate per i ruoli. Oltre agli utenti, ASP.NET Core Identity archivia informazioni sui diversi ruoli usati dall'applicazione e tiene traccia degli utenti a cui sono assegnati i vari ruoli. Queste assegnazioni possono essere modificate a livello di codice con il tipo `RoleManager`, che aggiorna i ruoli nell'archiviazione persistente e con il tipo `UserManager`, che può concedere o revocare i ruoli degli utenti.

Se si esegue l'autenticazione con i token di portatore JWT, il middleware di autenticazione del portatore JWT di ASP.NET base popolerà i ruoli di un utente in base alle attestazioni di ruolo presenti nel token. Per limitare l'accesso a un'azione o un controller MVC a utenti con ruoli specifici, è possibile includere un parametro Roles nell'annotazione (attributo) Authorize, come illustrato nel frammento di codice seguente:

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

In questo esempio, solo gli utenti con i ruoli Administrator o PowerUser possono accedere alle API nel controller ControlPanel (ad esempio, l'esecuzione dell'azione SetTime). L'API ShutDown è ulteriormente limitata in modo da consentire l'accesso solo agli utenti con il ruolo Administrator.

Per richiedere l'appartenenza di un utente a più ruoli, è possibile usare più attributi Authorize, come illustrato nell'esempio seguente:

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

In questo esempio, per chiamare API1, un utente deve:

- Appartenere al ruolo Administrator *o* PowerUser *e*

- Appartenere al ruolo RemoteEmployee *e*

- Soddisfare un gestore personalizzato per l'autorizzazione CustomPolicy.

## <a name="implement-policy-based-authorization"></a>Implementare l'autorizzazione basata su criteri

È anche possibile scrivere regole di autorizzazione personalizzate usando i [criteri di autorizzazione](https://docs.asp.net/en/latest/security/authorization/policies.html). Questa sezione offre una panoramica. Per altre informazioni, vedere [AspNetAuthorizationWorkshop
](https://github.com/blowdart/AspNetAuthorizationWorkshop).

I criteri di autorizzazione personalizzati vengono registrati nel metodo Startup.ConfigureServices mediante il metodo service.AddAuthorization. Questo metodo accetta un delegato che configura un argomento AuthorizationOptions.

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

Come illustrato nell'esempio, i criteri possono essere associati a diversi tipi di requisiti. Dopo la registrazione, i criteri possono essere applicati a un'azione o a un controller passando il `[Authorize(Policy="EmployeesOnly")]`nome del criterio come argomento Policy dell'attributo Authorize (ad esempio, ) I criteri possono avere più requisiti, non solo uno (come illustrato in questi esempi).

Nell'esempio precedente, la prima chiamata AddPolicy è un metodo alternativo per eseguire l'autorizzazione in base al ruolo. Se `[Authorize(Policy="AdministratorsOnly")]` viene applicato a un'API, solo gli utenti con il ruolo Administrator saranno in grado di accedervi.

La seconda chiamata <xref:Microsoft.AspNetCore.Authorization.AuthorizationOptions.AddPolicy%2A> illustra un modo semplice per richiedere la presenza di una determinata attestazione per l'utente. Facoltativamente, il metodo <xref:Microsoft.AspNetCore.Authorization.AuthorizationPolicyBuilder.RequireClaim%2A> accetta anche i valori previsti per l'attestazione. Se si specificano i valori, il requisito viene soddisfatto solo se l'utente dispone di un'attestazione di tipo corretto e di uno dei valori specificati. Se si usa il middleware di autenticazione del bearer token JWT, tutte le proprietà JWT sono disponibili come attestazioni utente.

I criteri più interessanti illustrati di seguito si trovano nel terzo metodo `AddPolicy`, perché usano un requisito di autorizzazione personalizzato. Con i requisiti di autorizzazione personalizzati, è possibile avere un notevole controllo sulla modalità di esecuzione dell'autorizzazione. Per garantirne il funzionamento, è necessario implementare questi tipi:

- Un tipo Requirements che deriva da <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> e contiene campi che specificano i dettagli del requisito. Nell'esempio, si tratta di un campo relativo all'età per il tipo `MinimumAgeRequirement` di esempio.

- Un gestore che implementa <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601>, dove T è il tipo di <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> che il gestore di è in grado di soddisfare. Il gestore deve implementare il metodo <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601.HandleRequirementAsync%2A>, che verifica se un contesto specificato contenente informazioni sull'utente soddisfa il requisito.

Se l'utente soddisfa il requisito, una chiamata a `context.Succeed` indicherà che l'utente è autorizzato. Se esistono diversi modi in cui un utente potrebbe soddisfare un requisito di autorizzazione, è possibile creare più gestori.

Oltre a registrare i requisiti dei criteri personalizzati con le chiamate `AddPolicy`, è necessario registrare i gestori dei requisiti personalizzati tramite l'inserimento di dipendenze (`services.AddTransient<IAuthorizationHandler, MinimumAgeHandler>()`).

Un esempio di un requisito di autorizzazione personalizzato e un `DateOfBirth` gestore per controllare l'età di un utente (in base a un'attestazione) è disponibile nella [documentazione](https://docs.asp.net/en/latest/security/authorization/policies.html)di autorizzazione ASP.NET Core .

## <a name="additional-resources"></a>Risorse aggiuntive

- **Autenticazione di base di ASP.NET** \
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- **Autorizzazione ASP.NET core** \
  [https://docs.microsoft.com/aspnet/core/security/authorization/introduction](/aspnet/core/security/authorization/introduction)

- **Autorizzazione basata sui ruoli** \
  [https://docs.microsoft.com/aspnet/core/security/authorization/roles](/aspnet/core/security/authorization/roles)

- **Autorizzazione basata su criteri personalizzatiCustom Policy-Based Authorization** \
  [https://docs.microsoft.com/aspnet/core/security/authorization/policies](/aspnet/core/security/authorization/policies)

>[!div class="step-by-step"]
>[Successivo](index.md)
>[precedente](developer-app-secrets-storage.md)
