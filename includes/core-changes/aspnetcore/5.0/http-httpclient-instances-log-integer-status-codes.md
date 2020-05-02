---
ms.openlocfilehash: 44d33fb28e66e590e4604c6dd2c73616e4c5e943
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728283"
---
### <a name="http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes"></a><span data-ttu-id="8dd92-101">HTTP: HttpClient istanze create dai codici di stato IHttpClientFactory log Integer</span><span class="sxs-lookup"><span data-stu-id="8dd92-101">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>

<span data-ttu-id="8dd92-102"><xref:System.Net.Http.HttpClient>istanze create dai <xref:System.Net.Http.IHttpClientFactory> codici di stato http di log come numeri interi anziché con i nomi dei codici di stato.</span><span class="sxs-lookup"><span data-stu-id="8dd92-102"><xref:System.Net.Http.HttpClient> instances created by <xref:System.Net.Http.IHttpClientFactory> log HTTP status codes as integers instead of with status code names.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8dd92-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="8dd92-103">Version introduced</span></span>

<span data-ttu-id="8dd92-104">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="8dd92-104">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="8dd92-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="8dd92-105">Old behavior</span></span>

<span data-ttu-id="8dd92-106">La registrazione usa le descrizioni testuali dei codici di stato HTTP.</span><span class="sxs-lookup"><span data-stu-id="8dd92-106">Logging uses the textual descriptions of HTTP status codes.</span></span> <span data-ttu-id="8dd92-107">Si considerino i messaggi di log seguenti:</span><span class="sxs-lookup"><span data-stu-id="8dd92-107">Consider the following log messages:</span></span>

```
Received HTTP response after 56.0044ms - OK
End processing HTTP request after 70.0862ms - OK
```

#### <a name="new-behavior"></a><span data-ttu-id="8dd92-108">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="8dd92-108">New behavior</span></span>

<span data-ttu-id="8dd92-109">La registrazione usa i valori integer dei codici di stato HTTP.</span><span class="sxs-lookup"><span data-stu-id="8dd92-109">Logging uses the integer values of HTTP status codes.</span></span> <span data-ttu-id="8dd92-110">Si considerino i messaggi di log seguenti:</span><span class="sxs-lookup"><span data-stu-id="8dd92-110">Consider the following log messages:</span></span>

```
Received HTTP response after 56.0044ms - 200
End processing HTTP request after 70.0862ms - 200
```

#### <a name="reason-for-change"></a><span data-ttu-id="8dd92-111">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="8dd92-111">Reason for change</span></span>

<span data-ttu-id="8dd92-112">Il comportamento originale di questa registrazione è incoerente con altre parti di ASP.NET Core che hanno sempre usato valori integer.</span><span class="sxs-lookup"><span data-stu-id="8dd92-112">The original behavior of this logging is inconsistent with other parts of ASP.NET Core that have always used integer values.</span></span> <span data-ttu-id="8dd92-113">L'incoerenza rende i log difficili da eseguire per eseguire query tramite sistemi di registrazione strutturati, ad esempio [elasticsearch](https://www.elastic.co/elasticsearch/).</span><span class="sxs-lookup"><span data-stu-id="8dd92-113">The inconsistency makes logs difficult to query via structured logging systems such as [Elasticsearch](https://www.elastic.co/elasticsearch/).</span></span> <span data-ttu-id="8dd92-114">Per altri contesti, vedere [DotNet/Extensions # 1549](https://github.com/dotnet/extensions/issues/1549).</span><span class="sxs-lookup"><span data-stu-id="8dd92-114">For more context, see [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549).</span></span>

<span data-ttu-id="8dd92-115">L'utilizzo di valori integer è più flessibile del testo perché consente l'esecuzione di query su intervalli di valori.</span><span class="sxs-lookup"><span data-stu-id="8dd92-115">Using integer values is more flexible than text because it allows queries on ranges of values.</span></span>

<span data-ttu-id="8dd92-116">È stato preso in considerazione l'aggiunta di un altro valore di log per acquisire il codice di stato Integer.</span><span class="sxs-lookup"><span data-stu-id="8dd92-116">Adding another log value to capture the integer status code was considered.</span></span> <span data-ttu-id="8dd92-117">Sfortunatamente, questa operazione introdurrebbe un'altra incoerenza con il resto del ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="8dd92-117">Unfortunately, doing so would introduce another inconsistency with the rest of ASP.NET Core.</span></span> <span data-ttu-id="8dd92-118">La registrazione HttpClient e la registrazione di server/hosting HTTP `StatusCode` usano già lo stesso nome di chiave.</span><span class="sxs-lookup"><span data-stu-id="8dd92-118">HttpClient logging and HTTP server/hosting logging use the same `StatusCode` key name already.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8dd92-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="8dd92-119">Recommended action</span></span>

<span data-ttu-id="8dd92-120">L'opzione migliore consiste nell'aggiornare le query di registrazione per usare i valori integer dei codici di stato.</span><span class="sxs-lookup"><span data-stu-id="8dd92-120">The best option is to update logging queries to use the integer values of status codes.</span></span> <span data-ttu-id="8dd92-121">Questa opzione può causare difficoltà nella scrittura di query in più versioni ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="8dd92-121">This option may cause some difficulty writing queries across multiple ASP.NET Core versions.</span></span> <span data-ttu-id="8dd92-122">Tuttavia, l'utilizzo di numeri interi a questo scopo è molto più flessibile per l'esecuzione di query sui log.</span><span class="sxs-lookup"><span data-stu-id="8dd92-122">However, using integers for this purpose is much more flexible for querying logs.</span></span>

<span data-ttu-id="8dd92-123">Se è necessario forzare la compatibilità con il comportamento precedente e usare i codici di stato testuale `IHttpClientFactory` , sostituire la registrazione con i propri:</span><span class="sxs-lookup"><span data-stu-id="8dd92-123">If you need to force compatibility with the old behavior and use textual status codes, replace the `IHttpClientFactory` logging with your own:</span></span>

1. <span data-ttu-id="8dd92-124">Copiare le versioni di .NET Core 3,1 delle classi seguenti nel progetto:</span><span class="sxs-lookup"><span data-stu-id="8dd92-124">Copy the .NET Core 3.1 versions of the following classes into your project:</span></span>

    * [<span data-ttu-id="8dd92-125">LoggingHttpMessageHandlerBuilderFilter</span><span class="sxs-lookup"><span data-stu-id="8dd92-125">LoggingHttpMessageHandlerBuilderFilter</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandlerBuilderFilter.cs)
    * [<span data-ttu-id="8dd92-126">LoggingHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="8dd92-126">LoggingHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandler.cs)
    * [<span data-ttu-id="8dd92-127">LoggingScopeHttpMessageHandler</span><span class="sxs-lookup"><span data-stu-id="8dd92-127">LoggingScopeHttpMessageHandler</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingScopeHttpMessageHandler.cs)
    * [<span data-ttu-id="8dd92-128">HttpHeadersLogValue</span><span class="sxs-lookup"><span data-stu-id="8dd92-128">HttpHeadersLogValue</span></span>](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/HttpHeadersLogValue.cs)

1. <span data-ttu-id="8dd92-129">Rinominare le classi per evitare conflitti con i tipi pubblici nel pacchetto NuGet [Microsoft. Extensions. http](https://www.nuget.org/packages/Microsoft.Extensions.Http) .</span><span class="sxs-lookup"><span data-stu-id="8dd92-129">Rename the classes to avoid conflicts with public types in the [Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http) NuGet package.</span></span>

1. <span data-ttu-id="8dd92-130">Sostituire l'implementazione predefinita di `LoggingHttpMessageHandlerBuilderFilter` con una propria nel `Startup.ConfigureServices` metodo del progetto.</span><span class="sxs-lookup"><span data-stu-id="8dd92-130">Replace the built-in implementation of `LoggingHttpMessageHandlerBuilderFilter` with your own in the project's `Startup.ConfigureServices` method.</span></span> <span data-ttu-id="8dd92-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8dd92-131">For example:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        // Other service registrations go first. Code omitted for brevity.

        // Place the following after all AddHttpClient registrations.
        var descriptors = services.Where(
            s => s.ServiceType == typeof(IHttpMessageHandlerBuilderFilter));
        foreach (var descriptor in descriptors)
        {
            services.Remove(descriptor);
        }

        services.AddSingleton<IHttpMessageHandlerBuilderFilter,
                              MyLoggingHttpMessageHandlerBuilderFilter>();
    }
    ```

#### <a name="category"></a><span data-ttu-id="8dd92-132">Category</span><span class="sxs-lookup"><span data-stu-id="8dd92-132">Category</span></span>

<span data-ttu-id="8dd92-133">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8dd92-133">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8dd92-134">API interessate</span><span class="sxs-lookup"><span data-stu-id="8dd92-134">Affected APIs</span></span>

<xref:System.Net.Http.HttpClient?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:System.Net.Http.HttpClient`

-->
