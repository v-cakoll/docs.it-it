---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 3c149b8ff60bcc2aba06856ad95f461fb18da4b6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352222"
---
# <a name="see-visual-basic"></a><span data-ttu-id="8f9fd-101">\<vedere > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f9fd-101">\<see> (Visual Basic)</span></span>
<span data-ttu-id="8f9fd-102">Specifica un collegamento a un altro membro.</span><span class="sxs-lookup"><span data-stu-id="8f9fd-102">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f9fd-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f9fd-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f9fd-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="8f9fd-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="8f9fd-105">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="8f9fd-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="8f9fd-106">Il compilatore verifica l'esistenza dell'elemento di codice specificato e passa `member` al nome dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="8f9fd-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="8f9fd-107">`member` deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="8f9fd-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f9fd-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8f9fd-108">Remarks</span></span>  
 <span data-ttu-id="8f9fd-109">Usare il tag `<see>` per specificare un collegamento dall'interno del testo.</span><span class="sxs-lookup"><span data-stu-id="8f9fd-109">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="8f9fd-110">Usare [\<> seealso](../../../visual-basic/language-reference/xmldoc/seealso.md) per indicare il testo che potrebbe essere necessario visualizzare in una sezione "vedere anche".</span><span class="sxs-lookup"><span data-stu-id="8f9fd-110">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="8f9fd-111">Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="8f9fd-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f9fd-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f9fd-112">Example</span></span>  
 <span data-ttu-id="8f9fd-113">Questo esempio usa il tag `<see>` nella sezione `UpdateRecord` osservazioni per fare riferimento al metodo `DoesRecordExist`.</span><span class="sxs-lookup"><span data-stu-id="8f9fd-113">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="8f9fd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f9fd-114">See also</span></span>

- [<span data-ttu-id="8f9fd-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="8f9fd-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
