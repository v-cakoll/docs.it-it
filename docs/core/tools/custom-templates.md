---
title: Modelli personalizzati per dotnet new
description: Informazioni sui modelli personalizzati per qualsiasi tipo di file o progetto .NET.
keywords: dotnet new,interfaccia della riga di comando,comando dell'interfaccia della riga di comando,.NET Core, modello,modelli
author: guardrex
ms.author: mairaw
ms.date: 08/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.translationtype: HT
ms.sourcegitcommit: c58ed1b3c09f1e358d0b66f6cf7186821601fd69
ms.openlocfilehash: c68e382450a763fd0521b7defdd79d8433e1acde
ms.contentlocale: it-it
ms.lasthandoff: 08/12/2017

---

# <a name="custom-templates-for-dotnet-new"></a>Modelli personalizzati per dotnet new

[.NET Core SDK](https://www.microsoft.com/net/download/core) viene fornito con molti modelli pre-installati da usare con il comando [ `dotnet new`](dotnet-new.md). A partire da .NET Core 2.0, è possibile creare modelli personalizzati per qualsiasi tipo di progetto, ad esempio un'app, un servizio, uno strumento o una libreria di classi. È possibile anche creare un modello che restituisce uno o più file indipendenti, ad esempio un file di configurazione.

È possibile installare modelli personalizzati da un pacchetto NuGet in qualsiasi feed, facendo riferimento a un file *nupkg* NuGet direttamente o specificando una directory del file system che contiene il modello. Il motore del modello offre funzionalità che consentono di sostituire i valori, includere ed escludere file e aree del file ed eseguire operazioni di elaborazione personalizzata quando si usa il modello.

Il motore del modello è open source e il repository del codice online si trova in [dotnet/templating](https://github.com/dotnet/templating/) su GitHub. Visitare il repository [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) per gli esempi di modelli. Più modelli, inclusi i modelli di terze parti, sono disponibili in [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Modelli disponibili per dotnet new) su GitHub. Per altre informazioni sulla creazione e l'uso di modelli personalizzati, vedere [Come creare modelli personalizzati per dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/) e la [wiki del repository GitHub dotnet/templating](https://github.com/dotnet/templating/wiki).

Per seguire una procedura dettagliata e creare un modello, vedere l'esercitazione [Creare un modello personalizzato per dotnet new](~/docs/core/tutorials/create-custom-template.md).

## <a name="configuration"></a>Configurazione

Un modello è costituito dai componenti seguenti:

- File e cartelle di origine
- Un file di configurazione (*template.json*)

### <a name="source-files-and-folders"></a>File e cartelle di origine

I file e le cartelle di origine includono tutti i file e le cartelle che si desidera vengano usati dal motore del modello quando viene eseguito il comando `dotnet new <TEMPLATE>`. Il motore del modello è progettato per usare *progetti eseguibili* come codice sorgente per creare i progetti. Ciò comporta diversi vantaggi:

- Il motore del modello non richiede di inserire speciali token nel codice sorgente del progetto.
- I file di codice non sono file speciali o modificati in alcun modo per essere usati con il motore del modello. Gli strumenti usati in genere quando si usano progetti funzionano quindi anche con il contenuto del modello.
- Compilare, eseguire ed effettuare il debug dei progetti di modello, proprio come per qualsiasi altro progetto.
- È possibile creare rapidamente un modello da un progetto esistente aggiungendo semplicemente un file di configurazione *template.json* al progetto.

File e cartelle archiviati nel modello non sono limitati ai tipi di progetto .NET formali, ad esempio soluzioni .NET Framework o .NET Core. Le cartelle e i file di origine possono essere costituiti da qualsiasi contenuto che si vuole creare quando viene usato il modello, anche se il motore del modello produce un solo file per l'output, ad esempio un file di configurazione o un file di soluzione. Ad esempio, è possibile creare un modello che contiene un file di origine *web.config* e crea un file *web.config* modificato per i progetti in cui viene usato il modello. Le modifiche ai file di origine si basano sulla logica e le impostazioni specificate nel file di configurazione *template.json*, insieme ai valori forniti dall'utente passati come opzioni al comando `dotnet new <TEMPLATE>`.

### <a name="templatejson"></a>template.json

Il file *template.json* si trova in una cartella *.template.config* nella directory radice del modello. Il file fornisce informazioni di configurazione al motore del modello. Per la configurazione minima sono necessari i membri visualizzati nella tabella seguente, sufficiente per creare un modello funzionale.

| Membro            | Tipo          | Descrizione |
| ----------------- | ------------- | ----------- |
| `$schema`         | URI           | Lo schema JSON per il file *template.json*. Gli editor che supportano gli schemi JSON abilitano le funzionalità di modifica JSON quando viene specificato lo schema. Ad esempio, [Visual Studio Code](https://code.visualstudio.com/) richiede questo membro per abilitare IntelliSense. Usare un valore di `http://json.schemastore.org/template`. |
| `author`          | string        | L'autore del modello. |
| `classifications` | array(string) | Zero o più caratteristiche del modello che un utente può usare per individuare il modello durante la ricerca. Le classificazioni vengono visualizzate anche nella colonna *Tags* quando viene visualizzata in un elenco di modelli generati usando il comando <code>dotnet new -l&#124;--list</code>. |
| `identity`        | string        | Un nome univoco per questo modello. |
| `name`            | string        | Il nome per il modello che verrà visualizzato agli utenti. |
| `shortName`       | string        | Una valore breve predefinito per la selezione del modello che si applica agli ambienti in cui il nome del modello viene specificato dall'utente e non selezionato tramite un'interfaccia utente grafica. Ad esempio, il nome breve è utile quando si usano i modelli da un prompt dei comandi con i comandi dell'interfaccia della riga di comando. |

#### <a name="example"></a>Esempio:

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Catalina Garcia",
  "classifications": [ "Common", "Console" ],
  "identity": "GarciaSoftware.ConsoleTemplate.CSharp",
  "name": "Garcia Software Console Application",
  "shortName": "garciaconsole"
}
```

Lo schema completo per il file *template.json* è disponibile nell'[archivio degli schemi JSON](http://json.schemastore.org/template).

## <a name="net-default-templates"></a>Modelli predefiniti .NET

Quando si installa [.NET Core SDK](https://www.microsoft.com/net/download/core), si riceve circa una decina di modelli predefiniti per la creazione di progetti e file, tra cui app console, librerie di classi, progetti unit test, app ASP.NET Core (inclusi i progetti [Angular](https://angular.io/) e [React](https://facebook.github.io/react/)) e file di configurazione. Per elencare i modelli predefiniti, eseguire il comando `dotnet new` con l'opzione `-l|--list`:

```console
dotnet new -l
```

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a>Compressione di un modello in un pacchetto NuGet (file nupkg)

Attualmente il pacchetto di un modello personalizzato viene creato in Windows con [nuget.exe](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe), non con [dotnet pack](dotnet-pack.md). Per la creazione del pacchetto multipiattaforma, è consigliabile usare [NuGetizer 3000](https://github.com/NuGet/Home/wiki/NuGetizer-3000).

Il contenuto della cartella del progetto e il relativo file *.template.config/template.json* vengono inseriti in una cartella denominata *content*. Accanto alla cartella *content* aggiungere un file [ *nuspec* ](/nuget/create-packages/creating-a-package), ovvero un file manifesto XML che descrive il contenuto di un pacchetto e guida il processo di creazione del pacchetto NuGet. All'interno di un elemento  **\<packageTypes>** nel file *nuspec*, includere un elemento  **\<packageType>** con un valore dell'attributo `name` di `Template`. La cartella *content* e il file *nuspec* devono trovarsi nella stessa directory. La tabella mostra gli elementi del file *nuspec* minimi necessari per produrre un modello come pacchetto NuGet.

| Elemento            | Tipo   | Descrizione |
| ------------------ | ------ | ----------- |
| **\<authors>**     | string | Elenco con valori delimitati da virgola di autori di pacchetti, corrispondenti ai nomi di profili in nuget.org. Gli autori, visualizzati nella raccolta NuGet in nuget.org, vengono usati per creare riferimenti incrociati ai pacchetti dello stesso autore. |
| **\<description>** | string | Descrizione lunga del pacchetto per la visualizzazione dell'interfaccia utente. |
| **\<id>**          | string | L'identificatore del pacchetto senza distinzione tra maiuscole e minuscole che deve essere univoco in nuget.org o qualsiasi raccolta in cui risiederà il pacchetto. L'ID non può contenere spazi o caratteri non validi per un URL e in genere segue le regole dello spazio dei nomi .NET. Vedere [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) (Scelta di un identificatore univoco del pacchetto e impostazione del numero di versione) per il materiale sussidiario. |
| **\<packageType>** | string | Inserire l'elemento all'interno di un elemento  **\<packageTypes >** tra elementi  **\<metadata >**. Impostare l'attributo `name` dell'elemento **\<packageType>** su `Template`. |
| **\<version>**     | string | La versione del pacchetto secondo il criterio major.minor.patch. I numeri di versione possono includere un suffisso di versione non definitiva, come descritto nell'argomento [Versioni non definitive](/nuget/create-packages/prerelease-packages#semantic-versioning). |

Vedere il [riferimento a .nuspec](/nuget/schema/nuspec) per lo schema completo del file *nuspec*. Un file *nuspec* di esempio per un modello viene visualizzato nell'esercitazione [Creare un modello personalizzato per dotnet new](~/docs/core/tutorials/create-custom-template.md).

[Creare un pacchetto](/nuget/create-packages/creating-a-package#creating-the-package) usando il comando `nuget pack <PATH_TO_NUSPEC_FILE>`.

## <a name="installing-a-template"></a>Installazione di un modello

Installare un modello personalizzato da un pacchetto NuGet in qualsiasi feed NuGet, facendo riferimento direttamente a un file *nupkg* o specificando una directory del file system che contiene la configurazione dei modelli. Usare l'opzione `-i|--install` con il comando [dotnet new](dotnet-new.md).

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a>Per installare un modello da un pacchetto NuGet archiviato in nuget.org

```console
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a>Per installare un modello da un file nupkg locale

```console
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a>Per installare un modello da una directory del file system

`FILE_SYSTEM_DIRECTORY` è la cartella di progetto che contiene il progetto e la cartella *.template.config*:

```console
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="uninstalling-a-template"></a>Disinstallazione di un modello

Disinstallare un modello personalizzato facendo riferimento a un pacchetto NuGet in base al relativo `id` o specificando una directory del file system che contiene una configurazione del modello. Usare l'opzione `-u|--uninstall` con il comando [dotnet new](dotnet-new.md).

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a>Per disinstallare un modello da un pacchetto NuGet archiviato in nuget.org

```console
dotnet new -u <NUGET_PACKAGE_ID>
```

### <a name="to-uninstall-a-template-from-a-local-nupkg-file"></a>Per disinstallare un modello da un file nupkg locale

Per disinstallare il modello, non tentare di usare il percorso del file *nupkg*. *Il tentativo di disinstallare un modello usando `dotnet new -u <PATH_TO_NUPKG_FILE>` ha esito negativo.* Fare riferimento al pacchetto in base al relativo `id`:

```console
dotnet new -u <NUGET_PACKAGE_ID>
```

### <a name="to-uninstall-a-template-from-a-file-system-directory"></a>Per disinstallare un modello da una directory del file system

`FILE_SYSTEM_DIRECTORY` è la cartella di progetto che contiene il progetto e la cartella *.template.config*:

```console
dotnet new -u <FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a>Creare un progetto usando un modello personalizzato

Dopo l'installazione di un modello, usare il modello eseguendo il comando `dotnet new <TEMPLATE>` come si farebbe con qualsiasi altro modello pre-installato. È possibile anche specificare [options](dotnet-new.md#options) al comando `dotnet new`, incluse le opzioni specifiche del modello configurate nelle impostazioni del modello. Specificare il nome breve del modello direttamente nel comando:

```console
dotnet new <TEMPLATE>
```

## <a name="see-also"></a>Vedere anche

[Creare un modello personalizzato per dotnet new (esercitazione)](../tutorials/create-custom-template.md)  
[Wiki del repository GitHub dotnet/templating](https://github.com/dotnet/templating/wiki)  
[Repository GitHub dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples)  
[Come creare modelli personalizzati per dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)  
Lo schema [*template.JSON* nell'archivio di schemi JSON](http://json.schemastore.org/template)  

