---
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 2ad54845645172acb5b91935f5347a828510e3aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411486"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="588d8-101">\<typeparam> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="588d8-101">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="588d8-102">Definisce il nome e la descrizione di un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="588d8-102">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="588d8-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="588d8-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="588d8-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="588d8-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="588d8-105">Nome del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="588d8-105">The name of the type parameter.</span></span> <span data-ttu-id="588d8-106">Racchiudere il nome tra virgolette doppie (" ").</span><span class="sxs-lookup"><span data-stu-id="588d8-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="588d8-107">Descrizione del parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="588d8-107">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="588d8-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="588d8-108">Remarks</span></span>  
 <span data-ttu-id="588d8-109">Usare il `<typeparam>` tag nel commento per una dichiarazione di un tipo generico o di un membro generico per descrivere uno dei parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="588d8-109">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="588d8-110">Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="588d8-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="588d8-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="588d8-111">Example</span></span>  
 <span data-ttu-id="588d8-112">Questo esempio usa il `<typeparam>` tag per descrivere il `id` parametro.</span><span class="sxs-lookup"><span data-stu-id="588d8-112">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="588d8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="588d8-113">See also</span></span>

- [<span data-ttu-id="588d8-114">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="588d8-114">XML Comment Tags</span></span>](index.md)
