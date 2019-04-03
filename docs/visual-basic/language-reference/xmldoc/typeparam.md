---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 014623be84f9d7eb8a25ac4aadcce450f158c154
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827237"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="b1567-102">\<typeparam > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1567-102">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="b1567-103">Definisce un parametro di tipo nome e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="b1567-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1567-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1567-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1567-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b1567-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="b1567-106">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="b1567-106">The name of the type parameter.</span></span> <span data-ttu-id="b1567-107">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="b1567-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="b1567-108">Descrizione del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="b1567-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1567-109">Note</span><span class="sxs-lookup"><span data-stu-id="b1567-109">Remarks</span></span>  
 <span data-ttu-id="b1567-110">Usare il `<typeparam>` tag del commento per un tipo generico o dichiarazione di un membro generico descrivere uno dei parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="b1567-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="b1567-111">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="b1567-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1567-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="b1567-112">Example</span></span>  
 <span data-ttu-id="b1567-113">Questo esempio Usa la `<typeparam>` tag per descrivere il `id` parametro.</span><span class="sxs-lookup"><span data-stu-id="b1567-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="b1567-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1567-114">See also</span></span>

- [<span data-ttu-id="b1567-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="b1567-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
