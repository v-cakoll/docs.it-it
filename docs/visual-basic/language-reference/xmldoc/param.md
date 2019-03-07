---
title: <param> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: f80d9f3024107ace2102fb9ec9e8657d3219aafa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502241"
---
# <a name="param-visual-basic"></a><span data-ttu-id="146db-102">\<param> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="146db-102">\<param> (Visual Basic)</span></span>
<span data-ttu-id="146db-103">Definisce un nome di parametro e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="146db-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="146db-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="146db-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="146db-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="146db-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="146db-106">Nome di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="146db-106">The name of a method parameter.</span></span> <span data-ttu-id="146db-107">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="146db-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="146db-108">Descrizione del parametro.</span><span class="sxs-lookup"><span data-stu-id="146db-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="146db-109">Note</span><span class="sxs-lookup"><span data-stu-id="146db-109">Remarks</span></span>  
 <span data-ttu-id="146db-110">Il `<param>` tag deve essere usato nel commento per una dichiarazione di metodo per descrivere uno dei parametri del metodo.</span><span class="sxs-lookup"><span data-stu-id="146db-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="146db-111">Il testo per il `<param>` tag verrà visualizzato nelle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="146db-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
-   <span data-ttu-id="146db-112">Informazioni sul parametro di IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="146db-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="146db-113">Per altre informazioni, vedere [Using IntelliSense](/visualstudio/ide/using-intellisense) (Uso di IntelliSense).</span><span class="sxs-lookup"><span data-stu-id="146db-113">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
-   <span data-ttu-id="146db-114">Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="146db-114">Object Browser.</span></span> <span data-ttu-id="146db-115">Per altre informazioni, vedere [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code) (Visualizzazione della struttura del codice).</span><span class="sxs-lookup"><span data-stu-id="146db-115">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="146db-116">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="146db-116">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="146db-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="146db-117">Example</span></span>  
 <span data-ttu-id="146db-118">Questo esempio Usa la `<param>` tag per descrivere il `id` parametro.</span><span class="sxs-lookup"><span data-stu-id="146db-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="146db-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="146db-119">See also</span></span>
- [<span data-ttu-id="146db-120">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="146db-120">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
