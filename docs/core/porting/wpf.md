---
title: Convertire un'app WPF in .NET Core 3.0
description: Illustra come convertire un'applicazione Windows Presentation Foundation di NET Framework in .NET Core 3.0 per Windows.
author: Thraka
ms.author: adegeo
ms.date: 03/27/2019
ms.custom: ''
ms.openlocfilehash: 5c7e3aca0a473abb831693244d1b194985f2ef7f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342206"
---
# <a name="how-to-port-a-wpf-desktop-app-to-net-core"></a>Procedura: Convertire un'app desktop WPF in .NET Core

Questo articolo descrive come convertire l'app desktop basata su Windows Presentation Foundation (WPF) da .NET Framework a .NET Core 3.0. .NET Core SDK 3.0 include supporto per applicazioni WPF. WPF è comunque un framework solo per Windows e supporta l'esecuzione solo in Windows. Questo esempio usa l'interfaccia della riga di comando di .NET Core SDK per creare e gestire il progetto.

In questo articolo vengono usati vari nomi per identificare i tipi di file usati per la migrazione. Durante la migrazione del progetto personale i file verranno denominati in modo diverso, pertanto abbinarli mentalmente a quelli elencati di seguito:

| File | Description |
| ---- | ----------- |
| **MyApps.sln** | Nome del file di soluzione. |
| **MyWPF.csproj** | Nome del progetto WPF di .NET Framework da convertire. |
| **MyWPFCore.csproj** | Nome del nuovo progetto .NET Core creato. |
| **MyAppCore.exe** | App WPF di .NET Core eseguibile. |

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) per tutte le operazioni di progettazione che si vogliono eseguire.

  Installare i carichi di lavoro di Visual Studio seguenti:
  - Sviluppo per desktop .NET
  - Sviluppo multipiattaforma .NET Core

- Un progetto WPF in uso in una soluzione che viene compilata ed eseguita senza problemi.
- Il progetto deve essere codificato in C#. 
- Installare l'anteprima più recente di [.NET Core 3.0](https://aka.ms/netcore3download).

>[!NOTE]
>**Visual Studio 2017** non supporta progetti .NET Core 3.0. **Visual Studio 2019** supporta i progetti .NET Core 3.0, ma non supporta ancora la finestra di progettazione grafica per i progetti WPF di .NET Core 3.0. Per usare la finestra di progettazione grafica, è necessario avere un progetto WPF di .NET nella soluzione che condivide i file con il progetto .NET Core.

### <a name="consider"></a>Consider

Per la conversione di un'applicazione WPF di .NET Framework, esistono alcuni aspetti da considerare.

01. Controllare che l'applicazione sia un buon candidato per la migrazione.

    Usare [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) per determinare se sarà possibile eseguire la migrazione del progetto a .NET Core 3.0. Se il progetto presenta problemi con .NET Core 3.0, l'analizzatore consente di identificarli.

01. Si usa una versione diversa di WPF.

    In concomitanza con il rilascio di .NET Core 3.0 Preview 1, è stato reso disponibile WPF come open source su GitHub. Il codice per WPF di .NET Core è un fork della base di codice di WPF di .NET Framework. È possibile che esistano alcune differenze che non consentono la conversione dell'app.

01. [Windows Compatibility Pack][compat-pack] può essere utile per la migrazione.

    Alcune API che sono disponibili in .NET Framework non sono disponibili in .NET Core 3.0. [Windows Compatibility Pack][compat-pack] aggiunge molte di queste API e può essere utile per rendere l'app WPF compatibile con .NET Core.

01. Aggiornare i pacchetti NuGet usati dal progetto.

    È sempre consigliabile usare le versioni più recenti dei pacchetti NuGet prima di qualsiasi migrazione. Se l'applicazione fa riferimento a pacchetti NuGet, aggiornarli alla versione più recente. Verificare che l'applicazione venga compilata correttamente. Dopo l'aggiornamento, se sono presenti errori di pacchetto, effettuare il downgrade del pacchetto alla versione più recente che non causa problemi al codice.

01. Visual Studio 2019 non supporta ancora WPF Designer per .NET Core 3.0

    Attualmente è necessario mantenere il file di progetto WPF di .NET Framework esistente se si vuole usare WPF Designer da Visual Studio.

## <a name="create-a-new-sdk-project"></a>Creare un nuovo progetto SDK

Il nuovo progetto .NET Core 3.0 creato deve essere in una directory diversa dal progetto .NET Framework. Se si trovano entrambi nella stessa directory, è possibile che si verifichino conflitti con i file generati nella directory **obj**. In questo esempio si creerà una directory denominata **MyWPFAppCore** nella directory **SolutionFolder**:

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore      <--- New folder for core project
```

Quindi sarà necessario creare il progetto **MyWPFCore.csproj** nella directory **MyWPFAppCore**. È possibile creare questo file manualmente usando l'editor di testo preferito. Incollare il codice XML seguente:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

Se non si vuole creare manualmente il file di progetto, è possibile usare Visual Studio o .NET Core SDK per generare il progetto. Tuttavia, è necessario eliminare tutti gli altri file generati dal modello di progetto, ad eccezione del file di progetto. Per usare l'SDK, eseguire il comando seguente dalla directory **SolutionFolder**:

```cli
dotnet new wpf -o MyWPFAppCore -n MyWPFCore
```

Dopo aver creato **MyWPFCore.csproj**, la struttura della directory dovrebbe essere simile alla seguente:

```
SolutionFolder
├───MyApps.sln
├───MyWPFApp
│   └───MyWPF.csproj
└───MyWPFAppCore
    └───MyWPFCore.csproj
```

Il progetto **MyFormsCore.csproj** sarà aggiunto a **MyApps.sln** con Visual Studio o con l'interfaccia della riga di comando di .NET Core dalla directory **SolutionFolder**:

```cli
dotnet sln add .\MyWPFAppCore\MyWPFCore.csproj
```

## <a name="fix-assembly-info-generation"></a>Correggere la generazione delle informazioni sull'assembly

I progetti Windows Presentation Foundation che sono stati creati con .NET Framework includono un file `AssemblyInfo.cs` che contiene gli attributi dell'assembly, ad esempio la versione dell'assembly da generare. I progetti in stile SDK generano automaticamente queste informazioni in base al file di progetto SDK. La presenza di entrambi i tipi di "informazioni sull'assembly" crea un conflitto. Per risolvere questo problema, disabilitare la generazione automatica, che impone l'uso del file `AssemblyInfo.cs` esistente nel progetto.

Sono disponibili tre impostazioni da aggiungere al nodo `<PropertyGroup>` principale. 

- **GenerateAssemblyInfo**\
Quando si imposta questa proprietà su `false`, non verranno generati gli attributi dell'assembly. Ciò consente di evitare il conflitto con il file `AssemblyInfo.cs` esistente dal progetto .NET Framework.

- **AssemblyName**\
Il valore di questa proprietà è il file binario di output creato durante la compilazione. Non è necessario aggiungere un'estensione al nome. Ad esempio, `MyCoreApp` produce `MyCoreApp.exe`.

- **RootNamespace**\
Spazio dei nomi predefinito usato dal progetto. Deve corrispondere allo spazio dei nomi predefinito del progetto .NET Framework.

Aggiungere questi tre elementi al nodo `<PropertyGroup>` nel file `MyWPFCore.csproj`:

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
    <UseWPF>true</UseWPF>

    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <AssemblyName>MyCoreApp</AssemblyName>
    <RootNamespace>MyWPF</RootNamespace>
  </PropertyGroup>

</Project>
```

## <a name="add-source-code"></a>Aggiungere codice sorgente
Il progetto **MyWPFCore.csproj** per il momento non compila il codice. Per impostazione predefinita, i progetti .NET Core includono automaticamente tutto il codice sorgente nella directory corrente e in eventuali directory figlio. È necessario configurare il progetto per includere il codice dal progetto .NET Framework usando un percorso relativo. Se il progetto .NET Framework usava file **con estensione resx** per le icone e le risorse delle finestre e dei controlli, sarà necessario includere anche questi. 

Il primo nodo `<ItemGroup>` da aggiungere al progetto include il file **App.xaml** che rappresenta la configurazione di avvio e le risorse usate dall'app. Il file **App.xaml** include anche un file **App.xaml.cs** di accompagnamento, che sarà tuttavia incluso automaticamente in un elemento `<ItemGroup>` diverso.

```xml
  <ItemGroup>
    <ApplicationDefinition Include="..\MyWPFApp\App.xaml">
      <Generator>MSBuild:Compile</Generator>
    </ApplicationDefinition>
  </ItemGroup>
```

A questo punto aggiungere il nodo `<ItemGroup>` seguente al progetto. Ogni istruzione include un criterio GLOB per i file che include le directory figlio. Include il codice sorgente per il progetto, tutti i file di impostazioni e tutte le risorse. La directory **obj** è esplicitamente esclusa.

```xml
  <ItemGroup>
    <Compile Include="..\MyWPFApp\**\*.cs" Exclude="..\MyWPFApp\obj\**" />
    <None Include="..\MyWPFApp\**\*.settings" />
    <EmbeddedResource Include="..\MyWPFApp\**\*.resx" />
  </ItemGroup>
```

Quindi includere un altro nodo `<ItemGroup>` che contiene una voce `<Page>` per ogni file **xaml** nel progetto, ad eccezione del file **App.xaml**. Contengono tutte le finestre, le pagine e le risorse nel formato **xaml**. Qui non è possibile usare un criterio GLOB. È necessario aggiungere una voce per ogni file e indicare l'elemento `<Generator>` usato.

```xml
  <ItemGroup>
    <Page Include="..\MyWPFApp\MainWindow.xaml">
      <Generator>MSBuild:Compile</Generator>
    </Page>
  </ItemGroup>
```

## <a name="add-nuget-packages"></a>Aggiungere pacchetti NuGet

Aggiungere al progetto .NET Core ogni pacchetto NuGet a cui fa riferimento il progetto .NET Framework. 

È molto probabile che l'app WPF di .NET Framework includa un file **packages.config** che contiene un elenco di tutti i pacchetti NuGet a cui fa riferimento il progetto. È possibile esaminare questo elenco per determinare quali pacchetti NuGet aggiungere al progetto .NET Core. Ad esempio, se il progetto .NET Framework fa riferimento al pacchetto NuGet `MahApps.Metro`, aggiungerlo al progetto usando Visual Studio. È anche possibile aggiungere un riferimento al pacchetto con l'interfaccia della riga di comando di .NET Core dalla directory **SolutionFolder**:

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package MahApps.Metro -v 2.0.0-alpha0262
```

Il comando precedente consente di aggiungere il riferimento NuGet seguente al progetto **MyWPFCore.csproj**:

```xml
  <ItemGroup>
    <PackageReference Include="MahApps.Metro" Version="2.0.0-alpha0262" />
  </ItemGroup>
```

## <a name="problems-compiling"></a>Problemi di compilazione

Se si riscontrano problemi durante la compilazione dei progetti, è possibile che siano in uso alcune API solo per Windows disponibili in .NET Framework, ma non in .NET Core. È possibile provare ad aggiungere il pacchetto NuGet [Windows Compatibility Pack][compat-pack] al progetto. Questo pacchetto può essere eseguito solo in Windows e aggiunge circa 20.000 API Windows ai progetti .NET Core e .NET Standard.

```cli
dotnet add .\MyWPFAppCore\MyWPFCore.csproj package Microsoft.Windows.Compatibility
```

Il comando precedente aggiunge il codice seguente al progetto **MyWPFCore.csproj**:

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="2.0.1" />
  </ItemGroup>
```

## <a name="wpf-designer"></a>WPF Designer

Come descritto in dettaglio in questo articolo, Visual Studio 2019 supporta solo WPF Designer nei progetti .NET Framework. È possibile creare un progetto .NET Core affiancato per testare il progetto .NET Core mentre si usa progetto .NET Framework per la progettazione dei moduli. Il file di soluzione include sia i progetti .NET Framework che .NET Core. Aggiungere e progettare i moduli e i controlli nel progetto .NET Framework e, in base ai criteri GLOB per i file aggiunti ai progetti .NET Core, qualsiasi file nuovo o modificato verrà incluso automaticamente nei progetti .NET Core.

Quando Visual Studio 2019 supporterà WPF Designer, sarà possibile copiare e incollare il contenuto del file di progetto .NET Core nel file di progetto .NET Framework. Eliminare quindi i criteri GLOB per i file aggiunti con gli elementi `<Source>` e `<EmbeddedResource>`. Correggere i percorsi per qualsiasi riferimento del progetto usato dall'app. In questo modo il progetto .NET Framework viene effettivamente aggiornato a .NET Core.
 
## <a name="next-steps"></a>Passaggi successivi

* Vedere altre informazioni su [Windows Compatibility Pack][compat-pack].
* Guardare un [video sulla conversione](https://www.youtube.com/watch?v=5MomsgkWkVw&list=PLS__JrkRveTMiWxG-Lv4cBwYfMQ6m2gmt) del progetto WPF di .NET Framework in .NET Core.

[compat-pack]: windows-compat-pack.md
