---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 62f70ae7f40fa3cde9492563b7bd14dfa5940a5f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352236"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="025f8-101">\<restituisce > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="025f8-101">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="025f8-102">Specifica il valore restituito della proprietà o della funzione.</span><span class="sxs-lookup"><span data-stu-id="025f8-102">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="025f8-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="025f8-103">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="025f8-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="025f8-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="025f8-105">Descrizione del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="025f8-105">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="025f8-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="025f8-106">Remarks</span></span>  
 <span data-ttu-id="025f8-107">Usare il tag `<returns>` nel commento per una dichiarazione di metodo per descrivere il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="025f8-107">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="025f8-108">Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="025f8-108">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="025f8-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="025f8-109">Example</span></span>  
 <span data-ttu-id="025f8-110">Questo esempio usa il tag `<returns>` per spiegare il risultato restituito dalla funzione `DoesRecordExist`.</span><span class="sxs-lookup"><span data-stu-id="025f8-110">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="025f8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="025f8-111">See also</span></span>

- [<span data-ttu-id="025f8-112">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="025f8-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
