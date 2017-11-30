---
title: "Porting a .NET Core, utilizzando il pacchetto di compatibilità di Windows"
description: "Informazioni sul pacchetto di compatibilità di Windows e come possibile utilizzarla per porting del codice .NET Framework esistente a .NET Core"
keywords: ".NET, .NET core, Windows, compatibilità"
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 5094baee77aba4d1e148f807d842a4a2d3405cf7
ms.sourcegitcommit: 86cf9b4c7104485a9870645705b9a1a4b6ca8e2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2017
---
# <a name="using-the-windows-compatibility-pack"></a><span data-ttu-id="5ad59-104">Tramite il pacchetto di compatibilità di Windows</span><span class="sxs-lookup"><span data-stu-id="5ad59-104">Using the Windows Compatibility Pack</span></span>

<span data-ttu-id="5ad59-105">Uno dei problemi più comuni che gli sviluppatori devono affrontare durante il porting del codice esistente per .NET Core è che dipendono API e le tecnologie che esistono solo in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5ad59-105">One of the most common issues that developers face when porting their existing code to .NET Core is that they depend on APIs and technologies that only exist in the .NET Framework.</span></span> <span data-ttu-id="5ad59-106">Il *Windows Compatibility Pack* è fornire molte di queste tecnologie in modo che la creazione di applicazioni .NET Core, nonché le librerie .NET Standard diventa molto più efficiente per il codice esistente.</span><span class="sxs-lookup"><span data-stu-id="5ad59-106">The *Windows Compatibility Pack* is about providing many of these technologies so that building .NET Core applications as well as .NET Standard libraries becomes much more viable for existing code.</span></span>

<span data-ttu-id="5ad59-107">Questo pacchetto è logico [estensione di .NET 2.0 Standard](../whats-new/index.md#api-changes-and-library-support) che in modo significativo il set di API aumenta e il codice esistente viene compilato con quasi alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="5ad59-107">This package is a logical [extension of .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support) that significantly increases API set and existing code compiles with almost no modifications.</span></span> <span data-ttu-id="5ad59-108">Ma per mantenere la promessa di .NET Standard ("è il set di API che forniscono tutte le implementazioni .NET"), tale opzione non include tecnologie che non funzionano con tutte le piattaforme, ad esempio del Registro di sistema, Strumentazione gestione Windows (WMI), o la reflection emit API.</span><span class="sxs-lookup"><span data-stu-id="5ad59-108">But in order to keep the promise of .NET Standard ("it is the set of APIs that all .NET implementations provide"), this didn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span>

<span data-ttu-id="5ad59-109">Il *Windows Compatibility Pack* si trova nella parte superiore Standard .NET e fornisce l'accesso a tecnologie di Windows solo.</span><span class="sxs-lookup"><span data-stu-id="5ad59-109">The *Windows Compatibility Pack* sits on top of .NET Standard and provides access to technologies that are Windows only.</span></span> <span data-ttu-id="5ad59-110">È particolarmente utile per i clienti che si desidera spostare in .NET Core ma piano di rimanere in Windows come primo passaggio.</span><span class="sxs-lookup"><span data-stu-id="5ad59-110">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows as a first step.</span></span> <span data-ttu-id="5ad59-111">In questo scenario, non è in grado di usare tecnologie di Windows è solo un ostacolo migrazione con zero vantaggi dell'architettura.</span><span class="sxs-lookup"><span data-stu-id="5ad59-111">In that scenario, not being able to use Windows-only technologies is only a migration hurdle with zero architectural benefits.</span></span>

## <a name="package-contents"></a><span data-ttu-id="5ad59-112">Contenuto del pacchetto</span><span class="sxs-lookup"><span data-stu-id="5ad59-112">Package contents</span></span>

<span data-ttu-id="5ad59-113">Il *Windows Compatibility Pack* viene fornito tramite il pacchetto NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) e può essere specificato da progetti destinati a .NET Core o .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="5ad59-113">The *Windows Compatibility Pack* is provided via the NuGet Package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects targeting .NET Core or .NET Standard.</span></span>

<span data-ttu-id="5ad59-114">Fornisce informazioni 20.000 API, incluse le API solo per Windows nonché multipiattaforma di aree tecnologiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ad59-114">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

* <span data-ttu-id="5ad59-115">Tabelle codici</span><span class="sxs-lookup"><span data-stu-id="5ad59-115">Code Pages</span></span>
* <span data-ttu-id="5ad59-116">CodeDom</span><span class="sxs-lookup"><span data-stu-id="5ad59-116">CodeDom</span></span>
* <span data-ttu-id="5ad59-117">Configurazione</span><span class="sxs-lookup"><span data-stu-id="5ad59-117">Configuration</span></span>
* <span data-ttu-id="5ad59-118">Servizi directory</span><span class="sxs-lookup"><span data-stu-id="5ad59-118">Directory Services</span></span>
* <span data-ttu-id="5ad59-119">disegno</span><span class="sxs-lookup"><span data-stu-id="5ad59-119">Drawing</span></span>
* <span data-ttu-id="5ad59-120">ODBC</span><span class="sxs-lookup"><span data-stu-id="5ad59-120">ODBC</span></span>
* <span data-ttu-id="5ad59-121">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5ad59-121">Permissions</span></span>
* <span data-ttu-id="5ad59-122">Porte</span><span class="sxs-lookup"><span data-stu-id="5ad59-122">Ports</span></span>
* <span data-ttu-id="5ad59-123">Elenchi di controllo di accesso (ACL) di Windows</span><span class="sxs-lookup"><span data-stu-id="5ad59-123">Windows Access Control Lists (ACL)</span></span>
* <span data-ttu-id="5ad59-124">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="5ad59-124">Windows Communication Foundation (WCF)</span></span>
* <span data-ttu-id="5ad59-125">Crittografia di Windows</span><span class="sxs-lookup"><span data-stu-id="5ad59-125">Windows Cryptography</span></span>
* <span data-ttu-id="5ad59-126">Registro eventi di Windows</span><span class="sxs-lookup"><span data-stu-id="5ad59-126">Windows EventLog</span></span>
* <span data-ttu-id="5ad59-127">Strumentazione gestione Windows (WMI, Windows Management Instrumentation)</span><span class="sxs-lookup"><span data-stu-id="5ad59-127">Windows Management Instrumentation (WMI)</span></span>
* <span data-ttu-id="5ad59-128">Contatori delle prestazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="5ad59-128">Windows Performance Counters</span></span>
* <span data-ttu-id="5ad59-129">Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="5ad59-129">Windows Registry</span></span>
* <span data-ttu-id="5ad59-130">La memorizzazione nella cache di Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="5ad59-130">Windows Runtime Caching</span></span>
* <span data-ttu-id="5ad59-131">servizi Windows</span><span class="sxs-lookup"><span data-stu-id="5ad59-131">Windows Services</span></span>

<span data-ttu-id="5ad59-132">Per ulteriori informazioni, vedere il [specifiche del pacchetto di compatibilità](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="5ad59-132">For more information, see the [spec of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="5ad59-133">Introduzione</span><span class="sxs-lookup"><span data-stu-id="5ad59-133">Get started</span></span>

1. <span data-ttu-id="5ad59-134">Prima di porting, assicurarsi di esaminare il [il processo di Porting](index.md).</span><span class="sxs-lookup"><span data-stu-id="5ad59-134">Before porting, make sure to take a look at the [Porting Process](index.md).</span></span>

2. <span data-ttu-id="5ad59-135">Durante il porting del codice esistente .NET Core o .NET Standard, installare il pacchetto NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span><span class="sxs-lookup"><span data-stu-id="5ad59-135">When porting existing code to .NET Core or .NET Standard, install the NuGet package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

3. <span data-ttu-id="5ad59-136">Se si desidera mantenere in Windows, disporre delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="5ad59-136">If you want to stay on Windows, you're all set.</span></span>

4. <span data-ttu-id="5ad59-137">Se si desidera eseguire l'applicazione di .NET Core o di una libreria .NET Standard per Linux o Mac OS, utilizzare il [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) per trovare l'utilizzo di API che non funzioneranno più piattaforme.</span><span class="sxs-lookup"><span data-stu-id="5ad59-137">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) to find usage of APIs that won't work cross-platform.</span></span>

5. <span data-ttu-id="5ad59-138">Rimuovere gli utilizzi di tali API, sostituirli con alternative multipiattaforma o proteggerli con un controllo di piattaforma, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5ad59-138">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

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

<span data-ttu-id="5ad59-139">Per una demo, consultare il [video di Channel 9 del pacchetto di compatibilità Windows](https://channel9.msdn.com/Events/Connect/2017/T123).</span><span class="sxs-lookup"><span data-stu-id="5ad59-139">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>

