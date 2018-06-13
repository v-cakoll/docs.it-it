---
title: '&lt;paramref&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 763e311dfb46ceeed358c3b3bebd6212d3e2489c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598662"
---
# <a name="ltparamrefgt-visual-basic"></a><span data-ttu-id="d2f03-102">&lt;paramref&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2f03-102">&lt;paramref&gt; (Visual Basic)</span></span>
<span data-ttu-id="d2f03-103">Formatta una parola come parametro.</span><span class="sxs-lookup"><span data-stu-id="d2f03-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2f03-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2f03-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2f03-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d2f03-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d2f03-106">Nome del parametro a cui fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="d2f03-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="d2f03-107">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="d2f03-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2f03-108">Note</span><span class="sxs-lookup"><span data-stu-id="d2f03-108">Remarks</span></span>  
 <span data-ttu-id="d2f03-109">Il `<paramref>` tag offre un modo per indicare che una parola è un parametro.</span><span class="sxs-lookup"><span data-stu-id="d2f03-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="d2f03-110">Il file XML può essere elaborato per formattare questo parametro in modo specifico.</span><span class="sxs-lookup"><span data-stu-id="d2f03-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="d2f03-111">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="d2f03-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2f03-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="d2f03-112">Example</span></span>  
 <span data-ttu-id="d2f03-113">Questo esempio viene utilizzato il `<paramref>` tag per fare riferimento al `id` parametro.</span><span class="sxs-lookup"><span data-stu-id="d2f03-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/paramref_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d2f03-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2f03-114">See Also</span></span>  
 [<span data-ttu-id="d2f03-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="d2f03-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
