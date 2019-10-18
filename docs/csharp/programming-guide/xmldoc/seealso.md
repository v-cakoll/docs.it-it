---
title: <seealso> - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
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
ms.openlocfilehash: 430270c170f2829d9bf9b90d258c948176b9c086
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523322"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="70ce9-102">\<seealso> (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="70ce9-102">\<seealso> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="70ce9-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="70ce9-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="70ce9-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="70ce9-104">Parameters</span></span>  
 <span data-ttu-id="70ce9-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="70ce9-105">cref = " `member`"</span></span>  
 <span data-ttu-id="70ce9-106">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="70ce9-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="70ce9-107">Il compilatore verifica l'esistenza dell'elemento di codice specificato e passa `member` al nome dell'elemento nel file XML di output. `member`</span><span class="sxs-lookup"><span data-stu-id="70ce9-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="70ce9-108">deve essere racchiuso tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="70ce9-108">must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="70ce9-109">Per informazioni su come creare un riferimento cref a un tipo generico, vedere [\<see>](./see.md).</span><span class="sxs-lookup"><span data-stu-id="70ce9-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70ce9-110">Note</span><span class="sxs-lookup"><span data-stu-id="70ce9-110">Remarks</span></span>  
 <span data-ttu-id="70ce9-111">Il tag \<seealso> consente di specificare il testo da visualizzare in una sezione Vedere anche.</span><span class="sxs-lookup"><span data-stu-id="70ce9-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="70ce9-112">Usare [\<see>](./see.md) per specificare un collegamento nel testo.</span><span class="sxs-lookup"><span data-stu-id="70ce9-112">Use [\<see>](./see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="70ce9-113">Compilare con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="70ce9-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70ce9-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="70ce9-114">Example</span></span>  
 <span data-ttu-id="70ce9-115">Per un esempio d'uso di \<seealso>, vedere [\<summary>](./summary.md).</span><span class="sxs-lookup"><span data-stu-id="70ce9-115">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70ce9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70ce9-116">See also</span></span>

- [<span data-ttu-id="70ce9-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="70ce9-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="70ce9-118">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="70ce9-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
