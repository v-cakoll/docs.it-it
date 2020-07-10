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
# <a name="modules-handlers-and-middleware"></a><span data-ttu-id="9c9f2-103">Moduli, gestori e middleware</span><span class="sxs-lookup"><span data-stu-id="9c9f2-103">Modules, handlers, and middleware</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="9c9f2-104">Un'app ASP.NET Core si basa su una serie di *middleware*.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-104">An ASP.NET Core app is built upon a series of *middleware*.</span></span> <span data-ttu-id="9c9f2-105">Il middleware è costituito da gestori disposti in una pipeline per gestire le richieste e le risposte.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-105">Middleware is handlers that are arranged into a pipeline to handle requests and responses.</span></span> <span data-ttu-id="9c9f2-106">In un'app Web Form, i gestori e i moduli HTTP risolvono problemi simili.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-106">In a Web Forms app, HTTP handlers and modules solve similar problems.</span></span> <span data-ttu-id="9c9f2-107">In ASP.NET Core i moduli, i gestori, *Global.asax.cs*e il ciclo di vita dell'app vengono sostituiti con il middleware.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-107">In ASP.NET Core, modules, handlers, *Global.asax.cs*, and the app life cycle are replaced with middleware.</span></span> <span data-ttu-id="9c9f2-108">In questo capitolo verrà illustrato il middleware nel contesto di un' Blazor app.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-108">In this chapter, you'll learn what middleware in the context of a Blazor app.</span></span>

## <a name="overview"></a><span data-ttu-id="9c9f2-109">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9c9f2-109">Overview</span></span>

<span data-ttu-id="9c9f2-110">La pipeline delle richieste ASP.NET Core è costituita da una sequenza di delegati di richiesta, chiamati uno dopo l'altro.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-110">The ASP.NET Core request pipeline consists of a sequence of request delegates, called one after the other.</span></span> <span data-ttu-id="9c9f2-111">Il diagramma seguente illustra il concetto.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-111">The following diagram demonstrates the concept.</span></span> <span data-ttu-id="9c9f2-112">Il thread di esecuzione seguente le frecce nere.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-112">The thread of execution follows the black arrows.</span></span>

![pipeline](media/middleware/request-delegate-pipeline.png)

<span data-ttu-id="9c9f2-114">Il diagramma precedente non dispone di un concetto di eventi del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-114">The preceding diagram lacks a concept of lifecycle events.</span></span> <span data-ttu-id="9c9f2-115">Questo concetto è fondamentale per il modo in cui vengono gestite le richieste Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-115">This concept is foundational to how ASP.NET Web Forms requests are handled.</span></span> <span data-ttu-id="9c9f2-116">Questo sistema rende più semplice la motivazione del processo che si verifica e consente di inserire il middleware in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-116">This system makes it easier to reason about what process is occurring and allows middleware to be inserted at any point.</span></span> <span data-ttu-id="9c9f2-117">Il middleware viene eseguito nell'ordine in cui viene aggiunto alla pipeline della richiesta.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-117">Middleware executes in the order in which it's added to the request pipeline.</span></span> <span data-ttu-id="9c9f2-118">Vengono inoltre aggiunti nel codice anziché nei file di configurazione, in genere in *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-118">They're also added in code instead of configuration files, usually in *Startup.cs*.</span></span>

## <a name="katana"></a><span data-ttu-id="9c9f2-119">Katana</span><span class="sxs-lookup"><span data-stu-id="9c9f2-119">Katana</span></span>

<span data-ttu-id="9c9f2-120">I lettori che hanno familiarità con katana si troveranno a proprio agio in ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-120">Readers familiar with Katana will feel comfortable in ASP.NET Core.</span></span> <span data-ttu-id="9c9f2-121">Infatti, Katana è un Framework da cui deriva ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-121">In fact, Katana is a framework from which ASP.NET Core derives.</span></span> <span data-ttu-id="9c9f2-122">Sono stati introdotti modelli middleware e pipeline simili per ASP.NET 4. x.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-122">It introduced similar middleware and pipeline patterns for ASP.NET 4.x.</span></span> <span data-ttu-id="9c9f2-123">Il middleware progettato per Katana può essere adattato per funzionare con la pipeline ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-123">Middleware designed for Katana can be adapted to work with the ASP.NET Core pipeline.</span></span>

## <a name="common-middleware"></a><span data-ttu-id="9c9f2-124">Middleware comune</span><span class="sxs-lookup"><span data-stu-id="9c9f2-124">Common middleware</span></span>

<span data-ttu-id="9c9f2-125">ASP.NET 4. x include molti moduli.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-125">ASP.NET 4.x includes many modules.</span></span> <span data-ttu-id="9c9f2-126">In modo analogo, ASP.NET Core dispone anche di molti componenti middleware.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-126">In a similar fashion, ASP.NET Core has many middleware components available as well.</span></span> <span data-ttu-id="9c9f2-127">I moduli di IIS possono essere utilizzati in alcuni casi con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-127">IIS modules may be used in some cases with ASP.NET Core.</span></span> <span data-ttu-id="9c9f2-128">In altri casi, potrebbe essere disponibile il middleware ASP.NET Core nativo.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-128">In other cases, native ASP.NET Core middleware may be available.</span></span>

<span data-ttu-id="9c9f2-129">La tabella seguente elenca i componenti e il middleware di sostituzione in ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-129">The following table lists replacement middleware and components in ASP.NET Core.</span></span>

|<span data-ttu-id="9c9f2-130">Modulo</span><span class="sxs-lookup"><span data-stu-id="9c9f2-130">Module</span></span>                 |<span data-ttu-id="9c9f2-131">Modulo ASP.NET 4. x</span><span class="sxs-lookup"><span data-stu-id="9c9f2-131">ASP.NET 4.x module</span></span>           |<span data-ttu-id="9c9f2-132">Opzione ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9c9f2-132">ASP.NET Core option</span></span>|
|-----------------------|-----------------------------|-------------------|
|<span data-ttu-id="9c9f2-133">Errori HTTP</span><span class="sxs-lookup"><span data-stu-id="9c9f2-133">HTTP errors</span></span>            |`CustomErrorModule`          |[<span data-ttu-id="9c9f2-134">Middleware delle tabelle codici di stato</span><span class="sxs-lookup"><span data-stu-id="9c9f2-134">Status Code Pages Middleware</span></span>](/aspnet/core/fundamentals/error-handling#usestatuscodepages)|
|<span data-ttu-id="9c9f2-135">Documento predefinito</span><span class="sxs-lookup"><span data-stu-id="9c9f2-135">Default document</span></span>       |`DefaultDocumentModule`      |[<span data-ttu-id="9c9f2-136">Middleware dei file predefiniti</span><span class="sxs-lookup"><span data-stu-id="9c9f2-136">Default Files Middleware</span></span>](/aspnet/core/fundamentals/static-files#serve-a-default-document)|
|<span data-ttu-id="9c9f2-137">Esplorazione directory</span><span class="sxs-lookup"><span data-stu-id="9c9f2-137">Directory browsing</span></span>     |`DirectoryListingModule`     |[<span data-ttu-id="9c9f2-138">Middleware di esplorazione directory</span><span class="sxs-lookup"><span data-stu-id="9c9f2-138">Directory Browsing Middleware</span></span>](/aspnet/core/fundamentals/static-files#enable-directory-browsing)|
|<span data-ttu-id="9c9f2-139">Compressione dinamica</span><span class="sxs-lookup"><span data-stu-id="9c9f2-139">Dynamic compression</span></span>    |`DynamicCompressionModule`   |[<span data-ttu-id="9c9f2-140">Middleware di compressione delle risposte</span><span class="sxs-lookup"><span data-stu-id="9c9f2-140">Response Compression Middleware</span></span>](/aspnet/core/performance/response-compression)|
|<span data-ttu-id="9c9f2-141">Traccia richieste non riuscite</span><span class="sxs-lookup"><span data-stu-id="9c9f2-141">Failed requests tracing</span></span>|`FailedRequestsTracingModule`|[<span data-ttu-id="9c9f2-142">Registrazione ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9c9f2-142">ASP.NET Core Logging</span></span>](/aspnet/core/fundamentals/logging/index#tracesource-provider)|
|<span data-ttu-id="9c9f2-143">Memorizzazione nella cache di file</span><span class="sxs-lookup"><span data-stu-id="9c9f2-143">File caching</span></span>           |`FileCacheModule`            |[<span data-ttu-id="9c9f2-144">Middleware di memorizzazione nella cache delle risposte</span><span class="sxs-lookup"><span data-stu-id="9c9f2-144">Response Caching Middleware</span></span>](/aspnet/core/performance/caching/middleware)|
|<span data-ttu-id="9c9f2-145">Caching HTTP</span><span class="sxs-lookup"><span data-stu-id="9c9f2-145">HTTP caching</span></span>           |`HttpCacheModule`            |[<span data-ttu-id="9c9f2-146">Middleware di memorizzazione nella cache delle risposte</span><span class="sxs-lookup"><span data-stu-id="9c9f2-146">Response Caching Middleware</span></span>](/aspnet/core/performance/caching/middleware)|
|<span data-ttu-id="9c9f2-147">Registrazione HTTP</span><span class="sxs-lookup"><span data-stu-id="9c9f2-147">HTTP logging</span></span>           |`HttpLoggingModule`          |[<span data-ttu-id="9c9f2-148">Registrazione ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9c9f2-148">ASP.NET Core Logging</span></span>](/aspnet/core/fundamentals/logging/index)|
|<span data-ttu-id="9c9f2-149">Reindirizzamento HTTP</span><span class="sxs-lookup"><span data-stu-id="9c9f2-149">HTTP redirection</span></span>       |`HttpRedirectionModule`      |[<span data-ttu-id="9c9f2-150">Middleware di riscrittura URL</span><span class="sxs-lookup"><span data-stu-id="9c9f2-150">URL Rewriting Middleware</span></span>](/aspnet/core/fundamentals/url-rewriting)|
|<span data-ttu-id="9c9f2-151">Filtri ISAPI</span><span class="sxs-lookup"><span data-stu-id="9c9f2-151">ISAPI filters</span></span>          |`IsapiFilterModule`          |[<span data-ttu-id="9c9f2-152">Middleware</span><span class="sxs-lookup"><span data-stu-id="9c9f2-152">Middleware</span></span>](/aspnet/core/fundamentals/middleware/index)|
|<span data-ttu-id="9c9f2-153">ISAPI</span><span class="sxs-lookup"><span data-stu-id="9c9f2-153">ISAPI</span></span>                  |`IsapiModule`                |[<span data-ttu-id="9c9f2-154">Middleware</span><span class="sxs-lookup"><span data-stu-id="9c9f2-154">Middleware</span></span>](/aspnet/core/fundamentals/middleware/index)|
|<span data-ttu-id="9c9f2-155">Filtro richieste</span><span class="sxs-lookup"><span data-stu-id="9c9f2-155">Request filtering</span></span>      |`RequestFilteringModule`     |[<span data-ttu-id="9c9f2-156">IRule middleware di riscrittura URL</span><span class="sxs-lookup"><span data-stu-id="9c9f2-156">URL Rewriting Middleware IRule</span></span>](/aspnet/core/fundamentals/url-rewriting#irule-based-rule)|
|<span data-ttu-id="9c9f2-157">Riscrittura URL&#8224;</span><span class="sxs-lookup"><span data-stu-id="9c9f2-157">URL rewriting&#8224;</span></span>   |`RewriteModule`              |[<span data-ttu-id="9c9f2-158">Middleware di riscrittura URL</span><span class="sxs-lookup"><span data-stu-id="9c9f2-158">URL Rewriting Middleware</span></span>](/aspnet/core/fundamentals/url-rewriting)|
|<span data-ttu-id="9c9f2-159">Compressione statica</span><span class="sxs-lookup"><span data-stu-id="9c9f2-159">Static compression</span></span>     |`StaticCompressionModule`    |[<span data-ttu-id="9c9f2-160">Middleware di compressione delle risposte</span><span class="sxs-lookup"><span data-stu-id="9c9f2-160">Response Compression Middleware</span></span>](/aspnet/core/performance/response-compression)|
|<span data-ttu-id="9c9f2-161">Contenuto statico</span><span class="sxs-lookup"><span data-stu-id="9c9f2-161">Static content</span></span>         |`StaticFileModule`           |[<span data-ttu-id="9c9f2-162">Middleware dei file statici</span><span class="sxs-lookup"><span data-stu-id="9c9f2-162">Static File Middleware</span></span>](/aspnet/core/fundamentals/static-files)|
|<span data-ttu-id="9c9f2-163">Autorizzazione URL</span><span class="sxs-lookup"><span data-stu-id="9c9f2-163">URL authorization</span></span>      |`UrlAuthorizationModule`     |[<span data-ttu-id="9c9f2-164">Identità di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9c9f2-164">ASP.NET Core Identity</span></span>](/aspnet/core/security/authentication/identity)|

<span data-ttu-id="9c9f2-165">Questo elenco non è esaustivo, ma dovrebbe dare un'idea del mapping esistente tra i due Framework.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-165">This list isn't exhaustive but should give an idea of what mapping exists between the two frameworks.</span></span> <span data-ttu-id="9c9f2-166">Per un elenco più dettagliato, vedere [moduli IIS con ASP.NET Core](/aspnet/core/host-and-deploy/iis/modules).</span><span class="sxs-lookup"><span data-stu-id="9c9f2-166">For a more detailed list, see [IIS modules with ASP.NET Core](/aspnet/core/host-and-deploy/iis/modules).</span></span>

## <a name="custom-middleware"></a><span data-ttu-id="9c9f2-167">Middleware personalizzato</span><span class="sxs-lookup"><span data-stu-id="9c9f2-167">Custom middleware</span></span>

<span data-ttu-id="9c9f2-168">Il middleware incorporato potrebbe non gestire tutti gli scenari necessari per un'app.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-168">Built-in middleware may not handle all scenarios needed for an app.</span></span> <span data-ttu-id="9c9f2-169">In questi casi, è opportuno creare un middleware personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-169">In such cases, it makes sense to create your own middleware.</span></span> <span data-ttu-id="9c9f2-170">Esistono diversi modi per definire il middleware, più semplice è costituito da un semplice delegato.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-170">There are multiple ways of defining middleware, with the simplest being a simple delegate.</span></span> <span data-ttu-id="9c9f2-171">Si consideri il middleware seguente, che accetta una richiesta di impostazioni cultura da una stringa di query:</span><span class="sxs-lookup"><span data-stu-id="9c9f2-171">Consider the following middleware, which accepts a culture request from a query string:</span></span>

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

<span data-ttu-id="9c9f2-172">Il middleware può anche essere definito come classe, implementando l' `IMiddleware` interfaccia o seguendo la convenzione middleware.</span><span class="sxs-lookup"><span data-stu-id="9c9f2-172">Middleware can also be defined as class, either by implementing the `IMiddleware` interface or by following middleware convention.</span></span> <span data-ttu-id="9c9f2-173">Per ulteriori informazioni, vedere la pagina relativa alla [scrittura di middleware ASP.NET Core personalizzati](/aspnet/core/fundamentals/middleware/write).</span><span class="sxs-lookup"><span data-stu-id="9c9f2-173">For more information, see [Write custom ASP.NET Core middleware](/aspnet/core/fundamentals/middleware/write).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9c9f2-174">[Precedente](data.md) 
> [Avanti](config.md)</span><span class="sxs-lookup"><span data-stu-id="9c9f2-174">[Previous](data.md)
[Next](config.md)</span></span>
