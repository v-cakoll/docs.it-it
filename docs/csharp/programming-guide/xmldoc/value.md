---
title: <value> - Guida alla programmazione in C
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 120805346672738e614743ab8c98388b8dbac0f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793355"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="4094b-102">\<> di valore (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="4094b-102">\<value> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="4094b-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4094b-103">Syntax</span></span>

```xml
<value>property-description</value>
```

## <a name="parameters"></a><span data-ttu-id="4094b-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="4094b-104">Parameters</span></span>

- `property-description`

  <span data-ttu-id="4094b-105">Descrizione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="4094b-105">A description for the property.</span></span>

## <a name="remarks"></a><span data-ttu-id="4094b-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4094b-106">Remarks</span></span>

<span data-ttu-id="4094b-107">Il tag \<value> consente di descrivere il valore che rappresenta una proprietà.</span><span class="sxs-lookup"><span data-stu-id="4094b-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="4094b-108">Si noti che quando si aggiunge una proprietà tramite la creazione [ \<](./summary.md) guidata codice nell'ambiente di sviluppo di Visual Studio .NET, verrà aggiunto un riepilogo>tag per la nuova proprietà.</span><span class="sxs-lookup"><span data-stu-id="4094b-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="4094b-109">È quindi necessario aggiungere manualmente un tag \<value> per descrivere il valore rappresentato dalla proprietà.</span><span class="sxs-lookup"><span data-stu-id="4094b-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>

<span data-ttu-id="4094b-110">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="4094b-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="4094b-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="4094b-111">Example</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a><span data-ttu-id="4094b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4094b-112">See also</span></span>

- [<span data-ttu-id="4094b-113">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="4094b-113">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="4094b-114">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="4094b-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
