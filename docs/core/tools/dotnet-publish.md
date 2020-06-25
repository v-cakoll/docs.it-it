---
title: Comando dotnet publish
description: Il dotnet publish comando pubblica un progetto o una soluzione .NET Core in una directory.
ms.date: 02/24/2020
ms.openlocfilehash: 61cfcf06586f3ac66526de69a17b8aef3cf0c795
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365583"
---
# <a name="dotnet-publish"></a>dotnet publish

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet publish`-Pubblica l'applicazione e le relative dipendenze in una cartella per la distribuzione in un sistema di hosting.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [-f|--framework <FRAMEWORK>] [--force] [--interactive]
    [--manifest <PATH_TO_MANIFEST_FILE>] [--no-build] [--no-dependencies]
    [--no-restore] [--nologo] [-o|--output <OUTPUT_DIRECTORY>]
    [-p:PublishReadyToRun=true] [-p:PublishSingleFile=true] [-p:PublishTrimmed=true]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [--self-contained [true|false]]
    [--no-self-contained] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet publish -h|--help
```

## <a name="description"></a>Descrizione

`dotnet publish` compila l'applicazione, legge le relative dipendenze specificate nel file di progetto e pubblica il set di file risultante in una directory. L'output include gli asset seguenti:

- Codice linguaggio intermedio (IL) in un assembly con un'estensione *dll*.
- *.deps.jssu* file che include tutte le dipendenze del progetto.
- *.runtimeconfig.jsnel* file che specifica il runtime condiviso previsto dall'applicazione, nonché altre opzioni di configurazione per il runtime, ad esempio Garbage Collection tipo.
- Dipendenze dell'applicazione copiate dalla cache NuGet nella cartella di output.

L'output del comando `dotnet publish` è pronto per la distribuzione in un sistema di hosting (ad esempio, un server, un PC, un Mac, un laptop) per l'esecuzione. È l'unico metodo supportato ufficialmente per preparare l'applicazione per la distribuzione. A seconda del tipo di distribuzione specificato dal progetto, nel sistema host il runtime condiviso di .NET Core può essere installato o meno. Per altre informazioni, vedere [pubblicare app .NET Core con il interfaccia della riga di comando di .NET Core](../deploying/deploy-with-cli.md).

### <a name="implicit-restore"></a>Ripristino implicito

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

### <a name="msbuild"></a>MSBuild

Il comando `dotnet publish` chiama MSBuild che richiama la destinazione `Publish`. Tutti i parametri passati a `dotnet publish` vengono passati a MSBuild. I parametri `-c` e `-o` sono mappati rispettivamente alle proprietà `Configuration` e `PublishDir` di MSBuild.

Il `dotnet publish` comando accetta opzioni MSBuild, ad esempio `-p` per l'impostazione delle proprietà e `-l` per la definizione di un logger. È ad esempio possibile impostare una proprietà MSBuild utilizzando il formato: `-p:<NAME>=<VALUE>` . È anche possibile impostare le proprietà relative alla pubblicazione facendo riferimento a un file con *estensione pubxml* , ad esempio:

```dotnetcli
dotnet publish -p:PublishProfile=Properties\PublishProfiles\FolderProfile.pubxml
```

Per altre informazioni, vedere le seguenti risorse:

- [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference)
- [Profili di pubblicazione di Visual Studio (con estensione pubxml) per la distribuzione di app ASP.NET Core](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [dotnet msbuild](dotnet-msbuild.md)

## <a name="arguments"></a>Argomenti

- **`PROJECT|SOLUTION`**

  Progetto o soluzione da pubblicare.
  
  * `PROJECT`è il percorso e il nome file di un file di progetto [c#](csproj.md), f # o Visual Basic o il percorso di una directory che contiene un file di progetto C#, f # o Visual Basic. Se la directory non è specificata, il valore predefinito è la directory corrente.

  * `SOLUTION`è il percorso e il nome file di un file di soluzione (estensione*sln* ) o il percorso di una directory che contiene un file di soluzione. Se la directory non è specificata, il valore predefinito è la directory corrente. Disponibile a partire da .NET Core 3.0 SDK.

## <a name="options"></a>Opzioni

- **`-c|--configuration <CONFIGURATION>`**

  Definisce la configurazione di compilazione. Il valore predefinito per la maggior parte dei progetti è `Debug` , ma è possibile eseguire l'override delle impostazioni di configurazione della build nel progetto.

- **`-f|--framework <FRAMEWORK>`**

  Pubblica l'applicazione per il [framework di destinazione](../../standard/frameworks.md) specificato. È necessario specificare il framework di destinazione nel file di progetto.

- **`--force`**

  Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo. La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente, ad esempio il completamento dell'autenticazione. Disponibile a partire da .NET Core 3.0 SDK.

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  Specifica uno o più [manifesti di destinazione](../deploying/runtime-store.md) da usare per rimuovere il set di pacchetti pubblicati con l'app. Il file manifesto fa parte dell'output del [ `dotnet store` comando](dotnet-store.md). Per specificare più manifesti, aggiungere un'opzione `--manifest` per ogni manifesto.

- **`--no-build`**

  Non compila il progetto prima della pubblicazione. Imposta anche in modo implicito il flag `--no-restore`.

- **`--no-dependencies`**

  Ignora i riferimenti da progetto a progetto e ripristina solo il progetto radice.

- **`--nologo`**

  Non visualizza il messaggio di avvio né il messaggio di copyright. Disponibile a partire da .NET Core 3.0 SDK.

- **`--no-restore`**

  Non esegue un ripristino implicito quando si esegue il comando.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Specifica il percorso della directory di output.
  
  Se non specificato, il valore predefinito è *[project_file_folder]./bin/[Configuration]/[Framework]/Publish/* per un eseguibile dipendente dal runtime e binari multipiattaforma. Il valore predefinito è *[project_file_folder]/bin/[Configuration]/[Framework]/[Runtime]/Publish/* per un file eseguibile autonomo.

  In un progetto Web, se la cartella di output si trova nella cartella del progetto, i `dotnet publish` comandi successivi generano cartelle di output nidificate. Ad esempio, se la cartella del progetto *è MyProject*e la cartella di output di pubblicazione è *MyProject/Publish*ed è stata eseguita `dotnet publish` due volte, la seconda esecuzione inserisce i file di contenuto, ad esempio i file con *estensione config* e *JSON* , in *MyProject/Publish/Publish*. Per evitare di nidificare le cartelle di pubblicazione, specificare una cartella di pubblicazione che non si trovi **direttamente** nella cartella del progetto o escludere la cartella di pubblicazione dal progetto. Per escludere una cartella di pubblicazione denominata *publishoutput*, aggiungere l'elemento seguente a un `PropertyGroup` elemento nel file con *estensione csproj* :

  ```xml
  <DefaultItemExcludes>$(DefaultItemExcludes);publishoutput**</DefaultItemExcludes>
  ```

  - .NET Core 3. x SDK e versioni successive
  
    Se quando si pubblica un progetto viene specificato un percorso relativo, la directory di output generata è relativa alla directory di lavoro corrente, non al percorso del file di progetto.

    Se viene specificato un percorso relativo durante la pubblicazione di una soluzione, tutti gli output per tutti i progetti vengono inseriti nella cartella specificata rispetto alla directory di lavoro corrente. Per fare in modo che l'output di pubblicazione vada in cartelle separate per ogni progetto, specificare un percorso relativo usando la `PublishDir` Proprietà MSBuild anziché l' `--output` opzione. Ad esempio, `dotnet publish -p:PublishDir=.\publish` Invia l'output di pubblicazione per ogni progetto a una `publish` cartella nella cartella che contiene il file di progetto.

  - SDK di .NET Core 2. x
  
    Se quando si pubblica un progetto viene specificato un percorso relativo, la directory di output generata è relativa al percorso del file di progetto e non alla directory di lavoro corrente.

    Se viene specificato un percorso relativo quando si pubblica una soluzione, l'output di ogni progetto viene inserito in una cartella distinta rispetto al percorso del file di progetto. Se viene specificato un percorso assoluto durante la pubblicazione di una soluzione, tutti gli output di pubblicazione per tutti i progetti vengono inseriti nella cartella specificata.

- **`-p:PublishReadyToRun=true`**

  Compila gli assembly dell'applicazione come formato ReadyToRun (R2R). R2R è un formato di compilazione AOT (Ahead-of-time). Per altre informazioni, vedere [ReadyToRun images](../whats-new/dotnet-core-3-0.md#readytorun-images). Disponibile a partire da .NET Core 3.0 SDK.

  È consigliabile specificare questa opzione in un profilo di pubblicazione anziché nella riga di comando. Per ulteriori informazioni, vedere [MSBuild](#msbuild).

- **`-p:PublishSingleFile=true`**

  Inserisce l'app in un eseguibile di un singolo file specifico della piattaforma. Il file eseguibile è autoestraente e contiene tutte le dipendenze (incluso native) necessarie per eseguire l'app. Quando l'app viene eseguita per la prima volta, l'applicazione viene estratta in una directory in base al nome dell'app e all'identificatore di compilazione. L'avvio dell'applicazione sarà più veloce alla successiva esecuzione. Non è necessario estrarre l'applicazione una seconda volta, a meno che non venga usata una nuova versione. Disponibile a partire da .NET Core 3.0 SDK.

  Per altre informazioni sulla pubblicazione di file singolo, vedere il [documento sulla progettazione di un bundler con file singolo](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).

  È consigliabile specificare questa opzione in un profilo di pubblicazione anziché nella riga di comando. Per ulteriori informazioni, vedere [MSBuild](#msbuild).

- **`-p:PublishTrimmed=true`**

  Elimina le librerie inutilizzate per ridurre le dimensioni di distribuzione di un'app durante la pubblicazione di un eseguibile autonomo. Per altre informazioni, vedere [tagliare le distribuzioni e gli eseguibili autonomi](../deploying/trim-self-contained.md). Disponibile a partire da .NET Core 3.0 SDK.

  È consigliabile specificare questa opzione in un profilo di pubblicazione anziché nella riga di comando. Per ulteriori informazioni, vedere [MSBuild](#msbuild).

- **`--self-contained [true|false]`**

  Pubblica il runtime .NET Core con l'applicazione in modo che non sia necessario installare il runtime nel computer di destinazione. Il valore predefinito è `true` se viene specificato un identificatore di runtime e il progetto è un progetto eseguibile (non un progetto di libreria). Per altre informazioni, vedere [pubblicazione di applicazioni .NET Core](../deploying/index.md) e pubblicazione [di app .net core con la interfaccia della riga di comando di .NET Core](../deploying/deploy-with-cli.md).

  Se questa opzione viene utilizzata senza specificare `true` o `false` , il valore predefinito è `true` . In tal caso, non inserire l'argomento della soluzione o del progetto subito dopo `--self-contained` , perché `true` o `false` è previsto in tale posizione.

- **`--no-self-contained`**

  È equivalente a `--self-contained false`. Disponibile a partire da .NET Core 3.0 SDK.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Pubblica l'applicazione per un determinato runtime. Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md). Per altre informazioni, vedere [pubblicazione di applicazioni .NET Core](../deploying/index.md) e pubblicazione [di app .net core con la interfaccia della riga di comando di .NET Core](../deploying/deploy-with-cli.md).

- **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `minimal`.

- **`--version-suffix <VERSION_SUFFIX>`**

  Definisce il suffisso di versione che sostituirà l'asterisco (`*`) nel campo del file di progetto relativo alla versione.

## <a name="examples"></a>Esempio

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

## <a name="see-also"></a>Vedi anche

- [Panoramica della pubblicazione di applicazioni .NET Core](../deploying/index.md)
- [Pubblicare app .NET Core con il interfaccia della riga di comando di .NET Core](../deploying/deploy-with-cli.md)
- [Framework di destinazione](../../standard/frameworks.md)
- [Catalogo di runtime IDentifier (RID)](../rid-catalog.md)
- [Uso dell'autenticazione di macOS Catalina](../install/macos-notarization-issues.md)
- [Struttura di directory di un'applicazione pubblicata](/aspnet/core/hosting/directory-structure)
- [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference)
- [Profili di pubblicazione di Visual Studio (con estensione pubxml) per la distribuzione di app ASP.NET Core](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [dotnet msbuild](dotnet-msbuild.md)
- [ILLInk. Tasks](https://aka.ms/dotnet-illink)
