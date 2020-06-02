---
title: <returns> -Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: 7bc950a8d89a3ac2b5c3b7a68e05c7778e97f85c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287233"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="a50d1-102">\<returns>(Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="a50d1-102">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="a50d1-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a50d1-103">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="a50d1-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="a50d1-104">Parameters</span></span>

- `description`

  <span data-ttu-id="a50d1-105">Descrizione del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="a50d1-105">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="a50d1-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a50d1-106">Remarks</span></span>

<span data-ttu-id="a50d1-107">Il `<returns>` tag deve essere usato nel commento per una dichiarazione di metodo per descrivere il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="a50d1-107">The `<returns>` tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="a50d1-108">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="a50d1-108">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="a50d1-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="a50d1-109">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="a50d1-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a50d1-110">See also</span></span>

- [<span data-ttu-id="a50d1-111">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a50d1-111">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="a50d1-112">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="a50d1-112">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
