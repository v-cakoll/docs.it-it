---
title: <typeparam> - Guida alla programmazione in C
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 867ecacf58f95533395ded203a8f17bc92558ccf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793357"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="388b5-102">\<> typeparam (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="388b5-102">\<typeparam> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="388b5-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="388b5-103">Syntax</span></span>

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a><span data-ttu-id="388b5-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="388b5-104">Parameters</span></span>

- `name`

  <span data-ttu-id="388b5-105">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="388b5-105">The name of the type parameter.</span></span> <span data-ttu-id="388b5-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="388b5-106">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="388b5-107">Descrizione del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="388b5-107">A description for the type parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="388b5-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="388b5-108">Remarks</span></span>

<span data-ttu-id="388b5-109">Il tag `<typeparam>` deve essere usato nel commento per una dichiarazione di tipo o metodo generico per descrivere un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="388b5-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="388b5-110">Aggiungere un tag per ogni parametro di tipo del tipo o del metodo generico.</span><span class="sxs-lookup"><span data-stu-id="388b5-110">Add a tag for each type parameter of the generic type or method.</span></span>

<span data-ttu-id="388b5-111">Per altre informazioni, vedere [Generics](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="388b5-111">For more information, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="388b5-112">Il testo del tag `<typeparam>` verrà visualizzato in IntelliSense, nella [finestra Visualizzatore oggetti](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) e nel report Web sui commenti del codice.</span><span class="sxs-lookup"><span data-stu-id="388b5-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>

<span data-ttu-id="388b5-113">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="388b5-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="388b5-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="388b5-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="388b5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="388b5-115">See also</span></span>

- [<span data-ttu-id="388b5-116">Informazioni di riferimento su C#</span><span class="sxs-lookup"><span data-stu-id="388b5-116">C# reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="388b5-117">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="388b5-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="388b5-118">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="388b5-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
