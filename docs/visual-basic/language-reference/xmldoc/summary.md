---
title: '&lt;riepilogo&gt; (Visual Basic) | Documenti di Microsoft'
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
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
caps.latest.revision: 12
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
ms.openlocfilehash: 42321daf092c4b637d2f75fb7f6d7e95201791ba
ms.contentlocale: it-it
ms.lasthandoff: 06/01/2017

---
# <a name="ltsummarygt-visual-basic"></a><span data-ttu-id="46fe3-102">&lt;riepilogo&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46fe3-102">&lt;summary&gt; (Visual Basic)</span></span>
<span data-ttu-id="46fe3-103">Specifica il riepilogo del membro.</span><span class="sxs-lookup"><span data-stu-id="46fe3-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46fe3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46fe3-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46fe3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="46fe3-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="46fe3-106">Un riepilogo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="46fe3-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46fe3-107">Note</span><span class="sxs-lookup"><span data-stu-id="46fe3-107">Remarks</span></span>  
 <span data-ttu-id="46fe3-108">Utilizzare il `<summary>` tag per descrivere un tipo o un membro del tipo.</span><span class="sxs-lookup"><span data-stu-id="46fe3-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="46fe3-109">Utilizzare [ \<osservazioni >](../../../visual-basic/language-reference/xmldoc/remarks.md) per aggiungere informazioni supplementari per una descrizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="46fe3-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="46fe3-110">Il testo per il `<summary>` tag è l'unica fonte di informazioni sul tipo in IntelliSense e viene anche visualizzato nel Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="46fe3-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="46fe3-111">Per informazioni sul Visualizzatore oggetti, vedere [visualizzando il codice di struttura](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="46fe3-111">For information about the Object Browser, see [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="46fe3-112">Esegue la compilazione con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) ai commenti di documentazione di processo in un file.</span><span class="sxs-lookup"><span data-stu-id="46fe3-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46fe3-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="46fe3-113">Example</span></span>  
 <span data-ttu-id="46fe3-114">Questo esempio viene utilizzato il `<summary>` tag per descrivere il `ResetCounter` (metodo) e `Counter` proprietà.</span><span class="sxs-lookup"><span data-stu-id="46fe3-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 <span data-ttu-id="46fe3-115">[!code-vb[VbVbcnXmlDocComments n.&1;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="46fe3-115">[!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46fe3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46fe3-116">See Also</span></span>  
 [<span data-ttu-id="46fe3-117">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="46fe3-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
