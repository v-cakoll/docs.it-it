---
title: Creare un modello di progetto per dotnet new
description: Informazioni su come creare un modello di progetto per il comando dotnet new.
author: thraka
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: f53f4037f832265a35f65bf2e5096c7e5a37bcf1
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503528"
---
# <a name="tutorial-create-a-project-template"></a>Esercitazione: creare un modello di progetto

Con .NET Core è possibile creare e distribuire modelli per generare progetti, file e persino risorse. Questa esercitazione è la seconda parte di una serie che illustra come creare, installare e disinstallare i modelli da usare con il comando `dotnet new`.

In questa parte della serie si apprenderà come:

> [!div class="checklist"]
>
> * Creare le risorse di un modello di progetto
> * Creare la cartella e il file di configurazione del modello
> * Installare un modello da un percorso di file
> * Testare un modello di elemento
> * Disinstallare un modello di elemento

## <a name="prerequisites"></a>Prerequisites

* Completare la [parte 1](cli-templates-create-item-template.md) di questa serie di esercitazioni.
* Aprire un terminale e passare alla cartella _working\templates_

## <a name="create-a-project-template"></a>Creare un modello di progetto

I modelli di progetto producono progetti pronti per l'esecuzione che consentono agli utenti di iniziare in modo facile a utilizzare un working set di codice. .NET Core include alcuni modelli di progetto, ad esempio un'applicazione console o una libreria di classi. In questo esempio verrà creato un nuovo progetto console che abilita C# 8.0 e produce un punto di ingresso `async main`.

Nel terminale passare alla cartella _working\templates_ e creare una nuova sottocartella denominata _consoleasync_. Immettere la sottocartella ed eseguire `dotnet new console` per generare l'applicazione console standard. Verranno modificati i file prodotti da questo modello per creare un nuovo modello.

```console
working
└───templates
    └───consoleasync
            consoleasync.csproj
            Program.cs
```

## <a name="modify-programcs"></a>Modificare Program.cs

Aprire il file _program.cs_. Il progetto console non usa un punto di ingresso asincrono, quindi è consigliabile aggiungerlo. Modificare il codice nel modo seguente e salvare il file.

```csharp
using System;
using System.Threading.Tasks;

namespace consoleasync
{
    class Program
    {
        static async Task Main(string[] args)
        {
            await Console.Out.WriteAsync("Hello World with C# 8.0!");
        }
    }
}
```

## <a name="modify-consoleasynccsproj"></a>Modificare consoleasync.csproj

La versione del linguaggio C# usata dal progetto verrà ora aggiornata alla versione 8.0. Modificare il file _consoleasync.csproj_ e aggiungere l'impostazione `<LangVersion>` a un nodo `<PropertyGroup>`.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.2</TargetFramework>

    <LangVersion>8.0</LangVersion>

  </PropertyGroup>
  
</Project>
```

## <a name="build-the-project"></a>Compilare il progetto

Prima di completare un modello di progetto, è necessario testarlo per assicurarsi che venga compilato ed eseguito correttamente.

Nel terminale eseguire il comando seguente.

```dotnetcli
dotnet run
```

Si ottiene l'output seguente.

```console
Hello World with C# 8.0!
```

È possibile eliminare le cartelle _obj_ e _bin_ create usando `dotnet run`. L'eliminazione di questi file garantisce che il modello includa solo i file correlati al modello e non tutti i file che risultano da un'azione di compilazione.

Ora che è stato creato il contenuto del modello, è necessario creare la configurazione del modello nella cartella radice del modello.

## <a name="create-the-template-config"></a>Crea la configurazione del modello

I modelli sono riconosciuti in .NET Core grazie a una cartella e a un file di configurazione speciali disponibili nella radice del modello. In questa esercitazione la cartella dei modelli si trova in _working\templates\consoleasync_.

Quando si crea un modello, tutti i file e le cartelle nella cartella del modello vengono inclusi come parte del modello, ad eccezione della cartella di configurazione speciale. Questa cartella di configurazione è denominata _.template.config_.

Per prima cosa, creare una nuova sottocartella denominata _.template.config_ e aprirla. Creare quindi un nuovo file denominato _template.json_. La struttura di cartelle dovrebbe essere simile alla seguente.

```console
working
└───templates
    └───consoleasync
        └───.template.config
                template.json
```

Aprire il file _template. JSON_ con l'editor di testo preferito e incollare il codice JSON seguente e salvarlo.

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Console", "C#8" ],
  "identity": "ExampleTemplate.AsyncProject",
  "name": "Example templates: async project",
  "shortName": "consoleasync",
  "tags": {
    "language": "C#",
    "type": "project"
  }
}
```

Questo file di configurazione contiene tutte le impostazioni per il modello. È possibile visualizzare le impostazioni di base, ad esempio `name` e `shortName`, ma anche un valore `tags/type` impostato su `project`. Questo valore designa il modello come modello di progetto. Non esiste alcuna restrizione per il tipo di modello che si può creare. I valori `item` e `project` sono nomi comuni consigliati da .NET Core in modo che gli utenti possano filtrare facilmente il tipo di modello per eventuali ricerche.

L'elemento `classifications` rappresenta la colonna **tags** visualizzata quando si esegue `dotnet new` e si ottiene un elenco di modelli. Gli utenti possono anche eseguire ricerche in base ai tag di classificazione. Non confondere la proprietà `tags` nel file JSON con l'elenco dei tag `classifications`. Si tratta di due cose diverse, sfortunatamente con nomi simili. Lo schema completo per il file *template.json* è disponibile nell'[archivio degli schemi JSON](http://json.schemastore.org/template). Per altre informazioni sul file *template.json*, vedere il [wiki sulla creazione di modelli dotnet](https://github.com/dotnet/templating/wiki).

Ora che è disponibile un file _.template.config/template.json_ valido, il modello è pronto per l'installazione. Prima di installare il modello, assicurarsi di eliminare eventuali file e cartelle aggiuntivi che non si vuole includere nel modello, ad esempio le cartelle _bin_ o _obj_. Nel terminale passare alla cartella _consoleasync_ ed eseguire `dotnet new -i .\` per installare il modello che si trova nella cartella corrente. Se si usa un sistema operativo Linux o macOS, usare una barra: `dotnet new -i ./`.

Questo comando restituisce l'elenco dei modelli installati, che dovrebbe includere quello creato in questa esercitazione.

```dotnetcli
dotnet new -i .\
```

Si otterrà un output simile al seguente.

```console
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Console Application                               console               [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync          [C#]              Common/Console/C#8
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

### <a name="test-the-project-template"></a>Testare il modello di progetto

Ora che è stato installato un modello di elemento, è opportuno testarlo.

1. Passare alla cartella _test_

1. Creare una nuova applicazione console con il comando seguente che genera un progetto funzionante che è possibile testare facilmente con il comando `dotnet run`.

    ```dotnetcli
    dotnet new consoleasync
    ```

    Si ottiene l'output seguente.

    ```console
    The template "Example templates: async project" was created successfully.
    ```

1. Eseguire il progetto usando il comando seguente.

    ```dotnetcli
    dotnet run
    ```

    Si ottiene l'output seguente.

    ```console
    Hello World with C# 8.0!
    ```

Congratulazioni! È stato creato e distribuito un modello di progetto con .NET Core. Per prepararsi per la parte successiva di questa serie di esercitazioni, è necessario disinstallare il modello creato. Assicurarsi di eliminare anche tutti i file dalla cartella _test_. Verrà ripristinato uno stato pulito, pronto per la prossima sezione principale di questa esercitazione.

### <a name="uninstall-the-template"></a>Disinstallare il modello

Poiché il modello è stato installato usando un percorso di file, è necessario disinstallarlo con il percorso di file **assoluto**. È possibile visualizzare un elenco dei modelli installati eseguendo il comando `dotnet new -u`. Il modello creato in questo articolo dovrebbe essere l'ultimo dell'elenco. Usare il percorso indicato per disinstallare il modello con il comando `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>`.

```dotnetcli
dotnet new -u
```

Si otterrà un output simile al seguente.

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
  C:\working\templates\consoleasync
    Templates:
      Example templates: async project (consoleasync) C#
```

Per disinstallare un modello, eseguire il comando seguente.

```dotnetcli
dotnet new -u C:\working\templates\consoleasync
```

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stato creato un modello di progetto. Per informazioni su come creare un pacchetto dei modelli di elementi e di progetto in un file di facile utilizzo, continuare con questa serie di esercitazioni.

> [!div class="nextstepaction"]
> [Creare un pacchetto di modelli](cli-templates-create-template-pack.md)
