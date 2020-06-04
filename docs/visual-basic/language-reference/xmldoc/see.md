---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 380923c2313450afc5745b25eeea6a444705dd3f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411525"
---
# <a name="see-visual-basic"></a><span data-ttu-id="4ee64-101">\<see> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ee64-101">\<see> (Visual Basic)</span></span>
<span data-ttu-id="4ee64-102">Specifica un collegamento a un altro membro.</span><span class="sxs-lookup"><span data-stu-id="4ee64-102">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ee64-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ee64-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ee64-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="4ee64-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="4ee64-105">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="4ee64-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="4ee64-106">Il compilatore verifica l'esistenza dell'elemento di codice specificato e passa `member` al nome dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="4ee64-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="4ee64-107">`member` deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="4ee64-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ee64-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="4ee64-108">Remarks</span></span>  
 <span data-ttu-id="4ee64-109">Usare il `<see>` tag per specificare un collegamento dall'interno del testo.</span><span class="sxs-lookup"><span data-stu-id="4ee64-109">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="4ee64-110">Usare [\<seealso>](seealso.md) per indicare il testo che potrebbe essere necessario visualizzare in una sezione "vedere anche".</span><span class="sxs-lookup"><span data-stu-id="4ee64-110">Use [\<seealso>](seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="4ee64-111">Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="4ee64-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ee64-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ee64-112">Example</span></span>  
 <span data-ttu-id="4ee64-113">Questo esempio usa il `<see>` tag nella `UpdateRecord` sezione Note per fare riferimento al `DoesRecordExist` metodo.</span><span class="sxs-lookup"><span data-stu-id="4ee64-113">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="4ee64-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ee64-114">See also</span></span>

- [<span data-ttu-id="4ee64-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="4ee64-115">XML Comment Tags</span></span>](index.md)
