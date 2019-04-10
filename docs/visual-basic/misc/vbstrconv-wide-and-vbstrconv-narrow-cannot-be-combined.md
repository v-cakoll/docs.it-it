---
title: VbStrConv.Wide e VbStrConv.Narrow non possono essere combinati
ms.date: 07/20/2015
f1_keywords:
- vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
ms.openlocfilehash: 917fcdfcb34778074db6a19c04e12c3cf8de90dc
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307925"
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a>VbStrConv.Wide e VbStrConv.Narrow non possono essere combinati
L'applicazione sta tentando di combinare i membri `VbStrConv` e `Wide` dell'enumerazione `Narrow`, che si escludono reciprocamente.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Rimuovere `VbStrConv.Wide` o `VbStrConv.Narrow`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Globalization>

- [Introduzione alle applicazioni internazionali basate su .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
