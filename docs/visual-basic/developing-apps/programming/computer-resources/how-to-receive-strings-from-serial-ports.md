---
title: 'Procedura: Ricevere stringhe da porte seriali'
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
ms.openlocfilehash: 93b6b47d89d05331c85a6459bba7d6fd5e2e3377
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401836"
---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a>Procedura: ricevere stringhe da porte seriali in Visual Basic

Questo argomento descrive come usare `My.Computer.Ports` per ricevere stringhe dalle porte seriali del computer in Visual Basic.  
  
### <a name="to-receive-strings-from-the-serial-port"></a>Per ricevere stringhe dalla porta seriale  
  
1. Inizializzare la stringa restituita.  
  
     [!code-vb[VbVbalrMyComputer#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#38)]  
  
2. Determinare quale porta seriale deve fornire le stringhe. In questo esempio si presuppone che sia `COM1`.  
  
3. Usare il metodo `My.Computer.Ports.OpenSerialPort` per ottenere un riferimento alla porta. Per altre informazioni, vedere <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.  
  
     Il blocco `Try...Catch...Finally` consente all'applicazione di chiudere la porta seriale, anche se viene generata un'eccezione. Tutto il codice per la modifica della porta seriale deve essere contenuto all'interno di questo blocco.  
  
     [!code-vb[VbVbalrMyComputer#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#39)]  
  
4. Creare un ciclo `Do` per leggere le righe di testo fino a quando non sono più disponibili righe.  
  
     [!code-vb[VbVbalrMyComputer#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#40)]  
  
5. Usare il metodo <xref:System.IO.Ports.SerialPort.ReadLine> per leggere la successiva riga di testo disponibile dalla porta seriale.  
  
     [!code-vb[VbVbalrMyComputer#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#41)]  
  
6. Usare un'istruzione `If` per determinare se il metodo <xref:System.IO.Ports.SerialPort.ReadLine> restituisce `Nothing`, il che significa che non è più disponibile testo. Se restituisce `Nothing`, uscire dal ciclo `Do`.  
  
     [!code-vb[VbVbalrMyComputer#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#42)]  
  
7. Aggiungere un blocco `Else` all'istruzione `If` per gestire la situazione se la stringa viene effettivamente letta. Il blocco consente di aggiungere la stringa dalla porta seriale alla stringa restituita.  
  
     [!code-vb[VbVbalrMyComputer#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#43)]  
  
8. Restituire la stringa.  
  
     [!code-vb[VbVbalrMyComputer#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#44)]  
  
## <a name="example"></a>Esempio  

 [!code-vb[VbVbalrMyComputer#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#37)]  
  
 Questo esempio di codice è disponibile anche come frammento di codice IntelliSense. Nella selezione del frammento di codice si trova in **Connettività e rete**. Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  

 Questo esempio presuppone l'uso della porta `COM1`.  
  
## <a name="robust-programming"></a>Programmazione efficiente  

 Questo esempio presuppone l'uso della porta `COM1`. Per garantire una maggiore flessibilità, il codice deve consentire all'utente di selezionare la porta seriale desiderata da un elenco di porte disponibili. Per altre informazioni, vedere [Procedura: Mostrare le porte seriali disponibili](how-to-show-available-serial-ports.md).  
  
 Questo esempio usa un blocco `Try...Catch...Finally` per verificare che l'applicazione chiuda la porta e per rilevare tutte le eccezioni di timeout. Per altre informazioni, vedere [Istruzione Try...Catch...Finally](../../../language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [Procedura: Comporre numeri con modem collegati a porte seriali](how-to-dial-modems-attached-to-serial-ports.md)
- [Procedura: Inviare stringhe a porte seriali](how-to-send-strings-to-serial-ports.md)
- [Procedura: Mostrare le porte seriali disponibili](how-to-show-available-serial-ports.md)
