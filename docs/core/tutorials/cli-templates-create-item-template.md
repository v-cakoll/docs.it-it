---
title: Creare un modello di elemento per dotnet new - Interfaccia della riga di comando di .NET Core
description: Informazioni su come creare un modello di elemento per il comando dotnet new. I modelli di elemento possono contenere un numero qualsiasi di file.
author: thraka
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 5f4038e863d9bb59df470d3516c08fd2ad29c078
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503552"
---
# <a name="tutorial-create-an-item-template"></a>Esercitazione: creare un modello di elemento

Con .NET Core è possibile creare e distribuire modelli per generare progetti, file e persino risorse. Questa esercitazione è la prima parte di una serie che illustra come creare, installare e disinstallare i modelli da usare con il comando `dotnet new`.

In questa parte della serie si apprenderà come:

> [!div class="checklist"]
>
> * Creare una classe per un modello di elemento
> * Creare la cartella e il file di configurazione del modello
> * Installare un modello da un percorso di file
> * Testare un modello di elemento
> * Disinstallare un modello di elemento

## <a name="prerequisites"></a>Prerequisites

* [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) o versioni successive.
* Leggere l'articolo di riferimento [Modelli personalizzati per dotnet new](../tools/custom-templates.md).

  L'articolo di riferimento presenta i concetti di base sui modelli e il modo in cui vengono creati. Alcune di queste informazioni verranno ripetute qui.

* Aprire un terminale e passare alla cartella _working\templates_

## <a name="create-the-required-folders"></a>Creare le cartelle necessarie

Questa serie usa una "cartella di lavoro" in cui è contenuta l'origine del modello e una "cartella di test" usata per testare i modelli. La cartella di lavoro e la cartella di test devono trovarsi nella stessa cartella padre.

Prima di tutto creare la cartella padre. Il nome non è rilevante. Creare quindi una sottocartella denominata _working_. All'interno della cartella _working_ creare una sottocartella denominata _templates_.

Creare poi una cartella nella cartella padre denominata _test_. La struttura di cartelle dovrebbe essere simile alla seguente.

```console
parent_folder
├───test
└───working
    └───templates
```

## <a name="create-an-item-template"></a>Creare un modello di elemento

Un modello di elemento è un tipo specifico di modello che contiene uno o più file. Questi tipi di modelli sono utili quando si vogliono generare elementi come un file di configurazione, di codice o di soluzione. In questo esempio verrà creata una classe che aggiunge un metodo di estensione al tipo stringa.

Nel terminale passare alla cartella _working\templates_ e creare una nuova sottocartella denominata _Extensions_. Accedere alla cartella.

```console
working
└───templates
    └───extensions
```

Creare un nuovo file denominato _CommonExtensions.cs_ e aprirlo con l'editor di testo preferito. Questa classe fornirà un metodo di estensione denominato `Reverse` che inverte il contenuto di una stringa. Incollare il codice seguente e salvare il file:

```csharp
using System;

namespace System
{
    public static class StringExtensions
    {
        public static string Reverse(this string value)
        {
            var tempArray = value.ToCharArray();
            Array.Reverse(tempArray);
            return new string(tempArray);
        }
    }
}
```

Ora che è stato creato il contenuto del modello, è necessario creare la configurazione del modello nella cartella radice del modello.

## <a name="create-the-template-config"></a>Crea la configurazione del modello

I modelli sono riconosciuti in .NET Core grazie a una cartella e a un file di configurazione speciali disponibili nella radice del modello. In questa esercitazione la cartella dei modelli si trova in _working\templates\extensions_.

Quando si crea un modello, tutti i file e le cartelle nella cartella del modello vengono inclusi come parte del modello, ad eccezione della cartella di configurazione speciale. Questa cartella di configurazione è denominata _.template.config_.

Per prima cosa, creare una nuova sottocartella denominata _.template.config_ e aprirla. Creare quindi un nuovo file denominato _template.json_. La struttura di cartelle dovrebbe essere simile alla seguente:

```console
working
└───templates
    └───extensions
        └───.template.config
                template.json
```

Aprire il file _template. JSON_ con l'editor di testo preferito e incollare il codice JSON seguente e salvarlo.

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Code" ],
  "identity": "ExampleTemplate.StringExtensions",
  "name": "Example templates: string extensions",
  "shortName": "stringext",
  "tags": {
    "language": "C#",
    "type": "item"
  }
}
```

Questo file di configurazione contiene tutte le impostazioni per il modello. È possibile visualizzare le impostazioni di base, ad esempio `name` e `shortName`, ma anche un valore `tags/type` impostato su `item`. In questo modo il modello viene categorizzato come modello di elemento. Non esiste alcuna restrizione per il tipo di modello che si può creare. I valori `item` e `project` sono nomi comuni consigliati da .NET Core in modo che gli utenti possano filtrare facilmente il tipo di modello per eventuali ricerche.

L'elemento `classifications` rappresenta la colonna **tags** visualizzata quando si esegue `dotnet new` e si ottiene un elenco di modelli. Gli utenti possono anche eseguire ricerche in base ai tag di classificazione. Non confondere la proprietà `tags` nel file \*.json con l'elenco dei tag `classifications`. Si tratta di due cose diverse, sfortunatamente con nomi simili. Lo schema completo per il file *template.json* è disponibile nell'[archivio degli schemi JSON](http://json.schemastore.org/template). Per altre informazioni sul file *template.json*, vedere il [wiki sulla creazione di modelli dotnet](https://github.com/dotnet/templating/wiki).

Ora che è disponibile un file _.template.config/template.json_ valido, il modello è pronto per l'installazione. Nel terminale passare alla cartella _extensions_ ed eseguire il comando seguente per installare il modello che si trova nella cartella corrente:

* **In Windows**: `dotnet new -i .\`
* **In Linux o macOS**: `dotnet new -i ./`

Questo comando restituisce l'elenco dei modelli installati, che dovrebbe includere quello creato in questa esercitazione.

```console
C:\working\templates\extensions> dotnet new -i .\
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Example templates: string extensions              stringext             [C#]              Common/Code
Console Application                               console               [C#], F#, VB      Common/Console
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

## <a name="test-the-item-template"></a>Testare il modello di elemento

Ora che è stato installato un modello di elemento, è opportuno testarlo. Passare alla cartella _test/_ e creare una nuova applicazione console con `dotnet new console`. Viene generato un progetto funzionante che è possibile testare facilmente con il comando `dotnet run`.

```dotnetcli
dotnet new console
```

Si otterrà un output simile al seguente.

```console
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\test\test.csproj...
  Restore completed in 54.82 ms for C:\test\test.csproj.

Restore succeeded.
```

Eseguire il progetto con.

```dotnetcli
dotnet run
```

Si ottiene l'output seguente.

```console
Hello World!
```

Eseguire quindi `dotnet new stringext` per generare il file _CommonExtensions.cs_ dal modello.

```dotnetcli
dotnet new stringext
```

Si ottiene l'output seguente.

```console
The template "Example templates: string extensions" was created successfully.
```

Modificare il codice in _Program.cs_ per invertire la stringa `"Hello World"` con il metodo di estensione fornito dal modello.

```csharp
Console.WriteLine("Hello World!".Reverse());
```

Eseguire di nuovo il programma per verificare che il risultato sia invertito.

```dotnetcli
dotnet run
```

Si ottiene l'output seguente.

```console
!dlroW olleH
```

Congratulazioni! È stato creato e distribuito un modello di elemento con .NET Core. Per prepararsi per la parte successiva di questa serie di esercitazioni, è necessario disinstallare il modello creato. Assicurarsi di eliminare anche tutti i file dalla cartella _test_. Verrà ripristinato uno stato pulito, pronto per la prossima sezione principale di questa esercitazione.

## <a name="uninstall-the-template"></a>Disinstallare il modello

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
  C:\working\templates\extensions
    Templates:
      Example templates: string extensions (stringext) C#
```

Per disinstallare un modello, eseguire il comando seguente.

```dotnetcli
dotnet new -u C:\working\templates\extensions
```

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stato creato un modello di elemento. Per scoprire come creare un modello di progetto, continuare con questa serie di esercitazioni.

> [!div class="nextstepaction"]
> [Creare un modello di progetto](cli-templates-create-project-template.md)
