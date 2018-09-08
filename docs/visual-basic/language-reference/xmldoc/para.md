---
title: '&lt;para&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: fa11c713a5ed5793b50865753f8bcdeaabf56e83
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44209695"
---
# <a name="ltparagt-visual-basic"></a><span data-ttu-id="96489-102">&lt;para&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96489-102">&lt;para&gt; (Visual Basic)</span></span>
<span data-ttu-id="96489-103">Specifica che il contenuto viene formattato come un paragrafo.</span><span class="sxs-lookup"><span data-stu-id="96489-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96489-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96489-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96489-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="96489-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="96489-106">Testo del paragrafo.</span><span class="sxs-lookup"><span data-stu-id="96489-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96489-107">Note</span><span class="sxs-lookup"><span data-stu-id="96489-107">Remarks</span></span>  
 <span data-ttu-id="96489-108">Il `<para>` tag è utilizzato all'interno di un tag, ad esempio [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md), [ \<remarks >](../../../visual-basic/language-reference/xmldoc/remarks.md), o [ \<restituisce >](../../../visual-basic/language-reference/xmldoc/returns.md), e consente di aggiungere una struttura al testo.</span><span class="sxs-lookup"><span data-stu-id="96489-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="96489-109">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="96489-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96489-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="96489-110">Example</span></span>  
 <span data-ttu-id="96489-111">Questo esempio Usa la `<para>` tag per suddividere la sezione Osservazioni per il `UpdateRecord` metodo in due paragrafi.</span><span class="sxs-lookup"><span data-stu-id="96489-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/para_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="96489-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96489-112">See Also</span></span>  
 [<span data-ttu-id="96489-113">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="96489-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
