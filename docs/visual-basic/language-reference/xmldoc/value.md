---
title: '&lt;valore&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: ef14836c438cf6a1de300270d9882c1e53e716ee
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "43258043"
---
# <a name="ltvaluegt-visual-basic"></a><span data-ttu-id="8fa64-102">&lt;valore&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fa64-102">&lt;value&gt; (Visual Basic)</span></span>
<span data-ttu-id="8fa64-103">Specifica la descrizione di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="8fa64-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fa64-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8fa64-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8fa64-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8fa64-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="8fa64-106">Descrizione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8fa64-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fa64-107">Note</span><span class="sxs-lookup"><span data-stu-id="8fa64-107">Remarks</span></span>  
 <span data-ttu-id="8fa64-108">Usare il `<value>` tag per descrivere una proprietà.</span><span class="sxs-lookup"><span data-stu-id="8fa64-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="8fa64-109">Si noti che quando si aggiunge una proprietà usando la procedura guidata per codice nell'ambiente di sviluppo Visual Studio, verrà aggiunto un [ \<riepilogo >](../../../visual-basic/language-reference/xmldoc/summary.md) tag per la nuova proprietà.</span><span class="sxs-lookup"><span data-stu-id="8fa64-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="8fa64-110">È quindi necessario aggiungere manualmente un `<value>` tag per descrivere il valore che rappresenta la proprietà.</span><span class="sxs-lookup"><span data-stu-id="8fa64-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="8fa64-111">Compilare con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) per elaborare i commenti relativi alla documentazione in un file.</span><span class="sxs-lookup"><span data-stu-id="8fa64-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fa64-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="8fa64-112">Example</span></span>  
 <span data-ttu-id="8fa64-113">Questo esempio Usa la `<value>` tag per descrivere il valore di `Counter` contiene proprietà.</span><span class="sxs-lookup"><span data-stu-id="8fa64-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8fa64-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fa64-114">See Also</span></span>  
 [<span data-ttu-id="8fa64-115">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="8fa64-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
