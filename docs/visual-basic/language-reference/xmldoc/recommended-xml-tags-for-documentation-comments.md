---
title: Tag XML consigliati per i commenti relativi alla documentazione (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7815d4c9fddc4e760c7495ef7a2509c55141e96e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="88bec-102">Tag XML consigliati per i commenti relativi alla documentazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88bec-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="88bec-103">Il compilatore Visual Basic può elaborare i commenti della documentazione nel codice in un file XML.</span><span class="sxs-lookup"><span data-stu-id="88bec-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="88bec-104">È possibile utilizzare strumenti aggiuntivi per elaborare il file XML nella documentazione.</span><span class="sxs-lookup"><span data-stu-id="88bec-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="88bec-105">I commenti XML sono consentiti nei costrutti di codice, ad esempio tipi e membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="88bec-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="88bec-106">Per i tipi parziali, solo una parte del tipo possa contenere commenti XML, anche se non esiste alcuna restrizione sui commenti sui relativi membri.</span><span class="sxs-lookup"><span data-stu-id="88bec-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88bec-107">Impossibile applicare i commenti della documentazione per gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="88bec-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="88bec-108">Il motivo è che uno spazio dei nomi può estendersi a diversi assembly e non tutti gli assembly devono essere caricati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="88bec-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="88bec-109">Il compilatore elabora qualsiasi tag che è un XML valido.</span><span class="sxs-lookup"><span data-stu-id="88bec-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="88bec-110">I tag seguenti forniscono funzionalità comunemente utilizzate nella documentazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="88bec-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="88bec-111">\<c></span><span class="sxs-lookup"><span data-stu-id="88bec-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="88bec-112">\<code></span><span class="sxs-lookup"><span data-stu-id="88bec-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="88bec-113">\<example></span><span class="sxs-lookup"><span data-stu-id="88bec-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="88bec-114">[\<eccezione >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="88bec-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="88bec-115">[\<includere >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="88bec-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="88bec-116">\<list></span><span class="sxs-lookup"><span data-stu-id="88bec-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="88bec-117">\<para></span><span class="sxs-lookup"><span data-stu-id="88bec-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="88bec-118">[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="88bec-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="88bec-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="88bec-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="88bec-120">[\<autorizzazione >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="88bec-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="88bec-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="88bec-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="88bec-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="88bec-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="88bec-123">[\<vedere >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="88bec-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="88bec-124">[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="88bec-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="88bec-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="88bec-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="88bec-126">[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="88bec-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="88bec-127">\<value></span><span class="sxs-lookup"><span data-stu-id="88bec-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="88bec-128">(<sup>1</sup> il compilatore verifica la sintassi.)</span><span class="sxs-lookup"><span data-stu-id="88bec-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88bec-129">Se si desidera venga visualizzato nel testo di un commento di documentazione tra parentesi angolari, utilizzare `<` e `>`.</span><span class="sxs-lookup"><span data-stu-id="88bec-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`.</span></span> <span data-ttu-id="88bec-130">Ad esempio, la stringa `"<text in angle brackets>"` verrà visualizzato come `<text in angle``brackets>`.</span><span class="sxs-lookup"><span data-stu-id="88bec-130">For example, the string `"<text in angle brackets>"` will appear as `<text in angle``brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88bec-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88bec-131">See Also</span></span>  
 [<span data-ttu-id="88bec-132">Documentazione del codice tramite XML</span><span class="sxs-lookup"><span data-stu-id="88bec-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="88bec-133">/doc</span><span class="sxs-lookup"><span data-stu-id="88bec-133">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [<span data-ttu-id="88bec-134">Procedura: Creare documentazione XML</span><span class="sxs-lookup"><span data-stu-id="88bec-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
