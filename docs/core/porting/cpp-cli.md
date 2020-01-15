---
title: Migrazione C++di progetti/CLI a .NET Core
description: Informazioni sul porting C++di progetti/CLI a .NET Core.
author: mjrousos
ms.date: 01/10/2020
ms.openlocfilehash: eb03f2a5ff42e8279fd3ebd6ee6fb6d955f6798d
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964930"
---
# <a name="how-to-port-a-ccli-project-to-net-core"></a>Come trasferire un C++progetto/CLI a .NET Core

A partire da .NET Core 3,1 e Visual Studio 2019 versione 16,4, [ C++i progetti/CLI](/cpp/dotnet/dotnet-programming-with-cpp-cli-visual-cpp) possono essere destinati a .NET Core. Questo supporto rende possibile trasferire le applicazioni desktop di Windows con C++i livelli di interoperabilità/CLI a .NET Core. Questo articolo descrive come trasferire C++i progetti/cli da .NET Framework a .net core 3,1.

## <a name="ccli-net-core-limitations"></a>C++Limitazioni di .NET Core/CLI

Esistono alcune importanti limitazioni per il porting C++di progetti/CLI a .NET Core rispetto ad altri linguaggi:

* C++Il supporto di/CLI per .NET Core è solo Windows.
* C++I progetti/CLI non possono avere come destinazione .NET Standard, solo .NET Core (o .NET Framework).
* C++I progetti/CLI non supportano il nuovo formato di file di progetto in stile SDK. In alternativa, anche quando la destinazione è .NET C++core, i progetti/CLI usano il formato di file vcxproj esistente.
* C++I progetti/CLI non possono usare più piattaforme .NET come destinazione. Se è necessario compilare un C++progetto/cli per .NET Framework e .NET Core, usare file di progetto distinti.
* .NET Core non supporta la compilazione `-clr:pure` o `-clr:safe`, ma solo la nuova opzione `-clr:netcore` (equivalente a `-clr` per .NET Framework).

## <a name="port-a-ccli-project"></a>Porta un C++progetto/CLI

Per trasferire un C++progetto/CLI a .NET Core, apportare le modifiche seguenti al file vcxproj. Questi passaggi di migrazione sono diversi dai passaggi necessari per altri tipi di C++progetto perché i progetti/CLI non utilizzano file di progetto in stile SDK.

1. Sostituire `<CLRSupport>true</CLRSupport>` proprietà con `<CLRSupport>NetCore</CLRSupport>`. Questa proprietà è spesso presente nei gruppi di proprietà specifici della configurazione, pertanto potrebbe essere necessario sostituirla in più posizioni.
2. Sostituire `<TargetFrameworkVersion>` proprietà con `<TargetFramework>netcoreapp3.1</TargetFramework>`.
3. Rimuovere tutti i riferimenti .NET Framework, ad esempio `<Reference Include="System" />`. Viene fatto automaticamente riferimento agli assembly .NET Core SDK quando si usa `<CLRSupport>NetCore</CLRSupport>`.
4. Aggiornare l'utilizzo dell'API nei file cpp, se necessario, per rimuovere le API non disponibili in .NET Core. Poiché C++i progetti/CLI tendono a essere piuttosto sottili, spesso non è necessario apportare molte modifiche. [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) può essere usato per identificare le API .NET non supportate usate dai C++file binari/CLI come per i file binari puramente gestiti. Le linee guida per determinare la portabilità del codice e l'aggiornamento dei progetti da usare con le API .NET Core sono disponibili nelle linee guida per la [portabilità della libreria](./libraries.md#determine-portability).

### <a name="wpf-and-windows-forms-usage"></a>Utilizzo di WPF e Windows Forms

I progetti C++.NET Core/CLI possono usare le API Windows Forms e WPF. Per usare queste API desktop di Windows, è necessario aggiungere riferimenti espliciti ai Framework alle librerie dell'interfaccia utente. I progetti di tipo SDK che usano le API di Windows Desktop fanno riferimento alle librerie di Framework necessarie automaticamente usando il `Microsoft.NET.Sdk.WindowsDesktop` SDK. Poiché C++i progetti/CLI non usano il formato di progetto in stile SDK, devono aggiungere riferimenti espliciti al framework quando sono destinati a .NET Core.

Per usare Windows Forms API, aggiungere questo riferimento al file vcxproj:

```xml
<!-- Reference all of Windows Forms -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App.WindowsForms" />
```

Per usare le API WPF, aggiungere questo riferimento al file vcxproj:

```xml
<!-- Reference all of WPF -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App.WPF" />
```

Per usare sia Windows Forms che le API WPF, aggiungere questo riferimento al file vcxproj:

```xml
<!-- Reference the entirety of the Windows desktop framework:
     Windows Forms, WPF, and the types that provide integration between them -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App" />
```

Attualmente, non è possibile aggiungere questi riferimenti usando Gestione riferimenti di Visual Studio. Aggiornare invece manualmente il file di progetto. Questo aggiornamento può essere eseguito in Visual Studio scaricando il progetto e quindi modificando il file di progetto. È anche possibile usare un altro editor, ad esempio VS Code.

## <a name="build-without-msbuild"></a>Compila senza MSBuild

È anche possibile compilare C++progetti/CLI senza usare MSBuild. Per compilare un C++progetto/CLI per .NET Core direttamente con *CL. exe* e *link. exe*, seguire questa procedura:

1. Quando si esegue la compilazione, passare `-clr:netcore` a *CL. exe*.
2. Fare riferimento agli assembly di riferimento di .NET Core necessari.
3. Quando si esegue il collegamento, fornire la directory host dell'app .NET Core come `LibPath` (in modo che sia possibile trovare *ijwhost. lib* ).
4. Copiare *ijwhost. dll* (dalla directory host dell'app .NET Core) alla directory di output del progetto.
5. Assicurarsi che esista un file [runtimeconfig. JSON](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) per il primo componente dell'applicazione che eseguirà il codice gestito. Se l'applicazione dispone di un punto di ingresso gestito, un file di `runtime.config` verrà creato e copiato automaticamente. Se l'applicazione dispone di un punto di ingresso nativo, tuttavia, è necessario creare un file di `runtimeconfig.json` per C++la prima libreria/CLI per l'uso del runtime di .NET Core.

## <a name="known-issues"></a>Problemi noti

Esistono un paio di problemi noti da considerare quando si usano progetti C++/CLI destinati a .NET Core.

* Un riferimento a un framework WPF nei C++progetti .NET Core/CLI causa attualmente alcuni avvisi estranei che non sono in grado di importare simboli. Questi avvisi possono essere tranquillamente ignorati e devono essere risolti a breve.
* Se l'applicazione dispone di un punto di ingresso nativo C++, la libreria/CLI che esegue per la prima volta il codice gestito necessita di un file [runtimeconfig. JSON](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) . Questo file di configurazione viene usato all'avvio del runtime di .NET Core. C++I progetti/CLI non creano ancora file di `runtimeconfig.json` in fase di compilazione, pertanto il file deve essere generato manualmente. Se una C++libreria/CLI viene chiamata da un punto di ingresso gestito, la C++libreria/CLI non necessita di un file di `runtimeconfig.json` (dal momento che l'assembly del punto di ingresso ne avrà uno usato all'avvio del Runtime). Di seguito è riportato un semplice file di `runtimeconfig.json` di esempio. Per altre informazioni, vedere la [specifica su GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).

    ```json
    {
          "runtimeOptions": {
             "tfm": "netcoreapp3.1",
             "framework": {
                "name": "Microsoft.NETCore.App",
                "version": "3.1.0"
             }
          }
    }
    ```
