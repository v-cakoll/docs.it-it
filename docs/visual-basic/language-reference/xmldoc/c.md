---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: c8ba03d9cc01c4751d15c01530c6cbf7d499dc3b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400163"
---
# <a name="c-visual-basic"></a><span data-ttu-id="42952-101">\<c> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42952-101">\<c> (Visual Basic)</span></span>
<span data-ttu-id="42952-102">Indica che il testo all'interno di una descrizione è codice.</span><span class="sxs-lookup"><span data-stu-id="42952-102">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42952-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42952-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="42952-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="42952-104">Parameters</span></span>  
  
|<span data-ttu-id="42952-105">Parametro</span><span class="sxs-lookup"><span data-stu-id="42952-105">Parameter</span></span>|<span data-ttu-id="42952-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42952-106">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="42952-107">Il testo che si desidera indicare come codice.</span><span class="sxs-lookup"><span data-stu-id="42952-107">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42952-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="42952-108">Remarks</span></span>  
 <span data-ttu-id="42952-109">Il `<c>` tag fornisce un modo per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.</span><span class="sxs-lookup"><span data-stu-id="42952-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="42952-110">Usare [\<code>](code.md) per indicare più righe come codice.</span><span class="sxs-lookup"><span data-stu-id="42952-110">Use [\<code>](code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="42952-111">Compilare con [-doc](../../reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="42952-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42952-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="42952-112">Example</span></span>  
 <span data-ttu-id="42952-113">Questo esempio usa il `<c>` tag nella sezione Summary per indicare che `Counter` si tratta di codice.</span><span class="sxs-lookup"><span data-stu-id="42952-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="42952-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42952-114">See also</span></span>

- [<span data-ttu-id="42952-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="42952-115">XML Comment Tags</span></span>](index.md)
