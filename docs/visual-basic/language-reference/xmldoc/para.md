---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 16d10b2f955a4d9a02075ee4cc40dfa2b18c3541
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940871"
---
# <a name="para-visual-basic"></a><span data-ttu-id="3b945-102">\<para> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b945-102">\<para> (Visual Basic)</span></span>
<span data-ttu-id="3b945-103">Specifica che il contenuto viene formattato come un paragrafo.</span><span class="sxs-lookup"><span data-stu-id="3b945-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b945-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3b945-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b945-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3b945-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="3b945-106">Testo del paragrafo.</span><span class="sxs-lookup"><span data-stu-id="3b945-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b945-107">Note</span><span class="sxs-lookup"><span data-stu-id="3b945-107">Remarks</span></span>  
 <span data-ttu-id="3b945-108">Il `<para>` tag è utilizzato all'interno di un tag, ad esempio [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md), [ \<remarks >](../../../visual-basic/language-reference/xmldoc/remarks.md), o [ \<restituisce >](../../../visual-basic/language-reference/xmldoc/returns.md), e consente di aggiungere una struttura al testo.</span><span class="sxs-lookup"><span data-stu-id="3b945-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="3b945-109">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="3b945-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b945-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="3b945-110">Example</span></span>  
 <span data-ttu-id="3b945-111">Questo esempio Usa la `<para>` tag per suddividere la sezione Osservazioni per il `UpdateRecord` metodo in due paragrafi.</span><span class="sxs-lookup"><span data-stu-id="3b945-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="3b945-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b945-112">See also</span></span>

- [<span data-ttu-id="3b945-113">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="3b945-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
