---
title: <see>- Guida alla programmazione in C
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: f4834f88c646b44269f8290c2ad08698c34e714a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77627672"
---
# <a name="see-c-programming-guide"></a><span data-ttu-id="5d587-102">\<Vedere> (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="5d587-102">\<see> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="5d587-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d587-103">Syntax</span></span>

```xml
<see cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="5d587-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="5d587-104">Parameters</span></span>

- <span data-ttu-id="5d587-105">cref -`member`" "</span><span class="sxs-lookup"><span data-stu-id="5d587-105">cref = "`member`"</span></span>

  <span data-ttu-id="5d587-106">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="5d587-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="5d587-107">Il compilatore verifica l'esistenza dell'elemento di codice specificato e passa `member` al nome dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="5d587-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="5d587-108">Racchiudere *member* tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="5d587-108">Place *member* within double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="5d587-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5d587-109">Remarks</span></span>

<span data-ttu-id="5d587-110">Con il tag \<see> è possibile specificare un collegamento nel testo.</span><span class="sxs-lookup"><span data-stu-id="5d587-110">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="5d587-111">Utilizzate [ \<anche see>](./seealso.md) per indicare che il testo deve essere inserito in una sezione Vedere anche.</span><span class="sxs-lookup"><span data-stu-id="5d587-111">Use [\<seealso>](./seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="5d587-112">Usare l'[attributo cref](./cref-attribute.md) per creare collegamenti ipertestuali interni alle pagine della documentazione per gli elementi di codice.</span><span class="sxs-lookup"><span data-stu-id="5d587-112">Use the [cref Attribute](./cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>

<span data-ttu-id="5d587-113">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="5d587-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="5d587-114">Nell'esempio seguente viene illustrato un tag \<see> all'interno di una sezione di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="5d587-114">The following example shows a \<see> tag within a summary section.</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a><span data-ttu-id="5d587-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d587-115">See also</span></span>

- [<span data-ttu-id="5d587-116">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="5d587-116">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="5d587-117">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="5d587-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
