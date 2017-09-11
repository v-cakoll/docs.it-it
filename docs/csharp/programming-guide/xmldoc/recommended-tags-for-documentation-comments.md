---
title: Tag consigliati per i commenti relativi alla documentazione (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4f4033ed66fd68afceb9d98cbc6da18c262ae02b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="1790f-102">Tag consigliati per i commenti relativi alla documentazione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="1790f-102">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="1790f-103">Il compilatore C# elabora i commenti alla documentazione nel codice e li formatta come XML in un file il cui nome è stato specificato nell'opzione della riga di comando **/doc**.</span><span class="sxs-lookup"><span data-stu-id="1790f-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="1790f-104">Per creare la documentazione finale basata sul file generato dal compilatore, è possibile creare uno strumento personalizzato o usare uno strumento come [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="1790f-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="1790f-105">I tag vengono elaborati in costrutti di codice come tipi e membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="1790f-105">Tags are processed on code constructs such as types and type members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1790f-106">Non è possibile applicare a uno spazio dei nomi i commenti relativi alla documentazione.</span><span class="sxs-lookup"><span data-stu-id="1790f-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="1790f-107">Il compilatore elabora tutti i tag validi per XML.</span><span class="sxs-lookup"><span data-stu-id="1790f-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="1790f-108">I tag seguenti forniscono le funzionalità comunemente usate nella documentazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1790f-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="1790f-109">Tag</span><span class="sxs-lookup"><span data-stu-id="1790f-109">Tags</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="1790f-110">\<c></span><span class="sxs-lookup"><span data-stu-id="1790f-110">\<c></span></span>](../../../csharp/programming-guide/xmldoc/code-inline.md)|[<span data-ttu-id="1790f-111">\<para></span><span class="sxs-lookup"><span data-stu-id="1790f-111">\<para></span></span>](../../../csharp/programming-guide/xmldoc/para.md)|<span data-ttu-id="1790f-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)*</span><span class="sxs-lookup"><span data-stu-id="1790f-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)*</span></span>|  
|[<span data-ttu-id="1790f-113">\<code></span><span class="sxs-lookup"><span data-stu-id="1790f-113">\<code></span></span>](../../../csharp/programming-guide/xmldoc/code.md)|<span data-ttu-id="1790f-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)*</span><span class="sxs-lookup"><span data-stu-id="1790f-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)*</span></span>|<span data-ttu-id="1790f-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)*</span><span class="sxs-lookup"><span data-stu-id="1790f-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)*</span></span>|  
|[<span data-ttu-id="1790f-116">\<example></span><span class="sxs-lookup"><span data-stu-id="1790f-116">\<example></span></span>](../../../csharp/programming-guide/xmldoc/example.md)|[<span data-ttu-id="1790f-117">\<paramref></span><span class="sxs-lookup"><span data-stu-id="1790f-117">\<paramref></span></span>](../../../csharp/programming-guide/xmldoc/paramref.md)|[<span data-ttu-id="1790f-118">\<summary></span><span class="sxs-lookup"><span data-stu-id="1790f-118">\<summary></span></span>](../../../csharp/programming-guide/xmldoc/summary.md)|  
|<span data-ttu-id="1790f-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)*</span><span class="sxs-lookup"><span data-stu-id="1790f-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)*</span></span>|<span data-ttu-id="1790f-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)*</span><span class="sxs-lookup"><span data-stu-id="1790f-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)*</span></span>|<span data-ttu-id="1790f-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)*</span><span class="sxs-lookup"><span data-stu-id="1790f-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)*</span></span>|  
|<span data-ttu-id="1790f-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)*</span><span class="sxs-lookup"><span data-stu-id="1790f-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)*</span></span>|[<span data-ttu-id="1790f-123">\<remarks></span><span class="sxs-lookup"><span data-stu-id="1790f-123">\<remarks></span></span>](../../../csharp/programming-guide/xmldoc/remarks.md)|[<span data-ttu-id="1790f-124">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="1790f-124">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)|  
|[<span data-ttu-id="1790f-125">\<list></span><span class="sxs-lookup"><span data-stu-id="1790f-125">\<list></span></span>](../../../csharp/programming-guide/xmldoc/list.md)|[<span data-ttu-id="1790f-126">\<returns></span><span class="sxs-lookup"><span data-stu-id="1790f-126">\<returns></span></span>](../../../csharp/programming-guide/xmldoc/returns.md)|[<span data-ttu-id="1790f-127">\<value></span><span class="sxs-lookup"><span data-stu-id="1790f-127">\<value></span></span>](../../../csharp/programming-guide/xmldoc/value.md)|  
  
 <span data-ttu-id="1790f-128">* indica che il compilatore esegue la verifica della sintassi.</span><span class="sxs-lookup"><span data-stu-id="1790f-128">(* denotes that the compiler verifies syntax.)</span></span>  
  
 <span data-ttu-id="1790f-129">Se si vuole che nel testo di un commento alla documentazione vengano visualizzate parentesi angolari, usare `<` e `>`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="1790f-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`, as shown in the following example.</span></span>  
  
```xml  
/// <summary cref="C < T >">  
/// </summary>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1790f-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1790f-130">See Also</span></span>  
 <span data-ttu-id="1790f-131">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1790f-131">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1790f-132">[/doc (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="1790f-132">[/doc (C# Compiler Options)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) </span></span>  
 [<span data-ttu-id="1790f-133">Commenti relativi alla documentazione XML</span><span class="sxs-lookup"><span data-stu-id="1790f-133">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

