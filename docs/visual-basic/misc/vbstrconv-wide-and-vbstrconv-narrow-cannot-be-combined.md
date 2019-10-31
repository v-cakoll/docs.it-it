---
title: VbStrConv.Wide e VbStrConv.Narrow non possono essere combinati
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
ms.openlocfilehash: e90af8ba91872a04be11524753d9df0d168315ca
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198250"
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a><span data-ttu-id="13093-102">VbStrConv.Wide e VbStrConv.Narrow non possono essere combinati</span><span class="sxs-lookup"><span data-stu-id="13093-102">VbStrConv.Wide and VbStrConv.Narrow cannot be combined</span></span>
<span data-ttu-id="13093-103">L'applicazione sta tentando di combinare i membri `VbStrConv` e `Wide` dell'enumerazione `Narrow`, che si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="13093-103">Your application is trying to combine the `VbStrConv` enumeration members `Wide` and `Narrow`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="13093-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="13093-104">To correct this error</span></span>  
  
1. <span data-ttu-id="13093-105">Rimuovere `VbStrConv.Wide` o `VbStrConv.Narrow`.</span><span class="sxs-lookup"><span data-stu-id="13093-105">Remove either `VbStrConv.Wide` or `VbStrConv.Narrow`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13093-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13093-106">See also</span></span>

- <xref:System.Globalization>

- [<span data-ttu-id="13093-107">Sviluppare app globalizzate e localizzate</span><span class="sxs-lookup"><span data-stu-id="13093-107">Develop globalized and localized apps</span></span>](/visualstudio/ide/globalizing-and-localizing-applications)
