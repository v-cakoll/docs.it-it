---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 96b9754332b7b9c6c7823aecab6a93b0aa7ffd21
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975459"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="8cc42-102">\<returns> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8cc42-102">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="8cc42-103">Specifica il valore restituito della proprietà o della funzione.</span><span class="sxs-lookup"><span data-stu-id="8cc42-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cc42-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8cc42-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8cc42-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8cc42-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="8cc42-106">Descrizione del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="8cc42-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cc42-107">Note</span><span class="sxs-lookup"><span data-stu-id="8cc42-107">Remarks</span></span>  
 <span data-ttu-id="8cc42-108">Usare il `<returns>` tag nel commento per una dichiarazione di metodo descrivere il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="8cc42-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="8cc42-109">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="8cc42-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cc42-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="8cc42-110">Example</span></span>  
 <span data-ttu-id="8cc42-111">Questo esempio Usa la `<returns>` tag per illustrare i valori di `DoesRecordExist` funzione restituisce.</span><span class="sxs-lookup"><span data-stu-id="8cc42-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="8cc42-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cc42-112">See also</span></span>
- [<span data-ttu-id="8cc42-113">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="8cc42-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
