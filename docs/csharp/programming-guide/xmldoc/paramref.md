---
title: '&lt;paramref&gt; (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- paramref
- <paramref>
dev_langs:
- CSharp
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 452701c4f70bf6cbc619064d62de552fa54bba65
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="ltparamrefgt-c-programming-guide"></a><span data-ttu-id="e65d8-102">&lt;paramref&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e65d8-102">&lt;paramref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="e65d8-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e65d8-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e65d8-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="e65d8-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="e65d8-105">Nome del parametro a cui fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="e65d8-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="e65d8-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="e65d8-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e65d8-107">Note</span><span class="sxs-lookup"><span data-stu-id="e65d8-107">Remarks</span></span>  
 <span data-ttu-id="e65d8-108">Il tag \<paramref> consente di indicare che una parola nei commenti del codice, ad esempio in un blocco \<summary> o \<remarks>, fa riferimento a un parametro.</span><span class="sxs-lookup"><span data-stu-id="e65d8-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="e65d8-109">È possibile elaborare il file XML in modo da formattare la parola in modo specifico, ad esempio in grassetto o in corsivo.</span><span class="sxs-lookup"><span data-stu-id="e65d8-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>  
  
 <span data-ttu-id="e65d8-110">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="e65d8-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e65d8-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="e65d8-111">Example</span></span>  
 <span data-ttu-id="e65d8-112">[!code-cs[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e65d8-112">[!code-cs[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e65d8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e65d8-113">See Also</span></span>  
 <span data-ttu-id="e65d8-114">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e65d8-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="e65d8-115">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="e65d8-115">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

