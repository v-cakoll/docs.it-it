---
title: <remarks> - C# Guida alla programmazione
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: e37dac9cb9fed1df6ca027f09f2c95dbbc8ea66d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793380"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="4982b-102">> osservazioni \<(C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="4982b-102">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="4982b-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4982b-103">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="4982b-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="4982b-104">Parameters</span></span>

- `Description`

  <span data-ttu-id="4982b-105">Descrizione del membro.</span><span class="sxs-lookup"><span data-stu-id="4982b-105">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="4982b-106">Note</span><span class="sxs-lookup"><span data-stu-id="4982b-106">Remarks</span></span>

<span data-ttu-id="4982b-107">Il tag \<remarks> viene usato per aggiungere informazioni su un tipo, integrando le informazioni con [\<summary>](./summary.md).</span><span class="sxs-lookup"><span data-stu-id="4982b-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="4982b-108">Queste informazioni vengono visualizzate nella finestra Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="4982b-108">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="4982b-109">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="4982b-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="4982b-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="4982b-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="4982b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4982b-111">See also</span></span>

- [<span data-ttu-id="4982b-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4982b-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4982b-113">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="4982b-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
