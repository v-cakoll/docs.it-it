---
title: <paramref> - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: e6d6c62c97179d74bdb6bdd88eeb1ee129226fed
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201404"
---
# <a name="paramref-c-programming-guide"></a><span data-ttu-id="d873a-102">\<paramref> (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d873a-102">\<paramref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="d873a-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d873a-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d873a-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="d873a-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d873a-105">Nome del parametro a cui fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="d873a-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="d873a-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="d873a-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d873a-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d873a-107">Remarks</span></span>  
 <span data-ttu-id="d873a-108">Il tag \<paramref> consente di indicare che una parola nei commenti del codice, ad esempio in un blocco \<summary> o \<remarks>, fa riferimento a un parametro.</span><span class="sxs-lookup"><span data-stu-id="d873a-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="d873a-109">È possibile elaborare il file XML in modo da formattare la parola in modo specifico, ad esempio in grassetto o in corsivo.</span><span class="sxs-lookup"><span data-stu-id="d873a-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>  
  
 <span data-ttu-id="d873a-110">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="d873a-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d873a-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="d873a-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]  
  
## <a name="see-also"></a><span data-ttu-id="d873a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d873a-112">See also</span></span>

- [<span data-ttu-id="d873a-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d873a-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d873a-114">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="d873a-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
