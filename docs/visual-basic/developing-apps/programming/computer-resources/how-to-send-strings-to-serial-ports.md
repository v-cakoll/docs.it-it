---
title: 'Procedura: inviare stringhe a porte seriali'
ms.date: 07/20/2015
helpviewer_keywords:
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
ms.openlocfilehash: b2051451142a7818a3b7d1bc564c5ae36b2579fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345579"
---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a>Procedura: inviare stringhe a porte seriali in Visual Basic

Questo argomento descrive come usare `My.Computer.Ports` per inviare stringhe alle porte seriali del computer in Visual Basic.  
  
## <a name="example"></a>Esempio  

 In questo esempio si invia una stringa alla porta seriale COM1. Potrebbe essere necessario usare un'altra porta seriale nel computer in uso.  
  
 Usare il metodo `My.Computer.Ports.OpenSerialPort` per ottenere un riferimento alla porta. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
 Il blocco `Using` consente all'applicazione di chiudere la porta seriale, anche se viene generata un'eccezione. Tutto il codice relativo alla porta seriale deve essere all'interno di questo blocco o di un blocco `Try...Catch...Finally`.  
  
 Il metodo <xref:System.IO.Ports.SerialPort.WriteLine%2A> invia i dati alla porta seriale.  
  
 [!code-vb[VbVbalrMyComputer#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#33)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
- Questo esempio presuppone l'uso della porta `COM1`.  
  
## <a name="robust-programming"></a>Programmazione efficiente  

 Questo esempio presuppone che il computer usi la porta `COM1`; per una maggiore flessibilità, il codice deve consentire all'utente di selezionare la porta seriale desiderata da un elenco di porte disponibili. Per altre informazioni, vedere [Procedura: Mostrare le porte seriali disponibili](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 Questo esempio usa un blocco `Using` per verificare che l'applicazione chiuda la porta anche se viene generata un'eccezione. Per ulteriori informazioni, vedere [Istruzione Using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [Procedura: comporre numeri con modem collegati a porte seriali](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)
- [Procedura: mostrare le porte seriali disponibili](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
