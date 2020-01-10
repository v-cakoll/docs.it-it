---
title: <typeparamref> - Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 3e96d55d7cf60b2a9085cf065ef3b8193b173c5d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711675"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="bddc9-102">\<typeparamref> (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="bddc9-102">\<typeparamref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="bddc9-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bddc9-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="bddc9-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="bddc9-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="bddc9-105">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="bddc9-105">The name of the type parameter.</span></span> <span data-ttu-id="bddc9-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="bddc9-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bddc9-107">Note</span><span class="sxs-lookup"><span data-stu-id="bddc9-107">Remarks</span></span>  
 <span data-ttu-id="bddc9-108">Per altre informazioni sui parametri di tipo in tipi e metodi generici, vedere [Generics](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="bddc9-108">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>  
  
 <span data-ttu-id="bddc9-109">Usare questo tag per consentire ai consumer del file di documentazione di formattare la parola in un modo specifico, ad esempio in corsivo.</span><span class="sxs-lookup"><span data-stu-id="bddc9-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="bddc9-110">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="bddc9-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bddc9-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="bddc9-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="bddc9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bddc9-112">See also</span></span>

- [<span data-ttu-id="bddc9-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="bddc9-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bddc9-114">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="bddc9-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
