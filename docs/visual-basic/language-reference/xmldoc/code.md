---
title: <code> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d4e887e3bbbc01e4cef5278f67b8c4afe273bf28
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524029"
---
# <a name="code-visual-basic"></a><span data-ttu-id="e4d75-101">\<code > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4d75-101">\<code> (Visual Basic)</span></span>
<span data-ttu-id="e4d75-102">Indica che il testo è costituito da più righe di codice.</span><span class="sxs-lookup"><span data-stu-id="e4d75-102">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4d75-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4d75-103">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4d75-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="e4d75-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="e4d75-105">Testo da contrassegnare come codice.</span><span class="sxs-lookup"><span data-stu-id="e4d75-105">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4d75-106">Note</span><span class="sxs-lookup"><span data-stu-id="e4d75-106">Remarks</span></span>  
 <span data-ttu-id="e4d75-107">Usare il tag `<code>` per indicare più righe come codice.</span><span class="sxs-lookup"><span data-stu-id="e4d75-107">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="e4d75-108">Usare [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.</span><span class="sxs-lookup"><span data-stu-id="e4d75-108">Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="e4d75-109">Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="e4d75-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4d75-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="e4d75-110">Example</span></span>  
 <span data-ttu-id="e4d75-111">Questo esempio usa il tag \<code > per includere il codice di esempio per l'uso del campo `ID`.</span><span class="sxs-lookup"><span data-stu-id="e4d75-111">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e4d75-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4d75-112">See also</span></span>

- [<span data-ttu-id="e4d75-113">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="e4d75-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
