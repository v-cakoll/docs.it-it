---
title: IdentityServer per le app cloud native
description: Architettura di app .NET cloud native per Azure | IdentityServer
ms.date: 06/30/2019
ms.openlocfilehash: 48d0b95a40682f3127127851781b4d0e26e44630
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728587"
---
# <a name="identityserver-for-cloud-native-applications"></a>IdentityServer per applicazioni native del cloud

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

IdentityServer è un server di autenticazione open source che implementa gli standard OpenID Connect (OIDC) e OAuth 2,0 per ASP.NET Core. È progettato per fornire un modo comune per autenticare le richieste a tutte le applicazioni, indipendentemente dal fatto che siano endpoint Web, nativi, per dispositivi mobili o API. IdentityServer può essere utilizzato per implementare l'accesso Single Sign-on (SSO) per più applicazioni e tipi di applicazione. Può essere usato per autenticare gli utenti effettivi tramite moduli di accesso e interfacce utente analoghe, oltre all'autenticazione basata su servizi che in genere comporta il rilascio, la verifica e il rinnovo dei token senza alcuna interfaccia utente. IdentityServer è progettato per essere una soluzione personalizzabile. Ogni istanza viene in genere personalizzata per adattarsi a una singola organizzazione e/o a un set di esigenze delle applicazioni.

## <a name="common-web-app-scenarios"></a>Scenari comuni di app Web

In genere, le applicazioni devono supportare alcuni o tutti gli scenari seguenti:

- Utenti umani che accedono alle applicazioni Web con un browser.
- Utenti umani che accedono alle API Web back-end dalle app basate su browser.
- Utenti umani nei client mobili/nativi che accedono alle API Web back-end.
- Altre applicazioni che accedono alle API Web back-end (senza interfaccia utente o utente attivo).
- Qualsiasi applicazione potrebbe dover interagire con altre API Web, usando la propria identità o delegando l'identità dell'utente.

![tipi di applicazione e scenari](./media/application-types.png)
**figura 8-1**. Tipi di applicazioni e scenari.

In ognuno di questi scenari, la funzionalità esposta deve essere protetta da un uso non autorizzato. Come minimo, questa operazione richiede in genere l'autenticazione dell'utente o dell'entità che effettua una richiesta di una risorsa. Questa autenticazione può usare uno dei diversi protocolli comuni, ad esempio SAML2p, WS-Fed o OpenID Connect. La comunicazione con le API USA in genere il protocollo OAuth2 e il relativo supporto per i token di sicurezza. La separazione di queste problematiche cruciali in materia di sicurezza e dei relativi dettagli di implementazione dalle applicazioni stesse garantisce coerenza e miglioramento della sicurezza e della gestibilità. L'outsourcing di queste preoccupazioni a un prodotto dedicato, ad esempio IdentityServer, consente a ogni applicazione di risolvere questi problemi.

IdentityServer fornisce il middleware eseguito all'interno di un'applicazione ASP.NET Core e aggiunge il supporto per OpenID Connect e OAuth2 (vedere le [specifiche supportate](http://docs.identityserver.io/en/latest/intro/specs.html)). Le organizzazioni creeranno una propria app ASP.NET Core usando il middleware IdentityServer per agire come servizio token di sicurezza per tutti i protocolli di sicurezza basati su token. Il middleware IdentityServer espone gli endpoint per supportare le funzionalità standard, tra cui:

- Autorizza (autenticazione dell'utente finale)
- Token (richiedere un token a livello di codice)
- Individuazione (metadati relativi al server)
- Informazioni utente (ottenere informazioni utente con un token di accesso valido)
- Autorizzazione del dispositivo (usata per avviare l'autorizzazione del flusso del dispositivo)
- Introspezione (convalida token)
- Revoca (revoca dei token)
- Termina sessione (attiva Single Sign-out in tutte le app)

## <a name="getting-started"></a>Per iniziare

IdentityServer4 è open source e gratuito. È possibile aggiungerlo alle applicazioni usando i pacchetti NuGet. Il pacchetto principale è [IdentityServer4](https://www.nuget.org/packages/IdentityServer4/) che è stato scaricato più di 4 milioni volte. Il pacchetto di base non include alcun codice dell'interfaccia utente e supporta solo la configurazione in memoria. Per usarlo con un database, è necessario anche un provider di dati come [IdentityServer4. EntityFramework](https://www.nuget.org/packages/IdentityServer4.EntityFramework) che usa Entity Framework Core per archiviare i dati di configurazione e operativi per IdentityServer. Per l'interfaccia utente, è possibile copiare i file dal [repository dell'interfaccia utente di avvio rapido](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI) nell'applicazione ASP.NET Core MVC per aggiungere il supporto per l'accesso e la disconnessione usando il middleware IdentityServer.

## <a name="configuration"></a>Configurazione

IdentityServer supporta diversi tipi di protocolli e provider di autenticazione basata su social network che possono essere configurati come parte di ogni installazione personalizzata. Questa operazione viene in genere eseguita nella classe `Startup` dell'applicazione ASP.NET Core nel metodo `ConfigureServices`. La configurazione prevede la specifica dei protocolli supportati e i percorsi dei server e degli endpoint che verranno usati. La figura 8-2 illustra una configurazione di esempio ricavata dal progetto dell'interfaccia utente di avvio rapido di IdentityServer4:

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();

        // some details omitted
        services.AddIdentityServer();

          services.AddAuthentication()
            .AddGoogle("Google", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;

                options.ClientId = "<insert here>";
                options.ClientSecret = "<insert here>";
            })
            .AddOpenIdConnect("demoidsrv", "IdentityServer", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;
                options.SignOutScheme = IdentityServerConstants.SignoutScheme;

                options.Authority = "https://demo.identityserver.io/";
                options.ClientId = "implicit";
                options.ResponseType = "id_token";
                options.SaveTokens = true;
                options.CallbackPath = new PathString("/signin-idsrv");
                options.SignedOutCallbackPath = new PathString("/signout-callback-idsrv");
                options.RemoteSignOutPath = new PathString("/signout-idsrv");

                options.TokenValidationParameters = new TokenValidationParameters
                {
                    NameClaimType = "name",
                    RoleClaimType = "role"
                };
            });
    }
}
```

**Figura 8-2**. Configurazione di IdentityServer.

IdentityServer ospita anche un sito demo pubblico che può essere usato per testare diversi protocolli e configurazioni. Si trova in [https://demo.identityserver.io/](https://demo.identityserver.io/) e include informazioni su come configurarne il comportamento in base al `client_id` fornito.

## <a name="javascript-clients"></a>Client JavaScript

Molte applicazioni native del Cloud sfruttano le API lato server e le applicazioni a pagina singola rich client (Spa) sul front-end. IdentityServer fornisce un [client JavaScript](http://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html) (`oidc-client.js`) tramite NPM che è possibile aggiungere alle Spa per consentire loro di usare IdentityServer per l'accesso, la disconnessione e l'autenticazione basata su token di API Web.

## <a name="references"></a>Riferimenti

- [Documentazione di IdentityServer](http://docs.identityserver.io/en/latest/)
- [Tipi di applicazioni](https://docs.microsoft.com/azure/active-directory/develop/app-types)
- [Client OIDC JavaScript](http://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html)

>[!div class="step-by-step"]
>[Precedente](azure-active-directory.md)
>[Successivo](security.md)
