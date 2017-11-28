---
title: '&lt;param&gt; (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1a5325b91130623442c9cf5453e52418bb44cc34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltparamgt-c-programming-guide"></a><span data-ttu-id="6385a-102">&lt;param&gt; (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="6385a-102">&lt;param&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="6385a-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6385a-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6385a-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="6385a-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="6385a-105">Nome di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="6385a-105">The name of a method parameter.</span></span> <span data-ttu-id="6385a-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="6385a-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="6385a-107">Descrizione del parametro.</span><span class="sxs-lookup"><span data-stu-id="6385a-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6385a-108">Note</span><span class="sxs-lookup"><span data-stu-id="6385a-108">Remarks</span></span>  
 <span data-ttu-id="6385a-109">Il tag \<param> viene usato nel commento di una dichiarazione di metodo per descrivere uno dei parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="6385a-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="6385a-110">Per documentare più parametri, usare più tag \<param>.</span><span class="sxs-lookup"><span data-stu-id="6385a-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="6385a-111">Il testo del tag \<param> verrà visualizzato in IntelliSense, nella finestra Visualizzatore oggetti e nel report Web sui commenti del codice.</span><span class="sxs-lookup"><span data-stu-id="6385a-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="6385a-112">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="6385a-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6385a-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="6385a-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6385a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6385a-114">See Also</span></span>  
 [<span data-ttu-id="6385a-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="6385a-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6385a-116">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="6385a-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
