---
title: Tag XML consigliati per i commenti della documentazione (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
dev_langs:
- VB
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e4a6c3128a69e8d666d44882ef3eac9f9a31a51a
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="ab4ff-102">Tag XML consigliati per i commenti relativi alla documentazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab4ff-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="ab4ff-103">Il [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore può elaborare i commenti della documentazione nel codice in un file XML.</span><span class="sxs-lookup"><span data-stu-id="ab4ff-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="ab4ff-104">È possibile utilizzare strumenti aggiuntivi per elaborare il file XML nella documentazione.</span><span class="sxs-lookup"><span data-stu-id="ab4ff-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="ab4ff-105">I commenti XML sono consentiti sui costrutti di codice, ad esempio tipi e membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="ab4ff-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="ab4ff-106">Per i tipi parziali, solo una parte del tipo possa contenere commenti XML, anche se vi è alcuna restrizione sui commenti sui relativi membri.</span><span class="sxs-lookup"><span data-stu-id="ab4ff-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab4ff-107">Impossibile applicare i commenti della documentazione per gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ab4ff-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="ab4ff-108">Il motivo è che uno spazio dei nomi può estendersi a diversi assembly e non tutti gli assembly devono essere caricati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="ab4ff-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="ab4ff-109">Il compilatore elabora qualsiasi tag XML valido.</span><span class="sxs-lookup"><span data-stu-id="ab4ff-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="ab4ff-110">I seguenti tag forniscono funzionalità comunemente utilizzate nella documentazione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="ab4ff-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="ab4ff-111">\<c ></span><span class="sxs-lookup"><span data-stu-id="ab4ff-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="ab4ff-112">\<codice ></span><span class="sxs-lookup"><span data-stu-id="ab4ff-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="ab4ff-113">\<esempio ></span><span class="sxs-lookup"><span data-stu-id="ab4ff-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="ab4ff-114">[\<eccezione >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ab4ff-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="ab4ff-115">[\<includere >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ab4ff-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="ab4ff-116">\<list></span><span class="sxs-lookup"><span data-stu-id="ab4ff-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="ab4ff-117">\<para ></span><span class="sxs-lookup"><span data-stu-id="ab4ff-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="ab4ff-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ab4ff-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="ab4ff-119">\<paramref ></span><span class="sxs-lookup"><span data-stu-id="ab4ff-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="ab4ff-120">[\<autorizzazione >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ab4ff-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="ab4ff-121">\<la sezione Osservazioni ></span><span class="sxs-lookup"><span data-stu-id="ab4ff-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="ab4ff-122">\<Restituisce ></span><span class="sxs-lookup"><span data-stu-id="ab4ff-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="ab4ff-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ab4ff-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="ab4ff-124">[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ab4ff-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="ab4ff-125">\<riepilogo ></span><span class="sxs-lookup"><span data-stu-id="ab4ff-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="ab4ff-126">[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ab4ff-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="ab4ff-127">\<valore ></span><span class="sxs-lookup"><span data-stu-id="ab4ff-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="ab4ff-128">(<sup>1</sup> il compilatore verifica la sintassi.)</span><span class="sxs-lookup"><span data-stu-id="ab4ff-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab4ff-129">Se si desidera vengano visualizzate nel testo di un commento di documentazione parentesi angolari, utilizzare `<` e `>`.</span><span class="sxs-lookup"><span data-stu-id="ab4ff-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`.</span></span> <span data-ttu-id="ab4ff-130">Ad esempio, la stringa `"<text in angle brackets>"` verrà visualizzato come `<text in angle``brackets>`.</span><span class="sxs-lookup"><span data-stu-id="ab4ff-130">For example, the string `"<text in angle brackets>"` will appear as `<text in angle``brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab4ff-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab4ff-131">See Also</span></span>  
 <span data-ttu-id="ab4ff-132">[Documentazione del codice tramite XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span><span class="sxs-lookup"><span data-stu-id="ab4ff-132">[Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span></span>  
<span data-ttu-id="ab4ff-133"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span><span class="sxs-lookup"><span data-stu-id="ab4ff-133"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span></span>  
<span data-ttu-id="ab4ff-134"> [Procedura: Creare documentazione XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span><span class="sxs-lookup"><span data-stu-id="ab4ff-134"> [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span></span>
