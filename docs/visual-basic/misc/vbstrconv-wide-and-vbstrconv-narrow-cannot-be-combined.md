---
title: VbStrConv.Wide e VbStrConv.Narrow non possono essere combinati
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
ms.openlocfilehash: 066a95b0baedec046082338cad2e2898e799bea6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33641806"
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a><span data-ttu-id="bf7a6-102">VbStrConv.Wide e VbStrConv.Narrow non possono essere combinati</span><span class="sxs-lookup"><span data-stu-id="bf7a6-102">VbStrConv.Wide and VbStrConv.Narrow cannot be combined</span></span>
<span data-ttu-id="bf7a6-103">L'applicazione sta tentando di combinare i membri `VbStrConv` e `Wide` dell'enumerazione `Narrow`, che si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="bf7a6-103">Your application is trying to combine the `VbStrConv` enumeration members `Wide` and `Narrow`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bf7a6-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="bf7a6-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="bf7a6-105">Rimuovere `VbStrConv.Wide` o `VbStrConv.Narrow`.</span><span class="sxs-lookup"><span data-stu-id="bf7a6-105">Remove either `VbStrConv.Wide` or `VbStrConv.Narrow`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf7a6-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf7a6-106">See Also</span></span>  
 <xref:System.Globalization>  
   
 [<span data-ttu-id="bf7a6-107">Introduzione alle applicazioni internazionali basate su .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bf7a6-107">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
