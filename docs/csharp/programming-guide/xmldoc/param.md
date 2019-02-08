---
title: <param> - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 3f1099da6a43ed7f48389a16e3be6a3b6b98a148
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271577"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="f8c2c-102">\<param> (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="f8c2c-102">\<param> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f8c2c-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8c2c-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8c2c-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="f8c2c-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="f8c2c-105">Nome di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="f8c2c-105">The name of a method parameter.</span></span> <span data-ttu-id="f8c2c-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="f8c2c-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="f8c2c-107">Descrizione del parametro.</span><span class="sxs-lookup"><span data-stu-id="f8c2c-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8c2c-108">Note</span><span class="sxs-lookup"><span data-stu-id="f8c2c-108">Remarks</span></span>  
 <span data-ttu-id="f8c2c-109">Il tag \<param> viene usato nel commento di una dichiarazione di metodo per descrivere uno dei parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="f8c2c-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="f8c2c-110">Per documentare più parametri, usare più tag \<param>.</span><span class="sxs-lookup"><span data-stu-id="f8c2c-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="f8c2c-111">Il testo del tag \<param> verrà visualizzato in IntelliSense, nella finestra Visualizzatore oggetti e nel report Web sui commenti del codice.</span><span class="sxs-lookup"><span data-stu-id="f8c2c-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="f8c2c-112">Compilare con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="f8c2c-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8c2c-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8c2c-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f8c2c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8c2c-114">See also</span></span>

- [<span data-ttu-id="f8c2c-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f8c2c-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f8c2c-116">Tag consigliati per i commenti relativi alla documentazione</span><span class="sxs-lookup"><span data-stu-id="f8c2c-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
