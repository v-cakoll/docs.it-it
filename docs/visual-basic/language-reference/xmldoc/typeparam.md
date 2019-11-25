---
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 00cb62827381146c172e0d15a2c64b167c21f025
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352195"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="1759e-101">\<typeparam> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1759e-101">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="1759e-102">Defines a type parameter name and description.</span><span class="sxs-lookup"><span data-stu-id="1759e-102">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1759e-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1759e-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="1759e-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="1759e-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="1759e-105">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="1759e-105">The name of the type parameter.</span></span> <span data-ttu-id="1759e-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="1759e-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="1759e-107">A description of the type parameter.</span><span class="sxs-lookup"><span data-stu-id="1759e-107">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1759e-108">Note</span><span class="sxs-lookup"><span data-stu-id="1759e-108">Remarks</span></span>  
 <span data-ttu-id="1759e-109">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span><span class="sxs-lookup"><span data-stu-id="1759e-109">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="1759e-110">Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="1759e-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1759e-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="1759e-111">Example</span></span>  
 <span data-ttu-id="1759e-112">This example uses the `<typeparam>` tag to describe the `id` parameter.</span><span class="sxs-lookup"><span data-stu-id="1759e-112">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="1759e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1759e-113">See also</span></span>

- [<span data-ttu-id="1759e-114">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="1759e-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
