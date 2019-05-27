---
title: Comando dotnet clean
description: Il comando dotnet clean consente di pulire la directory corrente.
ms.date: 04/14/2019
ms.openlocfilehash: fa19f1b041e4031082f928135395a5f06ce702e9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631817"
---
# <a name="dotnet-clean"></a>dotnet clean

**Questo argomento si applica a: ✓** .NET Core 2.1.x SDK e versioni successive

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>nome

`dotnet clean`: pulisce l'output di un progetto.

## <a name="synopsis"></a>Riepilogo

```
dotnet clean [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--interactive] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a>Description

Il comando `dotnet clean` pulisce l'output della compilazione precedente. Viene implementato come una [destinazione di MSBuild](/visualstudio/msbuild/msbuild-targets). Per questo motivo, il progetto viene valutato quando tale comando viene eseguito. Vengono puliti solo gli output creati durante la compilazione. Vengono pulite sia la cartella intermedia (*obj*) sia quella dell'output finale (*bin*).

## <a name="arguments"></a>Argomenti

`PROJECT | SOLUTION`

Progetto o soluzione MSBuild da pulire. Se non viene specificato alcun file di progetto o di soluzione, MSBuild cercherà nella directory di lavoro corrente un file con estensione *proj* o *sln* e userà questo file.

## <a name="options"></a>Opzioni

* **`-c|--configuration {Debug|Release}`**

  Definisce la configurazione di compilazione. Il valore predefinito è `Debug`. Se è stata specificata durante la fase di compilazione, questa opzione è necessaria soltanto al momento della pulizia.

* **`-f|--framework <FRAMEWORK>`**

  [Framework](../../standard/frameworks.md) specificato in fase di compilazione. Il framework deve essere definito nel [file di progetto](csproj.md). Se il framework è stato specificato in fase di compilazione, è necessario specificarlo al momento della pulizia.

* **`-h|--help`**

  Stampa una breve guida per il comando.

* **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente, ad esempio il completamento dell'autenticazione. Disponibile a partire da .NET Core 3.0 SDK.

* **`-o|--output <OUTPUT_DIRECTORY>`**

  Directory contenente gli artefatti di compilazione da pulire. Se al momento della compilazione del progetto è stato specificato il framework, specificare l'opzione `-f|--framework <FRAMEWORK>` con l'opzione della directory di output.

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Elimina la cartella di output del runtime specificato. Viene usato durante la creazione di una [distribuzione indipendente](../deploying/index.md#self-contained-deployments-scd). Opzione disponibile a partire da .NET Core 2.0 SDK.

* **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio di MSBuild. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`. Il valore predefinito è `normal`.

## <a name="examples"></a>Esempi

* Pulire una compilazione predefinita del progetto:

  ```console
  dotnet clean
  ```

* Pulire un progetto compilato con la configurazione di tipo Versione:

  ```console
  dotnet clean --configuration Release
  ```
