---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: d325d5f9fbfd132630cf280653be214a267a7a80
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400060"
---
# <a name="param-visual-basic"></a><span data-ttu-id="5d735-101">\<param> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d735-101">\<param> (Visual Basic)</span></span>
<span data-ttu-id="5d735-102">Definisce un nome di parametro e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="5d735-102">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d735-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d735-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d735-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="5d735-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="5d735-105">Nome di un parametro di metodo.</span><span class="sxs-lookup"><span data-stu-id="5d735-105">The name of a method parameter.</span></span> <span data-ttu-id="5d735-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="5d735-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="5d735-107">Descrizione del parametro.</span><span class="sxs-lookup"><span data-stu-id="5d735-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d735-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="5d735-108">Remarks</span></span>  
 <span data-ttu-id="5d735-109">Il `<param>` tag deve essere usato nel commento per una dichiarazione di metodo per descrivere uno dei parametri per il metodo.</span><span class="sxs-lookup"><span data-stu-id="5d735-109">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="5d735-110">Il testo del `<param>` tag verrà visualizzato nei percorsi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d735-110">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="5d735-111">Informazioni sul parametro di IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="5d735-111">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="5d735-112">Per altre informazioni, vedere [Using IntelliSense](/visualstudio/ide/using-intellisense) (Uso di IntelliSense).</span><span class="sxs-lookup"><span data-stu-id="5d735-112">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="5d735-113">Visualizzatore oggetti.</span><span class="sxs-lookup"><span data-stu-id="5d735-113">Object Browser.</span></span> <span data-ttu-id="5d735-114">Per ulteriori informazioni, vedere [visualizzazione della struttura del codice](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="5d735-114">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="5d735-115">Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="5d735-115">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d735-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="5d735-116">Example</span></span>  
 <span data-ttu-id="5d735-117">Questo esempio usa il `<param>` tag per descrivere il `id` parametro.</span><span class="sxs-lookup"><span data-stu-id="5d735-117">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="5d735-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d735-118">See also</span></span>

- [<span data-ttu-id="5d735-119">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="5d735-119">XML Comment Tags</span></span>](index.md)
