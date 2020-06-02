---
title: <remarks> -Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: 739027786e02e559d86f990bf614e261b497c76f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287285"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="e0e19-102">\<remarks>(Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e0e19-102">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="e0e19-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0e19-103">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="e0e19-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="e0e19-104">Parameters</span></span>

- `Description`

  <span data-ttu-id="e0e19-105">Descrizione del membro.</span><span class="sxs-lookup"><span data-stu-id="e0e19-105">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="e0e19-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e0e19-106">Remarks</span></span>

<span data-ttu-id="e0e19-107">Il `<remarks>` tag viene usato per aggiungere informazioni su un tipo, integrando le informazioni specificate con [\<summary>](./summary.md) .</span><span class="sxs-lookup"><span data-stu-id="e0e19-107">The `<remarks>` tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="e0e19-108">Queste informazioni vengono visualizzate nella finestra Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="e0e19-108">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="e0e19-109">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="e0e19-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="e0e19-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="e0e19-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="e0e19-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0e19-111">See also</span></span>

- [<span data-ttu-id="e0e19-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e0e19-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e0e19-113">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="e0e19-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
