---
title: Comando dotnet publish
description: Il comando dotnet publish pubblica un progetto o una soluzione .NET Core in una directory.
ms.date: 02/24/2020
ms.openlocfilehash: c34618409c9a539043c84c7e03daa8aa249d64f6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146555"
---
# <a name="dotnet-publish"></a>dotnet publish

**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet publish`- Pubblica l'applicazione e le relative dipendenze in una cartella per la distribuzione in un sistema di hosting.- Publishes the application and its dependencies to a folder for deployment to a hosting system.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration]
    [-f|--framework] [--force] [--interactive] [--manifest]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [--self-contained]
    [--no-self-contained] [-v|--verbosity] [--version-suffix]

dotnet publish [-h|--help]
```

## <a name="description"></a>Descrizione

`dotnet publish` compila l'applicazione, legge le relative dipendenze specificate nel file di progetto e pubblica il set di file risultante in una directory. L'output include gli asset seguenti:

- Codice linguaggio intermedio (IL) in un assembly con un'estensione *dll*.
- Un file *.deps.json* che include tutte le dipendenze del progetto.
- Un file *.runtimeconfig.json* che specifica il runtime condiviso previsto dall'applicazione, nonché altre opzioni di configurazione per il runtime (ad esempio, tipo di Garbage Collection).
- Dipendenze dell'applicazione copiate dalla cache NuGet nella cartella di output.

L'output del comando `dotnet publish` è pronto per la distribuzione in un sistema di hosting (ad esempio, un server, un PC, un Mac, un laptop) per l'esecuzione. È l'unico metodo supportato ufficialmente per preparare l'applicazione per la distribuzione. A seconda del tipo di distribuzione specificato dal progetto, nel sistema host il runtime condiviso di .NET Core può essere installato o meno.

## <a name="arguments"></a>Argomenti

- **`PROJECT|SOLUTION`**

  Progetto o soluzione da pubblicare.
  
  * `PROJECT`è il percorso e il nome del file di un file di progetto di [C,](csproj.md)F o Visual Basic oppure il percorso di una directory che contiene un file di progetto C, F o Visual Basic. Se la directory non è specificata, il valore predefinito è la directory corrente.

  * `SOLUTION`è il percorso e il nome file di un file di soluzione (estensione*sln)* o il percorso di una directory che contiene un file di soluzione. Se la directory non è specificata, il valore predefinito è la directory corrente. Disponibile a partire da .NET Core 3.0 SDK.

## <a name="options"></a>Opzioni

- **`-c|--configuration <CONFIGURATION>`**

  Definisce la configurazione di compilazione. L'impostazione predefinita `Debug`per la maggior parte dei progetti è , ma è possibile eseguire l'override delle impostazioni di configurazione della compilazione nel progetto.

- **`-f|--framework <FRAMEWORK>`**

  Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato. È necessario specificare il framework di destinazione nel file di progetto.

- **`--force`**

  Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo. La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente, ad esempio il completamento dell'autenticazione. Disponibile a partire da .NET Core 3.0 SDK.

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app. Il file manifesto fa parte [ `dotnet store` ](dotnet-store.md)dell'output del comando . Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.

- **`--no-build`**

  Non compila il progetto prima della pubblicazione. Imposta anche in modo implicito il flag `--no-restore`.

- **`--no-dependencies`**

  Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.

- **`--nologo`**

  Non visualizza il messaggio di avvio né il messaggio di copyright. Disponibile a partire da .NET Core 3.0 SDK.

- **`--no-restore`**

  Non esegue un ripristino implicito quando si esegue il comando.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Specifica il percorso della directory di output. Se non specificato, il valore predefinito è *./bin/[configuration]/[framework]/publish/* per un file eseguibile dipendente dal runtime e file binari tra piattaforme. Il valore predefinito è *./bin/[configuration]/[framework]/[runtime]/publish/* per un eseguibile indipendente.

  Se il percorso è relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.

- **`--self-contained [true|false]`**

  Pubblica il runtime .NET Core con l'applicazione in modo che non sia necessario installare il runtime nel computer di destinazione. Il `true` valore predefinito è se viene specificato un identificatore di runtime. Per altre informazioni, vedere Pubblicazione di applicazioni [.NET Core](../deploying/index.md) e [Pubblicare app .NET Core con l'interfaccia della riga](../deploying/deploy-with-cli.md)di comando .NET Core .

- **`--no-self-contained`**

  È equivalente a `--self-contained false`. Disponibile a partire da .NET Core 3.0 SDK.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Pubblica l'applicazione per un determinato runtime. Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md). Per altre informazioni, vedere Pubblicazione di applicazioni [.NET Core](../deploying/index.md) e [Pubblicare app .NET Core con l'interfaccia della riga](../deploying/deploy-with-cli.md)di comando .NET Core .

- **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `minimal`.

- **`--version-suffix <VERSION_SUFFIX>`**

  Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.

## <a name="examples"></a>Esempi

- Creare un file binario multipiattaforma dipendente dal runtime per il progetto nella directory corrente:Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:

  ```dotnetcli
  dotnet publish
  ```

  A partire da .NET Core 3.0 SDK, questo esempio crea anche un [eseguibile dipendente dal runtime](../deploying/index.md#publish-runtime-dependent) per la piattaforma corrente.

- Creare un eseguibile indipendente per il progetto nella directory corrente, per un runtime specifico:Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  Il RID deve essere nel file di progetto.

- Creare un eseguibile dipendente dal runtime per il progetto nella directory corrente, per una piattaforma specifica:Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  Il RID deve essere nel file di progetto. Questo esempio si applica a .NET Core 3.0 SDK e versioni successive.

- Pubblicare il progetto nella directory corrente, per un runtime e un framework di destinazione specifici:Publish the project in the current directory, for a specific runtime and target framework:

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- Pubblicare il file di progetto specificato:

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- Pubblicare l'applicazione corrente ma non ripristinare i riferimenti da progetto a progetto (P2P), solo il progetto radice durante l'operazione di ripristino:

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a>Vedere anche

- [Panoramica della pubblicazione delle applicazioni .NET Core](../deploying/index.md)
- [Pubblicare app .NET Core con l'interfaccia della riga di comando di .NET CorePublish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md)
- [Quadri di destinazione](../../standard/frameworks.md)
- [Catalogo dei runtime IDentifier (RID)](../rid-catalog.md)
- [Lavorare con la notarizzazione di catalina di macOS](../install/macos-notarization-issues.md) Per altre informazioni, vedere le risorse seguenti:For more information, see he following resources:
- [Struttura di directory di un'applicazione pubblicata](/aspnet/core/hosting/directory-structure)
