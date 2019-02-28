---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 96ef62d53fd1cc806c0dc72d2d0781b1c6297dc6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970870"
---
# <a name="para-visual-basic"></a><span data-ttu-id="9a6ce-102">\<para> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a6ce-102">\<para> (Visual Basic)</span></span>
<span data-ttu-id="9a6ce-103">Specifica che il contenuto viene formattato come un paragrafo.</span><span class="sxs-lookup"><span data-stu-id="9a6ce-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a6ce-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a6ce-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a6ce-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a6ce-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="9a6ce-106">Testo del paragrafo.</span><span class="sxs-lookup"><span data-stu-id="9a6ce-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a6ce-107">Note</span><span class="sxs-lookup"><span data-stu-id="9a6ce-107">Remarks</span></span>  
 <span data-ttu-id="9a6ce-108">Il `<para>` tag è utilizzato all'interno di un tag, ad esempio [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md), [ \<remarks >](../../../visual-basic/language-reference/xmldoc/remarks.md), o [ \<restituisce >](../../../visual-basic/language-reference/xmldoc/returns.md), e consente di aggiungere una struttura al testo.</span><span class="sxs-lookup"><span data-stu-id="9a6ce-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="9a6ce-109">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="9a6ce-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a6ce-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a6ce-110">Example</span></span>  
 <span data-ttu-id="9a6ce-111">Questo esempio Usa la `<para>` tag per suddividere la sezione Osservazioni per il `UpdateRecord` metodo in due paragrafi.</span><span class="sxs-lookup"><span data-stu-id="9a6ce-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="9a6ce-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a6ce-112">See also</span></span>
- [<span data-ttu-id="9a6ce-113">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="9a6ce-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
