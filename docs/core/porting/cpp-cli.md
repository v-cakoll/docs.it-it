---
title: Migrazione di progetti con c'è/CLI a .NET Core
description: Informazioni sul porting di progetti in .NET Core/CLI.
author: mjrousos
ms.date: 01/10/2020
ms.openlocfilehash: eb03f2a5ff42e8279fd3ebd6ee6fb6d955f6798d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75964930"
---
# <a name="how-to-port-a-ccli-project-to-net-core"></a>Come eseguire il porting di un progetto in .NET Core

A partire da .NET Core 3.1 e Visual Studio 2019 versione 16.4, i progetti di [C/CLI](/cpp/dotnet/dotnet-programming-with-cpp-cli-visual-cpp) possono essere destinati a .NET Core. Questo supporto consente di eseguire il porting delle applicazioni desktop di Windows con i livelli di interoperabilità C./CLI a .NET Core. In questo articolo viene descritto come eseguire la porta di progetti C , C , C , E CLI da .NET Framework a .NET Core 3.1.

## <a name="ccli-net-core-limitations"></a>Limitazioni di .NET Core di C/CLI

Esistono alcune importanti limitazioni per il porting di progetti in .NET Core rispetto ad altri linguaggi:

* Il supporto di C/CLI per .NET Core è solo Windows.
* I progetti di C/CLI non possono essere destinati a .NET Standard, ma solo a .NET Core (o .NET Framework).
* I progetti di progetto di tipo C/CLI non supportano il nuovo formato di file di progetto in stile SDK. Al contrario, anche quando è destinato a .NET Core, i progetti di C/CLI utilizzano il formato di file vcxproj esistente.
* Non è possibile eseguire più piattaforme .NET con più aree di sicurezza. Se è necessario compilare un progetto in linguaggio C,NET/CLI sia per .NET Framework che per .NET Core, utilizzare file di progetto separati.
* .NET Core non `-clr:pure` supporta `-clr:safe` o la `-clr:netcore` compilazione, solo `-clr` la nuova opzione (che è equivalente a per .NET Framework).

## <a name="port-a-ccli-project"></a>Convertire un progetto c/CLI

Per eseguire il porting di un progetto in .NET Core, apportare le modifiche seguenti al file vcxproj. Questi passaggi di migrazione differiscono dai passaggi necessari per altri tipi di progetto, perché i progetti di C/CLI non utilizzano file di progetto di tipo SDK.

1. Sostituire `<CLRSupport>true</CLRSupport>` le `<CLRSupport>NetCore</CLRSupport>`proprietà con . Questa proprietà si trova spesso in gruppi di proprietà specifici della configurazione, pertanto potrebbe essere necessario sostituirla in più posizioni.
2. Sostituire `<TargetFrameworkVersion>` le `<TargetFramework>netcoreapp3.1</TargetFramework>`proprietà con .
3. Rimuovere tutti i riferimenti `<Reference Include="System" />`di .NET Framework (ad esempio ). Agli assembly di .NET Core `<CLRSupport>NetCore</CLRSupport>`SDK viene fatto automaticamente riferimento quando si utilizza .
4. Aggiornare l'utilizzo dell'API nei file cpp, se necessario, per rimuovere le API non disponibili per .NET Core.Update API usage in cpp files, as necessary, to remove APIs unavailable to .NET Core. Dal caso in cui i progetti di c'è/CLI tendano ad essere livelli di interoperabilità piuttosto sottili, spesso non sono necessarie molte modifiche. [L'analizzatore di portabilità .NET](../../standard/analyzers/portability-analyzer.md) può essere utilizzato per identificare le API .NET non supportate utilizzate dai file binari di C.NET e non solo come per i file binari puramente gestiti. Le linee guida per determinare la portabilità del codice e l'aggiornamento dei progetti da utilizzare con le API di .NET Core sono disponibili nelle linee guida per il porting della [libreria.](./libraries.md#determine-portability)

### <a name="wpf-and-windows-forms-usage"></a>Utilizzo di WPF e Windows FormWPF and Windows Forms usage

I progetti di .NET Core di C/CLI possono utilizzare le API di Windows Form e WPF. Per usare queste API desktop di Windows, è necessario aggiungere riferimenti framework espliciti alle librerie dell'interfaccia utente. I progetti in stile SDK che utilizzano le API desktop `Microsoft.NET.Sdk.WindowsDesktop` di Windows fanno automaticamente riferimento alle librerie di framework necessarie utilizzando l'SDK. Dal momento che i progetti di c'è/CLI non utilizzano il formato di progetto di tipo SDK, è necessario aggiungere riferimenti a framework espliciti durante la destinazione di .NET Core.

Per utilizzare le API di Windows Form, aggiungere questo riferimento al file vcxproj:

```xml
<!-- Reference all of Windows Forms -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App.WindowsForms" />
```

Per usare le API WPFWPF, aggiungere questo riferimento al file vcxproj:

```xml
<!-- Reference all of WPF -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App.WPF" />
```

Per utilizzare entrambe le API Windows Form e WPF, aggiungere questo riferimento al file vcxproj:

```xml
<!-- Reference the entirety of the Windows desktop framework:
     Windows Forms, WPF, and the types that provide integration between them -->
<FrameworkReference Include="Microsoft.WindowsDesktop.App" />
```

Attualmente, non è possibile aggiungere questi riferimenti utilizzando il gestore dei riferimenti di Visual Studio.Currently, it's not possible to add these references using Visual Studio's reference manager. Al contrario, aggiornare manualmente il file di progetto. Questo aggiornamento può essere fatto in Visual Studio scaricando il progetto e quindi la modifica del file di progetto. È anche possibile usare un altro editor come VS Code.You can also use another editor like VS Code.

## <a name="build-without-msbuild"></a>Compilazione senza MSBuild

È anche possibile compilare progetti c'è/CLI senza utilizzare MSBuild. Attenersi alla seguente procedura per compilare un progetto di C/CLI per .NET Core direttamente con *cl.exe* e *link.exe*:

1. Durante la compilazione, passare `-clr:netcore` a *cl.exe*.
2. Fare riferimento agli assembly di riferimento .NET Core necessari.
3. Durante il collegamento, fornire la directory `LibPath` host dell'app .NET Core come (in modo che sia possibile *trovare ijwhost.lib).*
4. Copiare *ijwhost.dll* (dalla directory host dell'app .NET Core) nella directory di output del progetto.
5. Assicurarsi che esista un file [runtimeconfig.json](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) per il primo componente dell'applicazione che eseguirà codice gestito. Se l'applicazione dispone di `runtime.config` un punto di ingresso gestito, verrà creato e copiato automaticamente un file. Se l'applicazione dispone di un punto di `runtimeconfig.json` ingresso nativo, tuttavia, è necessario creare un file per la prima libreria C .

## <a name="known-issues"></a>Problemi noti

Ci sono un paio di problemi noti da guardare fuori per quando si lavora con i progetti di C .

* Un riferimento al framework WPF nei progetti .NET Core di .NET Core/CLI attualmente causa alcuni avvisi estranei sull'impossibilità di importare i simboli. Questi avvisi possono essere tranquillamente ignorati e devono essere corretti a breve.
* Se l'applicazione dispone di un punto di ingresso nativo, la libreria c'è/CLI che esegue per prima il codice gestito richiede un file [runtimeconfig.json.](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) Questo file di configurazione viene utilizzato all'avvio del runtime di .NET Core.This config file is used when the .NET Core runtime starts. I progetti di C/CLI `runtimeconfig.json` non creano ancora automaticamente i file in fase di compilazione, pertanto il file deve essere generato manualmente. Se viene chiamata una libreria c'è/CLI da un punto di ingresso gestito, `runtimeconfig.json` la libreria C/CLI non necessita di un file (poiché l'assembly del punto di ingresso ne avrà uno utilizzato all'avvio del runtime). Di seguito `runtimeconfig.json` è riportato un semplice file di esempio. Per ulteriori informazioni, vedere le [specifiche in GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).

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
