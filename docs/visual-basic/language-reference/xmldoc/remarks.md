---
title: '&lt;la sezione Osservazioni&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f70c2d7df190d2ff8187882a9176dbe98984296
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="f5ad4-102">&lt;la sezione Osservazioni&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5ad4-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="f5ad4-103">Specifica una sezione Osservazioni per il membro.</span><span class="sxs-lookup"><span data-stu-id="f5ad4-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5ad4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5ad4-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5ad4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f5ad4-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="f5ad4-106">Descrizione del membro.</span><span class="sxs-lookup"><span data-stu-id="f5ad4-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5ad4-107">Note</span><span class="sxs-lookup"><span data-stu-id="f5ad4-107">Remarks</span></span>  
 <span data-ttu-id="f5ad4-108">Utilizzare il `<remarks>` tag per aggiungere informazioni su un tipo, che integrano le informazioni specificate con [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="f5ad4-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="f5ad4-109">Queste informazioni vengono visualizzate nel Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="f5ad4-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="f5ad4-110">Per informazioni sul Visualizzatore oggetti, vedere [visualizzazione della struttura del codice](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="f5ad4-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="f5ad4-111">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="f5ad4-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5ad4-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5ad4-112">Example</span></span>  
 <span data-ttu-id="f5ad4-113">Questo esempio viene utilizzato il `<remarks>` tag per illustrare i valori di `UpdateRecord` metodo.</span><span class="sxs-lookup"><span data-stu-id="f5ad4-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f5ad4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5ad4-114">See Also</span></span>  
 [<span data-ttu-id="f5ad4-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="f5ad4-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
