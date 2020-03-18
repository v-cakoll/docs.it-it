---
title: <typeparamref>- Guida alla programmazione in C
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 266eadad322fd3c4167c7a911cb57ef1e1333012
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789655"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="4320f-102">\<> di typeparamref (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="4320f-102">\<typeparamref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="4320f-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4320f-103">Syntax</span></span>

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="4320f-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="4320f-104">Parameters</span></span>

- `name`

  <span data-ttu-id="4320f-105">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="4320f-105">The name of the type parameter.</span></span> <span data-ttu-id="4320f-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="4320f-106">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="4320f-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4320f-107">Remarks</span></span>

<span data-ttu-id="4320f-108">Per altre informazioni sui parametri di tipo in tipi e metodi generici, vedere [Generics](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="4320f-108">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="4320f-109">Usare questo tag per consentire ai consumer del file di documentazione di formattare la parola in un modo specifico, ad esempio in corsivo.</span><span class="sxs-lookup"><span data-stu-id="4320f-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>

<span data-ttu-id="4320f-110">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="4320f-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="4320f-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="4320f-111">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="4320f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4320f-112">See also</span></span>

- [<span data-ttu-id="4320f-113">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="4320f-113">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="4320f-114">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="4320f-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
