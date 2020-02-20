---
title: Creare un pacchetto di modelli per dotnet new
description: Informazioni su come creare un file csproj che compilerà un pacchetto di modelli per il comando dotnet new.
author: thraka
ms.date: 12/10/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 5bc926861dd6a501d7c2d24bd5f7c4116cc78b2c
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503498"
---
# <a name="tutorial-create-a-template-pack"></a>Esercitazione: creare un pacchetto di modelli

Con .NET Core è possibile creare e distribuire modelli per generare progetti, file e persino risorse. Questa esercitazione è la terza parte di una serie che illustra come creare, installare e disinstallare i modelli da usare con il comando `dotnet new`.

In questa parte della serie si apprenderà come:

> [!div class="checklist"]
>
> * Creare un progetto \*. csproj per compilare un pacchetto di modelli
> * Configurare il file di progetto per la creazione del pacchetto
> * Installare un modello da un file di pacchetto NuGet
> * Disinstallare un modello in base all'ID del pacchetto

## <a name="prerequisites"></a>Prerequisites

* Completare la [parte 1](cli-templates-create-item-template.md) e la [parte 2](cli-templates-create-project-template.md) di questa serie di esercitazioni.

  Questa esercitazione usa i due modelli creati nelle prime due parti di questa esercitazione. È possibile usare un modello diverso, purché si copi il modello, come cartella, nella cartella _working\templates\\_ .

* Aprire un terminale e passare alla cartella _working\\_ .

## <a name="create-a-template-pack-project"></a>Creare un progetto per il pacchetto di modelli

Un pacchetto di modelli è costituito da uno o più modelli assemblati in un file. Quando si installa o disinstalla un pacchetto, vengono aggiunti o rimossi rispettivamente tutti i modelli contenuti nel pacchetto. Nelle parti precedenti di questa serie di esercitazioni sono stati utilizzati solo i singoli modelli. Per condividere un modello non incluso in un pacchetto, è necessario copiare la cartella del modello e installarla tramite tale cartella. Dato che un pacchetto di modelli può includere più di un modello ed è un singolo file, la condivisione è più semplice.

I pacchetti di modelli sono rappresentati da un file di pacchetto NuGet (con estensione _nupkg_). Come per qualsiasi altro pacchetto NuGet è possibile caricare il pacchetto di modelli in un feed NuGet. Il comando `dotnet new -i` supporta l'installazione del pacchetto di modelli da un feed di pacchetti NuGet. È anche possibile installare un pacchetto di modelli direttamente da un file con estensione _nupkg_.

Normalmente si usa un file di progetto C# per compilare il codice e generare un file binario. Tuttavia, il progetto può essere usato anche per generare un pacchetto di modelli. Modificando le impostazioni del file _.csproj_, è possibile evitare la compilazione del codice e includere invece tutti gli asset dei modelli come risorse. Quando il progetto viene compilato, viene prodotto un pacchetto NuGet del pacchetto di modelli.

Il pacchetto che verrà creato includerà il [modello di elemento](cli-templates-create-item-template.md) e il [modello di pacchetto](cli-templates-create-project-template.md) creati in precedenza. Dato che i due modelli sono stati raggruppati nella cartella _working\templates\\_ , è possibile usare la cartella _working_ per il file con estensione _csproj_.

Nel terminale passare alla cartella _working_. Creare un nuovo progetto e impostare il nome su `templatepack` e la cartella di output sulla cartella corrente.

```dotnetcli
dotnet new console -n templatepack -o .
```

Il parametro `-n` imposta il nome del file con _estensione csproj_ su _TemplatePack. csproj_. Il parametro `-o` crea i file nella directory corrente. Viene visualizzato un risultato simile all'output seguente.

```dotnetcli
dotnet new console -n templatepack -o .
```

```console
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on .\templatepack.csproj...
  Restore completed in 52.38 ms for C:\working\templatepack.csproj.

Restore succeeded.
```

Aprire poi il file _templatepack.csproj_ nell'editor preferito e sostituire il contenuto con il codice XML seguente:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <PackageType>Template</PackageType>
    <PackageVersion>1.0</PackageVersion>
    <PackageId>AdatumCorporation.Utility.Templates</PackageId>
    <Title>AdatumCorporation Templates</Title>
    <Authors>Me</Authors>
    <Description>Templates to use when creating an application for Adatum Corporation.</Description>
    <PackageTags>dotnet-new;templates;contoso</PackageTags>

    <TargetFramework>netstandard2.0</TargetFramework>

    <IncludeContentInPack>true</IncludeContentInPack>
    <IncludeBuildOutput>false</IncludeBuildOutput>
    <ContentTargetFolders>content</ContentTargetFolders>
  </PropertyGroup>

  <ItemGroup>
    <Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />
    <Compile Remove="**\*" />
  </ItemGroup>

</Project>
```

Le impostazioni `<PropertyGroup>` nel codice XML precedente sono suddivise in tre gruppi. Il primo gruppo gestisce le proprietà necessarie per un pacchetto NuGet. Le tre impostazioni `<Package` riguardano le proprietà del pacchetto NuGet per identificare il pacchetto in un feed NuGet. In particolare, il valore `<PackageId>` viene usato per disinstallare il pacchetto di modelli con un nome singolo anziché con un percorso di directory. Può anche essere usato per installare il pacchetto di modelli da un feed NuGet. Le impostazioni rimanenti, come `<Title>` e `<PackageTags>`, si riferiscono ai metadati visualizzati nel feed NuGet. Per altre informazioni sulle impostazioni di NuGet, vedere le [proprietà di NuGet e MSBuild](/nuget/reference/msbuild-targets).

L'impostazione `<TargetFramework>` deve essere impostata in modo che MSBuild venga eseguito correttamente quando si esegue il comando pack per compilare il progetto e crearne il pacchetto.

Le ultime tre impostazioni riguardano la configurazione corretta del progetto per includere i modelli nella cartella appropriata nel pacchetto NuGet quando viene creato.

`<ItemGroup>` contiene due impostazioni. In primo luogo, l'impostazione `<Content>` include tutto il contenuto della cartella _templates_. Viene anche impostata per escludere qualsiasi cartella _bin_ o cartella _obj_ per impedire l'inclusione di codice compilato (se i modelli sono stati testati e compilati). In secondo luogo, l'impostazione `<Compile>` esclude tutti i file di codice dalla compilazione indipendentemente da dove si trovano. Questa impostazione impedisce che il progetto usato per creare un pacchetto di modelli provi a compilare il codice nella gerarchia di cartelle _templates_.

## <a name="build-and-install"></a>Compilare e installare

Salvare questo file e quindi eseguire il comando pack

```dotnetcli
dotnet pack
```

Questo comando compilerà il progetto e creerà un pacchetto NuGet nella cartella _working\bin\Debug_.

```dotnetcli
dotnet pack
```

```console
Microsoft (R) Build Engine version 16.2.0-preview-19278-01+d635043bd for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 123.86 ms for C:\working\templatepack.csproj.

  templatepack -> C:\working\bin\Debug\netstandard2.0\templatepack.dll
  Successfully created package 'C:\working\bin\Debug\AdatumCorporation.Utility.Templates.1.0.0.nupkg'.
```

Installare quindi il file del pacchetto di modelli con il comando `dotnet new -i PATH_TO_NUPKG_FILE`.

```console
C:\working> dotnet new -i C:\working\bin\Debug\AdatumCorporation.Utility.Templates.1.0.0.nupkg
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Example templates: string extensions              stringext             [C#]              Common/Code
Console Application                               console               [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync          [C#]              Common/Console/C#8
Class library                                     classlib              [C#], F#, VB      Common/Library
```

Se il pacchetto NuGet è stato caricato in un feed NuGet, è possibile usare il comando `dotnet new -i PACKAGEID`, dove `PACKAGEID` è uguale all'impostazione `<PackageId>` dal file _csproj_. Questo ID di pacchetto è uguale all'identificatore del pacchetto NuGet.

## <a name="uninstall-the-template-pack"></a>Disinstallare il pacchetto di modelli

Indipendentemente da come è stato installato il pacchetto di modelli, ovvero con il file _.nupkg_ direttamente o dal feed NuGet, la procedura per rimuovere un pacchetto di modelli è la stessa. Usare il `<PackageId>` del modello che si vuole disinstallare. È possibile ottenere un elenco dei modelli installati eseguendo il comando `dotnet new -u`.

```dotnetcli
dotnet new -u
```

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      dotnet gitignore file (gitignore)
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)

... cut to save space ...

  NUnit3.DotNetNew.Template
    Templates:
      NUnit 3 Test Project (nunit) C#
      NUnit 3 Test Item (nunit-test) C#
      NUnit 3 Test Project (nunit) F#
      NUnit 3 Test Item (nunit-test) F#
      NUnit 3 Test Project (nunit) VB
      NUnit 3 Test Item (nunit-test) VB
  AdatumCorporation.Utility.Templates
    Templates:
      Example templates: async project (consoleasync) C#
      Example templates: string extensions (stringext) C#
```

Eseguire `dotnet new -u AdatumCorporation.Utility.Templates` per disinstallare il modello. Il comando `dotnet new` restituirà informazioni che dovrebbero omettere i modelli installati in precedenza.

Congratulazioni! È stato installato e disinstallato un pacchetto di modelli.

## <a name="next-steps"></a>Passaggi successivi

Per altre informazioni sui modelli, la maggior parte delle quali è già nota, vedere l'articolo [Modelli personalizzati per dotnet new](../tools/custom-templates.md).

* [Wiki del repository GitHub dotnet/templating](https://github.com/dotnet/templating/wiki)
* [Repository GitHub dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples)
* Lo schema [*template.JSON* nell'archivio di schemi JSON](http://json.schemastore.org/template)
