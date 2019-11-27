---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: b327e548bcdce1522a888855bd88e3150695147b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352254"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="0f1a5-101">> osservazioni \<(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f1a5-101">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="0f1a5-102">Specifica una sezione di osservazioni per il membro.</span><span class="sxs-lookup"><span data-stu-id="0f1a5-102">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f1a5-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f1a5-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f1a5-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="0f1a5-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="0f1a5-105">Descrizione del membro.</span><span class="sxs-lookup"><span data-stu-id="0f1a5-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f1a5-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0f1a5-106">Remarks</span></span>  
 <span data-ttu-id="0f1a5-107">Usare il tag `<remarks>` per aggiungere informazioni su un tipo, integrando le informazioni specificate con [\<> di riepilogo](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="0f1a5-107">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="0f1a5-108">Queste informazioni vengono visualizzate nel Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="0f1a5-108">This information appears in the Object Browser.</span></span> <span data-ttu-id="0f1a5-109">Per informazioni sulla Visualizzatore oggetti, vedere [visualizzazione della struttura del codice](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="0f1a5-109">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="0f1a5-110">Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="0f1a5-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f1a5-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f1a5-111">Example</span></span>  
 <span data-ttu-id="0f1a5-112">Questo esempio usa il tag `<remarks>` per illustrare il funzionamento del metodo `UpdateRecord`.</span><span class="sxs-lookup"><span data-stu-id="0f1a5-112">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="0f1a5-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f1a5-113">See also</span></span>

- [<span data-ttu-id="0f1a5-114">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="0f1a5-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
