---
title: <typeparamref> - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 451f101a3002a9590bdf616b01c6c8bab27efd69
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523318"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="3034a-102">\<typeparamref> (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="3034a-102">\<typeparamref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="3034a-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3034a-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="3034a-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="3034a-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="3034a-105">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="3034a-105">The name of the type parameter.</span></span> <span data-ttu-id="3034a-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="3034a-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3034a-107">Note</span><span class="sxs-lookup"><span data-stu-id="3034a-107">Remarks</span></span>  
 <span data-ttu-id="3034a-108">Per altre informazioni sui parametri di tipo in tipi e metodi generici, vedere [Generics](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="3034a-108">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>  
  
 <span data-ttu-id="3034a-109">Usare questo tag per consentire ai consumer del file di documentazione di formattare la parola in un modo specifico, ad esempio in corsivo.</span><span class="sxs-lookup"><span data-stu-id="3034a-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="3034a-110">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="3034a-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3034a-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="3034a-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="3034a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3034a-112">See also</span></span>

- [<span data-ttu-id="3034a-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3034a-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3034a-114">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="3034a-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
