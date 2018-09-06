---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 06c6899895f278fdf652725a05ecc7229805f4d4
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43854730"
---
# <a name="ltcgt-visual-basic"></a><span data-ttu-id="1636f-102">&lt;c&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1636f-102">&lt;c&gt; (Visual Basic)</span></span>
<span data-ttu-id="1636f-103">Indica che il testo all'interno di una descrizione è codice.</span><span class="sxs-lookup"><span data-stu-id="1636f-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1636f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1636f-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1636f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1636f-105">Parameters</span></span>  
  
|<span data-ttu-id="1636f-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="1636f-106">Parameter</span></span>|<span data-ttu-id="1636f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1636f-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="1636f-108">Il testo che si desidera indicare come codice.</span><span class="sxs-lookup"><span data-stu-id="1636f-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1636f-109">Note</span><span class="sxs-lookup"><span data-stu-id="1636f-109">Remarks</span></span>  
 <span data-ttu-id="1636f-110">Il `<c>` tag offre un modo per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.</span><span class="sxs-lookup"><span data-stu-id="1636f-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="1636f-111">Usare [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) per indicare più righe come codice.</span><span class="sxs-lookup"><span data-stu-id="1636f-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="1636f-112">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="1636f-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1636f-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="1636f-113">Example</span></span>  
 <span data-ttu-id="1636f-114">Questo esempio Usa la `<c>` tag nella sezione di riepilogo per indicare che `Counter` è codice.</span><span class="sxs-lookup"><span data-stu-id="1636f-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1636f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1636f-115">See Also</span></span>  
 [<span data-ttu-id="1636f-116">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="1636f-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
