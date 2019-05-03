---
title: SimplifiedChinese e VbStrConv.TraditionalChinese non possono essere combinati
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_StrConvSCandTC
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
ms.openlocfilehash: a209a83ce5bd3ecd9580abab330f1e09ecc3864e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61594841"
---
# <a name="simplifiedchinese-and-vbstrconvtraditionalchinese-cannot-be-combined"></a>SimplifiedChinese e VbStrConv.TraditionalChinese non possono essere combinati
L'applicazione sta tentando di combinare i membri `VbStrConv` e `SimplifiedChinese` dell'enumerazione `TraditionalChinese`, che si escludono reciprocamente.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Rimuovere `VbStrConv.SimplifiedChinese` o `VbStrConv.TraditionalChinese`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Globalization>

- [Introduzione alle applicazioni internazionali basate su .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
