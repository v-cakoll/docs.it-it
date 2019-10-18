---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 4ea19ed5330dcbb8fcd84708d1546a81d909b04e
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523933"
---
# <a name="c-visual-basic"></a><span data-ttu-id="6e5dd-102">\<c > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e5dd-102">\<c> (Visual Basic)</span></span>
<span data-ttu-id="6e5dd-103">Indica che il testo all'interno di una descrizione è codice.</span><span class="sxs-lookup"><span data-stu-id="6e5dd-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e5dd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e5dd-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e5dd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6e5dd-105">Parameters</span></span>  
  
|<span data-ttu-id="6e5dd-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="6e5dd-106">Parameter</span></span>|<span data-ttu-id="6e5dd-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e5dd-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="6e5dd-108">Il testo che si desidera indicare come codice.</span><span class="sxs-lookup"><span data-stu-id="6e5dd-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e5dd-109">Note</span><span class="sxs-lookup"><span data-stu-id="6e5dd-109">Remarks</span></span>  
 <span data-ttu-id="6e5dd-110">Il tag `<c>` fornisce un modo per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.</span><span class="sxs-lookup"><span data-stu-id="6e5dd-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="6e5dd-111">Usare [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) per indicare più righe come codice.</span><span class="sxs-lookup"><span data-stu-id="6e5dd-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="6e5dd-112">Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="6e5dd-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e5dd-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e5dd-113">Example</span></span>  
 <span data-ttu-id="6e5dd-114">Questo esempio usa il tag `<c>` nella sezione Summary per indicare che `Counter` è il codice.</span><span class="sxs-lookup"><span data-stu-id="6e5dd-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6e5dd-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e5dd-115">See also</span></span>

- [<span data-ttu-id="6e5dd-116">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="6e5dd-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
