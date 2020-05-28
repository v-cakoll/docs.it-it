---
title: Disinstalla strumento
description: Panoramica dello strumento di disinstallazione di .NET Core, uno strumento guidato che consente la pulizia controllata degli SDK e dei runtime di .NET Core.
author: sfoslund
ms.date: 05/27/2020
ms.openlocfilehash: 1ad31cd42d8f8f87e3501b422fc4298c643e2067
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144513"
---
# <a name="net-core-uninstall-tool"></a>Strumento di disinstallazione di .NET Core

Lo [strumento di disinstallazione di .NET Core](https://aka.ms/dotnet-core-uninstall-tool) ( `dotnet-core-uninstall` ) consente di rimuovere gli SDK e i runtime di .NET Core da un sistema. È disponibile una raccolta di opzioni per specificare quali versioni si desidera disinstallare.

Lo strumento supporta Windows e macOS. Linux non è attualmente supportato.

In Windows, lo strumento può disinstallare solo gli SDK e i runtime installati usando uno dei programmi di installazione seguenti:

- Il programma di installazione di .NET Core SDK e Runtime.
- Programma di installazione di Visual Studio nelle versioni precedenti a Visual Studio 2019 versione 16,3.

In macOS lo strumento può disinstallare solo gli SDK e i runtime che si trovano nella cartella */usr/local/share/DotNet* .

A causa di queste limitazioni, lo strumento potrebbe non essere in grado di disinstallare tutti gli SDK e i runtime di .NET Core nel computer. È possibile usare il `dotnet --info` comando per trovare tutti gli SDK e i runtime di .net core installati, inclusi gli SDK e i runtime che questo strumento non è in grado di rimuovere. Il `dotnet-core-uninstall list` comando Visualizza gli SDK che è possibile disinstallare con lo strumento.

## <a name="install-the-tool"></a>Installare lo strumento

È possibile scaricare lo strumento di disinstallazione di .NET Core da [qui](https://aka.ms/dotnet-core-uninstall-tool) e trovare il codice sorgente nel repository GitHub [DotNet/CLI-Lab](https://github.com/dotnet/cli-lab) .

> [!NOTE]
> Per disinstallare SDK e runtime di .NET Core, lo strumento richiede l'elevazione dei privilegi. Pertanto, deve essere installato in una directory protetta da scrittura, ad esempio *c:\Programmi* in Windows o */usr/local/bin* in MacOS. Vedere anche [accesso con privilegi elevati per i comandi DotNet](../tools/elevated-access.md). Per ulteriori informazioni, vedere le [istruzioni dettagliate](https://aka.ms/dotnet-core-uninstall-tool)per l'installazione.

## <a name="run-the-tool"></a>Eseguire lo strumento

Nei passaggi seguenti viene illustrato l'approccio consigliato per l'esecuzione dello strumento di disinstallazione:

- [Passaggio 1: visualizzare gli SDK e i runtime di .NET Core installati](#step-1---display-installed-net-core-sdks-and-runtimes)
- [Passaggio 2: eseguire un'esecuzione a secco](#step-2---do-a-dry-run)
- [Passaggio 3: disinstallare SDK e runtime di .NET Core](#step-3---uninstall-net-core-sdks-and-runtimes)
- [Passaggio 4: eliminare la cartella di fallback NuGet (facoltativo)](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a>Passaggio 1: visualizzare gli SDK e i runtime di .NET Core installati

Il `dotnet-core-uninstall list` comando elenca gli SDK e i runtime di .net core installati che possono essere rimossi con questo strumento. Alcuni SDK e Runtime possono essere richiesti da Visual Studio e vengono visualizzati con una nota del motivo per cui non è consigliabile disinstallarli.

> [!NOTE]
> L'output del `dotnet-core-uninstall list` comando non corrisponderà all'elenco di versioni installate nell'output di `dotnet --info` nella maggior parte dei casi. In particolare, questo strumento non Visualizza le versioni installate da file zip o gestite da Visual Studio (qualsiasi versione installata con Visual Studio 2019 16,3 o versioni successive). Un modo per verificare se una versione è gestita da Visual Studio è visualizzarla in `Add or Remove Programs` , in cui le versioni gestite di Visual Studio sono contrassegnate come tali nei rispettivi nomi visualizzati.

**elenco di disinstallazione DotNet-Core**

#### <a name="synopsis"></a>Riepilogo

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a>Opzioni

## <a name="windows"></a>[Windows](#tab/windows)

* **`--aspnet-runtime`**

  Elenca tutti i runtime di ASP.NET Core che possono essere disinstallati con questo strumento.

* **`--hosting-bundle`**

  Elenca tutti i bundle di hosting .NET Core che possono essere disinstallati con questo strumento.

* **`--runtime`**

  Elenca tutti i runtime di .NET Core che possono essere disinstallati con questo strumento.

* **`--sdk`**

  Elenca tutti gli SDK di .NET Core che possono essere disinstallati con questo strumento.

* **`-v, --verbosity <LEVEL>`**

  Imposta il livello di dettaglio. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `normal`.

* **`--x64`**

  Elenca tutti i runtime e gli SDK .NET Core x64 che possono essere disinstallati con questo strumento.

* **`--x86`**

  Elenca tutti gli SDK di .NET core x86 e i runtime che possono essere disinstallati con questo strumento.

## <a name="macos"></a>[macOS](#tab/macos)

* **`--runtime`**

  Elenca tutti i runtime di .NET Core che possono essere disinstallati con questo strumento.

* **`--sdk`**

  Elenca tutti gli SDK di .NET Core che possono essere disinstallati con questo strumento.

* **`-v, --verbosity <LEVEL>`**

  Imposta il livello di dettaglio. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `normal`.
  
---

#### <a name="examples"></a>Esempio

* Elencare tutti i runtime e gli SDK di .NET Core che possono essere rimossi con questo strumento:

  ```console
  dotnet-core-uninstall list
  ```

* Elencare tutti i runtime e gli SDK di .NET Core x64:

  ```console
  dotnet-core-uninstall list --x64
  ```

* Elencare tutti gli SDK di .NET core x86:

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a>Passaggio 2: eseguire un'esecuzione a secco

I `dotnet-core-uninstall dry-run` `dotnet-core-uninstall whatif` comandi e visualizzano gli SDK e i runtime di .NET Core che verranno rimossi in base alle opzioni fornite senza eseguire la disinstallazione. Questi comandi sono sinonimi.

**DotNet-Core-Uninstall Dry-Run e DotNet-Core-Uninstall WhatIf**

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
  > Si tratta di file di testo, in genere con \* estensione rsp, e ogni versione è elencata in una riga separata.
  > Per specificare un file di risposta per l' `VERSION` argomento, usare il \@ carattere immediatamente seguito dal nome del file di risposta.

#### <a name="options"></a>Opzioni

## <a name="windows"></a>[Windows](#tab/windows)

* **`--all`**

  Rimuove tutti i runtime e gli SDK di .NET Core.

* **`--all-below <VERSION>`**

  Rimuove solo gli SDK di .NET Core e i runtime con una versione inferiore alla versione specificata. La versione specificata rimane installata.

* **`--all-but <VERSIONS>`**

  Rimuove tutti i runtime e gli SDK di .NET Core, ad eccezione di quelli specificati.

* **`--all-but-latest`**

  Rimuove gli SDK di .NET Core e i runtime, ad eccezione di una versione più recente.

* **`--all-lower-patches`**

  Rimuove gli SDK di .NET Core e i runtime sostituiti da patch più elevate. Questa opzione protegge Global. JSON.

* **`--all-previews`**

  Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime.

* **`--all-previews-but-latest`**

  Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime eccetto quella più alta.

* **`--aspnet-runtime`**

  Rimuove solo i runtime ASP.NET Core.

* **`--hosting-bundle`**

  Rimuove solo i pacchetti di runtime e hosting di .NET Core.

* **`--major-minor <MAJOR_MINOR>`**

  Rimuove gli SDK di .NET Core e i runtime che corrispondono alla `major.minor` versione specificata.

* **`--runtime`**

  Rimuove solo i runtime di .NET Core.

* **`--sdk`**

  Rimuove solo gli SDK di .NET Core.

* **`-v, --verbosity <LEVEL>`**

  Imposta il livello di dettaglio. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `normal`.

* **`--x64`**

  Deve essere utilizzato con `--sdk` , `--runtime` e `--aspnet-runtime` per rimuovere gli SDK o i runtime x64.

* **`--x86`**

  `--sdk` `--runtime` `--aspnet-runtime` Per rimuovere gli SDK o i Runtime x86, è necessario usare con, e.

* **`--force`** Forza la rimozione di versioni che potrebbero essere usate da Visual Studio.

Note:

1. È richiesto esattamente uno degli `--sdk` ,, `--runtime` `--aspnet-runtime` e `--hosting-bundle` .
2. `--all`, `--all-below` , `--all-but` , `--all-but-latest` , `--all-lower-patches` , `--all-previews` , `--all-previews-but-latest` , `--major-minor` e `[<VERSION>...]` sono esclusivi.
3. Se `--x64` o `--x86` non sono specificati, verranno rimossi sia x64 che x86.

## <a name="macos"></a>[macOS](#tab/macos)

* **`--all`**

  Rimuove tutti i runtime e gli SDK di .NET Core.

* **`--all-below <VERSION>`**

  Rimuove gli SDK e i Runtime .NET Core sotto la versione specificata. La versione specificata rimarrà.

* **`--all-but <VERSIONS>`**

  Rimuove gli SDK di .NET Core e i runtime, ad eccezione delle versioni specificate.

* **`--all-but-latest`**

  Rimuove gli SDK di .NET Core e i runtime, ad eccezione di una versione più recente.

* **`--all-lower-patches`**

  Rimuove gli SDK di .NET Core e i runtime sostituiti da patch più elevate. Questa opzione protegge Global. JSON.

* **`--all-previews`**

  Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime.

* **`--all-previews-but-latest`**

  Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime eccetto quella più alta.

* **`--major-minor <MAJOR_MINOR>`**

  Rimuove gli SDK di .NET Core e i runtime che corrispondono alla `major.minor` versione specificata.

* **`--runtime`**

  Rimuove solo i runtime di .NET Core.

* **`--sdk`**

  Rimuove solo gli SDK di .NET Core.

* **`-v, --verbosity <LEVEL>`**

  Imposta il livello di dettaglio. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `normal`.
  
* **`--force`** Forza la rimozione di versioni che potrebbero essere usate da Visual Studio o da SDK.

Note:

1. È necessario specificare esattamente uno dei `--sdk` e `--runtime` .
2. `--all`, `--all-below` , `--all-but` , `--all-but-latest` , `--all-lower-patches` , `--all-previews` , `--all-previews-but-latest` , `--major-minor` e `[<VERSION>...]` sono esclusivi.

---

#### <a name="examples"></a>Esempio

> [!NOTE]
> Per impostazione predefinita, gli SDK di .NET Core e i runtime che potrebbero essere richiesti da Visual Studio o altri SDK non sono inclusi nell' `dotnet-core-uninstall dry-run` output. Negli esempi seguenti alcuni degli SDK e dei runtime specificati potrebbero non essere inclusi nell'output, a seconda dello stato del computer. Per includere tutti gli SDK e i runtime, elencarli in modo esplicito come argomenti oppure usare l' `--force` opzione.

* Esecuzione a secco della rimozione di tutti i runtime di .NET Core sostituiti da patch superiori:

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* Esecuzione a secco della rimozione di tutti gli SDK di .NET Core sotto la versione `2.2.301` :

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a>Passaggio 3: disinstallare SDK e runtime di .NET Core

`dotnet-core-uninstall remove`Disinstalla gli SDK e i Runtime .NET Core specificati da una raccolta di opzioni. Non è possibile usare lo strumento per disinstallare SDK e Runtime con la versione 5,0 o successive.

Poiché questo strumento presenta un comportamento distruttivo, è **consigliabile eseguire** un'esecuzione a secco prima di eseguire il comando Rimuovi. L'esecuzione a secco mostrerà quali SDK e runtime di .NET Core verranno rimossi quando si usa il `remove` comando. Per informazioni su quali SDK e Runtime è possibile rimuovere, fare [riferimento a.](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version)

> [!CAUTION]
> Tenere presenti le indicazioni seguenti:
>
>- Questo strumento consente di disinstallare le versioni dei .NET Core SDK richieste dai `global.json` file nel computer. È possibile reinstallare gli SDK di .NET Core dalla pagina [Scarica .NET Core](https://dotnet.microsoft.com/download/dotnet-core) .
>- Questo strumento consente di disinstallare le versioni del runtime di .NET Core richieste dalle applicazioni dipendenti dal Framework nel computer. È possibile reinstallare i runtime di .NET Core dalla pagina [Scarica .NET Core](https://dotnet.microsoft.com/download/dotnet-core) .
>- Questo strumento consente di disinstallare le versioni del .NET Core SDK e del runtime su cui si basa Visual Studio. Se si interrompe l'installazione di Visual Studio, eseguire "Repair" nel programma di installazione di Visual Studio per tornare allo stato di lavoro.

Per impostazione predefinita, tutti i comandi mantengono gli SDK e i Runtime .NET Core che potrebbero essere richiesti da Visual Studio o da altri SDK. Questi SDK e Runtime possono essere disinstallati elencando in modo esplicito come argomenti o usando l' `--force` opzione.

Per disinstallare SDK e runtime di .NET Core, lo strumento richiede l'elevazione dei privilegi. Eseguire lo strumento in un prompt dei comandi dell'amministratore in Windows e con `sudo` in MacOS. I `dry-run` `whatif` comandi e non richiedono l'elevazione dei privilegi.

**DotNet-Core-Disinstalla Rimuovi**

#### <a name="synopsis"></a>Riepilogo

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a>Argomenti

* **`VERSION`**

  Versione specificata da disinstallare. È possibile elencare diverse versioni una dopo l'altra, separate da spazi. Sono supportati anche i file di risposta.

  > [!TIP]
  > I file di risposta sono un'alternativa all'inserimento di tutte le versioni nella riga di comando.
  > Si tratta di file di testo, in genere con \* estensione rsp, e ogni versione è elencata in una riga separata.
  > Per specificare un file di risposta per l' `VERSION` argomento, usare il \@ carattere immediatamente seguito dal nome del file di risposta.

#### <a name="options"></a>Opzioni

## <a name="windows"></a>[Windows](#tab/windows)

* **`--all`**

  Rimuove tutti i runtime e gli SDK di .NET Core.

* **`--all-below <VERSION>`**

  Rimuove solo gli SDK di .NET Core e i runtime con una versione inferiore alla versione specificata. La versione specificata rimane installata.

* **`--all-but <VERSIONS>`**

  Rimuove tutti i runtime e gli SDK di .NET Core, ad eccezione di quelli specificati.

* **`--all-but-latest`**

  Rimuove gli SDK di .NET Core e i runtime, ad eccezione di una versione più recente.

* **`--all-lower-patches`**

  Rimuove gli SDK di .NET Core e i runtime sostituiti da patch più elevate. Questa opzione protegge Global. JSON.

* **`--all-previews`**

  Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime.

* **`--all-previews-but-latest`**

  Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime eccetto quella più alta.

* **`--aspnet-runtime`**

  Rimuove solo i runtime ASP.NET Core.

* **`--hosting-bundle`**

  Rimuove solo i pacchetti di runtime e hosting di .NET Core.

* **`--major-minor <MAJOR_MINOR>`**

  Rimuove gli SDK di .NET Core e i runtime che corrispondono alla `major.minor` versione specificata.

* **`--runtime`**

  Rimuove solo i runtime di .NET Core.

* **`--sdk`**

  Rimuove solo gli SDK di .NET Core.

* **`-v, --verbosity <LEVEL>`**

  Imposta il livello di dettaglio. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `normal`.

* **`--x64`**

  Deve essere utilizzato con `--sdk` , `--runtime` e `--aspnet-runtime` per rimuovere gli SDK o i runtime x64.

* **`--x86`**

  `--sdk` `--runtime` `--aspnet-runtime` Per rimuovere gli SDK o i Runtime x86, è necessario usare con, e.

* **`-y, --yes`** Esegue il comando senza richiedere una conferma Yes o no.

* **`--force`** Forza la rimozione di versioni che potrebbero essere usate da Visual Studio.

Note:

1. È richiesto esattamente uno degli `--sdk` ,, `--runtime` `--aspnet-runtime` e `--hosting-bundle` .
2. `--all`, `--all-below` , `--all-but` , `--all-but-latest` , `--all-lower-patches` , `--all-previews` , `--all-previews-but-latest` , `--major-minor` e `[<VERSION>...]` sono esclusivi.
3. Se `--x64` o `--x86` non sono specificati, verranno rimossi sia x64 che x86.

## <a name="macos"></a>[macOS](#tab/macos)

* **`--all`**

  Rimuove tutti i runtime e gli SDK di .NET Core.

* **`--all-below <VERSION>`**

  Rimuove gli SDK e i Runtime .NET Core sotto la versione specificata. La versione specificata rimarrà.

* **`--all-but <VERSIONS>`**

  Rimuove gli SDK di .NET Core e i runtime, ad eccezione delle versioni specificate.

* **`--all-but-latest`**

  Rimuove gli SDK di .NET Core e i runtime, ad eccezione di una versione più recente.

* **`--all-lower-patches`**

  Rimuove gli SDK di .NET Core e i runtime sostituiti da patch più elevate. Questa opzione protegge Global. JSON.

* **`--all-previews`**

  Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime.

* **`--all-previews-but-latest`**

  Rimuove gli SDK di .NET Core e i runtime contrassegnati come anteprime eccetto quella più alta.

* **`--major-minor <MAJOR_MINOR>`**

  Rimuove gli SDK di .NET Core e i runtime che corrispondono alla `major.minor` versione specificata.

* **`--runtime`**

  Rimuove solo i runtime di .NET Core.

* **`--sdk`**

  Rimuove solo gli SDK di .NET Core.

* **`-v, --verbosity <LEVEL>`**

  Imposta il livello di dettaglio. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `normal`.

* **`-y, --yes`** Esegue il comando senza richiedere la conferma Y/N.
  
* **`--force`** Forza la rimozione di versioni che potrebbero essere usate da Visual Studio o da SDK.

Note:

1. È necessario specificare esattamente uno dei `--sdk` e `--runtime` .
2. `--all`, `--all-below` , `--all-but` , `--all-but-latest` , `--all-lower-patches` , `--all-previews` , `--all-previews-but-latest` , `--major-minor` e `[<VERSION>...]` sono esclusivi.

---

#### <a name="examples"></a>Esempio

> [!NOTE]
> Per impostazione predefinita, vengono conservati gli SDK e i Runtime .NET Core che potrebbero essere richiesti da Visual Studio o altri SDK. Negli esempi seguenti è possibile che alcuni degli SDK e dei runtime specificati rimangano, a seconda dello stato del computer. Per rimuovere tutti gli SDK e i runtime, elencarli in modo esplicito come argomenti oppure usare l' `--force` opzione.

* Rimuovere tutti i runtime di .NET Core eccetto la versione `3.0.0-preview6-27804-01` senza richiedere la conferma Y/N:

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* Rimuovere tutti gli SDK di .NET Core 1,1 senza richiedere la conferma Y/n:

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* Rimuovere .NET Core 1.1.11 SDK senza output della console:

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* Rimuovere tutti gli SDK di .NET Core che possono essere rimossi in modo sicuro da questo strumento:

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* Rimuovere tutti gli SDK di .NET Core che possono essere rimossi da questo strumento, inclusi gli SDK che potrebbero essere richiesti da Visual Studio (scelta non consigliata):

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* Rimuovere tutti gli SDK di .NET Core specificati nel file di risposta`versions.rsp`

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  Il contenuto di *Versions. rsp* è il seguente:
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a>Passaggio 4: eliminare la cartella di fallback NuGet (facoltativo)

In alcuni casi non è più necessario `NuGetFallbackFolder` e può essere opportuno eliminarlo. Per ulteriori informazioni sull'eliminazione di questa cartella, vedere [Remove the NuGetFallbackFolder](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).

## <a name="uninstall-the-tool"></a>Disinstalla lo strumento

## <a name="windows"></a>[Windows](#tab/windows)

1. Aprire **Installazione applicazioni**.
2. Cercare `Microsoft .NET Core SDK Uninstall Tool`.
3. Selezionare **Disinstalla**.

## <a name="macos"></a>[macOS](#tab/macos)

Eliminare il file *DotNet-Core-Uninstall. tar. gz* scaricato dalla directory in cui è stato installato. Se il contenuto di questo file è stato decompresso in un'altra directory, assicurarsi di eliminare anche tale contenuto.

---
