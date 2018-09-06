---
title: '&lt;la sezione Osservazioni&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 97fca8758d9c21ac0b8f15bf9d5831750fbabe77
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863033"
---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="a7ec1-102">&lt;la sezione Osservazioni&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7ec1-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="a7ec1-103">Specifica una sezione Osservazioni per il membro.</span><span class="sxs-lookup"><span data-stu-id="a7ec1-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ec1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7ec1-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7ec1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a7ec1-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="a7ec1-106">Descrizione del membro.</span><span class="sxs-lookup"><span data-stu-id="a7ec1-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7ec1-107">Note</span><span class="sxs-lookup"><span data-stu-id="a7ec1-107">Remarks</span></span>  
 <span data-ttu-id="a7ec1-108">Usare la `<remarks>` tag per aggiungere informazioni su un tipo, integrando le informazioni specificate con [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="a7ec1-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="a7ec1-109">Queste informazioni vengono visualizzate nel Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="a7ec1-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="a7ec1-110">Per informazioni sul Visualizzatore oggetti, vedere [visualizzazione della struttura del codice](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="a7ec1-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="a7ec1-111">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="a7ec1-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7ec1-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="a7ec1-112">Example</span></span>  
 <span data-ttu-id="a7ec1-113">Questo esempio Usa il `<remarks>` tag per illustrare i valori di `UpdateRecord` metodo.</span><span class="sxs-lookup"><span data-stu-id="a7ec1-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a7ec1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7ec1-114">See Also</span></span>  
 [<span data-ttu-id="a7ec1-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="a7ec1-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
