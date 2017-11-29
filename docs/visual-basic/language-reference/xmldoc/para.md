---
title: '&lt;para&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e2a034974ed94b18da374fbd372063ea4d575440
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ltparagt-visual-basic"></a><span data-ttu-id="5eee2-102">&lt;para&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5eee2-102">&lt;para&gt; (Visual Basic)</span></span>
<span data-ttu-id="5eee2-103">Specifica che il contenuto viene formattato come un paragrafo.</span><span class="sxs-lookup"><span data-stu-id="5eee2-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eee2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5eee2-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5eee2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5eee2-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="5eee2-106">Testo del paragrafo.</span><span class="sxs-lookup"><span data-stu-id="5eee2-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5eee2-107">Note</span><span class="sxs-lookup"><span data-stu-id="5eee2-107">Remarks</span></span>  
 <span data-ttu-id="5eee2-108">Il `<para>` tag viene utilizzato all'interno di un tag, ad esempio [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md), [ \<osservazioni >](../../../visual-basic/language-reference/xmldoc/remarks.md), o [ \<restituisce >](../../../visual-basic/language-reference/xmldoc/returns.md), e consente di aggiungere struttura al testo.</span><span class="sxs-lookup"><span data-stu-id="5eee2-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="5eee2-109">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="5eee2-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5eee2-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="5eee2-110">Example</span></span>  
 <span data-ttu-id="5eee2-111">Questo esempio viene utilizzato il `<para>` tag per la sezione Osservazioni per suddividere il `UpdateRecord` metodo in due paragrafi.</span><span class="sxs-lookup"><span data-stu-id="5eee2-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/para_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5eee2-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5eee2-112">See Also</span></span>  
 [<span data-ttu-id="5eee2-113">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="5eee2-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
