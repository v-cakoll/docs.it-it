---
title: Usare Windows Compatibility Pack per convertire il codice per .NET Core
description: Informazioni su Windows Compatibility Pack e su come è possibile usarlo per trasferire il codice di .NET Framework esistente a .NET Core.
author: terrajobst
ms.date: 12/07/2018
ms.openlocfilehash: 65530987a3cded941b6a292118ed9bfdb6f5b86c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715474"
---
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-core"></a><span data-ttu-id="e5fd8-103">Usare Windows Compatibility Pack per convertire il codice per .NET Core</span><span class="sxs-lookup"><span data-stu-id="e5fd8-103">Use the Windows Compatibility Pack to port code to .NET Core</span></span>

<span data-ttu-id="e5fd8-104">Alcuni dei problemi più comuni riscontrati durante il porting di codice esistente a .NET Core sono dipendenze da API e tecnologie disponibili solo in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e5fd8-104">Some of the most common issues found when porting existing code to .NET Core are dependencies on APIs and technologies that are only found in .NET Framework.</span></span> <span data-ttu-id="e5fd8-105">*Windows Compatibility Pack* fornisce molte di queste tecnologie ed è quindi molto più semplice compilare applicazioni .NET Core e librerie .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e5fd8-105">The *Windows Compatibility Pack* provides many of these technologies, so it's much easier to build .NET Core applications and .NET Standard libraries.</span></span>

<span data-ttu-id="e5fd8-106">Questo pacchetto è un'[estensione logica di .NET 2.0 Standard](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support) che incrementa in modo significativo il set di API e consente la compilazione di codice esistente praticamente senza modifiche.</span><span class="sxs-lookup"><span data-stu-id="e5fd8-106">This package is a logical [extension of .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support) that significantly increases API set and existing code compiles with almost no modifications.</span></span> <span data-ttu-id="e5fd8-107">Per garantire la promessa di .NET Standard ("è il set di API fornite da tutte le implementazioni .NET"), il pacchetto non include tecnologie che non possono essere usate in tutte le piattaforme, come registro di sistema, Strumentazione gestione Windows (WMI) o Reflection Emit API.</span><span class="sxs-lookup"><span data-stu-id="e5fd8-107">In order to keep the promise of .NET Standard ("it is the set of APIs that all .NET implementations provide"), the pack doesn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span>

<span data-ttu-id="e5fd8-108">Windows Compatibility Pack è posizionato sopra .NET Standard e fornisce l'accesso a tecnologie solo Windows.</span><span class="sxs-lookup"><span data-stu-id="e5fd8-108">The Windows Compatibility Pack sits on top of .NET Standard and provides access to technologies that are Windows only.</span></span> <span data-ttu-id="e5fd8-109">È particolarmente utile per i clienti che vogliono passare a .NET Core ma prevedono di rimanere sulla piattaforma Windows come primo passo.</span><span class="sxs-lookup"><span data-stu-id="e5fd8-109">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows as a first step.</span></span> <span data-ttu-id="e5fd8-110">In questo scenario, non è possibile utilizzare le tecnologie solo Windows è solo un ostacolo alla migrazione senza vantaggi architettonici.</span><span class="sxs-lookup"><span data-stu-id="e5fd8-110">In that scenario, not being able to use Windows-only technologies is only a migration hurdle with no architectural benefits.</span></span>

## <a name="package-contents"></a><span data-ttu-id="e5fd8-111">Contenuto del pacchetto</span><span class="sxs-lookup"><span data-stu-id="e5fd8-111">Package contents</span></span>

<span data-ttu-id="e5fd8-112">Windows Compatibility Pack viene fornito tramite il [pacchetto NuGet Microsoft. Windows. Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) ed è possibile farvi riferimento dai progetti destinati a .NET Core o .NET standard.</span><span class="sxs-lookup"><span data-stu-id="e5fd8-112">The Windows Compatibility Pack is provided via the [Microsoft.Windows.Compatibility NuGet package](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects that target .NET Core or .NET Standard.</span></span>

<span data-ttu-id="e5fd8-113">Include circa 20.000 API, incluse API solo per Windows e API multipiattaforma per le aree tecnologiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5fd8-113">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

- <span data-ttu-id="e5fd8-114">Tabelle codici</span><span class="sxs-lookup"><span data-stu-id="e5fd8-114">Code Pages</span></span>
- <span data-ttu-id="e5fd8-115">CodeDom</span><span class="sxs-lookup"><span data-stu-id="e5fd8-115">CodeDom</span></span>
- <span data-ttu-id="e5fd8-116">Configurazione di</span><span class="sxs-lookup"><span data-stu-id="e5fd8-116">Configuration</span></span>
- <span data-ttu-id="e5fd8-117">Servizi directory</span><span class="sxs-lookup"><span data-stu-id="e5fd8-117">Directory Services</span></span>
- <span data-ttu-id="e5fd8-118">Disegno</span><span class="sxs-lookup"><span data-stu-id="e5fd8-118">Drawing</span></span>
- <span data-ttu-id="e5fd8-119">ODBC</span><span class="sxs-lookup"><span data-stu-id="e5fd8-119">ODBC</span></span>
- <span data-ttu-id="e5fd8-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e5fd8-120">Permissions</span></span>
- <span data-ttu-id="e5fd8-121">Porte</span><span class="sxs-lookup"><span data-stu-id="e5fd8-121">Ports</span></span>
- <span data-ttu-id="e5fd8-122">Elenchi di controllo degli accessi (ACL) di Windows</span><span class="sxs-lookup"><span data-stu-id="e5fd8-122">Windows Access Control Lists (ACL)</span></span>
- <span data-ttu-id="e5fd8-123">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="e5fd8-123">Windows Communication Foundation (WCF)</span></span>
- <span data-ttu-id="e5fd8-124">Crittografia di Windows</span><span class="sxs-lookup"><span data-stu-id="e5fd8-124">Windows Cryptography</span></span>
- <span data-ttu-id="e5fd8-125">Registro eventi di Windows</span><span class="sxs-lookup"><span data-stu-id="e5fd8-125">Windows EventLog</span></span>
- <span data-ttu-id="e5fd8-126">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="e5fd8-126">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="e5fd8-127">Contatori delle prestazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="e5fd8-127">Windows Performance Counters</span></span>
- <span data-ttu-id="e5fd8-128">Registro di sistema di Windows</span><span class="sxs-lookup"><span data-stu-id="e5fd8-128">Windows Registry</span></span>
- <span data-ttu-id="e5fd8-129">Memorizzazione nella cache di Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="e5fd8-129">Windows Runtime Caching</span></span>
- <span data-ttu-id="e5fd8-130">Servizi Windows</span><span class="sxs-lookup"><span data-stu-id="e5fd8-130">Windows Services</span></span>

<span data-ttu-id="e5fd8-131">Per altre informazioni, vedere la [specifica del pacchetto di compatibilità](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e5fd8-131">For more information, see the [specification of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="e5fd8-132">Attività iniziali</span><span class="sxs-lookup"><span data-stu-id="e5fd8-132">Get started</span></span>

1. <span data-ttu-id="e5fd8-133">Prima di eseguire il porting, assicurarsi di esaminare il [processo di porting](index.md).</span><span class="sxs-lookup"><span data-stu-id="e5fd8-133">Before porting, make sure to take a look at the [Porting process](index.md).</span></span>

2. <span data-ttu-id="e5fd8-134">Quando si porta il codice esistente in .NET Core o .NET Standard, installare il [pacchetto NuGet Microsoft. Windows. Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span><span class="sxs-lookup"><span data-stu-id="e5fd8-134">When porting existing code to .NET Core or .NET Standard, install the [Microsoft.Windows.Compatibility NuGet package](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

   <span data-ttu-id="e5fd8-135">Se si desidera rimanere in ambiente Windows, questo è tutto.</span><span class="sxs-lookup"><span data-stu-id="e5fd8-135">If you want to stay on Windows, you're all set.</span></span>

3. <span data-ttu-id="e5fd8-136">Se si vuole eseguire l'applicazione .NET Core o la libreria .NET Standard in Linux o macOS, usare l'[analizzatore delle API](../../standard/analyzers/api-analyzer.md) per trovare informazioni sull'utilizzo delle API non supportato in tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="e5fd8-136">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](../../standard/analyzers/api-analyzer.md) to find usage of APIs that won't work cross-platform.</span></span>

4. <span data-ttu-id="e5fd8-137">Rimuovere questi utilizzi di tali API, sostituirli con alternative multipiattaforma o proteggerli con un controllo di piattaforma, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e5fd8-137">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

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

<span data-ttu-id="e5fd8-138">Per una demo, vedere il [video di Channel 9 dedicato a Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span><span class="sxs-lookup"><span data-stu-id="e5fd8-138">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>
