---
title: '&lt;param&gt; (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- param
- <param>
dev_langs:
- CSharp
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
caps.latest.revision: 15
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
ms.openlocfilehash: 1076405d60c85540eeaeba39821bd20bc628030d
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="ltparamgt-c-programming-guide"></a><span data-ttu-id="bbe47-102">&lt;param&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="bbe47-102">&lt;param&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="bbe47-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bbe47-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbe47-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="bbe47-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="bbe47-105">Nome di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="bbe47-105">The name of a method parameter.</span></span> <span data-ttu-id="bbe47-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="bbe47-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="bbe47-107">Descrizione del parametro.</span><span class="sxs-lookup"><span data-stu-id="bbe47-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbe47-108">Note</span><span class="sxs-lookup"><span data-stu-id="bbe47-108">Remarks</span></span>  
 <span data-ttu-id="bbe47-109">Il tag \<param> viene usato nel commento di una dichiarazione di metodo per descrivere uno dei parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="bbe47-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="bbe47-110">Per documentare più parametri, usare più tag \<param>.</span><span class="sxs-lookup"><span data-stu-id="bbe47-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="bbe47-111">Il testo del tag \<param> verrà visualizzato in IntelliSense, nella finestra Visualizzatore oggetti e nel report Web sui commenti del codice.</span><span class="sxs-lookup"><span data-stu-id="bbe47-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="bbe47-112">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="bbe47-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbe47-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbe47-113">Example</span></span>  
 <span data-ttu-id="bbe47-114">[!code-cs[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bbe47-114">[!code-cs[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe47-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbe47-115">See Also</span></span>  
 <span data-ttu-id="bbe47-116">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bbe47-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="bbe47-117">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="bbe47-117">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

