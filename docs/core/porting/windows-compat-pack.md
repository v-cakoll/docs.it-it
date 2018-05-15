---
title: Conversione per .NET Core - Uso di Windows Compatibility Pack
description: Informazioni su Windows Compatibility Pack e su come è possibile usarlo per la conversione di codice .NET Framework esistente per .NET Core
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.openlocfilehash: 6b25a2d5c197a6c9b0a7ead18370870ddc091e1c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-windows-compatibility-pack"></a><span data-ttu-id="fa266-103">Uso di Windows Compatibility Pack</span><span class="sxs-lookup"><span data-stu-id="fa266-103">Using the Windows Compatibility Pack</span></span>

<span data-ttu-id="fa266-104">Uno dei problemi più comuni che si trovano ad affrontare gli sviluppatori durante la conversione del codice esistente per .NET Core è la dipendenza da API e tecnologie che esistono solo in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fa266-104">One of the most common issues that developers face when porting their existing code to .NET Core is that they depend on APIs and technologies that only exist in the .NET Framework.</span></span> <span data-ttu-id="fa266-105">Scopo di *Windows Compatibility Pack* è fornire molte di queste tecnologie in modo che la creazione di applicazioni .NET Core, nonché di librerie .NET Standard, diventi molto più praticabile per il codice esistente.</span><span class="sxs-lookup"><span data-stu-id="fa266-105">The *Windows Compatibility Pack* is about providing many of these technologies so that building .NET Core applications as well as .NET Standard libraries becomes much more viable for existing code.</span></span>

<span data-ttu-id="fa266-106">Questo pacchetto è un'[estensione logica di .NET 2.0 Standard](../whats-new/index.md#api-changes-and-library-support) che incrementa in modo significativo il set di API e consente la compilazione di codice esistente praticamente senza modifiche.</span><span class="sxs-lookup"><span data-stu-id="fa266-106">This package is a logical [extension of .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support) that significantly increases API set and existing code compiles with almost no modifications.</span></span> <span data-ttu-id="fa266-107">Tuttavia, per rispettare i principi di .NET Standard ("è il set di API fornite da tutte le implementazioni .NET"), questo pacchetto non include tecnologie che non funzionano in tutte le piattaforme, ad esempio le API per Registro di sistema, Strumentazione gestione Windows (WMI) o reflection emit.</span><span class="sxs-lookup"><span data-stu-id="fa266-107">But in order to keep the promise of .NET Standard ("it is the set of APIs that all .NET implementations provide"), this didn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span>

<span data-ttu-id="fa266-108">*Windows Compatibility Pack* si sovrappone a .NET Standard e consente l'accesso a tecnologie solo Windows.</span><span class="sxs-lookup"><span data-stu-id="fa266-108">The *Windows Compatibility Pack* sits on top of .NET Standard and provides access to technologies that are Windows only.</span></span> <span data-ttu-id="fa266-109">È particolarmente utile per i clienti che vogliono passare a .NET Core ma prevedono di rimanere sulla piattaforma Windows come primo passo.</span><span class="sxs-lookup"><span data-stu-id="fa266-109">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows as a first step.</span></span> <span data-ttu-id="fa266-110">In questo scenario, l'impossibilità di usare tecnologie solo Windows è solo un ostacolo per la migrazione senza alcun vantaggio a livello di architettura.</span><span class="sxs-lookup"><span data-stu-id="fa266-110">In that scenario, not being able to use Windows-only technologies is only a migration hurdle with zero architectural benefits.</span></span>

## <a name="package-contents"></a><span data-ttu-id="fa266-111">Contenuto del pacchetto</span><span class="sxs-lookup"><span data-stu-id="fa266-111">Package contents</span></span>

<span data-ttu-id="fa266-112">*Windows Compatibility Pack* viene fornito tramite il pacchetto NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) ed è possibile farvi riferimento dai progetti destinati a .NET Core o .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="fa266-112">The *Windows Compatibility Pack* is provided via the NuGet Package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects targeting .NET Core or .NET Standard.</span></span>

<span data-ttu-id="fa266-113">Include circa 20.000 API, incluse API solo per Windows e API multipiattaforma per le aree tecnologiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa266-113">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

* <span data-ttu-id="fa266-114">Tabelle codici</span><span class="sxs-lookup"><span data-stu-id="fa266-114">Code Pages</span></span>
* <span data-ttu-id="fa266-115">CodeDom</span><span class="sxs-lookup"><span data-stu-id="fa266-115">CodeDom</span></span>
* <span data-ttu-id="fa266-116">Configurazione</span><span class="sxs-lookup"><span data-stu-id="fa266-116">Configuration</span></span>
* <span data-ttu-id="fa266-117">Servizi directory</span><span class="sxs-lookup"><span data-stu-id="fa266-117">Directory Services</span></span>
* <span data-ttu-id="fa266-118">Disegno</span><span class="sxs-lookup"><span data-stu-id="fa266-118">Drawing</span></span>
* <span data-ttu-id="fa266-119">ODBC</span><span class="sxs-lookup"><span data-stu-id="fa266-119">ODBC</span></span>
* <span data-ttu-id="fa266-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="fa266-120">Permissions</span></span>
* <span data-ttu-id="fa266-121">Porte</span><span class="sxs-lookup"><span data-stu-id="fa266-121">Ports</span></span>
* <span data-ttu-id="fa266-122">Elenchi di controllo degli accessi (ACL) di Windows</span><span class="sxs-lookup"><span data-stu-id="fa266-122">Windows Access Control Lists (ACL)</span></span>
* <span data-ttu-id="fa266-123">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="fa266-123">Windows Communication Foundation (WCF)</span></span>
* <span data-ttu-id="fa266-124">Crittografia di Windows</span><span class="sxs-lookup"><span data-stu-id="fa266-124">Windows Cryptography</span></span>
* <span data-ttu-id="fa266-125">Registro eventi di Windows</span><span class="sxs-lookup"><span data-stu-id="fa266-125">Windows EventLog</span></span>
* <span data-ttu-id="fa266-126">Strumentazione gestione Windows (WMI, Windows Management Instrumentation)</span><span class="sxs-lookup"><span data-stu-id="fa266-126">Windows Management Instrumentation (WMI)</span></span>
* <span data-ttu-id="fa266-127">Contatori delle prestazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="fa266-127">Windows Performance Counters</span></span>
* <span data-ttu-id="fa266-128">Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="fa266-128">Windows Registry</span></span>
* <span data-ttu-id="fa266-129">Memorizzazione nella cache di Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="fa266-129">Windows Runtime Caching</span></span>
* <span data-ttu-id="fa266-130">servizi Windows</span><span class="sxs-lookup"><span data-stu-id="fa266-130">Windows Services</span></span>

<span data-ttu-id="fa266-131">Per altre informazioni, vedere le [specifiche del pacchetto di compatibilità](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="fa266-131">For more information, see the [spec of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="fa266-132">Introduzione</span><span class="sxs-lookup"><span data-stu-id="fa266-132">Get started</span></span>

1. <span data-ttu-id="fa266-133">Prima di procedere alla conversione, assicurarsi di esaminare il [processo di conversione](index.md).</span><span class="sxs-lookup"><span data-stu-id="fa266-133">Before porting, make sure to take a look at the [Porting Process](index.md).</span></span>

2. <span data-ttu-id="fa266-134">Per la conversione di codice esistente per .NET Core o .NET Standard, installare il pacchetto NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span><span class="sxs-lookup"><span data-stu-id="fa266-134">When porting existing code to .NET Core or .NET Standard, install the NuGet package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

3. <span data-ttu-id="fa266-135">Se si desidera rimanere in ambiente Windows, questo è tutto.</span><span class="sxs-lookup"><span data-stu-id="fa266-135">If you want to stay on Windows, you're all set.</span></span>

4. <span data-ttu-id="fa266-136">Se si vuole eseguire l'applicazione .NET Core o la libreria .NET Standard in Linux o macOS, usare l'[analizzatore delle API](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) per trovare informazioni sull'utilizzo delle API non supportato in tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="fa266-136">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) to find usage of APIs that won't work cross-platform.</span></span>

5. <span data-ttu-id="fa266-137">Rimuovere questi utilizzi di tali API, sostituirli con alternative multipiattaforma o proteggerli con un controllo di piattaforma, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fa266-137">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

    ```csharp
    private static string GetLoggingPath()
    {
        // Verify the code is running on Windows.
        if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
        {
            using (var key = Registry.CurrentUser.OpenSubKey(@"Software\Fabrikam\AssetManagement"))
            {
                if (key?.GetValue("LoggingDirectoryPath") is string configuredPath)
                    return configuredPath;
            }
        }

        // This is either not running on Windows or no logging path was configured,
        // so just use the path for non-roaming user-specific data files.
        var appDataPath = Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData);
        return Path.Combine(appDataPath, "Fabrikam", "AssetManagement", "Logging");
    }
    ```

<span data-ttu-id="fa266-138">Per una demo, vedere il [video di Channel 9 dedicato a Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span><span class="sxs-lookup"><span data-stu-id="fa266-138">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>

