---
title: <remarks> - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: b2e91b868c35773033418c796b7c43b08e87a28b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480377"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="53f1f-102">\<remarks> (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="53f1f-102">\<remarks> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="53f1f-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53f1f-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="53f1f-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="53f1f-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="53f1f-105">Descrizione del membro.</span><span class="sxs-lookup"><span data-stu-id="53f1f-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53f1f-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="53f1f-106">Remarks</span></span>  
 <span data-ttu-id="53f1f-107">Il tag \<remarks> viene usato per aggiungere informazioni su un tipo, integrando le informazioni con [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="53f1f-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span></span> <span data-ttu-id="53f1f-108">Queste informazioni vengono visualizzate nella finestra Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="53f1f-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="53f1f-109">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="53f1f-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53f1f-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="53f1f-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="53f1f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53f1f-111">See also</span></span>

- [<span data-ttu-id="53f1f-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="53f1f-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="53f1f-113">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="53f1f-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
