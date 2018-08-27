---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 06c6899895f278fdf652725a05ecc7229805f4d4
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935358"
---
# <a name="ltcgt-visual-basic"></a><span data-ttu-id="4f197-102">&lt;c&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f197-102">&lt;c&gt; (Visual Basic)</span></span>
<span data-ttu-id="4f197-103">Indica che il testo all'interno di una descrizione è codice.</span><span class="sxs-lookup"><span data-stu-id="4f197-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f197-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f197-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f197-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f197-105">Parameters</span></span>  
  
|<span data-ttu-id="4f197-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="4f197-106">Parameter</span></span>|<span data-ttu-id="4f197-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f197-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="4f197-108">Il testo che si desidera indicare come codice.</span><span class="sxs-lookup"><span data-stu-id="4f197-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f197-109">Note</span><span class="sxs-lookup"><span data-stu-id="4f197-109">Remarks</span></span>  
 <span data-ttu-id="4f197-110">Il `<c>` tag offre un modo per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.</span><span class="sxs-lookup"><span data-stu-id="4f197-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="4f197-111">Usare [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) per indicare più righe come codice.</span><span class="sxs-lookup"><span data-stu-id="4f197-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="4f197-112">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="4f197-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f197-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f197-113">Example</span></span>  
 <span data-ttu-id="4f197-114">Questo esempio Usa la `<c>` tag nella sezione di riepilogo per indicare che `Counter` è codice.</span><span class="sxs-lookup"><span data-stu-id="4f197-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4f197-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f197-115">See Also</span></span>  
 [<span data-ttu-id="4f197-116">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="4f197-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
