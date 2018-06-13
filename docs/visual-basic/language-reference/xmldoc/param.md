---
title: '&lt;param&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: c992c96303eb1441eaf667693b7aefb5361b196c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602921"
---
# <a name="ltparamgt-visual-basic"></a><span data-ttu-id="ef3af-102">&lt;param&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef3af-102">&lt;param&gt; (Visual Basic)</span></span>
<span data-ttu-id="ef3af-103">Definisce un nome di parametro e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="ef3af-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef3af-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef3af-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef3af-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef3af-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="ef3af-106">Nome di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="ef3af-106">The name of a method parameter.</span></span> <span data-ttu-id="ef3af-107">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="ef3af-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="ef3af-108">Descrizione del parametro.</span><span class="sxs-lookup"><span data-stu-id="ef3af-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef3af-109">Note</span><span class="sxs-lookup"><span data-stu-id="ef3af-109">Remarks</span></span>  
 <span data-ttu-id="ef3af-110">Il `<param>` tag deve essere utilizzato per descrivere uno dei parametri per il metodo nel commento per una dichiarazione di metodo.</span><span class="sxs-lookup"><span data-stu-id="ef3af-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="ef3af-111">Il testo per il `<param>` tag verrà visualizzato nelle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef3af-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
-   <span data-ttu-id="ef3af-112">Informazioni sul parametro di IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="ef3af-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="ef3af-113">Per altre informazioni, vedere [Using IntelliSense](/visualstudio/ide/using-intellisense) (Uso di IntelliSense).</span><span class="sxs-lookup"><span data-stu-id="ef3af-113">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
-   <span data-ttu-id="ef3af-114">Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="ef3af-114">Object Browser.</span></span> <span data-ttu-id="ef3af-115">Per altre informazioni, vedere [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code) (Visualizzazione della struttura del codice).</span><span class="sxs-lookup"><span data-stu-id="ef3af-115">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="ef3af-116">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="ef3af-116">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef3af-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="ef3af-117">Example</span></span>  
 <span data-ttu-id="ef3af-118">Questo esempio viene utilizzato il `<param>` tag per descrivere il `id` parametro.</span><span class="sxs-lookup"><span data-stu-id="ef3af-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ef3af-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef3af-119">See Also</span></span>  
 [<span data-ttu-id="ef3af-120">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="ef3af-120">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
