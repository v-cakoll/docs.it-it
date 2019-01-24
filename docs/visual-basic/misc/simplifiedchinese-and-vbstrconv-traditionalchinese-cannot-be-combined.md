---
title: SimplifiedChinese e VbStrConv.TraditionalChinese non possono essere combinati
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_StrConvSCandTC
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
ms.openlocfilehash: 0d07b419f11692d080000ee689d545054ddfd92c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549577"
---
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a><span data-ttu-id="51735-102">SimplifiedChinese e VbStrConv.TraditionalChinese non possono essere combinati</span><span class="sxs-lookup"><span data-stu-id="51735-102">SimplifiedChinese and VbStrConv.TraditionalChinese cannot be combined</span></span>
<span data-ttu-id="51735-103">L'applicazione sta tentando di combinare i membri `VbStrConv` e `SimplifiedChinese` dell'enumerazione `TraditionalChinese`, che si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="51735-103">Your application is attempting to combine the `VbStrConv` enumeration members `SimplifiedChinese` and `TraditionalChinese`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="51735-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="51735-104">To correct this error</span></span>  
  
-   <span data-ttu-id="51735-105">Rimuovere `VbStrConv.SimplifiedChinese` o `VbStrConv.TraditionalChinese`.</span><span class="sxs-lookup"><span data-stu-id="51735-105">Remove either `VbStrConv.SimplifiedChinese` or `VbStrConv.TraditionalChinese`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51735-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51735-106">See also</span></span>
- <xref:System.Globalization>

- [<span data-ttu-id="51735-107">Introduzione alle applicazioni internazionali basate su .NET Framework</span><span class="sxs-lookup"><span data-stu-id="51735-107">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
