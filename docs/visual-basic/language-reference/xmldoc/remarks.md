---
title: <remarks> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 38549b2fcce0740b2b9cfd42d950e56b343e7a30
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524671"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="c68dc-102">\<remarks > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c68dc-102">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="c68dc-103">Specifica una sezione di osservazioni per il membro.</span><span class="sxs-lookup"><span data-stu-id="c68dc-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c68dc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c68dc-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c68dc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c68dc-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="c68dc-106">Descrizione del membro.</span><span class="sxs-lookup"><span data-stu-id="c68dc-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c68dc-107">Note</span><span class="sxs-lookup"><span data-stu-id="c68dc-107">Remarks</span></span>  
 <span data-ttu-id="c68dc-108">Usare il tag `<remarks>` per aggiungere informazioni su un tipo, integrando le informazioni specificate con [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="c68dc-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="c68dc-109">Queste informazioni vengono visualizzate nel Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="c68dc-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="c68dc-110">Per informazioni sulla Visualizzatore oggetti, vedere [visualizzazione della struttura del codice](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="c68dc-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="c68dc-111">Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="c68dc-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c68dc-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="c68dc-112">Example</span></span>  
 <span data-ttu-id="c68dc-113">Questo esempio usa il tag `<remarks>` per illustrare il funzionamento del metodo `UpdateRecord`.</span><span class="sxs-lookup"><span data-stu-id="c68dc-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="c68dc-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c68dc-114">See also</span></span>

- [<span data-ttu-id="c68dc-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="c68dc-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
