---
title: <remarks> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: c5c088472ae09a416953d9c0829cad1cb48646b8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833490"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="c72ff-102">\<remarks> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c72ff-102">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="c72ff-103">Specifica una sezione Osservazioni per il membro.</span><span class="sxs-lookup"><span data-stu-id="c72ff-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c72ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c72ff-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c72ff-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c72ff-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="c72ff-106">Descrizione del membro.</span><span class="sxs-lookup"><span data-stu-id="c72ff-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c72ff-107">Note</span><span class="sxs-lookup"><span data-stu-id="c72ff-107">Remarks</span></span>  
 <span data-ttu-id="c72ff-108">Usare la `<remarks>` tag per aggiungere informazioni su un tipo, integrando le informazioni specificate con [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="c72ff-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="c72ff-109">Queste informazioni vengono visualizzate nel Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="c72ff-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="c72ff-110">Per informazioni sul Visualizzatore oggetti, vedere [visualizzazione della struttura del codice](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="c72ff-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="c72ff-111">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="c72ff-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c72ff-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="c72ff-112">Example</span></span>  
 <span data-ttu-id="c72ff-113">Questo esempio Usa il `<remarks>` tag per illustrare i valori di `UpdateRecord` metodo.</span><span class="sxs-lookup"><span data-stu-id="c72ff-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="c72ff-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c72ff-114">See also</span></span>

- [<span data-ttu-id="c72ff-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="c72ff-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
