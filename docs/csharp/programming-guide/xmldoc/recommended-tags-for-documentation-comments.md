---
title: Tag consigliati per i commenti della documentazione - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: d17ff0b78d8ae40916447e8e12da7948a21e5717
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523362"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="ffd75-102">Tag consigliati per i commenti relativi alla documentazione (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="ffd75-102">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="ffd75-103">Il compilatore C# elabora i commenti alla documentazione nel codice e li formatta come XML in un file il cui nome è stato specificato nell'opzione della riga di comando **/doc**.</span><span class="sxs-lookup"><span data-stu-id="ffd75-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="ffd75-104">Per creare la documentazione finale basata sul file generato dal compilatore, è possibile creare uno strumento personalizzato o usare uno strumento come [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="ffd75-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="ffd75-105">I tag vengono elaborati in costrutti di codice come tipi e membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="ffd75-105">Tags are processed on code constructs such as types and type members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ffd75-106">Non è possibile applicare a uno spazio dei nomi i commenti relativi alla documentazione.</span><span class="sxs-lookup"><span data-stu-id="ffd75-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="ffd75-107">Il compilatore elabora tutti i tag validi per XML.</span><span class="sxs-lookup"><span data-stu-id="ffd75-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="ffd75-108">I tag seguenti forniscono le funzionalità comunemente usate nella documentazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ffd75-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="ffd75-109">Tag</span><span class="sxs-lookup"><span data-stu-id="ffd75-109">Tags</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="ffd75-110">\<c></span><span class="sxs-lookup"><span data-stu-id="ffd75-110">\<c></span></span>](./code-inline.md)|[<span data-ttu-id="ffd75-111">\<para></span><span class="sxs-lookup"><span data-stu-id="ffd75-111">\<para></span></span>](./para.md)|<span data-ttu-id="ffd75-112">[\<see>](./see.md)\*</span><span class="sxs-lookup"><span data-stu-id="ffd75-112">[\<see>](./see.md)\*</span></span>|  
|[<span data-ttu-id="ffd75-113">\<code></span><span class="sxs-lookup"><span data-stu-id="ffd75-113">\<code></span></span>](./code.md)|<span data-ttu-id="ffd75-114">[\<param>](./param.md)\*</span><span class="sxs-lookup"><span data-stu-id="ffd75-114">[\<param>](./param.md)\*</span></span>|<span data-ttu-id="ffd75-115">[\<seealso>](./seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="ffd75-115">[\<seealso>](./seealso.md)\*</span></span>|  
|[<span data-ttu-id="ffd75-116">\<example></span><span class="sxs-lookup"><span data-stu-id="ffd75-116">\<example></span></span>](./example.md)|[<span data-ttu-id="ffd75-117">\<paramref></span><span class="sxs-lookup"><span data-stu-id="ffd75-117">\<paramref></span></span>](./paramref.md)|[<span data-ttu-id="ffd75-118">\<summary></span><span class="sxs-lookup"><span data-stu-id="ffd75-118">\<summary></span></span>](./summary.md)|  
|<span data-ttu-id="ffd75-119">[\<exception>](./exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="ffd75-119">[\<exception>](./exception.md)\*</span></span>|<span data-ttu-id="ffd75-120">[\<permission>](./permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="ffd75-120">[\<permission>](./permission.md)\*</span></span>|<span data-ttu-id="ffd75-121">[\<typeparam>](./typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="ffd75-121">[\<typeparam>](./typeparam.md)\*</span></span>|  
|<span data-ttu-id="ffd75-122">[\<include>](./include.md)\*</span><span class="sxs-lookup"><span data-stu-id="ffd75-122">[\<include>](./include.md)\*</span></span>|[<span data-ttu-id="ffd75-123">\<remarks></span><span class="sxs-lookup"><span data-stu-id="ffd75-123">\<remarks></span></span>](./remarks.md)|[<span data-ttu-id="ffd75-124">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="ffd75-124">\<typeparamref></span></span>](./typeparamref.md)|  
|[<span data-ttu-id="ffd75-125">\<list></span><span class="sxs-lookup"><span data-stu-id="ffd75-125">\<list></span></span>](./list.md)|[<span data-ttu-id="ffd75-126">\<returns></span><span class="sxs-lookup"><span data-stu-id="ffd75-126">\<returns></span></span>](./returns.md)|[<span data-ttu-id="ffd75-127">\<value></span><span class="sxs-lookup"><span data-stu-id="ffd75-127">\<value></span></span>](./value.md)|  
  
 <span data-ttu-id="ffd75-128">\* indica che il compilatore esegue la verifica della sintassi.</span><span class="sxs-lookup"><span data-stu-id="ffd75-128">(\* denotes that the compiler verifies syntax.)</span></span>  
  
 <span data-ttu-id="ffd75-129">Se si vuole che nel testo di un commento alla documentazione vengano visualizzate parentesi angolari, usare la codifica HTML di `<` e `>`, ovvero rispettivamente `&lt;` e `&gt;`.</span><span class="sxs-lookup"><span data-stu-id="ffd75-129">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="ffd75-130">Questa codifica viene mostrata nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ffd75-130">This encoding is shown in the following example:</span></span>
  
```csharp  
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```
  
## <a name="see-also"></a><span data-ttu-id="ffd75-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffd75-131">See also</span></span>

- [<span data-ttu-id="ffd75-132">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ffd75-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ffd75-133">-doc (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="ffd75-133">-doc (C# Compiler Options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="ffd75-134">Commenti relativi alla documentazione XML</span><span class="sxs-lookup"><span data-stu-id="ffd75-134">XML Documentation Comments</span></span>](./index.md)
