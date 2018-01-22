---
title: Errore interno. Impossibile ottenere il nome completo del sistema operativo
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6e90de5a2fd0699a449e05b9c32e7450b8bdc991
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a>Errore interno. Impossibile ottenere il nome completo del sistema operativo
Errore interno. Impossibile ottenere il nome completo del sistema operativo. WMI potrebbe non essere presente sul computer in uso.  
  
 Una chiamata alla proprietà `My.Computer.Info.OSFullName` non è riuscita. L'errore può derivare dal fatto che Strumentazione gestione Windows (WMI) non è installato nel computer corrente.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Aggiungere un blocco `Try...Catch` nella chiamata alla proprietà `My.Computer.Info.OSFullName` .  
  
2.  Per ulteriori informazioni su WMI e su come installarlo, passare a e cercare "Windows Management Instrumentation Core".  
  
## <a name="see-also"></a>Vedere anche  
 [My.Computer.Info.OSFullName](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)  
 [Eccezioni e gestione degli errori in Visual Basic](http://msdn.microsoft.com/library/3e351e73-cf23-40ab-8b60-05794160529e)  
 [Istruzione Try...Catch...Finally](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
