---
title: <paramref> - Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 42c428b74f0df9d4ca37e85d805db8012670521c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75696545"
---
# <a name="paramref-c-programming-guide"></a><span data-ttu-id="aea18-102">\<paramref> (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="aea18-102">\<paramref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="aea18-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aea18-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="aea18-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="aea18-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="aea18-105">Nome del parametro a cui fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="aea18-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="aea18-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="aea18-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aea18-107">Note</span><span class="sxs-lookup"><span data-stu-id="aea18-107">Remarks</span></span>  
 <span data-ttu-id="aea18-108">Il tag \<paramref> consente di indicare che una parola nei commenti del codice, ad esempio in un blocco \<summary> o \<remarks>, fa riferimento a un parametro.</span><span class="sxs-lookup"><span data-stu-id="aea18-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="aea18-109">È possibile elaborare il file XML in modo da formattare la parola in modo specifico, ad esempio in grassetto o in corsivo.</span><span class="sxs-lookup"><span data-stu-id="aea18-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>  
  
 <span data-ttu-id="aea18-110">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="aea18-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aea18-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="aea18-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]  
  
## <a name="see-also"></a><span data-ttu-id="aea18-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aea18-112">See also</span></span>

- [<span data-ttu-id="aea18-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="aea18-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="aea18-114">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="aea18-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
