---
title: <c>-Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: a09bcd069e2f85f4a21736cb218c42c0e481d70b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287467"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="b092e-102">\<c>(Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="b092e-102">\<c> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="b092e-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b092e-103">Syntax</span></span>

```xml
<c>text</c>
```

## <a name="parameters"></a><span data-ttu-id="b092e-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="b092e-104">Parameters</span></span>

- `text`

  <span data-ttu-id="b092e-105">Il testo che si desidera indicare come codice.</span><span class="sxs-lookup"><span data-stu-id="b092e-105">The text you would like to indicate as code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b092e-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b092e-106">Remarks</span></span>

<span data-ttu-id="b092e-107">Il `<c>` tag fornisce un modo per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.</span><span class="sxs-lookup"><span data-stu-id="b092e-107">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="b092e-108">Usare [\<code>](./code.md) per indicare più righe come codice.</span><span class="sxs-lookup"><span data-stu-id="b092e-108">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>

<span data-ttu-id="b092e-109">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="b092e-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="b092e-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="b092e-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a><span data-ttu-id="b092e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b092e-111">See also</span></span>

- [<span data-ttu-id="b092e-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b092e-112">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="b092e-113">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="b092e-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
