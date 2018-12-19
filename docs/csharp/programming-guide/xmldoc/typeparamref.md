---
title: '&lt;typeparamref&gt; - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: bbe9bed5a32e463424b98f4066e95374401931e2
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243920"
---
# <a name="lttypeparamrefgt-c-programming-guide"></a><span data-ttu-id="6d21e-102">&lt;typeparamref&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="6d21e-102">&lt;typeparamref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="6d21e-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d21e-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d21e-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="6d21e-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="6d21e-105">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="6d21e-105">The name of the type parameter.</span></span> <span data-ttu-id="6d21e-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="6d21e-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d21e-107">Note</span><span class="sxs-lookup"><span data-stu-id="6d21e-107">Remarks</span></span>  
 <span data-ttu-id="6d21e-108">Per altre informazioni sui parametri di tipo in tipi e metodi generici, vedere [Generics](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="6d21e-108">For more information on type parameters in generic types and methods, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="6d21e-109">Usare questo tag per consentire ai consumer del file di documentazione di formattare la parola in un modo specifico, ad esempio in corsivo.</span><span class="sxs-lookup"><span data-stu-id="6d21e-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="6d21e-110">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="6d21e-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d21e-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d21e-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6d21e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d21e-112">See Also</span></span>

- [<span data-ttu-id="6d21e-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="6d21e-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6d21e-114">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="6d21e-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
