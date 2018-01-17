---
title: Conversione per .NET Core - Uso di Windows Compatibility Pack
description: "Informazioni su Windows Compatibility Pack e su come è possibile usarlo per la conversione di codice .NET Framework esistente per .NET Core"
keywords: ".NET, .NET Core, Windows, compatibilità"
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net-core
ms.workload: dotnetcore
ms.openlocfilehash: 3b1fe02aad4f78499158ecb7fa9b8521cb7d992e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="using-the-windows-compatibility-pack"></a>Uso di Windows Compatibility Pack

Uno dei problemi più comuni che si trovano ad affrontare gli sviluppatori durante la conversione del codice esistente per .NET Core è la dipendenza da API e tecnologie che esistono solo in .NET Framework. Scopo di *Windows Compatibility Pack* è fornire molte di queste tecnologie in modo che la creazione di applicazioni .NET Core, nonché di librerie .NET Standard, diventi molto più praticabile per il codice esistente.

Questo pacchetto è un'[estensione logica di .NET 2.0 Standard](../whats-new/index.md#api-changes-and-library-support) che incrementa in modo significativo il set di API e consente la compilazione di codice esistente praticamente senza modifiche. Tuttavia, per rispettare i principi di .NET Standard ("è il set di API fornite da tutte le implementazioni .NET"), questo pacchetto non include tecnologie che non funzionano in tutte le piattaforme, ad esempio le API per Registro di sistema, Strumentazione gestione Windows (WMI) o reflection emit.

*Windows Compatibility Pack* si sovrappone a .NET Standard e consente l'accesso a tecnologie solo Windows. È particolarmente utile per i clienti che vogliono passare a .NET Core ma prevedono di rimanere sulla piattaforma Windows come primo passo. In questo scenario, l'impossibilità di usare tecnologie solo Windows è solo un ostacolo per la migrazione senza alcun vantaggio a livello di architettura.

## <a name="package-contents"></a>Contenuto del pacchetto

*Windows Compatibility Pack* viene fornito tramite il pacchetto NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) ed è possibile farvi riferimento dai progetti destinati a .NET Core o .NET Standard.

Include circa 20.000 API, incluse API solo per Windows e API multipiattaforma per le aree tecnologiche seguenti:

* Tabelle codici
* CodeDom
* Configurazione
* Servizi directory
* Disegno
* ODBC
* Autorizzazioni
* Porte
* Elenchi di controllo degli accessi (ACL) di Windows
* Windows Communication Foundation (WCF)
* Crittografia di Windows
* Registro eventi di Windows
* Strumentazione gestione Windows (WMI, Windows Management Instrumentation)
* Contatori delle prestazioni di Windows
* Registro di sistema di Windows
* Memorizzazione nella cache di Windows Runtime
* servizi Windows

Per altre informazioni, vedere le [specifiche del pacchetto di compatibilità](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).

## <a name="get-started"></a>Introduzione

1. Prima di procedere alla conversione, assicurarsi di esaminare il [processo di conversione](index.md).

2. Per la conversione di codice esistente per .NET Core o .NET Standard, installare il pacchetto NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).

3. Se si desidera rimanere in ambiente Windows, questo è tutto.

4. Se si vuole eseguire l'applicazione .NET Core o la libreria .NET Standard in Linux o macOS, usare l'[analizzatore delle API](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) per trovare informazioni sull'utilizzo delle API non supportato in tutte le piattaforme.

5. Rimuovere questi utilizzi di tali API, sostituirli con alternative multipiattaforma o proteggerli con un controllo di piattaforma, ad esempio:

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

