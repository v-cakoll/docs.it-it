---
title: <paramref>- Guida alla programmazione in C
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 12df257271369dc7f0a5c066b712a8d8e6c38761
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793407"
---
# <a name="paramref-c-programming-guide"></a><span data-ttu-id="a4875-102">\<> paramref (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="a4875-102">\<paramref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="a4875-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4875-103">Syntax</span></span>

```xml
<paramref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="a4875-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4875-104">Parameters</span></span>

- `name`

  <span data-ttu-id="a4875-105">Nome del parametro a cui fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="a4875-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="a4875-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="a4875-106">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="a4875-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a4875-107">Remarks</span></span>

<span data-ttu-id="a4875-108">Il tag \<paramref> consente di indicare che una parola nei commenti del codice, ad esempio in un blocco \<summary> o \<remarks>, fa riferimento a un parametro.</span><span class="sxs-lookup"><span data-stu-id="a4875-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="a4875-109">È possibile elaborare il file XML in modo da formattare la parola in modo specifico, ad esempio in grassetto o in corsivo.</span><span class="sxs-lookup"><span data-stu-id="a4875-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>

<span data-ttu-id="a4875-110">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="a4875-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="a4875-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4875-111">Example</span></span>

[!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]

## <a name="see-also"></a><span data-ttu-id="a4875-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4875-112">See also</span></span>

- [<span data-ttu-id="a4875-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a4875-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a4875-114">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="a4875-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
