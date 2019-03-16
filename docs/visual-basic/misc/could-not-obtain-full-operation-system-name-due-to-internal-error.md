---
title: Errore interno. Impossibile ottenere il nome completo del sistema operativo
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 6a0e24743c861ba92fc284a84fa4ef26e2ee48a8
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2019
ms.locfileid: "58022766"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a>Errore interno. Impossibile ottenere il nome completo del sistema operativo
Errore interno. Impossibile ottenere il nome completo del sistema operativo. WMI potrebbe non essere presente sul computer in uso.  
  
 Una chiamata alla proprietà `My.Computer.Info.OSFullName` non è riuscita. L'errore può derivare dal fatto che Strumentazione gestione Windows (WMI) non è installato nel computer corrente.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Aggiungere un blocco `Try...Catch` nella chiamata alla proprietà `My.Computer.Info.OSFullName` .  
  
2.  Per altre informazioni su WMI e come installarla, passare a e cercare "Windows Management Instrumentation Core".  
  
## <a name="see-also"></a>Vedere anche

- [My.Computer.Info.OSFullName](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [Gestione e generazione di eccezioni in .NET](../../standard/exceptions/index.md)
- [Istruzione Try...Catch...Finally](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
