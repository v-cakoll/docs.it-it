---
title: Migrazione di .NET Core da project.json
description: Informazioni su come eseguire la migrazione di un progetto .NET Core meno recente usando project.json
ms.date: 07/19/2017
ms.openlocfilehash: 8a9dc05c82fd5476a70ee36a294a287abbfb68c4
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450687"
---
# <a name="migrating-net-core-projects-from-projectjson"></a>Migrazione di progetti .NET Core da project.json

Questo documento illustra i tre scenari di migrazione seguenti per i progetti .NET Core:

1. [Migrazione da uno schema valido più recente di *project.json* a *csproj*](#migration-from-projectjson-to-csproj)
2. [Migrazione da DNX a csproj](#migration-from-dnx-to-csproj)
3. [Migrazione da RC3 e progetti csproj .NET Core precedenti al formato finale](#migration-from-earlier-net-core-csproj-formats-to-rtm-csproj)

Questo documento è applicabile solo ai progetti .NET Core precedenti che usano Project. JSON. Non si applica alla migrazione da .NET Framework a .NET Core.

## <a name="migration-from-projectjson-to-csproj"></a>Migrazione da project.json a csproj

La migrazione dal formato con estensione *project.json* a quello con estensione *csproj* può essere eseguita mediante uno dei metodi seguenti:

- [Visual Studio](#visual-studio)
- [Strumento da riga di comando dotnet migrate](#dotnet-migrate)

Entrambi i metodi usano lo stesso motore sottostante per eseguire la migrazione dei progetti, pertanto i risultati saranno gli stessi. Nella maggior parte dei casi, l'uso di uno di questi due modi per eseguire la migrazione di *Project. JSON* a *csproj* è l'unico elemento necessario e non è necessaria alcuna modifica manuale del file di progetto. Il file in formato *csproj* risultante verrà denominato con lo stesso nome della directory che lo contiene.

### <a name="visual-studio"></a>Visual Studio

Quando si apre un file con estensione *xproj* o un file di soluzione che fa riferimento a file con *estensione Xproj* in Visual Studio 2017 o visual studio 2019 versione 16,2 e versioni precedenti, viene visualizzata la finestra di dialogo **aggiornamento unidirezionale** . La finestra di dialogo consente di visualizzare i progetti di cui eseguire la migrazione. Se si apre un file di soluzione, verranno elencati tutti i progetti specificati nel file di soluzione. Rivedere l'elenco dei progetti di cui eseguire la migrazione e selezionare **OK**.

![Finestra di dialogo Aggiornamento unidirezionale con l'elenco di progetti di cui eseguire la migrazione](media/one-way-upgrade.jpg)

Visual Studio esegue automaticamente la migrazione dei progetti selezionati. Quando si esegue la migrazione di una soluzione, se non si scelgono tutti i progetti, viene visualizzata la stessa finestra di dialogo in cui viene chiesto di aggiornare i progetti rimanenti dalla soluzione. Dopo la migrazione del progetto, è possibile visualizzare e modificare il relativo contenuto facendo clic sul progetto con il pulsante destro del mouse nella finestra **Esplora soluzioni** e selezionando **Modifica \<nome progetto>.csproj**.

I file di cui è stata eseguita la migrazione (*Project. JSON*, *Global. JSON*, *. xproj*e file di soluzione) vengono spostati in una cartella di *backup* . Il file di soluzione migrato viene aggiornato a Visual Studio 2017 o a Visual Studio 2019 e non sarà possibile aprire il file di soluzione in Visual Studio 2015 o versioni precedenti. Anche un file denominato *UpgradeLog. htm* che contiene un report di migrazione viene salvato e aperto automaticamente.

> [!IMPORTANT]
> In Visual Studio 2019 versione 16,3 e successive non è possibile caricare o migrare un file con *estensione xproj* . Inoltre, Visual Studio 2015 non offre la possibilità di eseguire la migrazione di un file con *estensione xproj* . Se si usa una di queste versioni di Visual Studio, installare una versione appropriata di Visual Studio o usare lo strumento di migrazione da riga di comando descritto di seguito.

### <a name="dotnet-migrate"></a>dotnet migrate

Nello scenario della riga di comando, è possibile usare il comando [`dotnet migrate`](../tools/dotnet-migrate.md). Viene eseguita la migrazione di un progetto, una soluzione o un set di cartelle in tale ordine, a seconda di quali sono stati trovati. Quando si esegue la migrazione di un progetto, questa riguarda il progetto e tutte le relative dipendenze.

I file di cui è stata eseguita la migrazione (*Project. JSON*, *Global. JSON*e *. xproj*) vengono spostati in una cartella di *backup* .

> [!NOTE]
> Se si usa Visual Studio Code, il comando `dotnet migrate` non modifica i file di Visual Studio Code specifici, ad esempio *Tasks. JSON*. Questi file devono essere modificati manualmente.
> Questo vale anche se si usa un editor o un ambiente di sviluppo integrato (IDE) diverso da Visual Studio.

Vedere [un mapping tra le proprietà Project. JSON e csproj](../tools/project-json-to-csproj.md) per un confronto dei formati *Project. JSON* e *. csproj* .

Se si verifica un errore:

> Non è stato trovato alcun eseguibile corrispondente al comando DotNet-migrate

Eseguire `dotnet --version` per visualizzare la versione in uso. [`dotnet migrate`](../tools/dotnet-migrate.md) è stato introdotto in .NET Core SDK 1.0.0 e rimosso nella versione 3.0.100.
Questo errore viene ricevuto se si dispone di un file *Global. JSON* nella directory corrente o padre e la versione `sdk` specificata non rientra nell'intervallo.

## <a name="migration-from-dnx-to-csproj"></a>Migrazione da DNX a csproj

Se si sta ancora usando DNX per lo sviluppo di .NET Core, il processo di migrazione deve essere eseguito in due fasi:

1. Usare la [guida alla migrazione esistente DNX](from-dnx.md) per eseguire la migrazione da DNX alla CLI abilitata per project.json.
2. Seguire la procedura indicata nella sezione precedente per eseguire la migrazione da *project.json* a *csproj*.

> [!NOTE]
> DNX è stato dichiarato ufficialmente deprecato in occasione della versione Preview 1 della CLI di .NET Core.

## <a name="migration-from-earlier-net-core-csproj-formats-to-rtm-csproj"></a>Migrazione da versioni precedenti dei formati csproj di.NET Core alla versione RTM

Il formato di file csproj di .NET Core è stato modificato e si è evoluto ad ogni versione provvisoria degli strumenti. Non esiste alcuno strumento che possa eseguire la migrazione del file di progetto da versioni precedenti del formato csproj alla versione più recente, pertanto è necessario modificare manualmente il file di progetto. I passaggi effettivi dipendono dalla versione del file di progetto di cui si esegue la migrazione. Di seguito vengono riportate alcune indicazioni da considerare in base alle modifiche avvenute tra le versioni:

- Rimuovere la proprietà della versione dall'elemento `<Project>`, se presente.
- Rimuovere lo spazio dei nomi XML (`xmlns`) dall'elemento `<Project>`.
- Se non è presente, aggiungere l'attributo `Sdk` all'elemento `<Project>` e impostarlo su `Microsoft.NET.Sdk` o su `Microsoft.NET.Sdk.Web`. Questo attributo specifica che il progetto usa l'SDK corretto. `Microsoft.NET.Sdk.Web` viene usato per le applicazioni web.
- Rimuovere le istruzioni `<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />` e `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` nella parte superiore e inferiore del progetto. Queste istruzioni di importazione sono previste dall'SDK, pertanto non sono necessarie nel progetto.
- Se si dispone di `Microsoft.NETCore.App` o `NETStandard.Library` `<PackageReference>` elementi del progetto, è necessario rimuoverli. Questi riferimenti al pacchetto sono [impliciti nell'SDK](https://aka.ms/sdkimplicitrefs).
- Rimuovere l'elemento `Microsoft.NET.Sdk` `<PackageReference>`, se esistente. Il riferimento all'SDK viene specificato tramite l'attributo `Sdk` dell'elemento `<Project>`.
- Rimuovere i [GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) che sono [impliciti nell'SDK](../project-sdk/overview.md#default-compilation-includes). Se i glob vengono lasciati nel progetto, verrà visualizzato un errore in fase di compilazione poiché gli elementi di compilazione verranno duplicati.

Dopo questi passaggi, il progetto sarà completamente compatibile con la versione RTM del formato di file csproj.

Per esempi del formato csproj prima e dopo la migrazione dalla versione precedente a quella nuova, vedere l'articolo [Updating Visual Studio 2017 RC – .NET Core Tooling improvements](https://devblogs.microsoft.com/dotnet/updating-visual-studio-2017-rc-net-core-tooling-improvements/) (Aggiornamento di Visual Studio 2017 RC - Miglioramento degli strumenti .NET Core) sul blog di .NET.

## <a name="see-also"></a>Vedere anche

- [Conversione, migrazione e aggiornamento dei progetti di Visual Studio](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects)
