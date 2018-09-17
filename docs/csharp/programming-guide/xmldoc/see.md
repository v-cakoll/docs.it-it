---
title: '&lt;see&gt; (Guida per programmatori C#)'
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: c37ad869b3eb904377cd4470a85cd557f6560290
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45591215"
---
# <a name="ltseegt-c-programming-guide"></a><span data-ttu-id="ea32b-102">&lt;see&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="ea32b-102">&lt;see&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="ea32b-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea32b-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea32b-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea32b-104">Parameters</span></span>  
 <span data-ttu-id="ea32b-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="ea32b-105">cref = " `member`"</span></span>  
 <span data-ttu-id="ea32b-106">Riferimento a un membro o a un campo disponibile per essere chiamato dall'ambiente di compilazione corrente.</span><span class="sxs-lookup"><span data-stu-id="ea32b-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="ea32b-107">Il compilatore controlla che l'elemento di codice specificato esista e passa `member` al nome dell'elemento nel *membro* XML.Place di output tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="ea32b-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.Place *member* within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea32b-108">Note</span><span class="sxs-lookup"><span data-stu-id="ea32b-108">Remarks</span></span>  
 <span data-ttu-id="ea32b-109">Con il tag \<see> è possibile specificare un collegamento nel testo.</span><span class="sxs-lookup"><span data-stu-id="ea32b-109">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="ea32b-110">Usare [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) per indicare che il testo deve essere inserito in una sezione Vedere anche.</span><span class="sxs-lookup"><span data-stu-id="ea32b-110">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="ea32b-111">Usare l'[attributo cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) per creare collegamenti ipertestuali interni alle pagine della documentazione per gli elementi di codice.</span><span class="sxs-lookup"><span data-stu-id="ea32b-111">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="ea32b-112">Compilare con [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="ea32b-112">Compile with [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="ea32b-113">Nell'esempio seguente viene illustrato un tag \<see> all'interno di una sezione di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="ea32b-113">The following example shows a \<see> tag within a summary section.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ea32b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea32b-114">See Also</span></span>

- [<span data-ttu-id="ea32b-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ea32b-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ea32b-116">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="ea32b-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
