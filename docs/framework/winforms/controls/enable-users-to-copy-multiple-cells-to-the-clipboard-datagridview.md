---
title: Consentire agli utenti di copiare più celle negli Appunti dal controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
ms.openlocfilehash: 2bb74a1f0c59b28ab496ce9c89c1c1b5f9d8147b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745780"
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a>Procedura: consentire agli utenti di copiare più celle negli Appunti dal controllo DataGridView di Windows Form
Quando si attiva la copia delle celle, i dati contenuti nel controllo <xref:System.Windows.Forms.DataGridView> sono facilmente accessibili da altre applicazioni tramite la classe <xref:System.Windows.Forms.Clipboard>. I valori delle celle selezionate vengono convertiti in stringhe e aggiunti negli Appunti sotto forma di valori di testo delimitato da tabulazioni, per consentirne l'inserimento in applicazioni quali Blocco note ed Excel, e sotto forma di una tabella in formato HTML, per consentirne l'inserimento in applicazioni come Word.  
  
 È possibile configurare la funzionalità di copia dalle celle in modo da copiare solo i valori delle celle, includere il testo della riga e dell'intestazione della colonna nei dati degli Appunti o includere il testo dell'intestazione solo quando gli utenti selezionano righe o colonne intere.  
  
 A seconda della modalità di selezione gli utenti possono selezionare più gruppi di celle scollegati. Quando un utente copia le celle negli Appunti, le righe e le colonne in cui non è selezionata alcuna cella non vengono copiate. Tutte le altre righe o colonne diventano righe o colonne nella tabella di dati copiati negli Appunti. Le celle non selezionate in queste righe o colonne vengono copiate come segnaposto vuoti negli Appunti.  
  
### <a name="to-enable-cell-copying"></a>Per abilitare la copia delle celle  
  
- Impostare la proprietà <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice completo seguente viene illustrato come le celle vengono copiate negli Appunti. In questo esempio è incluso un pulsante che consente di copiare le celle selezionate negli Appunti mediante il metodo <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> e viene visualizzato il contenuto degli Appunti in una casella di testo.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per questo codice sono necessari i requisiti seguenti:  
  
- Riferimenti agli assembly N:System e N:System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>
- <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>
- [Uso della selezione e degli Appunti con il controllo DataGridView di Windows Form](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
