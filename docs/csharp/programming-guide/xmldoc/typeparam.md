---
title: '&lt;typeparam&gt; - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 21819bebbb304eaace3950f40b97033762cd6ce8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568049"
---
# <a name="lttypeparamgt-c-programming-guide"></a><span data-ttu-id="39208-102">&lt;typeparam&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="39208-102">&lt;typeparam&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="39208-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39208-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39208-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="39208-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="39208-105">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="39208-105">The name of the type parameter.</span></span> <span data-ttu-id="39208-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="39208-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="39208-107">Descrizione del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="39208-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39208-108">Note</span><span class="sxs-lookup"><span data-stu-id="39208-108">Remarks</span></span>  
 <span data-ttu-id="39208-109">Il tag `<typeparam>` deve essere usato nel commento per una dichiarazione di tipo o metodo generico per descrivere un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="39208-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="39208-110">Aggiungere un tag per ogni parametro di tipo del tipo o del metodo generico.</span><span class="sxs-lookup"><span data-stu-id="39208-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="39208-111">Per altre informazioni, vedere [Generics](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="39208-111">For more information, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="39208-112">Il testo del tag `<typeparam>` verrà visualizzato in IntelliSense, nella [finestra Visualizzatore oggetti](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) e nel report Web sui commenti del codice.</span><span class="sxs-lookup"><span data-stu-id="39208-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>  
  
 <span data-ttu-id="39208-113">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="39208-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39208-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="39208-114">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="39208-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39208-115">See also</span></span>

- [<span data-ttu-id="39208-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="39208-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="39208-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="39208-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="39208-118">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="39208-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
