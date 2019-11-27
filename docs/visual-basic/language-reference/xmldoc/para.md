---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 8f28ecc33eea99150509bb4bade047489b4b826b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352310"
---
# <a name="para-visual-basic"></a><span data-ttu-id="38f2a-101">\<para > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38f2a-101">\<para> (Visual Basic)</span></span>
<span data-ttu-id="38f2a-102">Specifica che il contenuto è formattato come paragrafo.</span><span class="sxs-lookup"><span data-stu-id="38f2a-102">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38f2a-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38f2a-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="38f2a-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="38f2a-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="38f2a-105">Testo del paragrafo.</span><span class="sxs-lookup"><span data-stu-id="38f2a-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38f2a-106">Note</span><span class="sxs-lookup"><span data-stu-id="38f2a-106">Remarks</span></span>  
 <span data-ttu-id="38f2a-107">Il tag `<para>` è da usare all'interno di un tag, ad esempio [\<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md), [\<osservazioni >](../../../visual-basic/language-reference/xmldoc/remarks.md)o [\<restituisce >](../../../visual-basic/language-reference/xmldoc/returns.md)e consente di aggiungere la struttura al testo.</span><span class="sxs-lookup"><span data-stu-id="38f2a-107">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="38f2a-108">Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="38f2a-108">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38f2a-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="38f2a-109">Example</span></span>  
 <span data-ttu-id="38f2a-110">In questo esempio viene utilizzato il tag `<para>` per suddividere la sezione Osservazioni per il metodo `UpdateRecord` in due paragrafi.</span><span class="sxs-lookup"><span data-stu-id="38f2a-110">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="38f2a-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38f2a-111">See also</span></span>

- [<span data-ttu-id="38f2a-112">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="38f2a-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
