---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: d8efd2359ecb65bec1b427d8b1dca4b0c88a1152
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469027"
---
# <a name="c-visual-basic"></a><span data-ttu-id="1aa8c-102">\<c> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1aa8c-102">\<c> (Visual Basic)</span></span>
<span data-ttu-id="1aa8c-103">Indica che il testo all'interno di una descrizione è codice.</span><span class="sxs-lookup"><span data-stu-id="1aa8c-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aa8c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1aa8c-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="1aa8c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1aa8c-105">Parameters</span></span>  
  
|<span data-ttu-id="1aa8c-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="1aa8c-106">Parameter</span></span>|<span data-ttu-id="1aa8c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1aa8c-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="1aa8c-108">Il testo che si desidera indicare come codice.</span><span class="sxs-lookup"><span data-stu-id="1aa8c-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1aa8c-109">Note</span><span class="sxs-lookup"><span data-stu-id="1aa8c-109">Remarks</span></span>  
 <span data-ttu-id="1aa8c-110">Il `<c>` tag offre un modo per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.</span><span class="sxs-lookup"><span data-stu-id="1aa8c-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="1aa8c-111">Usare [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) per indicare più righe come codice.</span><span class="sxs-lookup"><span data-stu-id="1aa8c-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="1aa8c-112">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="1aa8c-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1aa8c-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="1aa8c-113">Example</span></span>  
 <span data-ttu-id="1aa8c-114">Questo esempio Usa la `<c>` tag nella sezione di riepilogo per indicare che `Counter` è codice.</span><span class="sxs-lookup"><span data-stu-id="1aa8c-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1aa8c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1aa8c-115">See also</span></span>
- [<span data-ttu-id="1aa8c-116">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="1aa8c-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
