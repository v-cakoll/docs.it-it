---
title: '&lt;param&gt; (Guida per programmatori C#)'
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: b4afa84aadc68ca2f0113023319f02a10dc17836
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508215"
---
# <a name="ltparamgt-c-programming-guide"></a><span data-ttu-id="970ea-102">&lt;param&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="970ea-102">&lt;param&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="970ea-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="970ea-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="970ea-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="970ea-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="970ea-105">Nome di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="970ea-105">The name of a method parameter.</span></span> <span data-ttu-id="970ea-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="970ea-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="970ea-107">Descrizione del parametro.</span><span class="sxs-lookup"><span data-stu-id="970ea-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="970ea-108">Note</span><span class="sxs-lookup"><span data-stu-id="970ea-108">Remarks</span></span>  
 <span data-ttu-id="970ea-109">Il tag \<param> viene usato nel commento di una dichiarazione di metodo per descrivere uno dei parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="970ea-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="970ea-110">Per documentare più parametri, usare più tag \<param>.</span><span class="sxs-lookup"><span data-stu-id="970ea-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="970ea-111">Il testo del tag \<param> verrà visualizzato in IntelliSense, nella finestra Visualizzatore oggetti e nel report Web sui commenti del codice.</span><span class="sxs-lookup"><span data-stu-id="970ea-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="970ea-112">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="970ea-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="970ea-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="970ea-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="970ea-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="970ea-114">See Also</span></span>

- [<span data-ttu-id="970ea-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="970ea-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="970ea-116">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="970ea-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
