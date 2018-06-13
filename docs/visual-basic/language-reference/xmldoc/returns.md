---
title: '&lt;Restituisce&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: effc55bd65ae6c54575b7931529499505a9523cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598365"
---
# <a name="ltreturnsgt-visual-basic"></a><span data-ttu-id="dbdac-102">&lt;Restituisce&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dbdac-102">&lt;returns&gt; (Visual Basic)</span></span>
<span data-ttu-id="dbdac-103">Specifica il valore restituito della proprietà o della funzione.</span><span class="sxs-lookup"><span data-stu-id="dbdac-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbdac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dbdac-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dbdac-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dbdac-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="dbdac-106">Descrizione del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="dbdac-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbdac-107">Note</span><span class="sxs-lookup"><span data-stu-id="dbdac-107">Remarks</span></span>  
 <span data-ttu-id="dbdac-108">Utilizzare il `<returns>` tag nel commento per descrivere il valore restituito di una dichiarazione di metodo.</span><span class="sxs-lookup"><span data-stu-id="dbdac-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="dbdac-109">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="dbdac-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbdac-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="dbdac-110">Example</span></span>  
 <span data-ttu-id="dbdac-111">Questo esempio viene utilizzato il `<returns>` tag per illustrare i valori di `DoesRecordExist` risultato della funzione.</span><span class="sxs-lookup"><span data-stu-id="dbdac-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="dbdac-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbdac-112">See Also</span></span>  
 [<span data-ttu-id="dbdac-113">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="dbdac-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
