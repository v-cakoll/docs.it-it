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
# <a name="about-authorization-in-net-microservices-and-web-applications"></a>Sull'autorizzazione nelle applicazioni web e microservizi .NET

Dopo l'autenticazione, è necessario autorizzare l'accesso API Web di ASP.NET Core. Questo processo consente a un servizio eseguire le API disponibili per alcuni utenti autenticati, ma non a tutti. [Autorizzazione](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) può essere eseguita in base ai ruoli degli utenti o in base ai criteri personalizzati, che potrebbero includere l'analisi basata sulle attestazioni o altre regole euristiche.

Limitare l'accesso a una route ASP.NET MVC di base è facile quanto l'applicazione di un attributo Authorize per il metodo di azione (o classe del controller, se le azioni del controller richiedono autorizzazione), come illustrato nell'esempio seguente:

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

Per impostazione predefinita, l'aggiunta di un attributo Authorize senza parametri limiteranno l'accesso agli utenti autenticati per tale controller o l'azione. Per limitare ulteriormente un'API che deve essere disponibile solo per specifici utenti, l'attributo può essere espanso per specificare che gli utenti devono soddisfare i criteri o i ruoli necessari.

## <a name="implementing-role-based-authorization"></a>Implementare l'autorizzazione basata sui ruoli

Identità di ASP.NET Core è un concetto di ruoli predefinito. Oltre a utenti, ASP.NET Identity Core archivia informazioni sui diversi ruoli utilizzati dall'applicazione e tiene traccia di quali utenti vengono assegnati a determinati ruoli. Queste assegnazioni possono essere modificate a livello di codice con il tipo RoleManager (che aggiorna i ruoli nel servizio di archiviazione persistente) e il tipo di classe UserManager (che può assegnare o annullare l'assegnazione di utenti da ruoli).

Se si esegue l'autenticazione con token di connessione JWT, il middleware di autenticazione di connessione JWT di ASP.NET Core popolerà ruoli di un utente in base alle attestazioni di ruolo trovate nel token. Per limitare l'accesso a un'azione MVC o il controller per gli utenti nei ruoli specifici, è possibile includere un parametro di ruoli nell'intestazione Authorize, come illustrato nell'esempio seguente:

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

In questo esempio, solo gli utenti ai ruoli amministratore o PowerUser possono accedere alle API nel controller di Pannello di controllo (ad esempio, l'esecuzione dell'azione di SetTime). L'API di arresto viene ulteriormente limitato per consentire l'accesso solo agli utenti nel ruolo di amministratore.

Per richiedere che l'utente sia in più ruoli, utilizzare più attributi autorizza, come illustrato nell'esempio seguente:

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

In questo esempio, per chiamare API1, un utente è necessario:

-   Nell'amministratore *o* ruolo PowerUser, *e*

-   Il ruolo RemoteEmployee, *e*

-   Soddisfa un gestore personalizzato per l'autorizzazione CustomPolicy.

## <a name="implementing-policy-based-authorization"></a>Implementare l'autorizzazione basata su criteri

Le regole di autorizzazione personalizzati possono anche essere scritti utilizzando [criteri di autorizzazione](https://docs.asp.net/en/latest/security/authorization/policies.html). In questa sezione viene fornita una panoramica. È disponibile in linea di dettaglio [Workshop autorizzazione ASP.NET](https://github.com/blowdart/AspNetAuthorizationWorkshop).

Criteri di autorizzazione personalizzati vengono registrati nel metodo Startup.ConfigureServices mediante il servizio. Metodo AddAuthorization. Questo metodo accetta un delegato che consente di configurare un argomento AuthorizationOptions.

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

Come illustrato nell'esempio, è possibile che i criteri possono essere associati a diversi tipi di requisiti. Dopo che i criteri vengono registrati, possono essere applicati a un'azione o controller passando il nome del criterio come argomento dell'attributo Authorize criteri (ad esempio, \[Authorize(Policy="EmployeesOnly")\]) possono avere criteri requisiti di più, non solo uno (come illustrato in questi esempi).

Nell'esempio precedente, la prima chiamata AddPolicy è un metodo alternativo di autorizzazione dal ruolo. Se \[Authorize(Policy="AdministratorsOnly")\] viene applicato a un'API, solo gli utenti del ruolo di amministratore sarà in grado di accedervi.

La seconda chiamata AddPolicy viene illustrato un modo semplice per richiedere che una determinata attestazione deve essere presente per l'utente. Facoltativamente, il metodo di RequireClaim accetta i valori previsti per l'attestazione. Se i valori vengono specificati, il requisito viene soddisfatto solo se l'utente dispone di un'attestazione di tipo corretto sia uno dei valori specificati. Se si utilizza il middleware di autenticazione di connessione JWT, tutte le proprietà JWT saranno disponibili come attestazioni utente.

I criteri più interessanti illustrato di seguito sono nel terzo metodo AddPolicy, perché utilizza un requisito di autorizzazione personalizzato. Con i requisiti di autorizzazione personalizzati, si può avere un notevole controllo sulla modalità di autorizzazione. Per il funzionamento, è necessario implementare questi tipi:

-   Un tipo di requisiti che deriva da IAuthorizationRequirement e che contiene campi che specificano i dettagli del requisito. Nell'esempio, si tratta di un campo di validità per il tipo di MinimumAgeRequirement di esempio.

-   Un gestore che implementa AuthorizationHandler&lt;T&gt;, dove T è il tipo di IAuthorizationRequirement in grado di soddisfare il gestore. Il gestore deve implementare il metodo HandleRequirementAsync, che controlla se un contesto specificato che contiene informazioni sull'utente soddisfa il requisito.

Se l'utente soddisfa i requisiti, una chiamata al contesto. Esito positivo verrà indicano che l'utente è autorizzato. Se sono disponibili diversi modi, che un utente potrebbe soddisfare un requisito di autorizzazione, è possono creare più gestori.

Oltre a registrare i requisiti dei criteri personalizzati con chiamate AddPolicy, è inoltre necessario registrare gestori requisito personalizzato tramite l'inserimento di dipendenze (servizi. AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).

Un esempio di un requisito di autorizzazione personalizzato e un gestore per il controllo di validità di un utente (basato su un'attestazione DateOfBirth) è disponibile in ASP.NET Core [documentazione autorizzazione](https://docs.asp.net/en/latest/security/authorization/policies.html).

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Autenticazione ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)

-   **Autorizzazione ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)

-   **Autorizzazione basata sui ruoli**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)

-   **Autorizzazione personalizzata basata su criteri**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)




>[!div class="step-by-step"]
[Precedente] [Avanti] (developer app-segreti storage.md) (index.md)
