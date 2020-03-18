---
ms.openlocfilehash: eb3fa768a491f6c0ff4b15479beabd71b0670338
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937267"
---
### <a name="hosting-https-redirection-enabled-for-iis-out-of-process-apps"></a>Hosting: reindirizzamento HTTPS abilitato per le app out-of-process di IISHosting: HTTPS redirection enabled for IIS out-of-process apps

La versione 13.0.19218.0 del [modulo ASP.NET Core Module (ANCM)](/aspnet/core/host-and-deploy/aspnet-core-module) per l'hosting tramite Out-of-process di IIS abilita una funzionalità di reindirizzamento HTTPS esistente per ASP.NET le app Core 3.0 e 2.2.

Per una discussione, vedere [dotnet/AspNetCore-15243](https://github.com/dotnet/AspNetCore/issues/15243).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Il modello di progetto ASP.NET Core 2.1 ha <xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A> <xref:Microsoft.AspNetCore.Builder.HstsBuilderExtensions.UseHsts%2A>introdotto per la prima volta il supporto per i metodi middleware HTTPS come e . L'abilitazione del reindirizzamento HTTPS richiedeva l'aggiunta della configurazione, poiché le app in fase di sviluppo non usano la porta predefinita 443. [HTTP Strict Transport Security (HSTS)](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html) è attivo solo se la richiesta utilizza già HTTPS. Localhost viene ignorato per impostazione predefinita.

#### <a name="new-behavior"></a>Nuovo comportamento

In ASP.NET Core 3.0, lo scenario HTTPS di IIS è stato [migliorato.](https://github.com/dotnet/AspNetCore/pull/4685) Con il miglioramento, un'app potrebbe individuare le `UseHttpsRedirection` porte HTTPS del server e rendere il lavoro di default. Il componente in-process ha eseguito l'individuazione delle porte con la `IServerAddresses` funzionalità, che interessa solo ASP.NET applicazioni Core 3.0 perché la libreria in-process è sottoposta a controllo del framework. Componente out-of-process modificato per `ASPNETCORE_HTTPS_PORT` aggiungere automaticamente la variabile di ambiente. Questa modifica ha interessato sia ASP.NET applicazioni Core 2.2 e 3.0 perché il componente out-of-process è condiviso a livello globale. ASP.NET core 2.1 le app non sono interessate perché usano una versione precedente di ANCM per impostazione predefinita.

Il comportamento precedente è stato modificato in ASP.NET Core 3.0.1 e 3.1.0 Preview 3 per annullare le modifiche di comportamento in ASP.NET Core 2.x. Queste modifiche interessano solo le app out-of-process di IIS.

Come descritto in precedenza, l'installazione di ASP.NET Core 3.0.0 ha avuto l'effetto collaterale di attivare anche il `UseHttpsRedirection` middleware nelle app ASP.NET Core 2.x. È stata apportata una modifica ad ANCM in ASP.NET Core 3.0.1 e 3.1.0 Preview 3 in modo che l'installazione non abbia più questo effetto sulle app di ASP.NET Core 2.x. La `ASPNETCORE_HTTPS_PORT` variabile di ambiente popolata da ANCM in `ASPNETCORE_ANCM_HTTPS_PORT` ASP.NET Core 3.0.0 è stata modificata in ASP.NET Core 3.0.1 e 3.1.0 Preview 3. `UseHttpsRedirection`è stato anche aggiornato in queste versioni per comprendere sia le variabili nuove che vecchie. ASP.NET Core 2.x non verrà aggiornato. Di conseguenza, viene ripristinato il comportamento precedente di essere disabilitato per impostazione predefinita.

#### <a name="reason-for-change"></a>Motivo della modifica

Migliorata ASP.NET funzionalità di Core 3.0.

#### <a name="recommended-action"></a>Azione consigliata

Non è richiesta alcuna azione se si desidera che tutti i client utilizzino HTTPS. Per consentire ad alcuni client di utilizzare HTTP, eseguire una delle operazioni seguenti:

* Rimuovere le `UseHttpsRedirection` chiamate `UseHsts` da e `Startup.Configure` verso il metodo del progetto e ridistribuire l'app.
* Nel file *web.config* impostare la `ASPNETCORE_HTTPS_PORT` variabile di ambiente su una stringa vuota. Questa modifica può verificarsi direttamente sul server senza ridistribuire l'app. Ad esempio:

    ```xml
    <aspNetCore processPath="dotnet" arguments=".\WebApplication3.dll" stdoutLogEnabled="false" stdoutLogFile="\\?\%home%\LogFiles\stdout" >
        <environmentVariables>
        <environmentVariable name="ASPNETCORE_HTTPS_PORT" value="" />
        </environmentVariables>
    </aspNetCore>
    ```

`UseHttpsRedirection`può ancora essere:

* Attivato manualmente in ASP.NET Core 2.x impostando la `ASPNETCORE_HTTPS_PORT` variabile di ambiente sul numero di porta appropriato (443 nella maggior parte degli scenari di produzione).
* Disattivato in ASP.NET Core 3.x definendo `ASPNETCORE_ANCM_HTTPS_PORT` con un valore di stringa vuota. Questo valore viene impostato nello stesso `ASPNETCORE_HTTPS_PORT` modo dell'esempio precedente.

I computer che eseguono ASP.NET app Core 3.0.0 devono installare il runtime ASP.NET Core 3.0.1 prima di installare l'ANCM di ASP.NET Core 3.1.0 Preview 3. In questo modo `UseHttpsRedirection` si garantisce che continui a funzionare come previsto per le app ASP.NET Core 3.0.

Nel servizio app di Azure ANCM viene distribuito in base a una pianificazione separata dal runtime a causa della sua natura globale. ANCM è stato distribuito in Azure con queste modifiche dopo ASP.NET Core 3.0.1 e 3.1.0 sono stati distribuiti.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)`

-->
