---
title: Moduli, gestori e middleware
description: Informazioni sulla gestione delle richieste HTTP con moduli, gestori e middleware.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 10/11/2019
ms.openlocfilehash: ff2b3fd41316a1c8c20a0eed9a585e5fd2733af3
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173185"
---
# <a name="modules-handlers-and-middleware"></a>Moduli, gestori e middleware

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Un'app ASP.NET Core si basa su una serie di *middleware*. Il middleware è costituito da gestori disposti in una pipeline per gestire le richieste e le risposte. In un'app Web Form, i gestori e i moduli HTTP risolvono problemi simili. In ASP.NET Core i moduli, i gestori, *Global.asax.cs*e il ciclo di vita dell'app vengono sostituiti con il middleware. In questo capitolo verrà illustrato il middleware nel contesto di un' Blazor app.

## <a name="overview"></a>Panoramica

La pipeline delle richieste ASP.NET Core è costituita da una sequenza di delegati di richiesta, chiamati uno dopo l'altro. Il diagramma seguente illustra il concetto. Il thread di esecuzione seguente le frecce nere.

![pipeline](media/middleware/request-delegate-pipeline.png)

Il diagramma precedente non dispone di un concetto di eventi del ciclo di vita. Questo concetto è fondamentale per il modo in cui vengono gestite le richieste Web Form ASP.NET. Questo sistema rende più semplice la motivazione del processo che si verifica e consente di inserire il middleware in qualsiasi momento. Il middleware viene eseguito nell'ordine in cui viene aggiunto alla pipeline della richiesta. Vengono inoltre aggiunti nel codice anziché nei file di configurazione, in genere in *Startup.cs*.

## <a name="katana"></a>Katana

I lettori che hanno familiarità con katana si troveranno a proprio agio in ASP.NET Core. Infatti, Katana è un Framework da cui deriva ASP.NET Core. Sono stati introdotti modelli middleware e pipeline simili per ASP.NET 4. x. Il middleware progettato per Katana può essere adattato per funzionare con la pipeline ASP.NET Core.

## <a name="common-middleware"></a>Middleware comune

ASP.NET 4. x include molti moduli. In modo analogo, ASP.NET Core dispone anche di molti componenti middleware. I moduli di IIS possono essere utilizzati in alcuni casi con ASP.NET Core. In altri casi, potrebbe essere disponibile il middleware ASP.NET Core nativo.

La tabella seguente elenca i componenti e il middleware di sostituzione in ASP.NET Core.

|Modulo                 |Modulo ASP.NET 4. x           |Opzione ASP.NET Core|
|-----------------------|-----------------------------|-------------------|
|Errori HTTP            |`CustomErrorModule`          |[Middleware delle tabelle codici di stato](/aspnet/core/fundamentals/error-handling#usestatuscodepages)|
|Documento predefinito       |`DefaultDocumentModule`      |[Middleware dei file predefiniti](/aspnet/core/fundamentals/static-files#serve-a-default-document)|
|Esplorazione directory     |`DirectoryListingModule`     |[Middleware di esplorazione directory](/aspnet/core/fundamentals/static-files#enable-directory-browsing)|
|Compressione dinamica    |`DynamicCompressionModule`   |[Middleware di compressione delle risposte](/aspnet/core/performance/response-compression)|
|Traccia richieste non riuscite|`FailedRequestsTracingModule`|[Registrazione ASP.NET Core](/aspnet/core/fundamentals/logging/index#tracesource-provider)|
|Memorizzazione nella cache di file           |`FileCacheModule`            |[Middleware di memorizzazione nella cache delle risposte](/aspnet/core/performance/caching/middleware)|
|Caching HTTP           |`HttpCacheModule`            |[Middleware di memorizzazione nella cache delle risposte](/aspnet/core/performance/caching/middleware)|
|Registrazione HTTP           |`HttpLoggingModule`          |[Registrazione ASP.NET Core](/aspnet/core/fundamentals/logging/index)|
|Reindirizzamento HTTP       |`HttpRedirectionModule`      |[Middleware di riscrittura URL](/aspnet/core/fundamentals/url-rewriting)|
|Filtri ISAPI          |`IsapiFilterModule`          |[Middleware](/aspnet/core/fundamentals/middleware/index)|
|ISAPI                  |`IsapiModule`                |[Middleware](/aspnet/core/fundamentals/middleware/index)|
|Filtro richieste      |`RequestFilteringModule`     |[IRule middleware di riscrittura URL](/aspnet/core/fundamentals/url-rewriting#irule-based-rule)|
|Riscrittura URL&#8224;   |`RewriteModule`              |[Middleware di riscrittura URL](/aspnet/core/fundamentals/url-rewriting)|
|Compressione statica     |`StaticCompressionModule`    |[Middleware di compressione delle risposte](/aspnet/core/performance/response-compression)|
|Contenuto statico         |`StaticFileModule`           |[Middleware dei file statici](/aspnet/core/fundamentals/static-files)|
|Autorizzazione URL      |`UrlAuthorizationModule`     |[Identità di ASP.NET Core](/aspnet/core/security/authentication/identity)|

Questo elenco non è esaustivo, ma dovrebbe dare un'idea del mapping esistente tra i due Framework. Per un elenco più dettagliato, vedere [moduli IIS con ASP.NET Core](/aspnet/core/host-and-deploy/iis/modules).

## <a name="custom-middleware"></a>Middleware personalizzato

Il middleware incorporato potrebbe non gestire tutti gli scenari necessari per un'app. In questi casi, è opportuno creare un middleware personalizzato. Esistono diversi modi per definire il middleware, più semplice è costituito da un semplice delegato. Si consideri il middleware seguente, che accetta una richiesta di impostazioni cultura da una stringa di query:

```csharp
public class Startup
{
    public void Configure(IApplicationBuilder app)
    {
        app.Use(async (context, next) =>
        {
            var cultureQuery = context.Request.Query["culture"];

            if (!string.IsNullOrWhiteSpace(cultureQuery))
            {
                var culture = new CultureInfo(cultureQuery);

                CultureInfo.CurrentCulture = culture;
                CultureInfo.CurrentUICulture = culture;
            }

            // Call the next delegate/middleware in the pipeline
            await next();
        });

        app.Run(async (context) =>
            await context.Response.WriteAsync(
                $"Hello {CultureInfo.CurrentCulture.DisplayName}"));
    }
}
```

Il middleware può anche essere definito come classe, implementando l' `IMiddleware` interfaccia o seguendo la convenzione middleware. Per ulteriori informazioni, vedere la pagina relativa alla [scrittura di middleware ASP.NET Core personalizzati](/aspnet/core/fundamentals/middleware/write).

>[!div class="step-by-step"]
>[Precedente](data.md) 
> [Avanti](config.md)
