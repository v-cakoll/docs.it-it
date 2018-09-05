---
title: '&lt;la sezione Osservazioni&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 97fca8758d9c21ac0b8f15bf9d5831750fbabe77
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43746967"
---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="2b71c-102">&lt;la sezione Osservazioni&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b71c-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="2b71c-103">Specifica una sezione Osservazioni per il membro.</span><span class="sxs-lookup"><span data-stu-id="2b71c-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b71c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b71c-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b71c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2b71c-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="2b71c-106">Descrizione del membro.</span><span class="sxs-lookup"><span data-stu-id="2b71c-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b71c-107">Note</span><span class="sxs-lookup"><span data-stu-id="2b71c-107">Remarks</span></span>  
 <span data-ttu-id="2b71c-108">Usare la `<remarks>` tag per aggiungere informazioni su un tipo, integrando le informazioni specificate con [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="2b71c-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="2b71c-109">Queste informazioni vengono visualizzate nel Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="2b71c-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="2b71c-110">Per informazioni sul Visualizzatore oggetti, vedere [visualizzazione della struttura del codice](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="2b71c-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="2b71c-111">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="2b71c-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b71c-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b71c-112">Example</span></span>  
 <span data-ttu-id="2b71c-113">Questo esempio Usa il `<remarks>` tag per illustrare i valori di `UpdateRecord` metodo.</span><span class="sxs-lookup"><span data-stu-id="2b71c-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2b71c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b71c-114">See Also</span></span>  
 [<span data-ttu-id="2b71c-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="2b71c-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
