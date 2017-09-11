---
title: '&lt;exception&gt; (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- exception
- <exception>
dev_langs:
- CSharp
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
caps.latest.revision: 16
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
ms.openlocfilehash: bdcbe116db4ed0f63ea73c524c482266b4ac1a38
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="ltexceptiongt-c-programming-guide"></a><span data-ttu-id="8970c-102">&lt;exception&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="8970c-102">&lt;exception&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="8970c-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8970c-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8970c-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="8970c-104">Parameters</span></span>  
 <span data-ttu-id="8970c-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="8970c-105">cref = " `member`"</span></span>  
 <span data-ttu-id="8970c-106">Riferimento ad un'eccezione disponibile dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="8970c-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="8970c-107">Il compilatore controlla che l'eccezione specificata esista e converte `member` nel nome canonico dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="8970c-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="8970c-108">`member` deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="8970c-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="8970c-109">Per altre informazioni su come creare un riferimento cref a un tipo generico, vedere [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="8970c-109">For more information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="8970c-110">Descrizione dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="8970c-110">A description of the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8970c-111">Note</span><span class="sxs-lookup"><span data-stu-id="8970c-111">Remarks</span></span>  
 <span data-ttu-id="8970c-112">Il tag \<exception> consente di specificare le eccezioni che possono essere generate.</span><span class="sxs-lookup"><span data-stu-id="8970c-112">The \<exception> tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="8970c-113">Questo tag può essere applicato alle definizioni di metodi, proprietà, eventi e indicizzatori.</span><span class="sxs-lookup"><span data-stu-id="8970c-113">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>  
  
 <span data-ttu-id="8970c-114">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="8970c-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="8970c-115">Per altre informazioni sulla gestione delle eccezioni, vedere [Eccezioni e gestione delle eccezioni](../../../csharp/programming-guide/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="8970c-115">For more information about exception handling, see [Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8970c-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="8970c-116">Example</span></span>  
 <span data-ttu-id="8970c-117">[!code-cs[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/exception_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8970c-117">[!code-cs[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/exception_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8970c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8970c-118">See Also</span></span>  
 <span data-ttu-id="8970c-119">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8970c-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="8970c-120">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="8970c-120">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

