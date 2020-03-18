---
title: <inheritdoc> - Guida per programmatori C#
ms.date: 01/21/2020
f1_keywords:
- inheritdoc
- <inheritdoc>
helpviewer_keywords:
- <inheritdoc> C# XML tag
- inheritdoc C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 6f42462f21d045428577cd2123e2180d866f1e1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156948"
---
# <a name="inheritdoc-c-programming-guide"></a><span data-ttu-id="841b7-102">\<> inheritdoc (Guida per programmatori C</span><span class="sxs-lookup"><span data-stu-id="841b7-102">\<inheritdoc> (C# Programming Guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="841b7-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="841b7-103">Syntax</span></span>  
  
```xml  
<inheritdoc/>
```  

## <a name="inheritdoc"></a><span data-ttu-id="841b7-104">EreditatoreDoc</span><span class="sxs-lookup"><span data-stu-id="841b7-104">InheritDoc</span></span>

<span data-ttu-id="841b7-105">Ereditare i commenti XML dalle classi base, dalle interfacce e da metodi simili.</span><span class="sxs-lookup"><span data-stu-id="841b7-105">Inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="841b7-106">In questo modo si eliminano le operazioni di copia e incolla indesiderate di commenti XML duplicati e mantiene automaticamente sincronizzati i commenti XML.</span><span class="sxs-lookup"><span data-stu-id="841b7-106">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="841b7-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="841b7-107">Remarks</span></span>  
<span data-ttu-id="841b7-108">Aggiungere i commenti XML nelle classi di base o nelle interfacce e consentire a InheritDoc di copiare i commenti nelle classi di implementazione.</span><span class="sxs-lookup"><span data-stu-id="841b7-108">Add your XML comments in base classes or interfaces and let InheritDoc copy the comments to implementing classes.</span></span>

<span data-ttu-id="841b7-109">Aggiungere i commenti XML ai metodi sincroni e consentire a InheritDoc di copiare i commenti nelle versioni asincrone degli stessi metodi.</span><span class="sxs-lookup"><span data-stu-id="841b7-109">Add your XML comments to your synchronous methods and let InheritDoc copy the comments to your asynchronous versions of the same methods.</span></span>  

<span data-ttu-id="841b7-110">Se si desidera copiare i commenti da un `cref` membro specifico, è possibile utilizzare l'attributo per specificare il membro.</span><span class="sxs-lookup"><span data-stu-id="841b7-110">If you want to copy the comments from a specific member you can use the `cref` attribute to specify the member.</span></span>
  
## <a name="examples"></a><span data-ttu-id="841b7-111">Esempi</span><span class="sxs-lookup"><span data-stu-id="841b7-111">Examples</span></span>
[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a><span data-ttu-id="841b7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="841b7-112">See also</span></span>

- [<span data-ttu-id="841b7-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="841b7-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="841b7-114">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="841b7-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
