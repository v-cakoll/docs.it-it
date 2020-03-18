---
title: Strumento di disinstallazione
description: Una panoramica dello strumento di disinstallazione di .NET Core, uno strumento guidato che consente la pulizia controllata di .NET Core SDK e runtime.
author: sfoslund
ms.date: 01/06/2020
ms.openlocfilehash: bd20cba133cbb754dcca48e48b76a391a9efacba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847052"
---
# <a name="net-core-uninstall-tool"></a>Strumento di disinstallazione di .NET Core

Lo strumento di [disinstallazione](https://aka.ms/dotnet-core-uninstall-tool) di .NET Core (`dotnet-core-uninstall`) consente di rimuovere gli SDK e i runtime di .NET Core da un sistema. È disponibile una raccolta di opzioni per specificare le versioni che si desidera disinstallare.

Lo strumento supporta Windows e macOS. Linux non è attualmente supportato.

In Windows, lo strumento può disinstallare solo SDK e runtime installati utilizzando uno dei seguenti programmi di installazione:

- Il programma di installazione di .NET Core SDK e runtime.
- Il programma di installazione di Visual Studio nelle versioni precedenti a Visual Studio 2019 versione 16.3.The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.

In macOS, lo strumento può disinstallare solo SDK e runtime che si trovano nella cartella */usr/local/share/dotnet.*

A causa di queste limitazioni, lo strumento potrebbe non essere in grado di disinstallare tutti gli SDK e runtime di .NET Core nel computer. È possibile `dotnet --info` utilizzare il comando per trovare tutti gli SDK e runtime di .NET Core installati, inclusi gli SDK e i runtime che questo strumento non può rimuovere. Il `dotnet-core-uninstall list` comando mostra quali SDK possono essere disinstallati con lo strumento.

## <a name="install-the-tool"></a>Installare lo strumento

È possibile scaricare lo strumento di disinstallazione di .NET Core da qui e trovare il codice sorgente nel repository dotnet/cli-lab GitHub.You can download the .NET Core Uninstall Tool from [here](https://aka.ms/dotnet-core-uninstall-tool) and find the source code at the [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub repository.

> [!NOTE]
> Lo strumento richiede l'elevazione dei privilegi per disinstallare gli SDK e i runtime di .NET Core.The tool requires elevation to uninstall .NET Core SDKs and runtimes. Pertanto, deve essere installato in una directory protetta da scrittura, ad esempio *C:* , Programmi su Windows o */usr/local/bin* su macOS. Vedere anche [Accesso elevato per i comandi dotnet](../tools/elevated-access.md). Per ulteriori informazioni, vedere le [istruzioni dettagliate per l'installazione.](https://aka.ms/dotnet-core-uninstall-tool)

## <a name="run-the-tool"></a>Eseguire lo strumento

I passaggi seguenti illustrano l'approccio consigliato per l'esecuzione dello strumento di disinstallazione:

- [Passaggio 1 - Visualizzare gli SDK e i runtime di .NET Core installatiStep 1 - Display installed .NET Core SDKs and runtimes](#step-1---display-installed-net-core-sdks-and-runtimes)
- [Fase 2 - Eseguire una corsa a secco](#step-2---do-a-dry-run)
- [Passaggio 3 - Disinstallare gli SDK e i runtime di .NET CoreStep 3 - Uninstall .NET Core SDKs and Runtimes](#step-3---uninstall-net-core-sdks-and-runtimes)
- [Passaggio 4 - Eliminare la cartella di fallback NuGet (facoltativo)Step 4 - Delete the NuGet fallback folder (optional)](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a>Passaggio 1 - Visualizzare gli SDK e i runtime di .NET Core installatiStep 1 - Display installed .NET Core SDKs and runtimes

Il `dotnet-core-uninstall list` comando elenca gli SDK e i runtime .NET Core installati che possono essere rimossi con questo strumento. Alcuni SDK e runtime potrebbero essere richiesti da Visual Studio e vengono visualizzati con una nota del motivo per cui non è consigliabile disinstallarli.

**elenco dotnet-core-uninstall**

#### <a name="synopsis"></a>Riepilogo

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a>Opzioni

## <a name="windows"></a>[Windows](#tab/windows)

* **`--aspnet-runtime`**

  Elenca tutti i runtime di ASP.NET Core che possono essere disinstallati con questo strumento.

* **`--hosting-bundle`**

  Elenca tutti i pacchetti di runtime e di hosting di .NET Core che possono essere disinstallati con questo strumento.

* **`--runtime`**

  Elenca tutti i runtime di .NET Core che possono essere disinstallati con questo strumento.

* **`--sdk`**

  Elenca tutti gli SDK di .NET Core che possono essere disinstallati con questo strumento.

* **`-v, --verbosity <LEVEL>`**

  Imposta il livello di dettaglio. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `normal`.

* **`--x64`**

  Elenca tutti gli SDK e i runtime x64 .NET Core che possono essere disinstallati con questo strumento.

* **`--x86`**

  Elenca tutti gli SDK e i runtime x86 .NET Core che possono essere disinstallati con questo strumento.

## <a name="macos"></a>[Macos](#tab/macos)

* **`--runtime`**

  Elenca tutti i runtime di .NET Core che possono essere disinstallati con questo strumento.

* **`--sdk`**

  Elenca tutti gli SDK di .NET Core che possono essere disinstallati con questo strumento.

* **`-v, --verbosity <LEVEL>`**

  Imposta il livello di dettaglio. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `normal`.
  
---

#### <a name="examples"></a>Esempi

* Elencare tutti gli SDK e i runtime di .NET Core che possono essere rimossi con questo strumento:List all .NET Core SDKs and runtimes that can be removed with this tool:

  ```console
  dotnet-core-uninstall list
  ```

* Elencare tutti gli SDK e i runtime x64 di .NET Core:

  ```console
  dotnet-core-uninstall list --x64
  ```

* Elencare tutti gli SDK x86 .NET Core:

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a>Fase 2 - Eseguire una corsa a secco

I `dotnet-core-uninstall dry-run` `dotnet-core-uninstall whatif` comandi e visualizzano gli SDK e i runtime di .NET Core che verranno rimossi in base alle opzioni fornite senza eseguire la disinstallazione. Questi comandi sono sinonimi.

**dotnet-core-uninstall dry-run e dotnet-core-uninstall whatif**

#### <a name="synopsis"></a>Riepilogo

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a>Argomenti

* **`VERSION`**

  Versione specificata da disinstallare. È possibile elencare diverse versioni una dopo l'altra, separate da spazi. Sono supportati anche i file di risposta.

  > [!TIP]
  > I file di risposta sono un'alternativa all'inserimento di tutte le versioni nella riga di comando.
  > Si tratta di file di \*testo, in genere con estensione rsp, e ogni versione è elencata su una riga separata.
  > Per specificare un `VERSION` file di \@ risposta per l'argomento, utilizzare il carattere immediatamente seguito dal nome del file di risposta.

#### <a name="options"></a>Opzioni

## <a name="windows"></a>[Windows](#tab/windows)

* **`--all`**

  Rimuove tutti gli SDK e runtime di .NET Core.

* **`--all-below <VERSION>`**

  Rimuove solo gli SDK e i runtime di .NET Core con una versione inferiore a quella specificata. La versione specificata rimane installata.

* **`--all-but <VERSIONS>`**

  Rimuove tutti gli SDK e runtime di .NET Core, ad eccezione di quelli specificati.

* **`--all-but-latest`**

  Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quella più alta.

* **`--all-lower-patches`**

  Rimuove gli SDK e i runtime di .NET Core sostituiti da patch più elevate. Questa opzione protegge global.json.

* **`--all-previews`**

  Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime.

* **`--all-previews-but-latest`**

  Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime tranne quello più alto.

* **`--aspnet-runtime`**

  Rimuove solo i runtime di ASP.NET Core.

* **`--hosting-bundle`**

  Rimuove solo i bundle di runtime e di hosting di .NET Core.

* **`--major-minor <MAJOR_MINOR>`**

  Rimuove gli SDK e i runtime di `major.minor` .NET Core che corrispondono alla versione specificata.

* **`--runtime`**

  Rimuove solo i runtime .NET Core.

* **`--sdk`**

  Rimuove solo gli SDK di .NET Core.

* **`-v, --verbosity <LEVEL>`**

  Imposta il livello di dettaglio. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `normal`.

* **`--x64`**

  Deve essere `--sdk`utilizzato `--runtime`con `--aspnet-runtime` , e per rimuovere SDK o runtime x64.

* **`--x86`**

  Deve essere `--sdk`utilizzato `--runtime`con `--aspnet-runtime` , e per rimuovere SDK o runtime x86.

* **`--force`** Forza la rimozione delle versioni che potrebbero essere utilizzate da Visual Studio.

Note:

1. Esattamente uno `--sdk` `--runtime`dei `--aspnet-runtime`, `--hosting-bundle` , , ed è obbligatorio.
2. `--all`, `--all-below` `--all-but`, `--all-but-latest` `--all-lower-patches`, `--all-previews` `--all-previews-but-latest`, `--major-minor`, `[<VERSION>...]` , , e sono esclusivi.
3. Se `--x64` `--x86` o non sono specificati, verranno rimossi sia x64 che x86.

## <a name="macos"></a>[Macos](#tab/macos)

* **`--all`**

  Rimuove tutti gli SDK e runtime di .NET Core.

* **`--all-below <VERSION>`**

  Rimuove gli SDK e i runtime di .NET Core al di sotto della versione specificata. La versione specificata rimarrà.

* **`--all-but <VERSIONS>`**

  Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quelli specificati.

* **`--all-but-latest`**

  Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quella più alta.

* **`--all-lower-patches`**

  Rimuove gli SDK e i runtime di .NET Core sostituiti da patch più elevate. Questa opzione protegge global.json.

* **`--all-previews`**

  Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime.

* **`--all-previews-but-latest`**

  Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime tranne quello più alto.

* **`--major-minor <MAJOR_MINOR>`**

  Rimuove gli SDK e i runtime di `major.minor` .NET Core che corrispondono alla versione specificata.

* **`--runtime`**

  Rimuove solo i runtime .NET Core.

* **`--sdk`**

  Rimuove solo gli SDK di .NET Core.

* **`-v, --verbosity <LEVEL>`**

  Imposta il livello di dettaglio. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `normal`.
  
* **`--force`** Forza la rimozione delle versioni che potrebbero essere utilizzate da Visual Studio o SDK.

Note:

1. Esattamente uno `--sdk` `--runtime` di ed è richiesto.
2. `--all`, `--all-below` `--all-but`, `--all-but-latest` `--all-lower-patches`, `--all-previews` `--all-previews-but-latest`, `--major-minor`, `[<VERSION>...]` , , e sono esclusivi.

---

#### <a name="examples"></a>Esempi

> [!NOTE]
> Per impostazione predefinita, gli SDK e i runtime di .NET Core che potrebbero `dotnet-core-uninstall dry-run` essere richiesti da Visual Studio o da altri SDK non sono inclusi nell'output. Negli esempi seguenti, alcuni SDK e runtime specificati potrebbero non essere inclusi nell'output, a seconda dello stato del computer. Per includere tutti gli SDK e i runtime, elencarli in modo esplicito come argomenti o utilizzare l'opzione `--force` .

* Esecuzione a secco di rimozione di tutti i runtime .NET Core che sono stati sostituiti da patch più elevate:

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* Esecuzione a secco di rimozione di tutti `2.2.301`gli SDK di .NET Core sotto la versione :

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a>Passaggio 3 - Disinstallare gli SDK e i runtime di .NET CoreStep 3 - Uninstall .NET Core SDKs and Runtimes

`dotnet-core-uninstall remove`disinstalla gli SDK e i runtime di .NET Core specificati da una raccolta di opzioni. Lo strumento non può essere utilizzato per disinstallare SDK e runtime con la versione 5.0 o successiva.

Poiché questo strumento ha un comportamento distruttivo, è **consigliabile** eseguire un'esecuzione a secco prima di eseguire il comando remove. L'esecuzione a secco mostrerà quali SDK e runtime di .NET Core verranno rimossi quando si utilizza il `remove` comando. Fare riferimento a [È necessario rimuovere una versione?](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version) per sapere quali SDK e runtime sono sicuri da rimuovere.

> [!CAUTION]
> Tenere presenti le indicazioni seguenti:
>
>- Questo strumento può disinstallare le versioni di `global.json` .NET Core SDK richieste dai file nel computer. È possibile reinstallare gli SDK di .NET Core dalla pagina [Scarica .NET Core.You can](https://dotnet.microsoft.com/download/dotnet-core) reinstall .NET Core SDKs from the Download .NET Core page.
>- Questo strumento può disinstallare le versioni del runtime di .NET Core richieste dalle applicazioni dipendenti dal framework nel computer. È possibile reinstallare i runtime .NET Core dalla pagina [Scarica .NET Core.You can](https://dotnet.microsoft.com/download/dotnet-core) reinstall .NET Core runtimes from the Download .NET Core page.
>- Questo strumento può disinstallare le versioni di .NET Core SDK e runtime su cui si basa Visual Studio. Se si interrompe l'installazione di Visual Studio, eseguire "Ripristina" nel programma di installazione di Visual Studio per tornare a uno stato funzionante.

Per impostazione predefinita, tutti i comandi mantengono gli SDK e i runtime di .NET Core che potrebbero essere richiesti da Visual Studio o da altri SDK. Questi SDK e runtime possono essere disinstallati elencandoli in modo `--force` esplicito come argomenti o utilizzando l'opzione .

Lo strumento richiede l'elevazione dei privilegi per disinstallare gli SDK e i runtime di .NET Core.The tool requires elevation to uninstall .NET Core SDKs and runtimes. Esegui lo strumento in un prompt `sudo` dei comandi di amministratore su Windows e con macOS. I `dry-run` `whatif` comandi e non richiedono l'elevazione dei privilegi.

**dotnet-core-uninstall rimuovere**

#### <a name="synopsis"></a>Riepilogo

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a>Argomenti

* **`VERSION`**

  Versione specificata da disinstallare. È possibile elencare diverse versioni una dopo l'altra, separate da spazi. Sono supportati anche i file di risposta.

  > [!TIP]
  > I file di risposta sono un'alternativa all'inserimento di tutte le versioni nella riga di comando.
  > Si tratta di file di \*testo, in genere con estensione rsp, e ogni versione è elencata su una riga separata.
  > Per specificare un `VERSION` file di \@ risposta per l'argomento, utilizzare il carattere immediatamente seguito dal nome del file di risposta.

#### <a name="options"></a>Opzioni

## <a name="windows"></a>[Windows](#tab/windows)

* **`--all`**

  Rimuove tutti gli SDK e runtime di .NET Core.

* **`--all-below <VERSION>`**

  Rimuove solo gli SDK e i runtime di .NET Core con una versione inferiore a quella specificata. La versione specificata rimane installata.

* **`--all-but <VERSIONS>`**

  Rimuove tutti gli SDK e runtime di .NET Core, ad eccezione di quelli specificati.

* **`--all-but-latest`**

  Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quella più alta.

* **`--all-lower-patches`**

  Rimuove gli SDK e i runtime di .NET Core sostituiti da patch più elevate. Questa opzione protegge global.json.

* **`--all-previews`**

  Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime.

* **`--all-previews-but-latest`**

  Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime tranne quello più alto.

* **`--aspnet-runtime`**

  Rimuove solo i runtime di ASP.NET Core.

* **`--hosting-bundle`**

  Rimuove solo i bundle di runtime e di hosting di .NET Core.

* **`--major-minor <MAJOR_MINOR>`**

  Rimuove gli SDK e i runtime di `major.minor` .NET Core che corrispondono alla versione specificata.

* **`--runtime`**

  Rimuove solo i runtime .NET Core.

* **`--sdk`**

  Rimuove solo gli SDK di .NET Core.

* **`-v, --verbosity <LEVEL>`**

  Imposta il livello di dettaglio. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `normal`.

* **`--x64`**

  Deve essere `--sdk`utilizzato `--runtime`con `--aspnet-runtime` , e per rimuovere SDK o runtime x64.

* **`--x86`**

  Deve essere `--sdk`utilizzato `--runtime`con `--aspnet-runtime` , e per rimuovere SDK o runtime x86.

* **`-y, --yes`** Esegue il comando senza richiedere una conferma sì o no.

* **`--force`** Forza la rimozione delle versioni che potrebbero essere utilizzate da Visual Studio.

Note:

1. Esattamente uno `--sdk` `--runtime`dei `--aspnet-runtime`, `--hosting-bundle` , , ed è obbligatorio.
2. `--all`, `--all-below` `--all-but`, `--all-but-latest` `--all-lower-patches`, `--all-previews` `--all-previews-but-latest`, `--major-minor`, `[<VERSION>...]` , , e sono esclusivi.
3. Se `--x64` `--x86` o non sono specificati, verranno rimossi sia x64 che x86.

## <a name="macos"></a>[Macos](#tab/macos)

* **`--all`**

  Rimuove tutti gli SDK e runtime di .NET Core.

* **`--all-below <VERSION>`**

  Rimuove gli SDK e i runtime di .NET Core al di sotto della versione specificata. La versione specificata rimarrà.

* **`--all-but <VERSIONS>`**

  Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quelli specificati.

* **`--all-but-latest`**

  Rimuove gli SDK e i runtime di .NET Core, ad eccezione di quella più alta.

* **`--all-lower-patches`**

  Rimuove gli SDK e i runtime di .NET Core sostituiti da patch più elevate. Questa opzione protegge global.json.

* **`--all-previews`**

  Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime.

* **`--all-previews-but-latest`**

  Rimuove gli SDK e i runtime di .NET Core contrassegnati come anteprime tranne quello più alto.

* **`--major-minor <MAJOR_MINOR>`**

  Rimuove gli SDK e i runtime di `major.minor` .NET Core che corrispondono alla versione specificata.

* **`--runtime`**

  Rimuove solo i runtime .NET Core.

* **`--sdk`**

  Rimuove solo gli SDK di .NET Core.

* **`-v, --verbosity <LEVEL>`**

  Imposta il livello di dettaglio. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `normal`.

* **`-y, --yes`** Esegue il comando senza richiedere la conferma Y/N.
  
* **`--force`** Forza la rimozione delle versioni che potrebbero essere utilizzate da Visual Studio o SDK.

Note:

1. Esattamente uno `--sdk` `--runtime` di ed è richiesto.
2. `--all`, `--all-below` `--all-but`, `--all-but-latest` `--all-lower-patches`, `--all-previews` `--all-previews-but-latest`, `--major-minor`, `[<VERSION>...]` , , e sono esclusivi.

---

#### <a name="examples"></a>Esempi

> [!NOTE]
> Per impostazione predefinita, gli SDK e i runtime di .NET Core che potrebbero essere richiesti da Visual Studio o da altri SDK vengono mantenuti. Negli esempi seguenti, alcuni degli SDK e dei runtime specificati possono rimanere, a seconda dello stato del computer. Per rimuovere tutti gli SDK e i runtime, elencarli in modo esplicito come argomenti o utilizzare l'opzione `--force` .

* Rimuovere tutti i runtime .NET `3.0.0-preview6-27804-01` Core tranne la versione senza richiedere la conferma Y/N:

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* Rimuovere tutti gli SDK di .NET Core 1.1 senza richiedere la conferma Y/n:Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* Rimuovere .NET Core 1.1.11 SDK senza output della console:

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* Rimuovere tutti gli SDK di .NET Core che possono essere rimossi in modo sicuro da questo strumento:Remove all .NET Core SDKs that can safely be removed by this tool:

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* Rimuovere tutti gli SDK di .NET Core che possono essere rimossi da questo strumento, inclusi gli SDK che potrebbero essere richiesti da Visual Studio (scelta non consigliata):

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* Rimuovere tutti gli SDK di .NET Core specificati nel file di rispostaRemove all .NET Core SDKs that are specified in the response file`versions.rsp`

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  Il contenuto di *versions.rsp* è il seguente:
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a>Passaggio 4 - Eliminare la cartella di fallback NuGet (facoltativo)Step 4 - Delete the NuGet fallback folder (optional)

In alcuni casi, non `NuGetFallbackFolder` è più necessario il e potrebbe voler eliminarlo. Per ulteriori informazioni sull'eliminazione di questa cartella, vedere [Rimuovere NuGetFallbackFolder](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).

## <a name="uninstall-the-tool"></a>Disinstallare lo strumento

## <a name="windows"></a>[Windows](#tab/windows)

1. Aprire **Installazione applicazioni**.
2. Cercare `Microsoft .NET Core SDK Uninstall Tool`.
3. Selezionare **Disinstalla**.

## <a name="macos"></a>[Macos](#tab/macos)

Eliminare il file *dotnet-core-uninstall.tar.gz* scaricato dalla directory in cui è stato installato. Se hai decompresso il contenuto di questo file in un'altra directory, assicurati di eliminare anche quel contenuto.

---
