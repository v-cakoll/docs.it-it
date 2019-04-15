---
title: 'Procedura: Comporre numeri con modem collegati a porte seriali in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- modems [Visual Basic], dialing
- serial ports [Visual Basic], dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
ms.openlocfilehash: db482af7750012d8805d4f834063a2c82224cf67
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337032"
---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a>Procedura: Comporre numeri con modem collegati a porte seriali in Visual Basic
Questo argomento descrive come usare `My.Computer.Ports` per comporre numeri con modem in Visual Basic.  
  
 In genere, il modem è collegato a una delle porte seriali del computer. Affinché l'applicazione comunichi con il modem, è necessario inviare i comandi alla porta seriale appropriata.  
  
### <a name="to-dial-a-modem"></a>Comporre numeri con modem  
  
1. Determinare a quale porta seriale è connesso il modem. Nell'esempio si presuppone che il modem sia collegato a COM1.  
  
2. Usare il metodo `My.Computer.Ports.OpenSerialPort` per ottenere un riferimento alla porta. Per ulteriori informazioni, vedere <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     Il blocco `Using` consente all'applicazione di chiudere la porta seriale anche se viene generata un'eccezione. Tutto il codice relativo alla porta seriale deve essere all'interno di questo blocco o di un blocco `Try...Catch...Finally`.  
  
     [!code-vb[VbVbalrMyComputer#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#28)]  
  
3. Impostare la proprietà `DtrEnable` per indicare che il computer è pronto ad accettare una trasmissione in ingresso dal modem.  
  
     [!code-vb[VbVbalrMyComputer#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#29)]  
  
4. Inviare il comando di connessione e il numero di telefono al modem attraverso la porta seriale usando il metodo <xref:System.IO.Ports.SerialPort.Write%2A>.  
  
     [!code-vb[VbVbalrMyComputer#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#30)]  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrMyComputer#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#27)]  
  
 Questo esempio di codice è disponibile anche come frammento di codice IntelliSense. Nella selezione del frammento di codice si trova in **Connettività e rete**. Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Nell'esempio è richiesto un riferimento allo spazio dei nomi <xref:System?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Nell'esempio si presuppone che il modem sia collegato a COM1. È consigliabile che il codice consenta all'utente di selezionare la porta seriale desiderata da un elenco di porte disponibili. Per altre informazioni, vedere [Procedura: Mostrare le porte seriali disponibili](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).  
  
 Questo esempio usa un blocco `Using` per verificare che l'applicazione chiuda la porta anche se viene generata un'eccezione. Per altre informazioni, vedere [Istruzione using](../../../../visual-basic/language-reference/statements/using-statement.md).  
  
 In questo esempio, l'applicazione si disconnette dalla porta seriale dopo aver composto il numero con il modem. In uno scenario reale, l'utente vuole trasferire i dati da e verso il modem. Per altre informazioni, vedere [Procedura: Ricevere stringhe da porte seriali](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [Procedura: Inviare stringhe a porte seriali](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)
- [Procedura: Ricevere stringhe da porte seriali](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)
- [Procedura: Mostrare le porte seriali disponibili](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
