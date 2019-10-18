---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: dbd99997fed33c192a2160fb45a739addbae254a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524616"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="dd350-102">\<typeparam > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd350-102">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="dd350-103">Definisce il nome e la descrizione di un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="dd350-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd350-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd350-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd350-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dd350-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="dd350-106">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="dd350-106">The name of the type parameter.</span></span> <span data-ttu-id="dd350-107">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="dd350-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="dd350-108">Descrizione del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="dd350-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd350-109">Note</span><span class="sxs-lookup"><span data-stu-id="dd350-109">Remarks</span></span>  
 <span data-ttu-id="dd350-110">Usare il tag `<typeparam>` nel commento per una dichiarazione di un tipo generico o di un membro generico per descrivere uno dei parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="dd350-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="dd350-111">Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="dd350-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd350-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd350-112">Example</span></span>  
 <span data-ttu-id="dd350-113">Questo esempio usa il tag `<typeparam>` per descrivere il parametro `id`.</span><span class="sxs-lookup"><span data-stu-id="dd350-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="dd350-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd350-114">See also</span></span>

- [<span data-ttu-id="dd350-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="dd350-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
