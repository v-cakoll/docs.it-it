---
title: <param> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 4bcfe96361de9e196cb684ac4ba734f82442e25c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825560"
---
# <a name="param-visual-basic"></a><span data-ttu-id="9522b-102">\<param> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9522b-102">\<param> (Visual Basic)</span></span>
<span data-ttu-id="9522b-103">Definisce un nome di parametro e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="9522b-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9522b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9522b-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="9522b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9522b-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="9522b-106">Nome di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="9522b-106">The name of a method parameter.</span></span> <span data-ttu-id="9522b-107">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="9522b-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="9522b-108">Descrizione del parametro.</span><span class="sxs-lookup"><span data-stu-id="9522b-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9522b-109">Note</span><span class="sxs-lookup"><span data-stu-id="9522b-109">Remarks</span></span>  
 <span data-ttu-id="9522b-110">Il `<param>` tag deve essere usato nel commento per una dichiarazione di metodo per descrivere uno dei parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="9522b-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="9522b-111">Il testo per il `<param>` tag verrà visualizzato nelle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9522b-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
-   <span data-ttu-id="9522b-112">Informazioni sul parametro di IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="9522b-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="9522b-113">Per altre informazioni, vedere [Using IntelliSense](/visualstudio/ide/using-intellisense) (Uso di IntelliSense).</span><span class="sxs-lookup"><span data-stu-id="9522b-113">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
-   <span data-ttu-id="9522b-114">Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="9522b-114">Object Browser.</span></span> <span data-ttu-id="9522b-115">Per altre informazioni, vedere [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code) (Visualizzazione della struttura del codice).</span><span class="sxs-lookup"><span data-stu-id="9522b-115">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="9522b-116">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="9522b-116">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9522b-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="9522b-117">Example</span></span>  
 <span data-ttu-id="9522b-118">Questo esempio Usa la `<param>` tag per descrivere il `id` parametro.</span><span class="sxs-lookup"><span data-stu-id="9522b-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="9522b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9522b-119">See also</span></span>

- [<span data-ttu-id="9522b-120">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="9522b-120">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
