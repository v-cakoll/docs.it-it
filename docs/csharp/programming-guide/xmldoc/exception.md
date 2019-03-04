---
title: <exception> - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: b316927c5dfd5eda05bea653f9a601cca9865af3
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982063"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="723f8-102">\<exception> (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="723f8-102">\<exception> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="723f8-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="723f8-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="723f8-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="723f8-104">Parameters</span></span>  
 <span data-ttu-id="723f8-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="723f8-105">cref = " `member`"</span></span>  
 <span data-ttu-id="723f8-106">Riferimento ad un'eccezione disponibile dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="723f8-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="723f8-107">Il compilatore controlla che l'eccezione specificata esista e converte `member` nel nome canonico dell'elemento nel file XML di output.</span><span class="sxs-lookup"><span data-stu-id="723f8-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="723f8-108">`member` deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="723f8-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="723f8-109">Per altre informazioni su come creare un riferimento cref a un tipo generico, vedere [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="723f8-109">For more information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="723f8-110">Descrizione dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="723f8-110">A description of the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="723f8-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="723f8-111">Remarks</span></span>  
 <span data-ttu-id="723f8-112">Il tag \<exception> consente di specificare le eccezioni che possono essere generate.</span><span class="sxs-lookup"><span data-stu-id="723f8-112">The \<exception> tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="723f8-113">Questo tag può essere applicato alle definizioni di metodi, proprietà, eventi e indicizzatori.</span><span class="sxs-lookup"><span data-stu-id="723f8-113">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>  
  
 <span data-ttu-id="723f8-114">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="723f8-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="723f8-115">Per altre informazioni sulla gestione delle eccezioni, vedere [Eccezioni e gestione delle eccezioni](../../../csharp/programming-guide/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="723f8-115">For more information about exception handling, see [Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="723f8-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="723f8-116">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="723f8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="723f8-117">See also</span></span>

- [<span data-ttu-id="723f8-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="723f8-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="723f8-119">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="723f8-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
