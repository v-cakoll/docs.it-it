---
title: <example> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 8d1c2a958fa148238eaeedb9c2af3df2cb86d33d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502605"
---
# <a name="example-visual-basic"></a><span data-ttu-id="fc046-102">\<example> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc046-102">\<example> (Visual Basic)</span></span>
<span data-ttu-id="fc046-103">Specifica un esempio per il membro.</span><span class="sxs-lookup"><span data-stu-id="fc046-103">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc046-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc046-104">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc046-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc046-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="fc046-106">Descrizione dell'esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="fc046-106">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc046-107">Note</span><span class="sxs-lookup"><span data-stu-id="fc046-107">Remarks</span></span>  
 <span data-ttu-id="fc046-108">Il `<example>` tag consente di specificare un esempio di come usare un metodo o un altro membro della raccolta.</span><span class="sxs-lookup"><span data-stu-id="fc046-108">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="fc046-109">In genere comporta l'uso del tag [\<code>](../../../visual-basic/language-reference/xmldoc/code.md).</span><span class="sxs-lookup"><span data-stu-id="fc046-109">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="fc046-110">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="fc046-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc046-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc046-111">Example</span></span>  
 <span data-ttu-id="fc046-112">Questo esempio Usa il `<example>` tag per includere un esempio dell'uso di `ID` campo.</span><span class="sxs-lookup"><span data-stu-id="fc046-112">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="fc046-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc046-113">See also</span></span>
- [<span data-ttu-id="fc046-114">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="fc046-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
