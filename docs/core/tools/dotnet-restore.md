---
title: Comando dotnet restore
description: Informazioni sul ripristino delle dipendenze e degli strumenti specifici per il progetto tramite il comando dotnet-restore.
ms.date: 02/27/2020
ms.openlocfilehash: 29f81b09a01e689d3f6d86c16b1f134c9fe6b6a0
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83840936"
---
# <a name="dotnet-restore"></a>dotnet restore

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet restore`: ripristina le dipendenze e gli strumenti di un progetto.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet restore [<ROOT>] [--configfile <FILE>] [--disable-parallel]
    [-f|--force] [--force-evaluate] [--ignore-failed-sources]
    [--interactive] [--lock-file-path <LOCK_FILE_PATH>] [--locked-mode]
    [--no-cache] [--no-dependencies] [--packages <PACKAGES_DIRECTORY>]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [-s|--source <SOURCE>]
    [--use-lockfile] [-v|--verbosity <LEVEL>]

dotnet restore -h|--help
```

## <a name="description"></a>Description

Il comando `dotnet restore` usa NuGet per ripristinare le dipendenze e gli strumenti specifici del progetto definiti nel file di progetto.  Nella maggior parte dei casi, non è necessario usare in modo esplicito il `dotnet restore` comando, poiché un ripristino NuGet viene eseguito in modo implicito se necessario quando si eseguono i comandi seguenti:

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

In alcuni casi potrebbe essere scomodo eseguire il ripristino NuGet implicito con questi comandi. È ad esempio necessario che alcuni sistemi automatizzati, come i sistemi di compilazione, chiamino `dotnet restore` in modo esplicito per controllare quando si verifica il ripristino in modo che possano controllare l'utilizzo della rete. Per evitare il ripristino NuGet implicito, è possibile usare il `--no-restore` flag con uno di questi comandi per disabilitare il ripristino implicito.

### <a name="specify-feeds"></a>Specificare i feed

Per ripristinare le dipendenze, NuGet necessita dei feed in cui si trovano i pacchetti. I feed vengono forniti in genere tramite il file di configurazione *nuget.config*. Quando viene installato il .NET Core SDK, viene fornito un file di configurazione predefinito. Per specificare feed aggiuntivi, effettuare una delle operazioni seguenti:

- Creare il proprio file *NuGet. config* nella directory del progetto. Per altre informazioni, vedere [configurazioni di NuGet comuni](/nuget/consume-packages/configuring-nuget-behavior) e [differenze di NuGet. config](#nugetconfig-differences) più avanti in questo articolo.
- Usare i `dotnet nuget` comandi come [`dotnet nuget add source`](dotnet-nuget-add-source.md) .

È possibile eseguire l'override dei feed *NuGet. config* con l' `-s` opzione.

Per informazioni sull'utilizzo dei feed autenticati, vedere Utilizzo [di pacchetti da feed autenticati](/nuget/consume-packages/consuming-packages-authenticated-feeds).

### <a name="global-packages-folder"></a>Cartella pacchetti globali

Per le dipendenze è possibile specificare dove vengono inseriti i pacchetti ripristinati durante l'operazione di ripristino, usando l'argomento `--packages`. Se questa destinazione non viene specificata, viene usata la cache predefinita dei pacchetti NuGet che si trova nella directory `.nuget/packages` della directory home dell'utente in tutti i sistemi operativi. Ad esempio, */home/user1* in Linux o *C:\Utenti\user1* in Windows.

### <a name="project-specific-tooling"></a>Strumenti specifici del progetto

Per gli strumenti specifici del progetto, `dotnet restore` ripristina innanzitutto il pacchetto in cui viene compresso lo strumento e quindi ripristina le dipendenze dello strumento come specificato nel file di progetto.

### <a name="nugetconfig-differences"></a>Differenze di nuget.config

Il funzionamento del comando `dotnet restore` può essere modificato dalle impostazioni del file *nuget.config*, se è presente. Se ad esempio si imposta `globalPackagesFolder` in *nuget.config*, i pacchetti NuGet ripristinati vengono posizionati nella cartella specificata. Questo approccio rappresenta un'alternativa all'impostazione dell'opzione `--packages` per il comando `dotnet restore`. Per altre informazioni, vedere [Informazioni di riferimento su nuget.config](/nuget/schema/nuget-config-file).

Esistono tre impostazioni specifiche che `dotnet restore` ignora:

- [bindingRedirects](/nuget/schema/nuget-config-file#bindingredirects-section)

  I reindirizzamenti di binding non funzionano con elementi `<PackageReference>` e .NET Core supporta solo elementi `<PackageReference>` per i pacchetti NuGet.

- [soluzione](/nuget/schema/nuget-config-file#solution-section)

  Questa impostazione è specifica di Visual Studio e non può essere applicata a .NET Core. .NET Core non usa un file `packages.config` ma usa invece elementi `<PackageReference>` per i pacchetti NuGet.

- [trustedSigners](/nuget/schema/nuget-config-file#trustedsigners-section)

  Questa impostazione non può essere applicata perché [NuGet non supporta ancora la verifica multipiattaforma](https://github.com/NuGet/Home/issues/7939) di pacchetti attendibili.

## <a name="arguments"></a>Argomenti

- **`ROOT`**

  Percorso facoltativo del file di progetto da ripristinare.

## <a name="options"></a>Opzioni

- **`--configfile <FILE>`**

  File di configurazione NuGet (*nuget.config*) da usare per l'operazione di ripristino.

- **`--disable-parallel`**

  Disabilita il ripristino di più progetti in parallelo.

- **`--force`**

  Forza la risoluzione di tutte le dipendenze, anche se l'ultimo ripristino ha avuto esito positivo. La specifica di questo flag equivale all'eliminazione del file *project.assets.json*.

- **`--force-evaluate`**

  Forza il ripristino per rivalutare tutte le dipendenze anche se un file di blocco esiste già.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--ignore-failed-sources`**

  Segnala le origini con esito negativo solo se sono presenti pacchetti che soddisfano il requisito di versione.

- **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione). A partire da .NET Core 2.1.400

- **`--lock-file-path <LOCK_FILE_PATH>`**

  Percorso di output in cui viene scritto il file di blocco del progetto. Per impostazione predefinita, questo valore è *PROJECT_ROOT \Packages.Lock.JSON*.

- **`--locked-mode`**

  Non consentire l'aggiornamento del file di blocco del progetto.

- **`--no-cache`**

  Specifica di non memorizzare nella cache le richieste HTTP.

- **`--no-dependencies`**

  Durante il ripristino di un progetto con riferimenti da progetto a progetto, ripristina il progetto radice e non i riferimenti.

- **`--packages <PACKAGES_DIRECTORY>`**

  Specifica la directory per i pacchetti ripristinati.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Specifica un runtime per il ripristino dei pacchetti. Questo runtime viene usato per ripristinare i pacchetti di runtime non esplicitamente elencati nel tag `<RuntimeIdentifiers>` del file *csproj*. Per un elenco degli identificatori di runtime (RID, Runtime Identifier), vedere il [catalogo RID](../rid-catalog.md). Specificare più origini selezionando questa opzione più volte.

- **`-s|--source <SOURCE>`**

  Specifica l'URI dell'origine del pacchetto NuGet da usare durante l'operazione di ripristino. Questa impostazione esegue l'override di tutte le origini specificate nei file *NuGet.config*. È possibile specificare più origini, selezionando questa opzione più volte.

- **`--use-lockfile`**

  Consente la generazione e l'utilizzo del file di blocco del progetto con il ripristino.

- **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `minimal`.

## <a name="examples"></a>Esempi

- Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente:

  ```dotnetcli
  dotnet restore
  ```

- Ripristinare le dipendenze e gli strumenti per il `app1` progetto trovato nel percorso specificato:

  ```dotnetcli
  dotnet restore ~/projects/app1/app1.csproj
  ```

- Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente usando il percorso del file fornito come origine:

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages
  ```

- Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente usando i due percorsi di file forniti come origini:

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages
  ```

- Ripristinare le dipendenze e gli strumenti per il progetto nella directory corrente che mostra l'output dettagliato:

  ```dotnetcli
  dotnet restore --verbosity detailed
  ```
