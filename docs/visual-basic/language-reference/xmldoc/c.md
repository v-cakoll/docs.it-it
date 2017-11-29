---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e57cae8fd4b93fee59992d717135ad7d3d78be5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltcgt-visual-basic"></a><span data-ttu-id="acad2-102">&lt;c&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acad2-102">&lt;c&gt; (Visual Basic)</span></span>
<span data-ttu-id="acad2-103">Indica che il testo all'interno di una descrizione è codice.</span><span class="sxs-lookup"><span data-stu-id="acad2-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acad2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="acad2-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="acad2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="acad2-105">Parameters</span></span>  
  
|<span data-ttu-id="acad2-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="acad2-106">Parameter</span></span>|<span data-ttu-id="acad2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="acad2-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="acad2-108">Il testo che si desidera indicare come codice.</span><span class="sxs-lookup"><span data-stu-id="acad2-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acad2-109">Note</span><span class="sxs-lookup"><span data-stu-id="acad2-109">Remarks</span></span>  
 <span data-ttu-id="acad2-110">Il `<c>` tag offre un modo per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.</span><span class="sxs-lookup"><span data-stu-id="acad2-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="acad2-111">Usare [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) per indicare più righe come codice.</span><span class="sxs-lookup"><span data-stu-id="acad2-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="acad2-112">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="acad2-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acad2-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="acad2-113">Example</span></span>  
 <span data-ttu-id="acad2-114">Questo esempio viene utilizzato il `<c>` tag nella sezione di riepilogo per indicare che `Counter` è codice.</span><span class="sxs-lookup"><span data-stu-id="acad2-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="acad2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acad2-115">See Also</span></span>  
 [<span data-ttu-id="acad2-116">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="acad2-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
