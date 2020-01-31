---
title: Tag consigliati per i commenti relativi C# alla documentazione-Guida alla programmazione
ms.date: 01/21/2020
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: c746615d0d7a7a3058fbe2f8506a7a7c5c4a8779
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789717"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="693b4-102">Tag consigliati per i commenti relativiC# alla documentazione (Guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="693b4-102">Recommended tags for documentation comments (C# programming guide)</span></span>

<span data-ttu-id="693b4-103">Il compilatore C# elabora i commenti alla documentazione nel codice e li formatta come XML in un file il cui nome è stato specificato nell'opzione della riga di comando **/doc**.</span><span class="sxs-lookup"><span data-stu-id="693b4-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="693b4-104">Per creare la documentazione finale basata sul file generato dal compilatore, è possibile creare uno strumento personalizzato o usare uno strumento come [DocFX](https://dotnet.github.io/docfx/) o [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="693b4-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="693b4-105">I tag vengono elaborati in costrutti di codice come tipi e membri dei tipi.</span><span class="sxs-lookup"><span data-stu-id="693b4-105">Tags are processed on code constructs such as types and type members.</span></span>

> [!NOTE]
> <span data-ttu-id="693b4-106">Non è possibile applicare a uno spazio dei nomi i commenti relativi alla documentazione.</span><span class="sxs-lookup"><span data-stu-id="693b4-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="693b4-107">Il compilatore elabora tutti i tag validi per XML.</span><span class="sxs-lookup"><span data-stu-id="693b4-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="693b4-108">I tag seguenti forniscono le funzionalità comunemente usate nella documentazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="693b4-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="693b4-109">Tag</span><span class="sxs-lookup"><span data-stu-id="693b4-109">Tags</span></span>  
  
|||||  
|---|---|---|---|
|[<span data-ttu-id="693b4-110">\<c></span><span class="sxs-lookup"><span data-stu-id="693b4-110">\<c></span></span>](./code-inline.md)|[<span data-ttu-id="693b4-111">\<para></span><span class="sxs-lookup"><span data-stu-id="693b4-111">\<para></span></span>](./para.md)|<span data-ttu-id="693b4-112">[\<see>](./see.md)\*</span><span class="sxs-lookup"><span data-stu-id="693b4-112">[\<see>](./see.md)\*</span></span>|[<span data-ttu-id="693b4-113">\<value></span><span class="sxs-lookup"><span data-stu-id="693b4-113">\<value></span></span>](./value.md)  
|[<span data-ttu-id="693b4-114">\<code></span><span class="sxs-lookup"><span data-stu-id="693b4-114">\<code></span></span>](./code.md)|<span data-ttu-id="693b4-115">[\<param>](./param.md)\*</span><span class="sxs-lookup"><span data-stu-id="693b4-115">[\<param>](./param.md)\*</span></span>|<span data-ttu-id="693b4-116">[\<seealso>](./seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="693b4-116">[\<seealso>](./seealso.md)\*</span></span>|  
|[<span data-ttu-id="693b4-117">\<example></span><span class="sxs-lookup"><span data-stu-id="693b4-117">\<example></span></span>](./example.md)|[<span data-ttu-id="693b4-118">\<paramref></span><span class="sxs-lookup"><span data-stu-id="693b4-118">\<paramref></span></span>](./paramref.md)|[<span data-ttu-id="693b4-119">\<summary></span><span class="sxs-lookup"><span data-stu-id="693b4-119">\<summary></span></span>](./summary.md)|  
|<span data-ttu-id="693b4-120">[\<exception>](./exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="693b4-120">[\<exception>](./exception.md)\*</span></span>|<span data-ttu-id="693b4-121">[\<permission>](./permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="693b4-121">[\<permission>](./permission.md)\*</span></span>|<span data-ttu-id="693b4-122">[\<typeparam>](./typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="693b4-122">[\<typeparam>](./typeparam.md)\*</span></span>|  
|<span data-ttu-id="693b4-123">[\<include>](./include.md)\*</span><span class="sxs-lookup"><span data-stu-id="693b4-123">[\<include>](./include.md)\*</span></span>|[<span data-ttu-id="693b4-124">\<remarks></span><span class="sxs-lookup"><span data-stu-id="693b4-124">\<remarks></span></span>](./remarks.md)|[<span data-ttu-id="693b4-125">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="693b4-125">\<typeparamref></span></span>](./typeparamref.md)|  
|[<span data-ttu-id="693b4-126">\<list></span><span class="sxs-lookup"><span data-stu-id="693b4-126">\<list></span></span>](./list.md)|[<span data-ttu-id="693b4-127">\<inheritdoc ></span><span class="sxs-lookup"><span data-stu-id="693b4-127">\<inheritdoc></span></span>](./inheritdoc.md)|[<span data-ttu-id="693b4-128">\<returns></span><span class="sxs-lookup"><span data-stu-id="693b4-128">\<returns></span></span>](./returns.md)|
  
<span data-ttu-id="693b4-129">(\* indica che il compilatore verifica la sintassi).</span><span class="sxs-lookup"><span data-stu-id="693b4-129">(\* denotes that the compiler verifies syntax.)</span></span>

<span data-ttu-id="693b4-130">Se si vuole che nel testo di un commento alla documentazione vengano visualizzate parentesi angolari, usare la codifica HTML di `<` e `>`, ovvero rispettivamente `&lt;` e `&gt;`.</span><span class="sxs-lookup"><span data-stu-id="693b4-130">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="693b4-131">Questa codifica è illustrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="693b4-131">This encoding is shown in the following example.</span></span>

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a><span data-ttu-id="693b4-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="693b4-132">See also</span></span>

- [<span data-ttu-id="693b4-133">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="693b4-133">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="693b4-134">-DOC (C# opzioni del compilatore)</span><span class="sxs-lookup"><span data-stu-id="693b4-134">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="693b4-135">Commenti relativi alla documentazione XML</span><span class="sxs-lookup"><span data-stu-id="693b4-135">XML documentation comments</span></span>](./index.md)
