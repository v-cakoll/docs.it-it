---
title: Informazioni di riferimento di global.json
description: Esaminare lo schema per il file global.json, che consente di impostare la versione degli strumenti di .NET Core.
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: ac53a899e76c99527f2670d0a6bed3f8cc6ce31f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="globaljson-reference"></a><span data-ttu-id="8f7e8-103">Informazioni di riferimento di global.json</span><span class="sxs-lookup"><span data-stu-id="8f7e8-103">global.json reference</span></span>

<span data-ttu-id="8f7e8-104">Il file *global.json* consente di selezionare la versione degli strumenti di .NET Core usata nella proprietà `sdk`.</span><span class="sxs-lookup"><span data-stu-id="8f7e8-104">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="8f7e8-105">Gli strumenti CLI di .NET Core cercano questo file nella directory di lavoro corrente (che non corrisponde necessariamente alla directory del progetto) o in una delle directory padre.</span><span class="sxs-lookup"><span data-stu-id="8f7e8-105">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="8f7e8-106">SDK</span><span class="sxs-lookup"><span data-stu-id="8f7e8-106">sdk</span></span>
<span data-ttu-id="8f7e8-107">Tipo: Object</span><span class="sxs-lookup"><span data-stu-id="8f7e8-107">Type: Object</span></span>

<span data-ttu-id="8f7e8-108">Specifica le informazioni sull'SDK.</span><span class="sxs-lookup"><span data-stu-id="8f7e8-108">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="8f7e8-109">version</span><span class="sxs-lookup"><span data-stu-id="8f7e8-109">version</span></span>
<span data-ttu-id="8f7e8-110">Tipo: String</span><span class="sxs-lookup"><span data-stu-id="8f7e8-110">Type: String</span></span>

<span data-ttu-id="8f7e8-111">La versione dell'SDK da usare.</span><span class="sxs-lookup"><span data-stu-id="8f7e8-111">The version of the SDK to use.</span></span>

<span data-ttu-id="8f7e8-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8f7e8-112">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```
