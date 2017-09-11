---
title: '&lt;param&gt; (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: ddf5baf83816d757edf67cdf1c66dc24e4313b83
ms.contentlocale: it-it
ms.lasthandoff: 06/01/2017

---
# <a name="ltparamgt-visual-basic"></a><span data-ttu-id="cbb49-102">&lt;param&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbb49-102">&lt;param&gt; (Visual Basic)</span></span>
<span data-ttu-id="cbb49-103">Definisce un nome di parametro e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="cbb49-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbb49-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cbb49-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cbb49-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cbb49-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="cbb49-106">Il nome di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="cbb49-106">The name of a method parameter.</span></span> <span data-ttu-id="cbb49-107">Racchiudere il nome tra virgolette doppie ("").</span><span class="sxs-lookup"><span data-stu-id="cbb49-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="cbb49-108">Una descrizione per il parametro.</span><span class="sxs-lookup"><span data-stu-id="cbb49-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbb49-109">Note</span><span class="sxs-lookup"><span data-stu-id="cbb49-109">Remarks</span></span>  
 <span data-ttu-id="cbb49-110">Il `<param>` tag deve essere utilizzato nel commento per una dichiarazione di metodo per descrivere uno dei parametri per il metodo.</span><span class="sxs-lookup"><span data-stu-id="cbb49-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="cbb49-111">Il testo per il `<param>` tag verrà visualizzato nei seguenti percorsi:</span><span class="sxs-lookup"><span data-stu-id="cbb49-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
-   <span data-ttu-id="cbb49-112">Informazioni sul parametro di IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="cbb49-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="cbb49-113">Per altre informazioni, vedere [Using IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense) (Uso di IntelliSense).</span><span class="sxs-lookup"><span data-stu-id="cbb49-113">For more information, see [Using IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense).</span></span>  
  
-   <span data-ttu-id="cbb49-114">Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="cbb49-114">Object Browser.</span></span> <span data-ttu-id="cbb49-115">Per altre informazioni, vedere [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code) (Visualizzazione della struttura del codice).</span><span class="sxs-lookup"><span data-stu-id="cbb49-115">For more information, see [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="cbb49-116">Esegue la compilazione con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) ai commenti di documentazione di processo in un file.</span><span class="sxs-lookup"><span data-stu-id="cbb49-116">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbb49-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="cbb49-117">Example</span></span>  
 <span data-ttu-id="cbb49-118">Questo esempio viene utilizzato il `<param>` tag per descrivere il `id` parametro.</span><span class="sxs-lookup"><span data-stu-id="cbb49-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 <span data-ttu-id="cbb49-119">[!code-vb[6 VbVbcnXmlDocComments](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="cbb49-119">[!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbb49-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbb49-120">See Also</span></span>  
 [<span data-ttu-id="cbb49-121">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="cbb49-121">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
