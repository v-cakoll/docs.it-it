---
title: Tag XML consigliati per i commenti relativi alla documentazione
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: af57fc7d55c5cfda24a2fd9406b17dedee898760
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400099"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="0771f-102">Tag XML consigliati per i commenti relativi alla documentazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0771f-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="0771f-103">Il compilatore Visual Basic può elaborare i commenti della documentazione nel codice in un file XML.</span><span class="sxs-lookup"><span data-stu-id="0771f-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="0771f-104">È possibile utilizzare altri strumenti per elaborare il file XML nella documentazione di.</span><span class="sxs-lookup"><span data-stu-id="0771f-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="0771f-105">I commenti XML sono consentiti in costrutti di codice, ad esempio tipi e membri di tipo.</span><span class="sxs-lookup"><span data-stu-id="0771f-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="0771f-106">Per i tipi parziali, solo una parte del tipo può presentare commenti XML, anche se non esiste alcuna restrizione per il commento dei relativi membri.</span><span class="sxs-lookup"><span data-stu-id="0771f-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0771f-107">Non è possibile applicare i commenti alla documentazione agli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="0771f-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="0771f-108">Il motivo è che uno spazio dei nomi può estendersi su più assembly e non tutti gli assembly devono essere caricati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="0771f-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="0771f-109">Il compilatore elabora qualsiasi tag che è un XML valido.</span><span class="sxs-lookup"><span data-stu-id="0771f-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="0771f-110">I seguenti tag forniscono la funzionalità comunemente utilizzata nella documentazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0771f-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[\<c>](c.md)|[\<code>](code.md)|[\<example>](example.md)|  
|<span data-ttu-id="0771f-111">[\<exception>](exception.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0771f-111">[\<exception>](exception.md) <sup>1</sup></span></span>|<span data-ttu-id="0771f-112">[\<include>](include.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0771f-112">[\<include>](include.md) <sup>1</sup></span></span>|[\<list>](list.md)|  
|[\<para>](para.md)|<span data-ttu-id="0771f-113">[\<param>](param.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0771f-113">[\<param>](param.md) <sup>1</sup></span></span>|[\<paramref>](paramref.md)|  
|<span data-ttu-id="0771f-114">[\<permission>](permission.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0771f-114">[\<permission>](permission.md) <sup>1</sup></span></span>|[\<remarks>](remarks.md)|[\<returns>](returns.md)|  
|<span data-ttu-id="0771f-115">[\<see>](see.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0771f-115">[\<see>](see.md) <sup>1</sup></span></span>|<span data-ttu-id="0771f-116">[\<seealso>](seealso.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0771f-116">[\<seealso>](seealso.md) <sup>1</sup></span></span>|[\<summary>](summary.md)|  
|<span data-ttu-id="0771f-117">[\<typeparam>](typeparam.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0771f-117">[\<typeparam>](typeparam.md) <sup>1</sup></span></span>|[\<value>](value.md)||  
  
 <span data-ttu-id="0771f-118">(<sup>1</sup> il compilatore verifica la sintassi).</span><span class="sxs-lookup"><span data-stu-id="0771f-118">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0771f-119">Se si desidera che le parentesi angolari vengano visualizzate nel testo di un commento della documentazione, utilizzare `&lt;` e `&gt;` .</span><span class="sxs-lookup"><span data-stu-id="0771f-119">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="0771f-120">Ad esempio, la stringa `"&lt;text in angle brackets&gt;"` viene visualizzata come `<text in angle brackets>` .</span><span class="sxs-lookup"><span data-stu-id="0771f-120">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0771f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0771f-121">See also</span></span>

- [<span data-ttu-id="0771f-122">Documentazione del codice tramite XML</span><span class="sxs-lookup"><span data-stu-id="0771f-122">Documenting Your Code with XML</span></span>](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="0771f-123">-doc</span><span class="sxs-lookup"><span data-stu-id="0771f-123">-doc</span></span>](../../reference/command-line-compiler/doc.md)
- [<span data-ttu-id="0771f-124">Procedura: Creare documentazione XML</span><span class="sxs-lookup"><span data-stu-id="0771f-124">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
