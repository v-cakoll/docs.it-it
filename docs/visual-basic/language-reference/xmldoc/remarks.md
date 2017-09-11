---
title: '&lt;la sezione Osservazioni&gt; (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: c1b2c48dc3247935f703ff4107f29829c494a305
ms.contentlocale: it-it
ms.lasthandoff: 06/01/2017

---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="2b407-102">&lt;la sezione Osservazioni&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b407-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="2b407-103">Specifica una sezione Note per il membro.</span><span class="sxs-lookup"><span data-stu-id="2b407-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b407-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b407-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b407-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2b407-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="2b407-106">Descrizione del membro.</span><span class="sxs-lookup"><span data-stu-id="2b407-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b407-107">Note</span><span class="sxs-lookup"><span data-stu-id="2b407-107">Remarks</span></span>  
 <span data-ttu-id="2b407-108">Utilizzare il `<remarks>` tag per aggiungere informazioni su un tipo, che integrano le informazioni specificate con [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="2b407-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="2b407-109">Queste informazioni vengono visualizzate nel Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="2b407-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="2b407-110">Per informazioni sul Visualizzatore oggetti, vedere [visualizzando il codice di struttura](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="2b407-110">For information about the Object Browser, see [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="2b407-111">Esegue la compilazione con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) ai commenti di documentazione di processo in un file.</span><span class="sxs-lookup"><span data-stu-id="2b407-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b407-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b407-112">Example</span></span>  
 <span data-ttu-id="2b407-113">Questo esempio viene utilizzato il `<remarks>` tag per illustrare i valori di `UpdateRecord` metodo.</span><span class="sxs-lookup"><span data-stu-id="2b407-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 <span data-ttu-id="2b407-114">[!code-vb[6 VbVbcnXmlDocComments](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2b407-114">[!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b407-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b407-115">See Also</span></span>  
 [<span data-ttu-id="2b407-116">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="2b407-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
