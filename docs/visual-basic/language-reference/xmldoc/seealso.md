---
title: '&lt;seealso&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: a792bbea108bcdf33d430c47773466ef3dccdb0c
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2018
ms.locfileid: "47862146"
---
# <a name="ltseealsogt-visual-basic"></a><span data-ttu-id="5d8cc-102">&lt;seealso&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d8cc-102">&lt;seealso&gt; (Visual Basic)</span></span>
<span data-ttu-id="5d8cc-103">Specifica un collegamento che viene visualizzato nella sezione Vedere anche.</span><span class="sxs-lookup"><span data-stu-id="5d8cc-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d8cc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d8cc-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d8cc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5d8cc-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="5d8cc-106">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="5d8cc-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="5d8cc-107">Il compilatore controlla che l'elemento di codice specificato esista e passa `member` al nome dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="5d8cc-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="5d8cc-108">`member` deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="5d8cc-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d8cc-109">Note</span><span class="sxs-lookup"><span data-stu-id="5d8cc-109">Remarks</span></span>  
 <span data-ttu-id="5d8cc-110">Usare il `<seealso>` tag per specificare il testo che si desidera visualizzare in una sezione Vedere anche.</span><span class="sxs-lookup"><span data-stu-id="5d8cc-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="5d8cc-111">Usare [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) per specificare un collegamento nel testo.</span><span class="sxs-lookup"><span data-stu-id="5d8cc-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="5d8cc-112">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="5d8cc-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d8cc-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="5d8cc-113">Example</span></span>  
 <span data-ttu-id="5d8cc-114">Questo esempio Usa la `<seealso>` contrassegnare nel `DoesRecordExist` per fare riferimento alla sezione relativa alle osservazioni di `UpdateRecord` (metodo).</span><span class="sxs-lookup"><span data-stu-id="5d8cc-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5d8cc-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d8cc-115">See Also</span></span>  
 [<span data-ttu-id="5d8cc-116">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="5d8cc-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
