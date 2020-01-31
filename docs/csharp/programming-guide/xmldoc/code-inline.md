---
title: Guida alla C# programmazione di <c>
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
ms.openlocfilehash: d5b28ee6db52d191f8454592d792ac0a1e1dc73b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793460"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="22744-102">> di \<cC# (Guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="22744-102">\<c> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="22744-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22744-103">Syntax</span></span>

```xml
<c>text</c>
```

## <a name="parameters"></a><span data-ttu-id="22744-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="22744-104">Parameters</span></span>

- `text`

  <span data-ttu-id="22744-105">Il testo che si desidera indicare come codice.</span><span class="sxs-lookup"><span data-stu-id="22744-105">The text you would like to indicate as code.</span></span>

## <a name="remarks"></a><span data-ttu-id="22744-106">Note</span><span class="sxs-lookup"><span data-stu-id="22744-106">Remarks</span></span>

<span data-ttu-id="22744-107">Il tag \<c> consente di indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.</span><span class="sxs-lookup"><span data-stu-id="22744-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="22744-108">Usare [\<code>](./code.md) per indicare più righe come codice.</span><span class="sxs-lookup"><span data-stu-id="22744-108">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>

<span data-ttu-id="22744-109">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="22744-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="22744-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="22744-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a><span data-ttu-id="22744-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22744-111">See also</span></span>

- [<span data-ttu-id="22744-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="22744-112">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="22744-113">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="22744-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
