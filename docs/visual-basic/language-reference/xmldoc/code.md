---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: 1cbac2162bd39cdc8af9a55dfd6e2f90bc40b08a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354315"
---
# <a name="code-visual-basic"></a><span data-ttu-id="81482-101">> del codice \<(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81482-101">\<code> (Visual Basic)</span></span>
<span data-ttu-id="81482-102">Indica che il testo è costituito da più righe di codice.</span><span class="sxs-lookup"><span data-stu-id="81482-102">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81482-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81482-103">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="81482-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="81482-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="81482-105">Testo da contrassegnare come codice.</span><span class="sxs-lookup"><span data-stu-id="81482-105">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81482-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="81482-106">Remarks</span></span>  
 <span data-ttu-id="81482-107">Usare il tag `<code>` per indicare più righe come codice.</span><span class="sxs-lookup"><span data-stu-id="81482-107">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="81482-108">Usare [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.</span><span class="sxs-lookup"><span data-stu-id="81482-108">Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="81482-109">Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="81482-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81482-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="81482-110">Example</span></span>  
 <span data-ttu-id="81482-111">Questo esempio usa il tag \<code > per includere il codice di esempio per l'uso del campo `ID`.</span><span class="sxs-lookup"><span data-stu-id="81482-111">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="81482-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81482-112">See also</span></span>

- [<span data-ttu-id="81482-113">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="81482-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
