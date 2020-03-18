---
title: Usare Windows Compatibility Pack per convertire il codice per .NET Core
description: Informazioni sul pacchetto di compatibilità di Windows e su come utilizzarlo per trasferire il codice .NET Framework esistente in .NET Core.
author: terrajobst
ms.date: 12/07/2018
ms.openlocfilehash: 91a653b2345d414c18ebdb6e8b7d6d49bbdbb83e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76733614"
---
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-core"></a>Usare Windows Compatibility Pack per convertire il codice per .NET Core

Alcuni dei problemi più comuni rilevati durante il porting di codice esistente in .NET Core sono le dipendenze da API e tecnologie che si trovano solo in .NET Framework. *Windows Compatibility Pack* fornisce molte di queste tecnologie ed è quindi molto più semplice compilare applicazioni .NET Core e librerie .NET Standard.

Il pacchetto di compatibilità è [un'estensione logica di .NET Standard 2.0](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support) che aumenta in modo significativo il set di API. Il codice esistente viene compilato con quasi nessuna modifica. Per mantenere la promessa di "il set di API che forniscono tutte le implementazioni di .NET", .NET Standard non include tecnologie che non possono funzionare su tutte le piattaforme, ad esempio il Registro di sistema, Strumentazione gestione Windows (WMI) o la reflection generano API. Il pacchetto di compatibilità di Windows si trova in cima a .NET Standard e fornisce l'accesso a queste tecnologie solo Windows. È particolarmente utile per i clienti che vogliono passare a .NET Core ma hanno intenzione di rimanere su Windows, almeno come primo passaggio. In questo scenario, la possibilità di utilizzare tecnologie solo Windows rimuove l'ostacolo per la migrazione.

## <a name="package-contents"></a>Contenuto del pacchetto

Il pacchetto di compatibilità di Windows viene fornito tramite il [pacchetto Microsoft.Windows.Compatibility NuGet](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) ed è possibile farvi riferimento da progetti destinati a .NET Core o .NET Standard.

Include circa 20.000 API, incluse API solo per Windows e API multipiattaforma per le aree tecnologiche seguenti:

- Tabelle codici
- CodeDom
- Configurazione
- Servizi directory
- Disegno
- ODBC
- Autorizzazioni
- Porte
- Elenchi di controllo degli accessi (ACL) di Windows
- Windows Communication Foundation (WCF)
- Crittografia di Windows
- Registro eventi di Windows
- Strumentazione gestione Windows (WMI, Windows Management Instrumentation)
- Contatori delle prestazioni di Windows
- Registro di sistema di Windows
- Memorizzazione nella cache di Windows Runtime
- servizi Windows

Per altre informazioni, vedere la [specifica del pacchetto di compatibilità](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).

## <a name="get-started"></a>Introduzione

1. Prima del porting, assicurarsi di dare un'occhiata al [processo di porting](index.md).

2. Quando si esegue il porting di codice esistente in .NET Core o .NET Standard, installare il [pacchetto Microsoft.Windows.Compatibility NuGet](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).

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
