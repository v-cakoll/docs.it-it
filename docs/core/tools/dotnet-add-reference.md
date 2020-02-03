---
title: comando DotNet Add Reference
description: Il comando dotnet add reference offre un'opzione utile per aggiungere riferimenti da progetto a progetto.
ms.date: 06/26/2019
ms.openlocfilehash: dc8bc01a2bff4f2cf3a8af9efb233448d7de337f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733280"
---
# <a name="dotnet-add-reference"></a>dotnet add reference

**Questo articolo si applica a:** ✔️ .NET Core 1. x SDK e versioni successive

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>Name

`dotnet add reference`: aggiunge riferimenti da progetto a progetto.

## <a name="synopsis"></a>Riepilogo

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help] [--interactive]`

## <a name="description"></a>Descrizione

Il comando `dotnet add reference` offre un'opzione utile per aggiungere i riferimenti al progetto in un progetto. Dopo l'esecuzione del comando, gli elementi `<ProjectReference>` vengono aggiunti al file di progetto.

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>Argomenti

- **`PROJECT`**

  Specifica il file di progetto. Se non specificato, il comando ne cerca uno nella directory corrente.

- **`PROJECT_REFERENCES`**

  Riferimenti da progetto a progetto da aggiungere. Specificare uno o più progetti. I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei sistemi basati su Unix/Linux.

## <a name="options"></a>Opzioni

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`-f|--framework <FRAMEWORK>`**

  Aggiunge riferimenti al progetto solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.

- **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione). Disponibile a partire da .NET Core 3.0 SDK.

## <a name="examples"></a>Esempi

- Aggiungere un riferimento al progetto:

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- Aggiungere più riferimenti al progetto nella directory corrente:

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- Aggiungere più riferimenti al progetto usando un criterio GLOB in Linux/Unix:

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
