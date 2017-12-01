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
# <a name="using-the-windows-compatibility-pack"></a>Tramite il pacchetto di compatibilità di Windows

Uno dei problemi più comuni che gli sviluppatori devono affrontare durante il porting del codice esistente per .NET Core è che dipendono API e le tecnologie che esistono solo in .NET Framework. Il *Windows Compatibility Pack* è fornire molte di queste tecnologie in modo che la creazione di applicazioni .NET Core, nonché le librerie .NET Standard diventa molto più efficiente per il codice esistente.

Questo pacchetto è logico [estensione di .NET 2.0 Standard](../whats-new/index.md#api-changes-and-library-support) che in modo significativo il set di API aumenta e il codice esistente viene compilato con quasi alcuna modifica. Ma per mantenere la promessa di .NET Standard ("è il set di API che forniscono tutte le implementazioni .NET"), tale opzione non include tecnologie che non funzionano con tutte le piattaforme, ad esempio del Registro di sistema, Strumentazione gestione Windows (WMI), o la reflection emit API.

Il *Windows Compatibility Pack* si trova nella parte superiore Standard .NET e fornisce l'accesso a tecnologie di Windows solo. È particolarmente utile per i clienti che si desidera spostare in .NET Core ma piano di rimanere in Windows come primo passaggio. In questo scenario, non è in grado di usare tecnologie di Windows è solo un ostacolo migrazione con zero vantaggi dell'architettura.

## <a name="package-contents"></a>Contenuto del pacchetto

Il *Windows Compatibility Pack* viene fornito tramite il pacchetto NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) e può essere specificato da progetti destinati a .NET Core o .NET Standard.

Fornisce informazioni 20.000 API, incluse le API solo per Windows nonché multipiattaforma di aree tecnologiche seguenti:

* Tabelle codici
* CodeDom
* Configurazione
* Servizi directory
* disegno
* ODBC
* Autorizzazioni
* Porte
* Elenchi di controllo di accesso (ACL) di Windows
* Windows Communication Foundation (WCF)
* Crittografia di Windows
* Registro eventi di Windows
* Strumentazione gestione Windows (WMI, Windows Management Instrumentation)
* Contatori delle prestazioni di Windows
* Registro di sistema di Windows
* La memorizzazione nella cache di Windows Runtime
* servizi Windows

Per ulteriori informazioni, vedere il [specifiche del pacchetto di compatibilità](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).

## <a name="get-started"></a>Introduzione

1. Prima di porting, assicurarsi di esaminare il [il processo di Porting](index.md).

2. Durante il porting del codice esistente .NET Core o .NET Standard, installare il pacchetto NuGet [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).

3. Se si desidera mantenere in Windows, disporre delle impostazioni.

4. Se si desidera eseguire l'applicazione di .NET Core o di una libreria .NET Standard per Linux o Mac OS, utilizzare il [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) per trovare l'utilizzo di API che non funzioneranno più piattaforme.

5. Rimuovere gli utilizzi di tali API, sostituirli con alternative multipiattaforma o proteggerli con un controllo di piattaforma, ad esempio:

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

Per una demo, consultare il [video di Channel 9 del pacchetto di compatibilità Windows](https://channel9.msdn.com/Events/Connect/2017/T123).

