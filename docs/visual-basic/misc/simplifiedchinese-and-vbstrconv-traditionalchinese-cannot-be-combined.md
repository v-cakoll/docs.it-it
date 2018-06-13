---
title: SimplifiedChinese e VbStrConv.TraditionalChinese non possono essere combinati
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_StrConvSCandTC
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
ms.openlocfilehash: e9bee8c0e9b534704bdd2bef7d61042886f0a91a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33639252"
---
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a>SimplifiedChinese e VbStrConv.TraditionalChinese non possono essere combinati
L'applicazione sta tentando di combinare i membri `VbStrConv` e `SimplifiedChinese` dell'enumerazione `TraditionalChinese`, che si escludono reciprocamente.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Rimuovere `VbStrConv.SimplifiedChinese` o `VbStrConv.TraditionalChinese`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Globalization>  
   
 [Introduzione alle applicazioni internazionali basate su .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
