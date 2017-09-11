---
title: '&lt;typeparam&gt; (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeparam
dev_langs:
- CSharp
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8bb1d13976cf2cc9df4f573702168c6abdfff3d5
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="lttypeparamgt-c-programming-guide"></a><span data-ttu-id="bcf81-102">&lt;typeparam&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="bcf81-102">&lt;typeparam&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="bcf81-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bcf81-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bcf81-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="bcf81-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="bcf81-105">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="bcf81-105">The name of the type parameter.</span></span> <span data-ttu-id="bcf81-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="bcf81-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="bcf81-107">Descrizione del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="bcf81-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcf81-108">Note</span><span class="sxs-lookup"><span data-stu-id="bcf81-108">Remarks</span></span>  
 <span data-ttu-id="bcf81-109">Il tag `<typeparam>` deve essere usato nel commento per una dichiarazione di tipo o metodo generico per descrivere un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="bcf81-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="bcf81-110">Aggiungere un tag per ogni parametro di tipo del tipo o del metodo generico.</span><span class="sxs-lookup"><span data-stu-id="bcf81-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="bcf81-111">Per altre informazioni, vedere [Generics](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="bcf81-111">For more information, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="bcf81-112">Il testo del tag `<typeparam>` verrà visualizzato in IntelliSense, nella [finestra Visualizzatore oggetti](http://msdn.microsoft.com/en-us/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) e nel report Web sui commenti del codice.</span><span class="sxs-lookup"><span data-stu-id="bcf81-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](http://msdn.microsoft.com/en-us/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) code comment web report.</span></span>  
  
 <span data-ttu-id="bcf81-113">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="bcf81-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcf81-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="bcf81-114">Example</span></span>  
 <span data-ttu-id="bcf81-115">[!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bcf81-115">[!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcf81-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcf81-116">See Also</span></span>  
 <span data-ttu-id="bcf81-117">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bcf81-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bcf81-118">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bcf81-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="bcf81-119">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="bcf81-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

