---
title: Parola chiave this - Riferimenti per C#
description: Parola chiave this (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
ms.openlocfilehash: 2a2c487ad93e6fc75ecf95c541e859b8b60bb5b5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715113"
---
# <a name="this-c-reference"></a><span data-ttu-id="34fbc-103">this (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="34fbc-103">this (C# Reference)</span></span>

<span data-ttu-id="34fbc-104">La parola chiave `this` fa riferimento all'istanza corrente della classe e viene anche usata come modificatore del primo parametro di un metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="34fbc-104">The `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.</span></span>

> [!NOTE]
> <span data-ttu-id="34fbc-105">Questo articolo illustra l'uso di `this` con istanze della classe.</span><span class="sxs-lookup"><span data-stu-id="34fbc-105">This article discusses the use of `this` with class instances.</span></span> <span data-ttu-id="34fbc-106">Per altre informazioni sull'uso nei metodi di estensione, vedere [Metodi di estensione](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="34fbc-106">For more information about its use in extension methods, see [Extension Methods](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

<span data-ttu-id="34fbc-107">Di seguito sono riportati gli usi comuni di `this`:</span><span class="sxs-lookup"><span data-stu-id="34fbc-107">The following are common uses of `this`:</span></span>

- <span data-ttu-id="34fbc-108">Per qualificare i membri nascosti da nomi simili, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="34fbc-108">To qualify members hidden by similar names, for example:</span></span>

  [!code-csharp[csrefKeywordsAccess#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#4)]  

- <span data-ttu-id="34fbc-109">Per passare un oggetto come parametro ad altri metodi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="34fbc-109">To pass an object as a parameter to other methods, for example:</span></span>

  ```csharp
  CalcTax(this);
  ```

- <span data-ttu-id="34fbc-110">Per dichiarare gli indicizzatori, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="34fbc-110">To declare indexers, for example:</span></span>

  [!code-csharp[csrefKeywordsAccess#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#5)]

<span data-ttu-id="34fbc-111">Le funzioni del membro statico, perché esistono a livello di classe e non come parte di un oggetto, non dispongono di un puntatore `this`.</span><span class="sxs-lookup"><span data-stu-id="34fbc-111">Static member functions, because they exist at the class level and not as part of an object, do not have a `this` pointer.</span></span> <span data-ttu-id="34fbc-112">È un errore fare riferimento a `this` in un metodo statico.</span><span class="sxs-lookup"><span data-stu-id="34fbc-112">It is an error to refer to `this` in a static method.</span></span>

## <a name="example"></a><span data-ttu-id="34fbc-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="34fbc-113">Example</span></span>

<span data-ttu-id="34fbc-114">In questo esempio, `this` viene usato per qualificare i membri della classe `Employee`, `name` e `alias`, che sono nascosti da nomi simili.</span><span class="sxs-lookup"><span data-stu-id="34fbc-114">In this example, `this` is used to qualify the `Employee` class members, `name` and `alias`, which are hidden by similar names.</span></span> <span data-ttu-id="34fbc-115">Viene anche usato per passare un oggetto al metodo `CalcTax`, che appartiene a un'altra classe.</span><span class="sxs-lookup"><span data-stu-id="34fbc-115">It is also used to pass an object to the method `CalcTax`, which belongs to another class.</span></span>

[!code-csharp[csrefKeywordsAccess#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="34fbc-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="34fbc-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="34fbc-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34fbc-117">See also</span></span>

- [<span data-ttu-id="34fbc-118">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="34fbc-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="34fbc-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="34fbc-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="34fbc-120">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="34fbc-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="34fbc-121">base</span><span class="sxs-lookup"><span data-stu-id="34fbc-121">base</span></span>](base.md)
- [<span data-ttu-id="34fbc-122">Metodi</span><span class="sxs-lookup"><span data-stu-id="34fbc-122">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
