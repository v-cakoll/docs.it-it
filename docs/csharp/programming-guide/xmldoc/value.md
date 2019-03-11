---
title: <value> - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 7f82008d000bf0316b505bfc5d40e9e64b2685a3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465193"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="90b14-102">\<value> (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="90b14-102">\<value> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="90b14-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90b14-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="90b14-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="90b14-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="90b14-105">Descrizione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="90b14-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90b14-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="90b14-106">Remarks</span></span>  
 <span data-ttu-id="90b14-107">Il tag \<value> consente di descrivere il valore che rappresenta una proprietà.</span><span class="sxs-lookup"><span data-stu-id="90b14-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="90b14-108">Si noti che quando si aggiunge una proprietà tramite la procedura guidata per il codice nell'ambiente di sviluppo di Visual Studio .NET, verrà aggiunto un tag [ \<summary>](../../../csharp/programming-guide/xmldoc/summary.md) per la nuova proprietà.</span><span class="sxs-lookup"><span data-stu-id="90b14-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="90b14-109">È quindi necessario aggiungere manualmente un tag \<value> per descrivere il valore rappresentato dalla proprietà.</span><span class="sxs-lookup"><span data-stu-id="90b14-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="90b14-110">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="90b14-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90b14-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="90b14-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]  
  
## <a name="see-also"></a><span data-ttu-id="90b14-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90b14-112">See also</span></span>

- [<span data-ttu-id="90b14-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="90b14-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="90b14-114">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="90b14-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
