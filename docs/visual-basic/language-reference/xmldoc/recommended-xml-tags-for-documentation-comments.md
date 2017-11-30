---
title: Tag XML consigliati per i commenti relativi alla documentazione (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 54712deb8bb2a5ed1e7b1f5fb8aa073dcdaf76d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="7ba12-102">Tag XML consigliati per i commenti relativi alla documentazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ba12-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="7ba12-103">Il [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilatore può elaborare i commenti di documentazione nel codice in un file XML.</span><span class="sxs-lookup"><span data-stu-id="7ba12-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="7ba12-104">È possibile utilizzare strumenti aggiuntivi per elaborare il file XML nella documentazione.</span><span class="sxs-lookup"><span data-stu-id="7ba12-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="7ba12-105">I commenti XML sono consentiti nei costrutti di codice, ad esempio tipi e membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="7ba12-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="7ba12-106">Per i tipi parziali, solo una parte del tipo possa contenere commenti XML, anche se non esiste alcuna restrizione sui commenti sui relativi membri.</span><span class="sxs-lookup"><span data-stu-id="7ba12-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ba12-107">Impossibile applicare i commenti della documentazione per gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7ba12-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="7ba12-108">Il motivo è che uno spazio dei nomi può estendersi a diversi assembly e non tutti gli assembly devono essere caricati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="7ba12-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="7ba12-109">Il compilatore elabora qualsiasi tag che è un XML valido.</span><span class="sxs-lookup"><span data-stu-id="7ba12-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="7ba12-110">I tag seguenti forniscono funzionalità comunemente utilizzate nella documentazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7ba12-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="7ba12-111">\<c></span><span class="sxs-lookup"><span data-stu-id="7ba12-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="7ba12-112">\<code></span><span class="sxs-lookup"><span data-stu-id="7ba12-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="7ba12-113">\<example></span><span class="sxs-lookup"><span data-stu-id="7ba12-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="7ba12-114">[\<eccezione >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ba12-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="7ba12-115">[\<includere >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ba12-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="7ba12-116">\<list></span><span class="sxs-lookup"><span data-stu-id="7ba12-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="7ba12-117">\<para></span><span class="sxs-lookup"><span data-stu-id="7ba12-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="7ba12-118">[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ba12-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="7ba12-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="7ba12-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="7ba12-120">[\<autorizzazione >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ba12-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="7ba12-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="7ba12-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="7ba12-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="7ba12-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="7ba12-123">[\<vedere >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ba12-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="7ba12-124">[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ba12-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="7ba12-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="7ba12-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="7ba12-126">[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ba12-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="7ba12-127">\<value></span><span class="sxs-lookup"><span data-stu-id="7ba12-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="7ba12-128">(<sup>1</sup> il compilatore verifica la sintassi.)</span><span class="sxs-lookup"><span data-stu-id="7ba12-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ba12-129">Se si desidera venga visualizzato nel testo di un commento di documentazione tra parentesi angolari, utilizzare `<` e `>`.</span><span class="sxs-lookup"><span data-stu-id="7ba12-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`.</span></span> <span data-ttu-id="7ba12-130">Ad esempio, la stringa `"<text in angle brackets>"` verrà visualizzato come `<text in angle``brackets>`.</span><span class="sxs-lookup"><span data-stu-id="7ba12-130">For example, the string `"<text in angle brackets>"` will appear as `<text in angle``brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ba12-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ba12-131">See Also</span></span>  
 [<span data-ttu-id="7ba12-132">Documentazione del codice tramite XML</span><span class="sxs-lookup"><span data-stu-id="7ba12-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="7ba12-133">/doc</span><span class="sxs-lookup"><span data-stu-id="7ba12-133">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [<span data-ttu-id="7ba12-134">Procedura: Creare documentazione XML</span><span class="sxs-lookup"><span data-stu-id="7ba12-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
