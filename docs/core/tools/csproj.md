---
title: Aggiunte al formato csproj per .NET Core
description: Informazioni sulle differenze tra i file csproj esistenti e .NET Core
ms.date: 04/08/2019
ms.openlocfilehash: fadc6de43f522129970e48bc72914cf187fe3f82
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607706"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a>Aggiunte al formato csproj per .NET Core

Questo documento descrive le modifiche aggiunte ai file di progetto nell'ambito del passaggio da *project.json* a *csproj* e a [MSBuild](https://github.com/Microsoft/MSBuild). Per altre informazioni sulla sintassi generale dei file di progetto e informazioni di riferimento, vedere la documentazione del [file di progetto MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).

## <a name="implicit-package-references"></a>Riferimenti impliciti al pacchetto

È possibile fare riferimento ai metapacchetti in modo implicito in base ai framework di destinazione specificati nella proprietà `<TargetFramework>` o `<TargetFrameworks>` del file di progetto. `<TargetFrameworks>` viene ignorato se è specificato `<TargetFramework>`, indipendentemente dall'ordine. Per ulteriori informazioni, consultate [Pacchetti, metapacchetti e framework.](../packages.md)

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp2.1</TargetFramework>
 </PropertyGroup>
 ```

 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a>Consigli

Poiché si fa riferimento ai metapacchetti `Microsoft.NETCore.App` o `NETStandard.Library` in modo implicito, ecco le procedure consigliate:

- Quando la destinazione è .NET Core o .NET Standard, non fare mai riferimento in modo esplicito ai metapacchetti `Microsoft.NETCore.App` o `NETStandard.Library` tramite l'elemento `<PackageReference>` nel file di progetto.
- Se occorre una versione specifica del runtime quando la destinazione è .NET Core, è necessario usare la proprietà `<RuntimeFrameworkVersion>` del progetto, ad esempio, `1.0.4`, anziché fare riferimento al metapacchetto.
  - Ciò può avvenire se si usano [distribuzioni autosufficienti](../deploying/index.md#publish-self-contained) e occorre una versione specifica, ad esempio, della patch del runtime 1.0.0 LTS.
- Se occorre una versione specifica del metapacchetto `NETStandard.Library` quando la destinazione è .NET Standard, è possibile usare la proprietà `<NetStandardImplicitPackageVersion>` e impostare la versione necessaria.
- Non aggiungere o aggiornare in modo esplicito i riferimenti al metapacchetto `Microsoft.NETCore.App` o `NETStandard.Library` nei progetti .NET Framework. Se è necessaria qualsiasi versione di `NETStandard.Library` durante l'uso di un pacchetto NuGet basato su .NET Standard, NuGet installa automaticamente tale versione.

## <a name="implicit-version-for-some-package-references"></a>Versione implicita per alcuni riferimenti al pacchetto

La maggior [`<PackageReference>`](#packagereference) parte degli `Version` utilizzi richiede l'impostazione dell'attributo per specificare la versione del pacchetto NuGet da utilizzare. Se però si usa .NET Core 2.1 o 2.2 e si fa riferimento a [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) o [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage), l'attributo non è necessario. .NET Core SDK può selezionare automaticamente la versione dei pacchetti che deve essere usata.

### <a name="recommendation"></a>Recommendation

Quando si fa riferimento ai pacchetti `Microsoft.AspNetCore.App` o `Microsoft.AspNetCore.All`, non specificarne la versione. Se si specifica una versione, l'SDK potrebbe visualizzare l'avviso NETSDK1071. Per non visualizzare più questo avviso, rimuovere la versione del pacchetto come nell'esempio seguente:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore.App" />
</ItemGroup>
```

> Problema noto: .NET Core 2.1 SDK supportava questa sintassi solo quando il progetto usa anche Microsoft.NET.Sdk.Web. Questo problema è stato risolto in .NET Core SDK 2.2.

Questi riferimenti ai metapacchetti ASP.NET Core hanno un comportamento leggermente diverso dalla maggior parte dei normali pacchetti NuGet. Le [distribuzioni dipendenti dal framework](../deploying/index.md#publish-runtime-dependent) delle applicazioni che usano questi metapacchetti sfruttano automaticamente il framework condiviso di ASP.NET Core. Quando si usano i metapacchetti, con l'applicazione **non** vengono distribuiti asset dai pacchetti NuGet di riferimento di ASP.NET Core. Questi asset sono infatti inclusi nel framework condiviso di ASP.NET Core. Gli asset contenuti nel framework condiviso sono ottimizzati per la piattaforma di destinazione per migliorare i tempi di avvio dell'applicazione. Per altre informazioni sul framework condiviso, vedere [Creazione di pacchetti di distribuzione di .NET Core](../distribution-packaging.md).

Se *è* specificata una versione, questa viene considerata come la versione *minima* del framework condiviso ASP.NET Core per le distribuzioni dipendenti dal framework e come una versione *esatta* per le distribuzioni autonome. Questo comportamento può avere le conseguenze seguenti:

- Se la versione di ASP.NET Core installata nel server è inferiore alla versione specificata in PackageReference, l'avvio del processo .NET Core non riesce. Gli aggiornamenti per il metapacchetto sono spesso disponibili su NuGet.org prima che vengano resi disponibili in ambienti di hosting come Azure. L'aggiornamento ad ASP.NET Core della versione in PackageReference potrebbe causare un errore in un'applicazione distribuita.
- Se l'applicazione è stata distribuita come [distribuzione autonoma](../deploying/index.md#publish-self-contained), potrebbe non contenere gli ultimi aggiornamenti della sicurezza a .NET Core. Quando non è specificata una versione, l'SDK può includere automaticamente la versione più recente di ASP.NET Core nella distribuzione autonoma.

## <a name="default-compilation-includes-in-net-core-projects"></a>Dichiarazioni Include di compilazione predefinite nei progetti .NET Core

Con il passaggio al formato *csproj* nelle ultime versioni dell'SDK, per gli elementi di compilazione e le risorse incorporate le dichiarazioni Include ed Exclude predefinite sono state spostate nei file delle proprietà dell'SDK. Ciò significa che non è più necessario specificare queste dichiarazioni nel file di progetto.

Il motivo principale di questo cambiamento è la riduzione del disordine nel file di progetto. Le dichiarazioni predefinite presenti nell'SDK coprono i casi di utilizzo più comuni, pertanto non c'è alcuna necessità di ripeterle per ogni progetto creato. Di conseguenza, i file di progetto sono più piccoli e molto più semplici da comprendere e, se necessario, da modificare manualmente.

La tabella seguente mostra gli elementi e i [GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) Include ed Exclude nell'SDK:

| Elemento           | GLOB Include                              | GLOB Exclude                                                  | GLOB Remove              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| Compilazione           | \*\*/\*.cs (o altre estensioni del linguaggio) | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc  | N/D                      |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | N/D                      |
| nessuno              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | \*\*/\*.cs; \*\*/\*.resx   |

> [!NOTE]
> Il criterio **GLOB Exclude** esclude sempre le cartelle `./bin` e `./obj`, rappresentate rispettivamente dalle proprietà MSBuild `$(BaseOutputPath)` e `$(BaseIntermediateOutputPath)`. Nel complesso, tutte le esclusioni sono rappresentate da `$(DefaultItemExcludes)`.

Se si tenta di compilare un progetto contenente GLOB con l'SDK più recente, viene visualizzato l'errore seguente:

> Duplicate Compile items were included. (Sono stati inclusi elementi di compilazione duplicati) The .NET SDK includes Compile items from your project directory by default. (Per impostazione predefinita, .NET SDK include elementi Compile della directory di progetto) You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file. (Rimuovere questi elementi dal file di progetto o impostare la proprietà 'EnableDefaultCompileItems' su 'false' se li si vuole includere esplicitamente nel file di progetto)

Per ovviare a questo errore, è possibile rimuovere gli elementi `Compile` corrispondenti a quelli elencati nella tabella precedente oppure impostare la proprietà `<EnableDefaultCompileItems>` su `false`, come segue:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

Se si imposta questa proprietà su `false`, si disabilita l'inclusione implicita e viene ripristinato il comportamento degli SDK precedenti, in cui era necessario specificare i GLOB predefiniti nel progetto.

Questa modifica non influisce sulle funzioni principali delle altre dichiarazioni Include. Se tuttavia si vogliono specificare, ad esempio, alcuni file da pubblicare con l'app, è ancora possibile usare i meccanismi noti in *csproj*, ad esempio l'elemento `<Content>`.

`<EnableDefaultCompileItems>` disabilita solo i glob `Compile` ma non influisce su altri glob, come il glob implicito `None`, che si applica anche agli elementi \*.cs. Per questo motivo, **Esplora soluzioni** continuerà a visualizzare elementi \*.cs come parte del progetto, inclusi come elementi `None`. Analogamente, è possibile impostare `<EnableDefaultNoneItems>` sul False per disabilitare il criterio GLOB `None` implicito nel modo seguente:

```xml
<PropertyGroup>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

Per disabilitare **tutti i glob impliciti**, è possibile impostare la proprietà `<EnableDefaultItems>` su `false` come nell'esempio seguente:

```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a>Visualizzare l'intero progetto come lo vede MSBuild

Mentre le modifiche di csproj semplificano notevolmente i file di progetto, si potrebbe voler vedere il progetto completamente espanso come lo vede MSBuild dopo che vengono inclusi l'SDK e le relative destinazioni. Pre-elaborare il progetto con [l'opzione `/pp`](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando [`dotnet msbuild`](dotnet-msbuild.md), che specifica i file importati, le relative risorse e i relativi contributi alla build senza compilare il progetto:

`dotnet msbuild -pp:fullproject.xml`

Se il progetto contiene più framework di destinazione, i risultati del comando devono essere destinati solo a uno di essi specificandolo come proprietà di MSBuild:

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a>Aggiornamenti

### <a name="sdk-attribute"></a>Attributo Sdk

L'elemento radice `<Project>` del file con estensione *csproj* ha un nuovo attributo, denominato `Sdk`. `Sdk` specifica l'SDK che viene usato dal progetto. l'SDK, come descritto dal [documento sui livelli](cli-msbuild-architecture.md), è un set di [attività](/visualstudio/msbuild/msbuild-tasks) e [destinazioni](/visualstudio/msbuild/msbuild-targets) di MSBuild che consente di compilare codice .NET Core. Per .NET Core sono disponibili i seguenti SDK:

1. .NET Core SDK con l'ID di `Microsoft.NET.Sdk`
2. .NET Core Web SDK con l'ID di `Microsoft.NET.Sdk.Web`
3. .NET Core Razor Class Library SDK con l'ID di `Microsoft.NET.Sdk.Razor`
4. Il servizio di lavoro .NET `Microsoft.NET.Sdk.Worker` Core con ID di (dal .NET Core 3.0)
5. I .NET Core WinForms e `Microsoft.NET.Sdk.WindowsDesktop` WPF con id di (da .NET Core 3.0)

Per usare gli strumenti di .NET Core e compilare il codice, è necessario impostare l'attributo `Sdk` su uno di questi ID nell'elemento `<Project>`.

### <a name="packagereference"></a>PackageReference

Un elemento `<PackageReference>` specifica una [dipendenza NuGet nel progetto](/nuget/consume-packages/package-references-in-project-files). L'attributo `Include` specifica l'ID del pacchetto.

```xml
<PackageReference Include="package-id" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a>Versione

L'attributo `Version` obbligatorio specifica la versione del pacchetto da ripristinare. L'attributo rispetta le regole dello schema dell'intervallo di [versioni NuGet.](/nuget/concepts/package-versioning#version-ranges) Il comportamento predefinito è una versione minima, una corrispondenza inclusiva. Ad esempio, `Version="1.2.3"` specificare è equivalente `[1.2.3, )` alla notazione NuGet e significa che il pacchetto risolto avrà la versione 1.2.3 se disponibile o superiore in caso contrario.

#### <a name="includeassets-excludeassets-and-privateassets"></a>IncludeAssets, ExcludeAssets e PrivateAssets

L'attributo `IncludeAssets` specifica gli asset appartenenti al pacchetto specificato da `<PackageReference>` che devono essere usati. Per impostazione predefinita, sono inclusi tutti gli asset del pacchetto.

L'attributo `ExcludeAssets` specifica gli asset appartenenti al pacchetto specificato da `<PackageReference>` che non devono essere usati.

L'attributo `PrivateAssets` specifica gli asset appartenenti al pacchetto specificato da `<PackageReference>` che devono essere usati, indicando inoltre che non devono essere trasmessi al progetto successivo. Gli asset `Analyzers`, `Build` e `ContentFiles` sono privati per impostazione predefinita quando questo attributo non è presente.

> [!NOTE]
> `PrivateAssets`è equivalente all'elemento*xproj* `SuppressParent` *project.json.*/

Questi attributi possono contenere uno o più degli elementi seguenti, separati dal carattere punto e virgola `;` se ne vengono elencati vari:

- `Compile`– il contenuto della cartella *lib* è disponibile per la compilazione.
- `Runtime`– il contenuto della cartella *di runtime* viene distribuito.
- `ContentFiles`: vengono usati i contenuti della cartella *contentfiles*.
- `Build`– vengono utilizzati gli oggetti di scena/destinazioni nella cartella di *compilazione.*
- `Native`– il contenuto delle risorse native viene copiato nella cartella di *output* per il runtime.
- `Analyzers`: vengono usati gli analizzatori.

In alternativa, l'attributo può contenere:

- `None`: nessuno degli asset viene usato.
- `All`: vengono usati tutti gli asset.

### <a name="dotnetclitoolreference"></a>DotNetCliToolReference

Un elemento `<DotNetCliToolReference>` specifica lo strumento dell'interfaccia della riga di comando che si vuole ripristinare nel contesto del progetto. Si tratta di una sostituzione per il nodo `tools` in *project.json*.

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

Si `DotNetCliToolReference` noti che è [ora deprecato](https://github.com/dotnet/announcements/issues/107) a favore di [.NET Core Local Tools](https://aka.ms/local-tools).

#### <a name="version"></a>Versione

`Version` specifica la versione del pacchetto da ripristinare. L'attributo rispetta le regole dello schema di [numerazione delle versioni NuGet](/nuget/create-packages/dependency-versions#version-ranges). Il comportamento predefinito è una versione minima, una corrispondenza inclusiva. Ad esempio, `Version="1.2.3"` specificare è equivalente `[1.2.3, )` alla notazione NuGet e significa che il pacchetto risolto avrà la versione 1.2.3 se disponibile o superiore in caso contrario.

### <a name="runtimeidentifiers"></a>Identificatori di runtime

L'elemento di proprietà `<RuntimeIdentifiers>` consente di specificare un elenco delimitato da punto e virgola di [identificatori di runtime (RID)](../rid-catalog.md) per il progetto.
I RID consentono di pubblicare distribuzioni autonome.

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a>RuntimeIdentifier

L'elemento di proprietà `<RuntimeIdentifier>` consente di specificare un solo [identificatore di runtime (RID)](../rid-catalog.md) per il progetto. Il RID consente di pubblicare una distribuzione autonoma.

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

Usare invece `<RuntimeIdentifiers>` (plurale) se è necessario pubblicare per più runtime. `<RuntimeIdentifier>` può offrire compilazioni più veloci quando è necessario solo un singolo runtime.

### <a name="packagetargetfallback"></a>PackageTargetFallback

L'elemento di proprietà `<PackageTargetFallback>` consente di specificare un set di destinazioni compatibili da usare durante il ripristino di pacchetti. È progettato per consentire ai pacchetti che usano il [TxM (Target x Moniker)](/nuget/schema/target-frameworks) di .NET di interagire con pacchetti che non dichiarano un TxM di .NET. Se il progetto usa il TxM di .NET, devono averlo anche tutti i pacchetti da cui il progetto dipende, a meno che non si aggiunga `<PackageTargetFallback>` al progetto, in modo da rendere compatibili con .NET le piattaforme che non lo sono.

L'esempio seguente include i fallback per tutte le destinazioni nel progetto:

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

L'esempio seguente specifica i fallback solo per la destinazione `netcoreapp2.1`:

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="build-events"></a>Eventi di compilazione

Il modo in cui gli eventi di pre-compilazione e post-compilazione vengono specificati nel file di progetto è stato modificato. Le proprietà PreBuildEvent e PostBuildEvent non sono consigliate nel formato di progetto in stile SDK, perché le macro come .(ProjectDir) non vengono risolte. Ad esempio, il codice seguente non è più supportato:For example, the following code is no longer supported:

```xml
<PropertyGroup>
    <PreBuildEvent>"$(ProjectDir)PreBuildEvent.bat" "$(ProjectDir)..\" "$(ProjectDir)" "$(TargetDir)"</PreBuildEvent>
</PropertyGroup>
```

Nei progetti di tipo SDK, utilizzare `PreBuild` `PostBuild` una destinazione `BeforeTargets` MSBuild denominata o e impostare la proprietà for `PreBuild` o la `AfterTargets` proprietà per `PostBuild`. Per l'esempio precedente, utilizzare il codice seguente:For the preceding example, use the following code:

```xml
<Target Name="PreBuild" BeforeTargets="PreBuildEvent">
    <Exec Command="&quot;$(ProjectDir)PreBuildEvent.bat&quot; &quot;$(ProjectDir)..\&quot; &quot;$(ProjectDir)&quot; &quot;$(TargetDir)&quot;" />
</Target>

<Target Name="PostBuild" AfterTargets="PostBuildEvent">
   <Exec Command="echo Output written to $(TargetDir)" />
</Target>
```

> [!NOTE]
>È possibile usare qualsiasi nome per le destinazioni MSBuild, ma l'IDE di Visual Studio riconosce e didestinazione, pertanto è consigliabile usare tali nomi in modo da poter modificare i comandi nell'IDE di Visual Studio.You can use any name for the MSBuild targets, but the Visual Studio IDE recognizes `PreBuild` and `PostBuild` targets, so we recommend using those names so that you can edit the commands in the Visual Studio IDE.

## <a name="nuget-metadata-properties"></a>Proprietà dei metadati NuGet

Con lo spostamento in MSBuild, sono stati spostati i metadati di input utilizzati durante la creazione del pacchetto NuGet dai file *project.json* a *.csproj.* Gli input sono proprietà di MSBuild, quindi devono trovarsi all'interno di un gruppo `<PropertyGroup>`. Di seguito è riportato l'elenco delle proprietà utilizzate come `dotnet pack` input `Pack` per il processo di compressione quando si utilizza il comando o la destinazione MSBuild che fa parte dell'SDK:

### <a name="ispackable"></a>IsPackable

Valore booleano che specifica se dal progetto può essere creato un pacchetto. Il valore predefinito è `true`.

### <a name="packageversion"></a>PackageVersion

Specifica la versione che avrà il pacchetto risultante. Accetta tutte le forme della stringa di versione NuGet. Il valore predefinito corrisponde al valore di `$(Version)`, vale a dire della proprietà `Version` nel progetto.

### <a name="packageid"></a>PackageId

Specifica il nome del pacchetto risultante. Se non specificato, l'impostazione predefinita per l'operazione `pack` corrisponde all'uso di `AssemblyName` o del nome della directory come nome del pacchetto.

### <a name="title"></a>Titolo

Titolo del pacchetto facilmente comprensibile per l'utente, usato di solito per la visualizzazione dell'interfaccia utente, ad esempio in nuget.org e in Gestione pacchetti in Visual Studio. Se non specificato, viene usato l'ID del pacchetto.

### <a name="authors"></a>Autori

Elenco di autori di pacchetti separati da punto e virgola, che corrispondono ai nomi dei profili in nuget.org. Questi vengono visualizzati nella raccolta NuGet nuget.org e vengono utilizzati per fare riferimento incrociato ai pacchetti dagli stessi autori.

### <a name="packagedescription"></a>PackageDescription

Descrizione lunga del pacchetto per la visualizzazione dell'interfaccia utente.

### <a name="description"></a>Descrizione

Descrizione lunga per l'assembly. Se `PackageDescription` non viene specificato, questa proprietà viene utilizzata anche come descrizione del pacchetto.

### <a name="copyright"></a>Copyright

Informazioni sul copyright per il pacchetto.

### <a name="packagerequirelicenseacceptance"></a>PackageRequireLicenseAcceptance

Valore booleano che specifica se il client deve richiedere al consumer di accettare la licenza del pacchetto prima di installarlo. Il valore predefinito è `false`.

### <a name="developmentdependency"></a>DevelopmentDependency

Valore booleano che specifica se il pacchetto è contrassegnato come dipendenza di solo sviluppo, che impedisce che il pacchetto venga incluso come dipendenza in altri pacchetti. Con PackageReference (NuGet 4.8) questo flag significa anche che gli asset in fase di compilazione vengono esclusi dalla compilazione. Per altre informazioni, vedere [Supporto di DevelopmentDependency per PackageReference](https://github.com/NuGet/Home/wiki/DevelopmentDependency-support-for-PackageReference).

### <a name="packagelicenseexpression"></a>PackageLicenseExpression

Un [identificatore di licenza SPDX](https://spdx.org/licenses/) o un'espressione. Ad esempio: `Apache-2.0`.

Ecco l'elenco completo degli [identificatori di licenza SPDX](https://spdx.org/licenses/). NuGet.org accetta solo licenze approvate OSI o FSF quando si usa un'espressione del tipo di licenza.

La sintassi esatta delle espressioni di licenza è descritta di seguito in [ABNF](https://tools.ietf.org/html/rfc5234).

```abnf
license-id            = <short form license identifier from https://spdx.org/spdx-specification-21-web-version#h.luq9dgcle9mo>

license-exception-id  = <short form license exception identifier from https://spdx.org/spdx-specification-21-web-version#h.ruv3yl8g6czd>

simple-expression = license-id / license-id”+”

compound-expression =  1*1(simple-expression /
                simple-expression "WITH" license-exception-id /
                compound-expression "AND" compound-expression /
                compound-expression "OR" compound-expression ) /
                "(" compound-expression ")" )

license-expression =  1*1(simple-expression / compound-expression / UNLICENSED)
```

> [!NOTE]
> È possibile specificare solo uno degli elementi `PackageLicenseExpression`, `PackageLicenseFile` e `PackageLicenseUrl` contemporaneamente.

### <a name="packagelicensefile"></a>PackageLicenseFile

Percorso di un file di licenza all'interno del pacchetto se si usa una licenza a cui non è stato assegnato un identificatore SPDX oppure una licenza personalizzata (in caso contrario, è preferibile l'elemento `PackageLicenseExpression`)

Sostituisce `PackageLicenseUrl`, non può `PackageLicenseExpression`essere combinato con e richiede Visual Studio versione 15.9.4 e .NET SDK 2.1.502 o 2.2.101 o versione successiva.

Sarà necessario assicurarsi che il file di licenza venga incluso nel pacchetto aggiungendolo in modo esplicito al progetto, come in questo esempio di utilizzo:

```xml
<PropertyGroup>
  <PackageLicenseFile>LICENSE.txt</PackageLicenseFile>
</PropertyGroup>
<ItemGroup>
  <None Include="licenses\LICENSE.txt" Pack="true" PackagePath="$(PackageLicenseFile)"/>
</ItemGroup>
```

### <a name="packagelicenseurl"></a>PackageLicenseUrl

URL della licenza applicabile al pacchetto. (_deprecato da Visual Studio 15.9.4, .NET SDK 2.1.502 e 2.2.101_)

### <a name="packageiconurl"></a>PackageIconUrl

URL di un'immagine 64 x 64 con sfondo trasparente da usare come icona per il pacchetto nella visualizzazione dell'interfaccia utente.

### <a name="packagereleasenotes"></a>PackageReleaseNotes

Note sulla versione per il pacchetto.

### <a name="packagetags"></a>PackageTags

Elenco di tag con valori delimitati da punto e virgola che designa il pacchetto.

### <a name="packageoutputpath"></a>PackageOutputPath

Determina il percorso di output in cui verrà rilasciato il pacchetto creato. Il valore predefinito è `$(OutputPath)`.

### <a name="includesymbols"></a>IncludeSymbols
Valore booleano che indica se al momento della creazione del pacchetto deve essere creato un pacchetto aggiuntivo di simboli. Il formato del pacchetto di simboli è controllato dalla proprietà `SymbolPackageFormat`.

### <a name="symbolpackageformat"></a>SymbolPackageFormat
Specifica il formato del pacchetto di simboli. Se il valore è "symbols.nupkg", verrà creato un pacchetto di simboli legacy con estensione *symbols.nupkg* che contiene i file PDB, DLL e altri file di output. Se il valore è "snupkg", verrà creato un pacchetto di simboli snupkg che contiene i file PDB portatili. Il valore predefinito è "symbols.nupkg".

### <a name="includesource"></a>IncludeSource

Valore booleano che indica se il processo di creazione del pacchetto deve creare un pacchetto di origine. Il pacchetto di origine contiene il codice sorgente della libreria, nonché i file PDB. I file di origine vengono posizionati nella directory `src/ProjectName` del file del pacchetto risultante.

### <a name="istool"></a>IsTool

Specifica se tutti i file di output devono essere copiati nella cartella *tools* anziché nella cartella *lib*. Questo valore è `DotNetCliTool`diverso da un `PackageType` oggetto , specificato impostando il file nel file *con estensione csproj.*

### <a name="repositoryurl"></a>RepositoryUrl

Specifica l'URL per l'archivio in cui si trova il codice sorgente per il pacchetto e/o da cui il codice sorgente viene compilato.

### <a name="repositorytype"></a>RepositoryType

Specifica il tipo dell'archivio. Il valore predefinito è "git".

### <a name="repositorybranch"></a>RepositoryBranch
Specifica il nome del ramo di origine nel repository. Quando il progetto viene incluso in un pacchetto NuGet, viene aggiunto ai metadati del pacchetto.

### <a name="repositorycommit"></a>RepositoryCommit
Commit o insieme di modifiche facoltativo per indicare l'origine con cui è stato compilato il pacchetto. `RepositoryUrl`deve essere specificato anche per questa proprietà da includere. Quando il progetto viene incluso in un pacchetto NuGet, questo commit o insieme di modifiche viene aggiunto ai metadati del pacchetto.

### <a name="nopackageanalysis"></a>NoPackageAnalysis

Specifica che pack non deve eseguire l'analisi del pacchetto dopo la compilazione di quest'ultimo.

### <a name="minclientversion"></a>MinClientVersion

Specifica la versione minima del client NuGet, imposta da nuget.exe e da Gestione pacchetti di Visual Studio, che può installare questo pacchetto.

### <a name="includebuildoutput"></a>IncludeBuildOutput

Questo valore booleano specifica se gli assembly di output di compilazione devono essere compressi o meno nel file *nupkg.*

### <a name="includecontentinpack"></a>IncludeContentInPack

Questo valore booleano specifica se gli elementi con tipo `Content` verranno inclusi automaticamente nel pacchetto risultante. Il valore predefinito è `true`.

### <a name="buildoutputtargetfolder"></a>BuildOutputTargetFolder

Specifica la cartella in cui inserire gli assembly di output. Gli assembly di output (e altri file di output) vengono copiati nelle rispettive cartelle per framework.

### <a name="contenttargetfolders"></a>ContentTargetFolders

Questa proprietà specifica il percorso predefinito in cui devono essere posizionati tutti i file di contenuto se per tali file `PackagePath` non è specificato. Il valore predefinito è "content;contentFiles".

### <a name="nuspecfile"></a>NuspecFile

Percorso relativo o assoluto per il file *.nuspec* usato per la creazione del pacchetto.

> [!NOTE]
> Se il file *.nuspec* è specificato, viene usato **esclusivamente** per le informazioni di creazione del pacchetto e le informazioni nei progetti non vengono usate.

### <a name="nuspecbasepath"></a>NuspecBasePath

Percorso di base per il file *.nuspec*.

### <a name="nuspecproperties"></a>NuspecProperties

Elenco con valori delimitati da punto e virgola di coppie chiave=valore.

## <a name="assemblyinfo-properties"></a>Proprietà AssemblyInfo

Gli [attributi dell'assembly](../../standard/assembly/set-attributes.md) che in genere erano presenti in un file *AssemblyInfo* ora vengono automaticamente generati dalle proprietà.

### <a name="properties-per-attribute"></a>Proprietà dei singoli attributi

Come illustrato nella tabella seguente, ogni attributo ha una proprietà che controlla il contenuto e un altro che ne disabilita la generazione:

| Attributo                                                      | Proprietà               | Proprietà da disabilitare                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

Note:

- Per impostazione predefinita, `AssemblyVersion` e `FileVersion` usano il valore di `$(Version)` senza suffisso. Se ad esempio `$(Version)` è `1.2.3-beta.4`, il valore sarà `1.2.3`.
- Il valore predefinito di `InformationalVersion` è `$(Version)`.
- A `InformationalVersion` viene aggiunto `$(SourceRevisionId)` se la proprietà è presente. Può essere disabilitata usando `IncludeSourceRevisionInInformationalVersion`.
- Le proprietà `Copyright` e `Description` vengono usate anche per i metadati NuGet.
- `Configuration` viene condivisa con tutto il processo di compilazione e impostata tramite il parametro `--configuration` dei comandi `dotnet`.

### <a name="generateassemblyinfo"></a>GenerateAssemblyInfo

Valore booleano che abilita o disabilita tutta la generazione di AssemblyInfo. Il valore predefinito è `true`.

### <a name="generatedassemblyinfofile"></a>GeneratedAssemblyInfoFile

Percorso del file di informazioni sull'assembly generato. L'impostazione predefinita è un file nella directory `$(IntermediateOutputPath)` (obj).
