---
title: <seealso>
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 5999a4ebcc90f21ee8331b96ffb2a50f7905b1b6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411512"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="64d94-101">\<seealso> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64d94-101">\<seealso> (Visual Basic)</span></span>
<span data-ttu-id="64d94-102">Specifica un collegamento visualizzato nella sezione vedere anche.</span><span class="sxs-lookup"><span data-stu-id="64d94-102">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64d94-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64d94-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="64d94-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="64d94-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="64d94-105">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="64d94-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="64d94-106">Il compilatore verifica l'esistenza dell'elemento di codice specificato e passa `member` al nome dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="64d94-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="64d94-107">`member` deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="64d94-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64d94-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="64d94-108">Remarks</span></span>  
 <span data-ttu-id="64d94-109">Usare il `<seealso>` tag per specificare il testo che si vuole visualizzare in una sezione vedere anche.</span><span class="sxs-lookup"><span data-stu-id="64d94-109">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="64d94-110">Usare [\<see>](see.md) per specificare un collegamento dall'interno del testo.</span><span class="sxs-lookup"><span data-stu-id="64d94-110">Use [\<see>](see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="64d94-111">Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="64d94-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64d94-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="64d94-112">Example</span></span>  
 <span data-ttu-id="64d94-113">Questo esempio usa il `<seealso>` tag nella `DoesRecordExist` sezione Note per fare riferimento al `UpdateRecord` metodo.</span><span class="sxs-lookup"><span data-stu-id="64d94-113">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="64d94-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64d94-114">See also</span></span>

- [<span data-ttu-id="64d94-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="64d94-115">XML Comment Tags</span></span>](index.md)
