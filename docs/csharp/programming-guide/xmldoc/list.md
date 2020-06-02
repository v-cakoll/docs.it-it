---
title: <list> -Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 78eec992671dab1aa59717a007a8e3a2662f6e87
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287337"
---
# <a name="list-c-programming-guide"></a><span data-ttu-id="2296b-102">\<list>(Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="2296b-102">\<list> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="2296b-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2296b-103">Syntax</span></span>

```xml
<list type="bullet|number|table">
    <listheader>
        <term>term</term>
        <description>description</description>
    </listheader>
    <item>
        <term>term</term>
        <description>description</description>
    </item>
</list>
```

## <a name="parameters"></a><span data-ttu-id="2296b-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="2296b-104">Parameters</span></span>

- `term`

  <span data-ttu-id="2296b-105">Termine da definire, che verrà definito in `description`.</span><span class="sxs-lookup"><span data-stu-id="2296b-105">A term to define, which will be defined in `description`.</span></span>

- `description`

  <span data-ttu-id="2296b-106">Elemento di un elenco puntato o numerato oppure la definizione di un `term`.</span><span class="sxs-lookup"><span data-stu-id="2296b-106">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2296b-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2296b-107">Remarks</span></span>

<span data-ttu-id="2296b-108">Il `<listheader>` blocco viene utilizzato per definire la riga di intestazione di un elenco di tabelle o definizioni.</span><span class="sxs-lookup"><span data-stu-id="2296b-108">The `<listheader>` block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="2296b-109">Per definire una tabella, è sufficiente specificare una voce per il termine nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="2296b-109">When defining a table, you only need to supply an entry for term in the heading.</span></span>

<span data-ttu-id="2296b-110">Ogni elemento nell'elenco viene specificato con un `<item>` blocco.</span><span class="sxs-lookup"><span data-stu-id="2296b-110">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="2296b-111">Quando si crea un elenco di definizioni, è necessario specificare sia `term` che `description`.</span><span class="sxs-lookup"><span data-stu-id="2296b-111">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="2296b-112">Per le tabelle e gli elenchi puntati o numerati, tuttavia, è sufficiente fornire una voce per `description`.</span><span class="sxs-lookup"><span data-stu-id="2296b-112">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>

<span data-ttu-id="2296b-113">Un elenco o una tabella può includere un numero di `<item>` blocchi sufficiente.</span><span class="sxs-lookup"><span data-stu-id="2296b-113">A list or table can have as many `<item>` blocks as needed.</span></span>

<span data-ttu-id="2296b-114">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="2296b-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="2296b-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="2296b-115">Example</span></span>

[!code-csharp[csProgGuideDocComments#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#6)]

## <a name="see-also"></a><span data-ttu-id="2296b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2296b-116">See also</span></span>

- [<span data-ttu-id="2296b-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2296b-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="2296b-118">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="2296b-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
