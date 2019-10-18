---
title: <para> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: aa4e4c14717b69b9ca4595e20c768a2b91aac1e4
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524734"
---
# <a name="para-visual-basic"></a><span data-ttu-id="3ce8f-102">\<para > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ce8f-102">\<para> (Visual Basic)</span></span>
<span data-ttu-id="3ce8f-103">Specifica che il contenuto è formattato come paragrafo.</span><span class="sxs-lookup"><span data-stu-id="3ce8f-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ce8f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ce8f-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ce8f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3ce8f-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="3ce8f-106">Testo del paragrafo.</span><span class="sxs-lookup"><span data-stu-id="3ce8f-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ce8f-107">Note</span><span class="sxs-lookup"><span data-stu-id="3ce8f-107">Remarks</span></span>  
 <span data-ttu-id="3ce8f-108">Il tag `<para>` è da usare all'interno di un tag, ad esempio [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks >](../../../visual-basic/language-reference/xmldoc/remarks.md) [o \<returns > e](../../../visual-basic/language-reference/xmldoc/returns.md)consente di aggiungere la struttura al testo.</span><span class="sxs-lookup"><span data-stu-id="3ce8f-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="3ce8f-109">Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="3ce8f-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ce8f-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="3ce8f-110">Example</span></span>  
 <span data-ttu-id="3ce8f-111">In questo esempio viene utilizzato il tag `<para>` per suddividere la sezione Osservazioni per il metodo `UpdateRecord` in due paragrafi.</span><span class="sxs-lookup"><span data-stu-id="3ce8f-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="3ce8f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ce8f-112">See also</span></span>

- [<span data-ttu-id="3ce8f-113">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="3ce8f-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
