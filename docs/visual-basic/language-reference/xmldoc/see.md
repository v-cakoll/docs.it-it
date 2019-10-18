---
title: <see> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: e3ae5fb63540e47e5b8da2e2d60d5bd736e019d7
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524665"
---
# <a name="see-visual-basic"></a><span data-ttu-id="ad4cb-102">\<see > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad4cb-102">\<see> (Visual Basic)</span></span>
<span data-ttu-id="ad4cb-103">Specifica un collegamento a un altro membro.</span><span class="sxs-lookup"><span data-stu-id="ad4cb-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad4cb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad4cb-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad4cb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ad4cb-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="ad4cb-106">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="ad4cb-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="ad4cb-107">Il compilatore verifica l'esistenza dell'elemento di codice specificato e passa `member` al nome dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="ad4cb-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="ad4cb-108">`member` deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="ad4cb-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad4cb-109">Note</span><span class="sxs-lookup"><span data-stu-id="ad4cb-109">Remarks</span></span>  
 <span data-ttu-id="ad4cb-110">Usare il tag `<see>` per specificare un collegamento dall'interno del testo.</span><span class="sxs-lookup"><span data-stu-id="ad4cb-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="ad4cb-111">Usare [\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) per indicare il testo che potrebbe essere necessario visualizzare in una sezione "vedere anche".</span><span class="sxs-lookup"><span data-stu-id="ad4cb-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="ad4cb-112">Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="ad4cb-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad4cb-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad4cb-113">Example</span></span>  
 <span data-ttu-id="ad4cb-114">Questo esempio usa il tag `<see>` nella sezione `UpdateRecord` osservazioni per fare riferimento al metodo `DoesRecordExist`.</span><span class="sxs-lookup"><span data-stu-id="ad4cb-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ad4cb-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad4cb-115">See also</span></span>

- [<span data-ttu-id="ad4cb-116">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="ad4cb-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
