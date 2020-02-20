---
title: Comando dotnet clean
description: Il comando dotnet clean consente di pulire la directory corrente.
ms.date: 02/14/2020
ms.openlocfilehash: 186f1ea07718a8e178f88c3d079cf6e2f1f8660b
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503750"
---
# <a name="dotnet-clean"></a>dotnet clean

**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive

## <a name="name"></a>Nome

`dotnet clean`: pulisce l'output di un progetto.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive]
    [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a>Descrizione

Il comando `dotnet clean` pulisce l'output della compilazione precedente. Viene implementato come una [destinazione di MSBuild](/visualstudio/msbuild/msbuild-targets). Per questo motivo, il progetto viene valutato quando tale comando viene eseguito. Vengono puliti solo gli output creati durante la compilazione. Vengono pulite sia la cartella intermedia (*obj*) sia quella dell'output finale (*bin*).

## <a name="arguments"></a>Argomenti

`PROJECT | SOLUTION`

Progetto o soluzione MSBuild da pulire. Se non viene specificato alcun file di progetto o di soluzione, MSBuild cercherà nella directory di lavoro corrente un file con estensione *proj* o *sln* e userà questo file.

## <a name="options"></a>Opzioni

* **`-c|--configuration <CONFIGURATION>`**

  Definisce la configurazione di compilazione. Il valore predefinito per la maggior parte dei progetti è `Debug`, ma è possibile eseguire l'override delle impostazioni di configurazione della build nel progetto. Se è stata specificata durante la fase di compilazione, questa opzione è necessaria soltanto al momento della pulizia.

* **`-f|--framework <FRAMEWORK>`**

  [Framework](../../standard/frameworks.md) specificato in fase di compilazione. Il framework deve essere definito nel [file di progetto](csproj.md). Se il framework è stato specificato in fase di compilazione, è necessario specificarlo al momento della pulizia.

* **`-h|--help`**

  Stampa una breve guida per il comando.

* **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente, ad esempio il completamento dell'autenticazione. Disponibile a partire da .NET Core 3.0 SDK.

* **`--nologo`**

  Non visualizza il messaggio di avvio né il messaggio di copyright. Disponibile a partire da .NET Core 3.0 SDK.

* **`-o|--output <OUTPUT_DIRECTORY>`**

  Directory contenente gli artefatti di compilazione da pulire. Se al momento della compilazione del progetto è stato specificato il framework, specificare l'opzione `-f|--framework <FRAMEWORK>` con l'opzione della directory di output.

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Elimina la cartella di output del runtime specificato. Viene usato durante la creazione di una [distribuzione indipendente](../deploying/index.md#publish-self-contained).

* **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio di MSBuild. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `normal`.

## <a name="examples"></a>Esempi

* Pulire una compilazione predefinita del progetto:

  ```dotnetcli
  dotnet clean
  ```

* Pulire un progetto compilato con la configurazione di tipo Versione:

  ```dotnetcli
  dotnet clean --configuration Release
  ```
