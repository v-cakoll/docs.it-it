---
title: Analizzare le dipendenze per convertire il codice per .NET Core
description: Informazioni su come analizzare le dipendenze esterne per convertire il progetto da .NET Framework a .NET Core.
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: 2aa09e551a99358d3a6961fafcfc0aa8dbd976b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398965"
---
# <a name="analyze-your-dependencies-to-port-code-to-net-core"></a>Analizzare le dipendenze per convertire il codice per .NET Core

Per convertire il codice a .NET Core o .NET Standard, è necessario conoscere le dipendenze. Le dipendenze esterne sono `.dll` i pacchetti NuGet o i file a cui si fa riferimento nel progetto, ma non vengono compilati manualmente.

## <a name="migrate-your-nuget-packages-to-packagereference"></a>Eseguire la migrazione dei pacchetti NuGet`PackageReference`

.NET Core usa [PackageReference](/nuget/consume-packages/package-references-in-project-files) per specificare le dipendenze dei pacchetti. Se si usa packages.config per specificare i pacchetti nel `PackageReference` progetto, `packages.config` convertilo nel formato, perché non è supportato in .NET Core.If you're using [packages.config](/nuget/reference/packages-config) to specify your packages in your project, convert it to the format, because isn't supported in .NET Core.

Per informazioni su come eseguire la migrazione, vedere l'articolo [Eseguire la migrazione da packages.config a PackageReference.To](/nuget/reference/migrate-packages-config-to-package-reference) learn how to migrate, see the Migrate from packages.config to PackageReference article.

## <a name="upgrade-your-nuget-packages"></a>Aggiornare i pacchetti NuGetUpgrade your NuGet packages

Dopo aver eseguito `PackageReference` la migrazione del progetto al formato, verificare se i pacchetti sono compatibili con .NET Core.After you migrate your project to the format, verify if your packages are compatible with .NET Core.

In primo luogo, aggiornare i pacchetti alla versione più recente che è possibile. Questa operazione può essere eseguita con l'interfaccia utente di NuGet Package Manager in Visual Studio.This can be done with the NuGet Package Manager UI in Visual Studio. È probabile che le versioni più recenti delle dipendenze del pacchetto siano già compatibili con .NET Core.

## <a name="analyze-your-package-dependencies"></a>Analizzare le dipendenze del pacchettoAnalyze your package dependencies

Se non è già stato verificato che le dipendenze del pacchetto convertito e aggiornato funzionino in .NET Core, è possibile eseguire alcune operazioni:If you haven't already verified that your converted and upgraded package dependencies work on .NET Core, there are a few ways that you can achieve that:

### <a name="analyze-nuget-packages-using-nugetorg"></a>Analizzare i pacchetti NuGet usando nuget.org

È possibile visualizzare i Moniker del framework di destinazione (TMS) supportati da ogni pacchetto [nuget.org](https://www.nuget.org/) nella sezione **Dipendenze** della pagina del pacchetto.

Anche se l'utilizzo del sito è un metodo più semplice per verificare la compatibilità, le informazioni **sulle dipendenze** non sono disponibili nel sito per tutti i pacchetti.

### <a name="analyze-nuget-packages-using-nuget-package-explorer"></a>Analizzare i pacchetti NuGet usando NuGet Package Explorer

Un pacchetto NuGet è un set di cartelle contenenti assembly specifici per la piattaforma. Verificare se è presente una cartella che contiene un assembly compatibile all'interno del pacchetto.

Il modo più semplice per esaminare le cartelle del pacchetto NuGet consiste nell'utilizzare lo strumento [Esplora pacchetti NuGet.The](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) easiest way to inspect NuGet package folders is to use the NuGet Package Explorer tool. Dopo aver installato lo strumento seguire questa procedura per visualizzare i nomi delle cartelle:

1. Aprire NuGet Package Explorer.
2. Fare clic su **Open package from online feed** (Apri il pacchetto dal feed online).
3. Cercare il nome del pacchetto.
4. Selezionare il nome del pacchetto nei risultati della ricerca e fare clic su **open** (Apri).
5. Espandere la cartella *lib* sul lato destro per visualizzare i nomi delle cartelle.

Cercare una cartella con nomi utilizzando `netstandardX.Y` uno `netcoreappX.Y`dei seguenti modelli: o .

Questi valori sono i [Target Framework Moniker (TFM)](../../standard/frameworks.md) che corrispondono a versioni dei profili [.NET Standard](../../standard/net-standard.md), .NET Core e dei tradizionali profili della libreria di classi portabile (PCL) compatibili con .NET Core.

> [!IMPORTANT]
> Quando si esaminano i TFM supportati da un pacchetto, si noti che `netcoreapp*` è compatibile, ma è destinato solo ai progetti .NET Core e non ai progetti .NET Standard.
> Una libreria che supporta solo `netcoreapp*` ma non `netstandard*` può essere usata solo da altre applicazioni .NET Core.

## <a name="net-framework-compatibility-mode"></a>Modalità di compatibilità di .NET Framework

Dopo aver analizzato i pacchetti NuGet, è possibile che siano destinati solo a .NET Framework.

A partire da .NET Standard 2.0 è stata introdotta la modalità di compatibilità di .NET Framework. Questa modalità consente a progetti .NET Standard e .NET Core di gestire riferimenti a librerie .NET Framework. I riferimenti alle librerie .NET Framework non funzionano per tutti i progetti, ad esempio se la libreria usa API Windows Presentation Foundation (WPF), ma sono in grado di risolvere molti scenari di portabilità.

Quando si fa riferimento a pacchetti NuGet destinati a .NET Framework nel progetto, ad esempio [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), viene visualizzato un avviso di fallback del pacchetto ([NU1701](/nuget/reference/errors-and-warnings/nu1701)) simile all'esempio seguente:

`NU1701: Package ‘Huitian.PowerCollections 1.0.0’ was restored using ‘.NETFramework,Version=v4.6.1’ instead of the project target framework ‘.NETStandard,Version=v2.0’. This package may not be fully compatible with your project.`

Questo avviso viene visualizzato quando si aggiunge il pacchetto e ogni volta che si esegue la compilazione, per garantire che il pacchetto venga testato con il progetto. Se il progetto funziona come previsto, è possibile eliminare l'avviso modificando le proprietà del pacchetto in Visual Studio o modificando manualmente il file di progetto nell'editor di codice preferito.

Per eliminare l'avviso modificando il file di progetto, trovare la voce `PackageReference` del pacchetto per il quale si vuole eliminare l'avviso e aggiungere l'attributo `NoWarn`. L'attributo `NoWarn` accetta un elenco delimitato da virgole di tutti gli ID avviso. L'esempio seguente illustra come eliminare l'avviso `NU1701` per il pacchetto `Huitian.PowerCollections` modificando manualmente il file di progetto:

```xml
<ItemGroup>
  <PackageReference Include="Huitian.PowerCollections" Version="1.0.0" NoWarn="NU1701" />
</ItemGroup>
```

Per altre informazioni sull'eliminazione degli avvisi del compilatore in Visual Studio, vedere [Non visualizzare avvisi per i pacchetti NuGet](/visualstudio/ide/how-to-suppress-compiler-warnings#suppress-warnings-for-nuget-packages).

## <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a>Operazioni da eseguire quando una dipendenza del pacchetto NuGet non viene eseguita in .NET Core

Se un pacchetto NuGet importante non può essere eseguito in .NET Core, è possibile provare varie soluzioni:

- Se il progetto è open source e ospitato in una posizione come GitHub, è possibile coinvolgere direttamente gli sviluppatori.
- È possibile contattare l'autore direttamente su [nuget.org](https://www.nuget.org/). Cerca il pacchetto e fai clic su **Contatta i proprietari** sul lato sinistro della pagina del pacchetto.
- È possibile cercare un altro pacchetto che supporta .NET Core ed esegue la stessa attività del pacchetto in uso.
- È possibile tentare di scrivere autonomamente il codice eseguito dal pacchetto.
- È inoltre possibile eliminare la dipendenza del pacchetto modificando la funzionalità dell'app, almeno fino a quando una versione compatibile del pacchetto non diventa disponibile.

Tenere presente che spesso i gestori di progetti open source e gli autori di pacchetti NuGet sono volontari. Questi utenti offrono il loro contributo a titolo gratuito perché sono interessati a un determinato argomento e in molti casi svolgono un'altra attività. Tenere presente che quando si contattano per richiedere il supporto di .NET Core.

Se non è possibile risolvere il problema con una di queste opzioni, potrebbe essere necessario eseguire il porting a .NET Core in un secondo momento.

Il team .NET è interessato a sapere quali sono le librerie più importanti da supportare in .NET Core. È possibile inviare un messaggio di posta elettronica indicando le librerie preferite all'indirizzo dotnet@microsoft.com.

## <a name="analyze-dependencies-that-arent-nuget-packages"></a>Analizzare le dipendenze che non sono pacchetti NuGet

Nel file system può essere presente una dipendenza diversa da un pacchetto NuGet, ad esempio una DLL. L'unico metodo per determinare la portabilità di tale dipendenza è l'esecuzione dello strumento [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport). The tool analyzes assemblies that target the .NET Framework and identifies APIs that aren't portable to other .NET platforms such as .NET Core. È possibile eseguire lo strumento come applicazione console o come [estensione di Visual Studio](../../standard/analyzers/portability-analyzer.md).

## <a name="next-steps"></a>Passaggi successivi

>[!div class="nextstepaction"]
>[Convertire le librerie](libraries.md)
