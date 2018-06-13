---
title: '&lt;para&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: cb80f4b39bee128790b311732adf1202dbbc6993
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601725"
---
# <a name="ltparagt-visual-basic"></a><span data-ttu-id="b8788-102">&lt;para&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8788-102">&lt;para&gt; (Visual Basic)</span></span>
<span data-ttu-id="b8788-103">Specifica che il contenuto viene formattato come un paragrafo.</span><span class="sxs-lookup"><span data-stu-id="b8788-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8788-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b8788-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8788-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b8788-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="b8788-106">Testo del paragrafo.</span><span class="sxs-lookup"><span data-stu-id="b8788-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8788-107">Note</span><span class="sxs-lookup"><span data-stu-id="b8788-107">Remarks</span></span>  
 <span data-ttu-id="b8788-108">Il `<para>` tag viene utilizzato all'interno di un tag, ad esempio [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md), [ \<osservazioni >](../../../visual-basic/language-reference/xmldoc/remarks.md), o [ \<restituisce >](../../../visual-basic/language-reference/xmldoc/returns.md), e consente di aggiungere struttura al testo.</span><span class="sxs-lookup"><span data-stu-id="b8788-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="b8788-109">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="b8788-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8788-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="b8788-110">Example</span></span>  
 <span data-ttu-id="b8788-111">Questo esempio viene utilizzato il `<para>` tag per la sezione Osservazioni per suddividere il `UpdateRecord` metodo in due paragrafi.</span><span class="sxs-lookup"><span data-stu-id="b8788-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/para_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b8788-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8788-112">See Also</span></span>  
 [<span data-ttu-id="b8788-113">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="b8788-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
