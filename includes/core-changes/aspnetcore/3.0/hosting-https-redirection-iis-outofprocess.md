---
ms.openlocfilehash: eb3fa768a491f6c0ff4b15479beabd71b0670338
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937267"
---
### <a name="hosting-https-redirection-enabled-for-iis-out-of-process-apps"></a>Hosting: reindirizzamento HTTPS abilitato per le app out-of-process di IIS

La versione 13.0.19218.0 del [modulo di ASP.NET Core (modulo ASP.NET Core)](/aspnet/core/host-and-deploy/aspnet-core-module) per l'hosting tramite IIS out-of-process Abilita una funzionalità di reindirizzamento HTTPS esistente per le app ASP.NET Core 3,0 e 2,2.

Per informazioni, vedere [DotNet/AspNetCore # 15243](https://github.com/dotnet/AspNetCore/issues/15243).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Il modello di progetto ASP.NET Core 2,1 ha introdotto per la prima volta il supporto per i metodi middleware HTTPS come <xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A> e <xref:Microsoft.AspNetCore.Builder.HstsBuilderExtensions.UseHsts%2A>. L'abilitazione del reindirizzamento HTTPS richiede l'aggiunta della configurazione, perché le app in fase di sviluppo non usano la porta predefinita 443. La [sicurezza del trasporto http Strict (HSTS)](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html) è attiva solo se la richiesta usa già HTTPS. Localhost viene ignorato per impostazione predefinita.

#### <a name="new-behavior"></a>Nuovo comportamento

In ASP.NET Core 3,0 lo scenario HTTPS di IIS è stato [migliorato](https://github.com/dotnet/AspNetCore/pull/4685). Con il miglioramento, un'app potrebbe individuare le porte HTTPS del server e rendere `UseHttpsRedirection` lavoro per impostazione predefinita. Il componente in-process ha eseguito l'individuazione delle porte con la funzionalità `IServerAddresses`, che influiscono solo sulle app ASP.NET Core 3,0, perché la libreria in-process ha una versione con il Framework. Il componente out-of-process è stato modificato per aggiungere automaticamente la variabile di ambiente `ASPNETCORE_HTTPS_PORT`. Questa modifica ha interessato entrambe le app ASP.NET Core 2,2 e 3,0 perché il componente out-of-process è condiviso a livello globale. ASP.NET Core 2,1 le app non sono interessate perché usano una versione precedente di modulo ASP.NET Core per impostazione predefinita.

Il comportamento precedente è stato modificato in ASP.NET Core 3.0.1 e 3.1.0 Preview 3 per annullare le modifiche del comportamento in ASP.NET Core 2. x. Queste modifiche influiscono solo sulle app IIS out-of-process.

Come descritto in precedenza, l'installazione di ASP.NET Core 3.0.0 ha avuto effetto collaterale anche sull'attivazione del middleware `UseHttpsRedirection` nelle app ASP.NET Core 2. x. È stata apportata una modifica a modulo ASP.NET Core in ASP.NET Core 3.0.1 e 3.1.0 Preview 3, in modo che l'installazione non abbia più questo effetto sulle app ASP.NET Core 2. x. La variabile di ambiente `ASPNETCORE_HTTPS_PORT` in cui modulo ASP.NET Core è stata popolata ASP.NET Core 3.0.0 è stata modificata in `ASPNETCORE_ANCM_HTTPS_PORT` ASP.NET Core 3.0.1 e 3.1.0 Preview 3. `UseHttpsRedirection` è stato aggiornato anche in queste versioni per comprendere le variabili nuove e obsolete. ASP.NET Core 2. x non verrà aggiornato. Di conseguenza, viene ripristinato il comportamento precedente di disabilitato per impostazione predefinita.

#### <a name="reason-for-change"></a>Motivo della modifica

Miglioramento della funzionalità ASP.NET Core 3,0.

#### <a name="recommended-action"></a>Azione consigliata

Non è richiesta alcuna azione se si desidera che tutti i client usino HTTPS. Per consentire l'uso di HTTP da parte dei client, eseguire una delle operazioni seguenti:

* Rimuovere le chiamate a `UseHttpsRedirection` e `UseHsts` dal metodo di `Startup.Configure` del progetto e ridistribuire l'app.
* Nel file *Web. config* , impostare la variabile di ambiente `ASPNETCORE_HTTPS_PORT` su una stringa vuota. Questa modifica può verificarsi direttamente nel server senza ridistribuire l'app. Ad esempio:

    ```xml
    <aspNetCore processPath="dotnet" arguments=".\WebApplication3.dll" stdoutLogEnabled="false" stdoutLogFile="\\?\%home%\LogFiles\stdout" >
        <environmentVariables>
        <environmentVariable name="ASPNETCORE_HTTPS_PORT" value="" />
        </environmentVariables>
    </aspNetCore>
    ```

`UseHttpsRedirection` può essere ancora:

* Attivato manualmente in ASP.NET Core 2. x impostando la variabile di ambiente `ASPNETCORE_HTTPS_PORT` sul numero di porta appropriato (443 nella maggior parte degli scenari di produzione).
* Disattivato in ASP.NET Core 3. x definendo `ASPNETCORE_ANCM_HTTPS_PORT` con un valore di stringa vuoto. Questo valore viene impostato in modo analogo all'esempio di `ASPNETCORE_HTTPS_PORT` precedente.

I computer che eseguono ASP.NET Core app 3.0.0 devono installare il runtime ASP.NET Core 3.0.1 prima di installare il ASP.NET Core 3.1.0 Preview 3 modulo ASP.NET Core. In questo modo si garantisce che `UseHttpsRedirection` continui a funzionare come previsto per le app ASP.NET Core 3,0.

Nel servizio app Azure, modulo ASP.NET Core viene distribuito in base a una pianificazione separata dal runtime a causa della sua natura globale. MODULO ASP.NET Core è stato distribuito in Azure con queste modifiche dopo la distribuzione di ASP.NET Core 3.0.1 e 3.1.0.

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)`

-->
