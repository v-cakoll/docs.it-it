---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: aa65fed863718f1f00b510f82051a13e764e1b23
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400144"
---
# <a name="code-visual-basic"></a><span data-ttu-id="504e0-101">\<code> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="504e0-101">\<code> (Visual Basic)</span></span>
<span data-ttu-id="504e0-102">Indica che il testo è costituito da più righe di codice.</span><span class="sxs-lookup"><span data-stu-id="504e0-102">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="504e0-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="504e0-103">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="504e0-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="504e0-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="504e0-105">Testo da contrassegnare come codice.</span><span class="sxs-lookup"><span data-stu-id="504e0-105">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="504e0-106">Commenti</span><span class="sxs-lookup"><span data-stu-id="504e0-106">Remarks</span></span>  
 <span data-ttu-id="504e0-107">Usare il `<code>` tag per indicare più righe come codice.</span><span class="sxs-lookup"><span data-stu-id="504e0-107">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="504e0-108">Usare [\<c>](c.md) per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.</span><span class="sxs-lookup"><span data-stu-id="504e0-108">Use [\<c>](c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="504e0-109">Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="504e0-109">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="504e0-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="504e0-110">Example</span></span>  
 <span data-ttu-id="504e0-111">Questo esempio usa il \<code> tag per includere il codice di esempio per l'uso del `ID` campo.</span><span class="sxs-lookup"><span data-stu-id="504e0-111">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="504e0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="504e0-112">See also</span></span>

- [<span data-ttu-id="504e0-113">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="504e0-113">XML Comment Tags</span></span>](index.md)
