---
title: Informazioni di riferimento di global.json
description: Esaminare lo schema per il file global.json, che consente di impostare la versione degli strumenti di .NET Core.
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.openlocfilehash: 7479774c7b9cdda233cf32d791c16e7fc6d733a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33209970"
---
# <a name="globaljson-reference"></a><span data-ttu-id="db314-103">Informazioni di riferimento di global.json</span><span class="sxs-lookup"><span data-stu-id="db314-103">global.json reference</span></span>

<span data-ttu-id="db314-104">Il file *global.json* consente di selezionare la versione degli strumenti di .NET Core usata nella proprietà `sdk`.</span><span class="sxs-lookup"><span data-stu-id="db314-104">The *global.json* file allows selection of the .NET Core tools version being used through the `sdk` property.</span></span>

<span data-ttu-id="db314-105">Gli strumenti CLI di .NET Core cercano questo file nella directory di lavoro corrente (che non corrisponde necessariamente alla directory del progetto) o in una delle directory padre.</span><span class="sxs-lookup"><span data-stu-id="db314-105">.NET Core CLI tools look for this file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="sdk"></a><span data-ttu-id="db314-106">SDK</span><span class="sxs-lookup"><span data-stu-id="db314-106">sdk</span></span>
<span data-ttu-id="db314-107">Tipo: Object</span><span class="sxs-lookup"><span data-stu-id="db314-107">Type: Object</span></span>

<span data-ttu-id="db314-108">Specifica le informazioni sull'SDK.</span><span class="sxs-lookup"><span data-stu-id="db314-108">Specifies information about the SDK.</span></span>

### <a name="version"></a><span data-ttu-id="db314-109">version</span><span class="sxs-lookup"><span data-stu-id="db314-109">version</span></span>
<span data-ttu-id="db314-110">Tipo: String</span><span class="sxs-lookup"><span data-stu-id="db314-110">Type: String</span></span>

<span data-ttu-id="db314-111">La versione dell'SDK da usare.</span><span class="sxs-lookup"><span data-stu-id="db314-111">The version of the SDK to use.</span></span>

<span data-ttu-id="db314-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="db314-112">For example:</span></span>

```json
{
  "sdk": {
    "version": "1.0.0-preview2-003121"
  }
}
```
