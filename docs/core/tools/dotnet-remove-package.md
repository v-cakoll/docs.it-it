---
title: Comando dotnet remove package
description: Il comando dotnet remove package offre un'opzione utile per rimuovere il riferimento del pacchetto NuGet a un progetto.
ms.date: 05/29/2018
ms.openlocfilehash: 4cc8ac927b761547dc5e53be9abeba827bf1e1d9
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168728"
---
# <a name="dotnet-remove-package"></a>dotnet remove package

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet remove package`: rimuove il riferimento al pacchetto da un file di progetto.

## <a name="synopsis"></a>Riepilogo

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a>Description

Il comando `dotnet remove package` offre un'opzione utile per rimuovere un riferimento al pacchetto NuGet da un progetto.

## <a name="arguments"></a>Argomenti

`PROJECT`

Specifica il file di progetto. Se non specificato, il comando ne cerca uno nella directory corrente.

`PACKAGE_NAME`

Riferimento al pacchetto da rimuovere.

## <a name="options"></a>Opzioni

`-h|--help`

Stampa una breve guida per il comando.

## <a name="examples"></a>Esempi

Rimuove il pacchetto NuGet `Newtonsoft.Json` da un progetto nella directory corrente:

`dotnet remove package Newtonsoft.Json`