---
title: Cinese semplificato e TraditionalChinese non possono essere combinati | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrArgument_StrConvSCandTC
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 981c1309f48f09c146c1a47c51828acde1321787
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a><span data-ttu-id="eec7d-102">SimplifiedChinese e VbStrConv.TraditionalChinese non possono essere combinati</span><span class="sxs-lookup"><span data-stu-id="eec7d-102">SimplifiedChinese and VbStrConv.TraditionalChinese cannot be combined</span></span>
<span data-ttu-id="eec7d-103">L'applicazione sta tentando di combinare i membri `VbStrConv` e `SimplifiedChinese` dell'enumerazione `TraditionalChinese`, che si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="eec7d-103">Your application is attempting to combine the `VbStrConv` enumeration members `SimplifiedChinese` and `TraditionalChinese`, which are mutually exclusive.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eec7d-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="eec7d-104">To correct this error</span></span>  
  
-   <span data-ttu-id="eec7d-105">Rimuovere `VbStrConv.SimplifiedChinese` o `VbStrConv.TraditionalChinese`.</span><span class="sxs-lookup"><span data-stu-id="eec7d-105">Remove either `VbStrConv.SimplifiedChinese` or `VbStrConv.TraditionalChinese`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eec7d-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eec7d-106">See Also</span></span>  
 <span data-ttu-id="eec7d-107"><xref:System.Globalization></span><span class="sxs-lookup"><span data-stu-id="eec7d-107"><xref:System.Globalization></span></span>   
<span data-ttu-id="eec7d-108"> [Enumerazione VbStrConv NOTINBUILD](http://msdn.microsoft.com/en-us/59f83dd9-6361-47df-a836-02ba9d4cb936) </span><span class="sxs-lookup"><span data-stu-id="eec7d-108"> [NOTINBUILD VbStrConv Enumeration](http://msdn.microsoft.com/en-us/59f83dd9-6361-47df-a836-02ba9d4cb936) </span></span>  
<span data-ttu-id="eec7d-109"> [Introduzione alle applicazioni internazionali basate su .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)</span><span class="sxs-lookup"><span data-stu-id="eec7d-109"> [Introduction to International Applications Based on the .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)</span></span>
