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
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-core"></a>Usare Windows Compatibility Pack per convertire il codice per .NET Core

Alcuni dei problemi più comuni riscontrati durante il porting di codice esistente a .NET Core sono dipendenze da API e tecnologie disponibili solo in .NET Framework. *Windows Compatibility Pack* fornisce molte di queste tecnologie ed è quindi molto più semplice compilare applicazioni .NET Core e librerie .NET Standard.

Questo pacchetto è un'[estensione logica di .NET 2.0 Standard](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support) che incrementa in modo significativo il set di API e consente la compilazione di codice esistente praticamente senza modifiche. Per garantire la promessa di .NET Standard ("è il set di API fornite da tutte le implementazioni .NET"), il pacchetto non include tecnologie che non possono essere usate in tutte le piattaforme, come registro di sistema, Strumentazione gestione Windows (WMI) o Reflection Emit API.

Windows Compatibility Pack è posizionato sopra .NET Standard e fornisce l'accesso a tecnologie solo Windows. È particolarmente utile per i clienti che vogliono passare a .NET Core ma prevedono di rimanere sulla piattaforma Windows come primo passo. In questo scenario, non è possibile utilizzare le tecnologie solo Windows è solo un ostacolo alla migrazione senza vantaggi architettonici.

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
