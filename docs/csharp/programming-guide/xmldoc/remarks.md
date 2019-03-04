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
ms.openlocfilehash: 3e6625c55a6f5c29fb55bff2eb87959f3237652e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975850"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="dfffc-102">\<remarks> (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="dfffc-102">\<remarks> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="dfffc-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dfffc-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dfffc-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="dfffc-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="dfffc-105">Descrizione del membro.</span><span class="sxs-lookup"><span data-stu-id="dfffc-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfffc-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dfffc-106">Remarks</span></span>  
 <span data-ttu-id="dfffc-107">Il tag \<remarks> viene usato per aggiungere informazioni su un tipo, integrando le informazioni con [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="dfffc-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span></span> <span data-ttu-id="dfffc-108">Queste informazioni vengono visualizzate nella finestra Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="dfffc-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="dfffc-109">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="dfffc-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfffc-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="dfffc-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="dfffc-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfffc-111">See also</span></span>

- [<span data-ttu-id="dfffc-112">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="dfffc-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="dfffc-113">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="dfffc-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
