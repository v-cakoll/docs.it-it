---
title: VbStrConv.Wide e VbStrConv.Narrow non possono essere combinati
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrArgument_IllegalWideNarrow
ms.assetid: a53b4e6a-36b1-4e36-b2c5-8196313ec599
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cb42ffd72a7e1f9bceabc8e8b67310b4ca2ab716
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="vbstrconvwide-and-vbstrconvnarrow-cannot-be-combined"></a>VbStrConv.Wide e VbStrConv.Narrow non possono essere combinati
L'applicazione sta tentando di combinare i membri `VbStrConv` e `Wide` dell'enumerazione `Narrow`, che si escludono reciprocamente.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Rimuovere `VbStrConv.Wide` o `VbStrConv.Narrow`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Globalization>  
 [NOTINBUILD Enumerazione VbStrConv](http://msdn.microsoft.com/en-us/59f83dd9-6361-47df-a836-02ba9d4cb936)  
 [Introduzione alle applicazioni internazionali basate su .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
