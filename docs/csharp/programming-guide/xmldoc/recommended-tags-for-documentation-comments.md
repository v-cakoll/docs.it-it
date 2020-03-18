---
title: Tag consigliati per i commenti relativi alla documentazione - Guida alla programmazione in C
ms.date: 01/21/2020
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: c746615d0d7a7a3058fbe2f8506a7a7c5c4a8779
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789717"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="4ab45-102">Tag consigliati per i commenti relativi alla documentazione (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="4ab45-102">Recommended tags for documentation comments (C# programming guide)</span></span>

<span data-ttu-id="4ab45-103">Il compilatore C# elabora i commenti alla documentazione nel codice e li formatta come XML in un file il cui nome è stato specificato nell'opzione della riga di comando **/doc**.</span><span class="sxs-lookup"><span data-stu-id="4ab45-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="4ab45-104">Per creare la documentazione finale basata sul file generato dal compilatore, è possibile creare uno strumento personalizzato oppure utilizzare uno strumento come [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="4ab45-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="4ab45-105">I tag vengono elaborati in costrutti di codice come tipi e membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="4ab45-105">Tags are processed on code constructs such as types and type members.</span></span>

> [!NOTE]
> <span data-ttu-id="4ab45-106">Non è possibile applicare a uno spazio dei nomi i commenti relativi alla documentazione.</span><span class="sxs-lookup"><span data-stu-id="4ab45-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="4ab45-107">Il compilatore elabora tutti i tag validi per XML.</span><span class="sxs-lookup"><span data-stu-id="4ab45-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="4ab45-108">I tag seguenti forniscono le funzionalità comunemente usate nella documentazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="4ab45-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="4ab45-109">Tag</span><span class="sxs-lookup"><span data-stu-id="4ab45-109">Tags</span></span>  
  
|||||  
|---|---|---|---|
|[<span data-ttu-id="4ab45-110">\<c></span><span class="sxs-lookup"><span data-stu-id="4ab45-110">\<c></span></span>](./code-inline.md)|[<span data-ttu-id="4ab45-111">\<para></span><span class="sxs-lookup"><span data-stu-id="4ab45-111">\<para></span></span>](./para.md)|<span data-ttu-id="4ab45-112">[\<vedi>](./see.md)\*</span><span class="sxs-lookup"><span data-stu-id="4ab45-112">[\<see>](./see.md)\*</span></span>|[<span data-ttu-id="4ab45-113">\<valore></span><span class="sxs-lookup"><span data-stu-id="4ab45-113">\<value></span></span>](./value.md)  
|[<span data-ttu-id="4ab45-114">\<>del codice</span><span class="sxs-lookup"><span data-stu-id="4ab45-114">\<code></span></span>](./code.md)|<span data-ttu-id="4ab45-115">[\<>param](./param.md)\*</span><span class="sxs-lookup"><span data-stu-id="4ab45-115">[\<param>](./param.md)\*</span></span>|<span data-ttu-id="4ab45-116">[\<vedianche>](./seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="4ab45-116">[\<seealso>](./seealso.md)\*</span></span>|  
|[<span data-ttu-id="4ab45-117">\<esempio></span><span class="sxs-lookup"><span data-stu-id="4ab45-117">\<example></span></span>](./example.md)|[<span data-ttu-id="4ab45-118">\<>paramref</span><span class="sxs-lookup"><span data-stu-id="4ab45-118">\<paramref></span></span>](./paramref.md)|[<span data-ttu-id="4ab45-119">\<>riepilogativo</span><span class="sxs-lookup"><span data-stu-id="4ab45-119">\<summary></span></span>](./summary.md)|  
|<span data-ttu-id="4ab45-120">[\<eccezione>](./exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="4ab45-120">[\<exception>](./exception.md)\*</span></span>|<span data-ttu-id="4ab45-121">[\<>di autorizzazione](./permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="4ab45-121">[\<permission>](./permission.md)\*</span></span>|<span data-ttu-id="4ab45-122">[\<>typeparam](./typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="4ab45-122">[\<typeparam>](./typeparam.md)\*</span></span>|  
|<span data-ttu-id="4ab45-123">[\<includere>](./include.md)\*</span><span class="sxs-lookup"><span data-stu-id="4ab45-123">[\<include>](./include.md)\*</span></span>|[<span data-ttu-id="4ab45-124">\<osservazioni></span><span class="sxs-lookup"><span data-stu-id="4ab45-124">\<remarks></span></span>](./remarks.md)|[<span data-ttu-id="4ab45-125">\<>typeparamref</span><span class="sxs-lookup"><span data-stu-id="4ab45-125">\<typeparamref></span></span>](./typeparamref.md)|  
|[<span data-ttu-id="4ab45-126">\<elenco></span><span class="sxs-lookup"><span data-stu-id="4ab45-126">\<list></span></span>](./list.md)|[<span data-ttu-id="4ab45-127">\<ereditadoc></span><span class="sxs-lookup"><span data-stu-id="4ab45-127">\<inheritdoc></span></span>](./inheritdoc.md)|[<span data-ttu-id="4ab45-128">\<restituisce></span><span class="sxs-lookup"><span data-stu-id="4ab45-128">\<returns></span></span>](./returns.md)|
  
<span data-ttu-id="4ab45-129">(indica\* che il compilatore verifica la sintassi.)</span><span class="sxs-lookup"><span data-stu-id="4ab45-129">(\* denotes that the compiler verifies syntax.)</span></span>

<span data-ttu-id="4ab45-130">Se si vuole che nel testo di un commento alla documentazione vengano visualizzate parentesi angolari, usare la codifica HTML di `<` e `>`, ovvero rispettivamente `&lt;` e `&gt;`.</span><span class="sxs-lookup"><span data-stu-id="4ab45-130">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="4ab45-131">Questa codifica è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4ab45-131">This encoding is shown in the following example.</span></span>

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a><span data-ttu-id="4ab45-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ab45-132">See also</span></span>

- [<span data-ttu-id="4ab45-133">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="4ab45-133">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="4ab45-134">-doc (opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="4ab45-134">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="4ab45-135">Commenti relativi alla documentazione XML</span><span class="sxs-lookup"><span data-stu-id="4ab45-135">XML documentation comments</span></span>](./index.md)
