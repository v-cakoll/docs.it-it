---
title: Usare Windows Compatibility Pack per convertire il codice per .NET Core
description: Informazioni su Windows Compatibility Pack e su come è possibile usarlo per trasferire il codice di .NET Framework esistente a .NET Core.
author: terrajobst
ms.date: 12/07/2018
ms.openlocfilehash: 91a653b2345d414c18ebdb6e8b7d6d49bbdbb83e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733614"
---
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-core"></a>Usare Windows Compatibility Pack per convertire il codice per .NET Core

Alcuni dei problemi più comuni riscontrati durante il porting di codice esistente a .NET Core sono dipendenze da API e tecnologie disponibili solo in .NET Framework. *Windows Compatibility Pack* fornisce molte di queste tecnologie ed è quindi molto più semplice compilare applicazioni .NET Core e librerie .NET Standard.

Il pacchetto di compatibilità è un' [estensione logica di .NET Standard 2,0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support) che aumenta significativamente il set di API. Il codice esistente viene compilato con quasi nessuna modifica. Per evitare che il set di API fornito da tutte le implementazioni di .NET, .NET Standard non includa tecnologie che non possono essere usate in tutte le piattaforme, ad esempio il registro di sistema, Strumentazione gestione Windows (WMI) o le API di Reflection Emit. Windows Compatibility Pack è posizionato sopra .NET Standard e fornisce l'accesso a queste tecnologie solo Windows. È particolarmente utile per i clienti che vogliono passare a .NET Core, ma che prevedono di rimanere in Windows, almeno come primo passaggio. In questo scenario, la possibilità di utilizzare le tecnologie solo Windows rimuove l'ostacolo alla migrazione.

## <a name="package-contents"></a>Contenuto del pacchetto

Windows Compatibility Pack viene fornito tramite il [pacchetto NuGet Microsoft. Windows. Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) ed è possibile farvi riferimento dai progetti destinati a .NET Core o .NET standard.

Include circa 20.000 API, incluse API solo per Windows e API multipiattaforma per le aree tecnologiche seguenti:

- Tabelle codici
- CodeDom
- Configurazione di
- Servizi directory
- Disegno
- ODBC
- Autorizzazioni
- Porte
- Elenchi di controllo degli accessi (ACL) di Windows
- Windows Communication Foundation (WCF)
- Crittografia di Windows
- Registro eventi di Windows
- Windows Management Instrumentation (WMI)
- Contatori delle prestazioni di Windows
- Registro di sistema di Windows
- Memorizzazione nella cache di Windows Runtime
- Servizi Windows

Per altre informazioni, vedere la [specifica del pacchetto di compatibilità](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).

## <a name="get-started"></a>Attività iniziali

1. Prima di eseguire il porting, assicurarsi di esaminare il [processo di porting](index.md).

2. Quando si porta il codice esistente in .NET Core o .NET Standard, installare il [pacchetto NuGet Microsoft. Windows. Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).

   Se si desidera rimanere in ambiente Windows, questo è tutto.

3. Se si vuole eseguire l'applicazione .NET Core o la libreria .NET Standard in Linux o macOS, usare l'[analizzatore delle API](../../standard/analyzers/api-analyzer.md) per trovare informazioni sull'utilizzo delle API non supportato in tutte le piattaforme.

4. Rimuovere questi utilizzi di tali API, sostituirli con alternative multipiattaforma o proteggerli con un controllo di piattaforma, ad esempio:

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

Per una demo, vedere il [video di Channel 9 dedicato a Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).
