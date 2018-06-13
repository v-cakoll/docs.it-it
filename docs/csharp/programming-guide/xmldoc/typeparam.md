---
title: '&lt;typeparam&gt; (Guida per programmatori C#)'
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 8c7fc1aba05af731d3df80e0b10c2981b5784197
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348778"
---
# <a name="lttypeparamgt-c-programming-guide"></a><span data-ttu-id="5c602-102">&lt;typeparam&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="5c602-102">&lt;typeparam&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="5c602-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c602-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c602-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c602-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="5c602-105">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="5c602-105">The name of the type parameter.</span></span> <span data-ttu-id="5c602-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="5c602-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="5c602-107">Descrizione del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="5c602-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c602-108">Note</span><span class="sxs-lookup"><span data-stu-id="5c602-108">Remarks</span></span>  
 <span data-ttu-id="5c602-109">Il tag `<typeparam>` deve essere usato nel commento per una dichiarazione di tipo o metodo generico per descrivere un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="5c602-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="5c602-110">Aggiungere un tag per ogni parametro di tipo del tipo o del metodo generico.</span><span class="sxs-lookup"><span data-stu-id="5c602-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="5c602-111">Per altre informazioni, vedere [Generics](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="5c602-111">For more information, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="5c602-112">Il testo del tag `<typeparam>` verrà visualizzato in IntelliSense, nella [finestra Visualizzatore oggetti](http://msdn.microsoft.com/library/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) e nel report Web sui commenti del codice.</span><span class="sxs-lookup"><span data-stu-id="5c602-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](http://msdn.microsoft.com/library/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) code comment web report.</span></span>  
  
 <span data-ttu-id="5c602-113">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="5c602-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c602-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c602-114">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="5c602-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c602-115">See Also</span></span>  
 [<span data-ttu-id="5c602-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="5c602-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5c602-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5c602-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5c602-118">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="5c602-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
