---
title: '&lt;typeparam&gt; (Guida per programmatori C#)'
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: ec19060008c1c06c54c89dbddee7d24001bcdebc
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187114"
---
# <a name="lttypeparamgt-c-programming-guide"></a><span data-ttu-id="0a692-102">&lt;typeparam&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="0a692-102">&lt;typeparam&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="0a692-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a692-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a692-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="0a692-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="0a692-105">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="0a692-105">The name of the type parameter.</span></span> <span data-ttu-id="0a692-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="0a692-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="0a692-107">Descrizione del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="0a692-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a692-108">Note</span><span class="sxs-lookup"><span data-stu-id="0a692-108">Remarks</span></span>  
 <span data-ttu-id="0a692-109">Il tag `<typeparam>` deve essere usato nel commento per una dichiarazione di tipo o metodo generico per descrivere un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="0a692-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="0a692-110">Aggiungere un tag per ogni parametro di tipo del tipo o del metodo generico.</span><span class="sxs-lookup"><span data-stu-id="0a692-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="0a692-111">Per altre informazioni, vedere [Generics](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="0a692-111">For more information, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="0a692-112">Il testo del tag `<typeparam>` verrà visualizzato in IntelliSense, nella [finestra Visualizzatore oggetti](https://msdn.microsoft.com/library/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) e nel report Web sui commenti del codice.</span><span class="sxs-lookup"><span data-stu-id="0a692-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](https://msdn.microsoft.com/library/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) code comment web report.</span></span>  
  
 <span data-ttu-id="0a692-113">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="0a692-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a692-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="0a692-114">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0a692-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a692-115">See Also</span></span>

- [<span data-ttu-id="0a692-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="0a692-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="0a692-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0a692-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="0a692-118">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="0a692-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
