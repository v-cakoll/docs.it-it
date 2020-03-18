---
title: <remarks> - Guida alla programmazione in C
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: e37dac9cb9fed1df6ca027f09f2c95dbbc8ea66d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793380"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="30bf5-102">\<osservazioni> (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="30bf5-102">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="30bf5-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30bf5-103">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="30bf5-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="30bf5-104">Parameters</span></span>

- `Description`

  <span data-ttu-id="30bf5-105">Descrizione del membro.</span><span class="sxs-lookup"><span data-stu-id="30bf5-105">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="30bf5-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="30bf5-106">Remarks</span></span>

<span data-ttu-id="30bf5-107">Il \<tag osservazioni> viene utilizzato per aggiungere informazioni su un tipo, integrando le informazioni specificate con [ \<>di riepilogo. ](./summary.md)</span><span class="sxs-lookup"><span data-stu-id="30bf5-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="30bf5-108">Queste informazioni vengono visualizzate nella finestra Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="30bf5-108">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="30bf5-109">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="30bf5-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="30bf5-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="30bf5-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="30bf5-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30bf5-111">See also</span></span>

- [<span data-ttu-id="30bf5-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="30bf5-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="30bf5-113">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="30bf5-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
