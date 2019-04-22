---
title: Tag XML consigliati per i commenti relativi alla documentazione (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: e59ee25b22c51e47dc83233af33099e6c55de87b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814950"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="152d7-102">Tag XML consigliati per i commenti relativi alla documentazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="152d7-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="152d7-103">Il compilatore Visual Basic può elaborare i commenti della documentazione nel codice in un file XML.</span><span class="sxs-lookup"><span data-stu-id="152d7-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="152d7-104">È possibile utilizzare strumenti aggiuntivi per elaborare il file XML nella documentazione.</span><span class="sxs-lookup"><span data-stu-id="152d7-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="152d7-105">Commenti in formato XML sono consentiti nei costrutti di codice, ad esempio tipi e membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="152d7-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="152d7-106">Per i tipi parziali, solo una parte del tipo può avere commenti in formato XML, anche se non esiste alcuna restrizione sui commenti relativi membri.</span><span class="sxs-lookup"><span data-stu-id="152d7-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="152d7-107">I commenti della documentazione non è possibile applicare agli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="152d7-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="152d7-108">Il motivo è che uno spazio dei nomi può estendersi a diversi assembly, e non tutti gli assembly da caricare nello stesso momento.</span><span class="sxs-lookup"><span data-stu-id="152d7-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="152d7-109">Il compilatore elabora tutti i tag XML valido.</span><span class="sxs-lookup"><span data-stu-id="152d7-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="152d7-110">I tag seguenti forniscono le funzionalità comunemente utilizzate nella documentazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="152d7-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="152d7-111">\<c></span><span class="sxs-lookup"><span data-stu-id="152d7-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="152d7-112">\<code></span><span class="sxs-lookup"><span data-stu-id="152d7-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="152d7-113">\<example></span><span class="sxs-lookup"><span data-stu-id="152d7-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="152d7-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="152d7-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="152d7-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="152d7-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="152d7-116">\<list></span><span class="sxs-lookup"><span data-stu-id="152d7-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="152d7-117">\<para></span><span class="sxs-lookup"><span data-stu-id="152d7-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="152d7-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="152d7-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="152d7-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="152d7-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="152d7-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="152d7-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="152d7-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="152d7-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="152d7-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="152d7-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="152d7-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="152d7-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="152d7-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="152d7-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="152d7-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="152d7-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="152d7-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="152d7-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="152d7-127">\<value></span><span class="sxs-lookup"><span data-stu-id="152d7-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="152d7-128">(<sup>1</sup> il compilatore verifica sintassi.)</span><span class="sxs-lookup"><span data-stu-id="152d7-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="152d7-129">Se si desidera che vengano visualizzati nel testo di un commento relativo alla documentazione parentesi angolari, usare `&lt;` e `&gt;`.</span><span class="sxs-lookup"><span data-stu-id="152d7-129">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="152d7-130">Ad esempio, la stringa `"&lt;text in angle brackets&gt;"` verranno visualizzati come `<text in angle brackets>`.</span><span class="sxs-lookup"><span data-stu-id="152d7-130">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="152d7-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="152d7-131">See also</span></span>

- [<span data-ttu-id="152d7-132">Documentazione del codice tramite XML</span><span class="sxs-lookup"><span data-stu-id="152d7-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="152d7-133">/doc</span><span class="sxs-lookup"><span data-stu-id="152d7-133">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
- [<span data-ttu-id="152d7-134">Procedura: Creare documentazione XML</span><span class="sxs-lookup"><span data-stu-id="152d7-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
