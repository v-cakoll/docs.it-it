---
title: '&lt;vedere&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 78311651593d3d4a47c723f64a9a74d4660f7c90
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43854905"
---
# <a name="ltseegt-visual-basic"></a><span data-ttu-id="bd749-102">&lt;vedere&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd749-102">&lt;see&gt; (Visual Basic)</span></span>
<span data-ttu-id="bd749-103">Specifica un collegamento a un altro membro.</span><span class="sxs-lookup"><span data-stu-id="bd749-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd749-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd749-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd749-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bd749-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="bd749-106">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="bd749-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="bd749-107">Il compilatore controlla che l'elemento di codice specificato esista e passa `member` al nome dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="bd749-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="bd749-108">`member` deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="bd749-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd749-109">Note</span><span class="sxs-lookup"><span data-stu-id="bd749-109">Remarks</span></span>  
 <span data-ttu-id="bd749-110">Usare il `<see>` tag per specificare un collegamento nel testo.</span><span class="sxs-lookup"><span data-stu-id="bd749-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="bd749-111">Uso [ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) per indicare il testo che è possibile visualizzare in una sezione "Vedere anche".</span><span class="sxs-lookup"><span data-stu-id="bd749-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="bd749-112">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="bd749-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd749-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="bd749-113">Example</span></span>  
 <span data-ttu-id="bd749-114">Questo esempio Usa la `<see>` contrassegnare nel `UpdateRecord` per fare riferimento alla sezione relativa alle osservazioni di `DoesRecordExist` (metodo).</span><span class="sxs-lookup"><span data-stu-id="bd749-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bd749-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd749-115">See Also</span></span>  
 [<span data-ttu-id="bd749-116">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="bd749-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
