---
title: '&lt;seealso&gt; (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 088445680375e1c1805f9fb4356fe98c730178e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltseealsogt-c-programming-guide"></a><span data-ttu-id="87a41-102">&lt;seealso&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="87a41-102">&lt;seealso&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="87a41-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87a41-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87a41-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="87a41-104">Parameters</span></span>  
 <span data-ttu-id="87a41-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="87a41-105">cref = " `member`"</span></span>  
 <span data-ttu-id="87a41-106">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="87a41-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="87a41-107">Il compilatore verifica l'esistenza dell'elemento di codice specificato e passa `member` al nome dell'elemento nel file XML di output. `member`</span><span class="sxs-lookup"><span data-stu-id="87a41-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="87a41-108">deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="87a41-108">must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="87a41-109">Per informazioni su come creare un riferimento cref a un tipo generico, vedere [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="87a41-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87a41-110">Note</span><span class="sxs-lookup"><span data-stu-id="87a41-110">Remarks</span></span>  
 <span data-ttu-id="87a41-111">Il tag \<seealso> consente di specificare il testo da visualizzare in una sezione Vedere anche.</span><span class="sxs-lookup"><span data-stu-id="87a41-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="87a41-112">Usare [\<see>](../../../csharp/programming-guide/xmldoc/see.md) per specificare un collegamento nel testo.</span><span class="sxs-lookup"><span data-stu-id="87a41-112">Use [\<see>](../../../csharp/programming-guide/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="87a41-113">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="87a41-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87a41-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="87a41-114">Example</span></span>  
 <span data-ttu-id="87a41-115">Per un esempio d'uso di \<seealso>, vedere [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="87a41-115">See [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) for an example of using \<seealso>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87a41-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87a41-116">See Also</span></span>  
 [<span data-ttu-id="87a41-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="87a41-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="87a41-118">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="87a41-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
