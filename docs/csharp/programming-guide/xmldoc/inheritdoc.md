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
ms.openlocfilehash: d660cb1739733c4e98ae0b7939476fe74e6cf200
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76795161"
---
# <a name="inheritdoc-c-programming-guide"></a><span data-ttu-id="7978a-102">> inheritdoc \<(C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="7978a-102">\<inheritdoc> (C# Programming Guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="7978a-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7978a-103">Syntax</span></span>  
  
```xml  
<inheritdoc/> 
```  

## <a name="inheritdoc"></a><span data-ttu-id="7978a-104">InheritDoc</span><span class="sxs-lookup"><span data-stu-id="7978a-104">InheritDoc</span></span>

<span data-ttu-id="7978a-105">Ereditano commenti XML da classi base, interfacce e metodi simili.</span><span class="sxs-lookup"><span data-stu-id="7978a-105">Inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="7978a-106">In questo modo si elimina la copia indesiderata e si incollano i commenti XML duplicati e i commenti XML vengono sincronizzati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7978a-106">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="7978a-107">Note</span><span class="sxs-lookup"><span data-stu-id="7978a-107">Remarks</span></span>  
<span data-ttu-id="7978a-108">Aggiungere i commenti XML in classi o interfacce di base e consentire a InheritDoc di copiare i commenti alle classi di implementazione.</span><span class="sxs-lookup"><span data-stu-id="7978a-108">Add your XML comments in base classes or interfaces and let InheritDoc copy the comments to implementing classes.</span></span>

<span data-ttu-id="7978a-109">Aggiungere i commenti XML ai metodi sincroni e consentire a InheritDoc di copiare i commenti nelle versioni asincrone degli stessi metodi.</span><span class="sxs-lookup"><span data-stu-id="7978a-109">Add your XML comments to your synchronous methods and let InheritDoc copy the comments to your asynchronous versions of the same methods.</span></span>  

<span data-ttu-id="7978a-110">Se si desidera copiare i commenti da un membro specifico, è possibile utilizzare l'attributo `cref` per specificare il membro.</span><span class="sxs-lookup"><span data-stu-id="7978a-110">If you want to copy the comments from a specific member you can use the `cref` attribute to specify the member.</span></span>
  
## <a name="examples"></a><span data-ttu-id="7978a-111">Esempi</span><span class="sxs-lookup"><span data-stu-id="7978a-111">Examples</span></span>
[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a><span data-ttu-id="7978a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7978a-112">See also</span></span>

- [<span data-ttu-id="7978a-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7978a-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7978a-114">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="7978a-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
