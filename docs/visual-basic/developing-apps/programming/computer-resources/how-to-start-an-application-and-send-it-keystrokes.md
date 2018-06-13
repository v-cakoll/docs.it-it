---
title: "Procedura: avviare un'applicazione e inviarle sequenze di tasti (Visual Basic)"
ms.date: 07/20/2015
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 716c88153ad01c7b225f31948c8aaaa2694dc512
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582148"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a>Procedura: avviare un'applicazione e inviarle sequenze di tasti (Visual Basic)
In questo esempio viene usata la funzione `Shell` per avviare l'applicazione Calcolatrice e vengono moltiplicati due numeri tramite l'invio di sequenze di tasti con il metodo `My.Computer.Keyboard.SendKeys`.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrMyComputer#25](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-start-an-application-and-send-it-keystrokes_1.vb)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Se non viene rilevata un'applicazione con l'identificatore di processo richiesto, viene generata un'eccezione <xref:System.ArgumentException>.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 La chiamata alla funzione `Shell` richiede l'attendibilità totale (classe <xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>  
 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
