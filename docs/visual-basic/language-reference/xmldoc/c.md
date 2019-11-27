---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 857ea1ccca4d74daf65bba03845004561afefd55
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348507"
---
# <a name="c-visual-basic"></a><span data-ttu-id="50742-101">> \<c (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50742-101">\<c> (Visual Basic)</span></span>
<span data-ttu-id="50742-102">Indica che il testo all'interno di una descrizione è codice.</span><span class="sxs-lookup"><span data-stu-id="50742-102">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50742-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50742-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="50742-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="50742-104">Parameters</span></span>  
  
|<span data-ttu-id="50742-105">Parametro</span><span class="sxs-lookup"><span data-stu-id="50742-105">Parameter</span></span>|<span data-ttu-id="50742-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50742-106">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="50742-107">Il testo che si desidera indicare come codice.</span><span class="sxs-lookup"><span data-stu-id="50742-107">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50742-108">Note</span><span class="sxs-lookup"><span data-stu-id="50742-108">Remarks</span></span>  
 <span data-ttu-id="50742-109">Il tag `<c>` fornisce un modo per indicare che il testo all'interno di una descrizione deve essere contrassegnato come codice.</span><span class="sxs-lookup"><span data-stu-id="50742-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="50742-110">Usare [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) per indicare più righe come codice.</span><span class="sxs-lookup"><span data-stu-id="50742-110">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="50742-111">Compilare con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="50742-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50742-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="50742-112">Example</span></span>  
 <span data-ttu-id="50742-113">Questo esempio usa il tag `<c>` nella sezione Summary per indicare che `Counter` è il codice.</span><span class="sxs-lookup"><span data-stu-id="50742-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="50742-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50742-114">See also</span></span>

- [<span data-ttu-id="50742-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="50742-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
