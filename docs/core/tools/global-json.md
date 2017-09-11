---
title: Informazioni di riferimento di global.json
description: Esaminare lo schema per il file global.json, che consente di impostare la versione degli strumenti di .NET Core.
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ffa97164736fc7f3edc450682d23bdf499b6eb34
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="globaljson-reference"></a><span data-ttu-id="f3498-104">Informazioni di riferimento di global.json</span><span class="sxs-lookup"><span data-stu-id="f3498-104">global.json reference</span></span>

<span data-ttu-id="f3498-105">Il file *global.json* consente di selezionare la versione degli strumenti di .NET Core usata nella proprietà `sdk`.</span><span class="sxs-lookup"><span data-stu-id="f3498-105">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="f3498-106">Gli strumenti CLI di .NET Core cercano questo file nella directory di lavoro corrente (che non corrisponde necessariamente alla directory del progetto) o in una delle directory padre.</span><span class="sxs-lookup"><span data-stu-id="f3498-106">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="f3498-107">SDK</span><span class="sxs-lookup"><span data-stu-id="f3498-107">sdk</span></span>
<span data-ttu-id="f3498-108">Tipo: Object</span><span class="sxs-lookup"><span data-stu-id="f3498-108">Type: Object</span></span>

<span data-ttu-id="f3498-109">Specifica le informazioni sull'SDK.</span><span class="sxs-lookup"><span data-stu-id="f3498-109">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="f3498-110">version</span><span class="sxs-lookup"><span data-stu-id="f3498-110">version</span></span>
<span data-ttu-id="f3498-111">Tipo: String</span><span class="sxs-lookup"><span data-stu-id="f3498-111">Type: String</span></span>

<span data-ttu-id="f3498-112">La versione dell'SDK da usare.</span><span class="sxs-lookup"><span data-stu-id="f3498-112">The version of the SDK to use.</span></span>

<span data-ttu-id="f3498-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f3498-113">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```

