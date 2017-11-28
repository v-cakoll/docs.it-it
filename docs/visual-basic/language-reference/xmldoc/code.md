---
title: '&lt;codice&gt; (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a7c1d8ab3db0c36c6a2935b9ffbef15e87df5ebc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltcodegt-visual-basic"></a><span data-ttu-id="e9694-102">&lt;codice&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9694-102">&lt;code&gt; (Visual Basic)</span></span>
<span data-ttu-id="e9694-103">Indica che il testo è più righe di codice.</span><span class="sxs-lookup"><span data-stu-id="e9694-103">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9694-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9694-104">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9694-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e9694-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="e9694-106">Testo da contrassegnare come codice.</span><span class="sxs-lookup"><span data-stu-id="e9694-106">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9694-107">Note</span><span class="sxs-lookup"><span data-stu-id="e9694-107">Remarks</span></span>  
 <span data-ttu-id="e9694-108">Utilizzare il `<code>` tag per indicare più righe di codice.</span><span class="sxs-lookup"><span data-stu-id="e9694-108">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="e9694-109">Usare [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.</span><span class="sxs-lookup"><span data-stu-id="e9694-109">Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="e9694-110">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="e9694-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9694-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9694-111">Example</span></span>  
 <span data-ttu-id="e9694-112">Questo esempio viene utilizzato il \<codice > tag per includere il codice di esempio per l'utilizzo di `ID` campo.</span><span class="sxs-lookup"><span data-stu-id="e9694-112">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/code_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e9694-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9694-113">See Also</span></span>  
 [<span data-ttu-id="e9694-114">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="e9694-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
