---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: edbc374332bdcd67b385ac3d061045664e942460
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84399995"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="2ce28-101">\<returns> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ce28-101">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="2ce28-102">Specifica il valore restituito della proprietà o della funzione.</span><span class="sxs-lookup"><span data-stu-id="2ce28-102">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ce28-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ce28-103">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ce28-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ce28-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="2ce28-105">Descrizione del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="2ce28-105">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ce28-106">Commenti</span><span class="sxs-lookup"><span data-stu-id="2ce28-106">Remarks</span></span>  
 <span data-ttu-id="2ce28-107">Usare il `<returns>` tag nel commento per una dichiarazione di metodo per descrivere il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="2ce28-107">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="2ce28-108">Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="2ce28-108">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ce28-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="2ce28-109">Example</span></span>  
 <span data-ttu-id="2ce28-110">Questo esempio usa il `<returns>` tag per spiegare il risultato `DoesRecordExist` restituito dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="2ce28-110">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="2ce28-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ce28-111">See also</span></span>

- [<span data-ttu-id="2ce28-112">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="2ce28-112">XML Comment Tags</span></span>](index.md)
