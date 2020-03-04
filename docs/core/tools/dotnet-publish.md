---
title: Comando dotnet publish
description: Il dotnet publish comando pubblica un progetto o una soluzione .NET Core in una directory.
ms.date: 02/24/2020
ms.openlocfilehash: cf41ee09244faad03feb8ccda19135b8c7780106
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156998"
---
# <a name="dotnet-publish"></a>dotnet publish

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet publish`: pubblica l'applicazione e le relative dipendenze in una cartella per la distribuzione in un sistema di hosting.

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
- Un file con *estensione Deps. JSON* che include tutte le dipendenze del progetto.
- Un file *. runtimeconfig. JSON* che specifica il runtime condiviso previsto dall'applicazione, nonché altre opzioni di configurazione per il runtime, ad esempio Garbage Collection tipo.
- Dipendenze dell'applicazione copiate dalla cache NuGet nella cartella di output.

L'output del comando `dotnet publish` è pronto per la distribuzione in un sistema di hosting (ad esempio, un server, un PC, un Mac, un laptop) per l'esecuzione. È l'unico metodo supportato ufficialmente per preparare l'applicazione per la distribuzione. A seconda del tipo di distribuzione specificato dal progetto, nel sistema host il runtime condiviso di .NET Core può essere installato o meno.

## <a name="arguments"></a>Argomenti

- **`PROJECT|SOLUTION`**

  Progetto o soluzione da pubblicare.
  
  * `PROJECT` è il percorso e il nome file [C#](csproj.md)di F#un file di progetto, o Visual Basic, oppure il percorso di una directory che C#contiene F#un file di progetto, o Visual Basic. Se la directory non è specificata, il valore predefinito è la directory corrente.

  * `SOLUTION` è il percorso e il nome file di un file di soluzione (estensione*sln* ) o il percorso di una directory che contiene un file di soluzione. Se la directory non è specificata, il valore predefinito è la directory corrente. **Disponibile a partire da .NET Core 3,0 SDK.** 

## <a name="options"></a>Opzioni

- **`-c|--configuration <CONFIGURATION>`**

  Definisce la configurazione di compilazione. Il valore predefinito per la maggior parte dei progetti è `Debug`, ma è possibile eseguire l'override delle impostazioni di configurazione della build nel progetto.

- **`-f|--framework <FRAMEWORK>`**

  Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato. È necessario specificare il framework di destinazione nel file di progetto.

- **`--force`**

  Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo. La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--interactive`** **disponibile a partire da .NET Core 3,0 SDK.**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente, ad esempio il completamento dell'autenticazione. 

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app. Il file manifesto fa parte dell'output del comando [`dotnet store`](dotnet-store.md). Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.

- **`--no-build`**

  Non compila il progetto prima della pubblicazione. Imposta anche in modo implicito il flag `--no-restore`.

- **`--no-dependencies`**

  Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.

- **`--nologo`** **disponibile a partire da .NET Core 3,0 SDK.**

  Non visualizza il messaggio di avvio né il messaggio di copyright. 

- **`--no-restore`**

  Non esegue un ripristino implicito quando si esegue il comando.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Specifica il percorso della directory di output. Se non specificato, il valore predefinito è *./bin/[Configuration]/[Framework]/Publish/* per un file eseguibile dipendente dal runtime e file binari multipiattaforma. Per impostazione predefinita, il valore predefinito è *./bin/[Configuration]/[Framework]/[Runtime]/Publish/* per un file eseguibile autonomo.

  Se il percorso è relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.

- **`--self-contained [true|false]`**

  Pubblica il runtime .NET Core con l'applicazione in modo che non sia necessario installare il runtime nel computer di destinazione. Il valore predefinito è `true` se viene specificato un identificatore di Runtime. Per altre informazioni, vedere [pubblicazione di applicazioni .NET Core](../deploying/index.md) e pubblicazione [di app .net core con la interfaccia della riga di comando di .NET Core](../deploying/deploy-with-cli.md).

- **`--no-self-contained`** **disponibile a partire da .NET Core 3,0 SDK.**  

  È equivalente a `--self-contained false`.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Pubblica l'applicazione per un determinato runtime. Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md). Per altre informazioni, vedere [pubblicazione di applicazioni .NET Core](../deploying/index.md) e pubblicazione [di app .net core con la interfaccia della riga di comando di .NET Core](../deploying/deploy-with-cli.md).

- **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

- **`--version-suffix <VERSION_SUFFIX>`**

  Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.

## <a name="examples"></a>Esempi

- Creare un [file binario multipiattaforma dipendente dal runtime](../deploying/index.md#produce-a-cross-platform-binary) per il progetto nella directory corrente:

  ```dotnetcli
  dotnet publish
  ```

  A partire da .NET Core 3,0 SDK, questo esempio crea anche un [eseguibile dipendente dal runtime](../deploying/index.md#publish-runtime-dependent) per la piattaforma corrente.

- Creare un [eseguibile indipendente](../deploying/index.md#publish-self-contained) per il progetto nella directory corrente, per un runtime specifico:

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  Il RID deve trovarsi nel file di progetto.

- Creare un [eseguibile dipendente dal runtime](../deploying/index.md#publish-runtime-dependent) per il progetto nella directory corrente, per una piattaforma specifica:

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  Il RID deve trovarsi nel file di progetto. Questo esempio si applica a .NET Core 3,0 SDK e versioni successive.

- Pubblicare il progetto nella directory corrente, per un runtime e un Framework di destinazione specifici:

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- Pubblicare il file di progetto specificato:

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- Pubblicare l'applicazione corrente, ma non ripristinare i riferimenti da progetto a progetto (P2P), solo il progetto radice durante l'operazione di ripristino:

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a>Vedere anche

- [Panoramica della pubblicazione di applicazioni .NET Core](../deploying/index.md)
- [Pubblicare app .NET Core con il interfaccia della riga di comando di .NET Core](../deploying/deploy-with-cli.md)
- [Framework di destinazione](../../standard/frameworks.md)
- [Catalogo RID (Runtime IDentifier)](../rid-catalog.md)
- [Uso dell'autenticazione di MacOS Catalina](../install/macos-notarization-issues.md) Per ulteriori informazioni, vedere le risorse seguenti:
- [Struttura di directory di un'applicazione pubblicata](/aspnet/core/hosting/directory-structure)
