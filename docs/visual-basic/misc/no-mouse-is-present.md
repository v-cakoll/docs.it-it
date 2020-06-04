---
title: Mouse non presente
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoMouseIsPresent
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
ms.openlocfilehash: 748661cae35292968aae989789a96d1df855b6ce
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84376124"
---
# <a name="no-mouse-is-present"></a>Mouse non presente
È stata chiamata una delle proprietà dell'oggetto `My.Computer.Mouse` , ma nel computer non è installato alcun mouse o porta del mouse.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Aggiungere un blocco `Try...Catch` nella chiamata alla proprietà dell'oggetto `My.Computer.Mouse` .  
  
     - o -  
  
- Installare un mouse del computer.  
  
## <a name="see-also"></a>Vedere anche

- [My.Computer.Mouse](xref:Microsoft.VisualBasic.Devices.Mouse)
- [Gestione e generazione di eccezioni in .NET](../../standard/exceptions/index.md)
- [Istruzione Try...Catch...Finally](../language-reference/statements/try-catch-finally-statement.md)
