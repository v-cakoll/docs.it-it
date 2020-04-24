---
title: "Procedura: avviare un'applicazione e inviarle sequenze di tasti Visual Basic"
ms.date: 10/23/2019
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 033999c07bb5839a264122b2ca330916bdf844b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "72919396"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a>Procedura: avviare un'applicazione e inviarle sequenze di tasti (Visual Basic)

In questo esempio viene <xref:Microsoft.VisualBasic.Interaction.Shell%2A> utilizzato il metodo per avviare l'applicazione blocco note e quindi viene stampata una frase inviando sequenze di tasti utilizzando il metodo [My. computer. Keyboard. SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A) .

## <a name="example"></a>Esempio

[!code-vb[VbVbalrMyComputer#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#25)]

## <a name="robust-programming"></a>Programmazione efficiente

Se <xref:System.ArgumentException> non è possibile trovare un'applicazione con l'identificatore di processo richiesto, viene generata un'eccezione.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework

La chiamata alla funzione `Shell` richiede l'attendibilità totale (classe <xref:System.Security.SecurityException>).

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
