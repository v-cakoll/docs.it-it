---
title: Comando dotnet clean
description: Il comando dotnet clean consente di pulire la directory corrente.
ms.date: 12/04/2018
ms.openlocfilehash: a25b7930794795e3dff5051a8ca1dd1b9c261dfd
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169859"
---
# <a name="dotnet-clean"></a>dotnet clean

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet clean`: pulisce l'output di un progetto.

## <a name="synopsis"></a>Riepilogo

```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```

## <a name="description"></a>Description

Il comando `dotnet clean` pulisce l'output della compilazione precedente. Viene implementato come una [destinazione di MSBuild](/visualstudio/msbuild/msbuild-targets). Per questo motivo, il progetto viene valutato quando tale comando viene eseguito. Vengono puliti solo gli output creati durante la compilazione. Vengono pulite sia la cartella intermedia (*obj*) sia quella dell'output finale (*bin*).

## <a name="arguments"></a>Argomenti

`PROJECT`

Progetto MSBuild da pulire. Se non viene specificato un file di progetto, MSBuild cerca nella directory di lavoro corrente un file con estensione che termina con *proj* e usa tale file.

## <a name="options"></a>Opzioni

* **`-c|--configuration {Debug|Release}`**

  Definisce la configurazione di compilazione. Il valore predefinito è `Debug`. Se è stata specificata durante la fase di compilazione, questa opzione è necessaria soltanto al momento della pulizia.

* **`-f|--framework <FRAMEWORK>`**

  [Framework](../../standard/frameworks.md) specificato in fase di compilazione. Il framework deve essere definito nel [file di progetto](csproj.md). Se il framework è stato specificato in fase di compilazione, è necessario specificarlo al momento della pulizia.

* **`-h|--help`**

  Stampa una breve guida per il comando.

* **`-o|--output <OUTPUT_DIRECTORY>`**

  Directory in cui vengono inseriti gli output di compilazione. Se al momento della compilazione del progetto è stato specificato il framework, specificare l'opzione `-f|--framework <FRAMEWORK>` con l'opzione della directory di output.

* **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Elimina la cartella di output del runtime specificato. Viene usato durante la creazione di una [distribuzione indipendente](../deploying/index.md#self-contained-deployments-scd). Opzione disponibile a partire da .NET Core 2.0 SDK.

* **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio del comando. I livelli consentiti sono q[uiet], m[inimal], n[ormal], d[etailed] e diag[nostic].

## <a name="examples"></a>Esempi

* Pulire una compilazione predefinita del progetto:

  ```console
  dotnet clean
  ```

* Pulire un progetto compilato con la configurazione di tipo Versione:

  ```console
  dotnet clean --configuration Release
  ```