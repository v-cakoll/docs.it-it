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
ms.openlocfilehash: 834aff6e4673a306559daa1b9517e11538e90ad0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273348"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="2b66d-102">\<typeparamref> (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="2b66d-102">\<typeparamref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="2b66d-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b66d-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b66d-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="2b66d-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="2b66d-105">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="2b66d-105">The name of the type parameter.</span></span> <span data-ttu-id="2b66d-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="2b66d-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b66d-107">Note</span><span class="sxs-lookup"><span data-stu-id="2b66d-107">Remarks</span></span>  
 <span data-ttu-id="2b66d-108">Per altre informazioni sui parametri di tipo in tipi e metodi generici, vedere [Generics](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="2b66d-108">For more information on type parameters in generic types and methods, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="2b66d-109">Usare questo tag per consentire ai consumer del file di documentazione di formattare la parola in un modo specifico, ad esempio in corsivo.</span><span class="sxs-lookup"><span data-stu-id="2b66d-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="2b66d-110">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="2b66d-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b66d-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b66d-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2b66d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b66d-112">See also</span></span>

- [<span data-ttu-id="2b66d-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2b66d-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2b66d-114">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="2b66d-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
