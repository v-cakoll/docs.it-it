---
title: Stampa con anteprima di stampa
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing [Windows Forms], using print preview
- printing [Windows Forms], with print preview
- print preview
ms.assetid: 4a16f7e2-ae10-4485-b0ae-3d558334d0fe
ms.openlocfilehash: 1975c902fdb56326c763f2e2fc11e381ffc7fbd3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740600"
---
# <a name="how-to-print-in-windows-forms-using-print-preview"></a>Procedura: stampare in Windows Form tramite l'anteprima di stampa
Nella programmazione di Windows Form è comune offrire servizi di anteprima di stampa oltre che di stampa. Per aggiungere facilmente i servizi di anteprima di stampa all'applicazione, usare un controllo <xref:System.Windows.Forms.PrintPreviewDialog> in combinazione con la logica di gestione degli eventi <xref:System.Drawing.Printing.PrintDocument.PrintPage> per la stampa di un file.  
  
### <a name="to-preview-a-text-document-with-a-printpreviewdialog-control"></a>Per visualizzare in anteprima un documento di testo con un controllo PrintPreviewDialog  
  
1. Aggiungere un oggetto <xref:System.Windows.Forms.PrintPreviewDialog>, un oggetto <xref:System.Drawing.Printing.PrintDocument>e due stringhe al form.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#1)]  
  
2. Impostare la proprietà <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> sul documento da stampare, quindi aprire e leggere il contenuto del documento fino alla stringa aggiunta in precedenza.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#2)]  
  
3. Come per la stampa del documento, nel gestore eventi <xref:System.Drawing.Printing.PrintDocument.PrintPage> usare la proprietà <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> della classe <xref:System.Drawing.Printing.PrintPageEventArgs> e il contenuto del file per calcolare le righe per pagina ed eseguire il rendering del contenuto del documento. Dopo la generazione di ogni pagina, controllare se si tratta dell'ultima pagina e impostare la proprietà <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> della classe <xref:System.Drawing.Printing.PrintPageEventArgs> di conseguenza. L'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> viene generato finché la proprietà <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> non assume valore `false`. Al termine del rendering del documento, reimpostare la stringa da sottoporre a rendering. Assicurarsi inoltre che l'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> sia associato al relativo metodo di gestione degli eventi.  
  
    > [!NOTE]
    > Se è stata implementata la stampa nell'applicazione, è possibile che i passaggi 2 e 3 siano già stati completati.  
  
     Nell'esempio di codice seguente il gestore eventi viene usato per stampare il file "testPage.txt" con lo stesso tipo di carattere usato nel form.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#3)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#3)]  
  
4. Impostare la proprietà <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> del controllo <xref:System.Windows.Forms.PrintPreviewDialog> sul componente <xref:System.Drawing.Printing.PrintDocument> nel form.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#5)]  
  
5. Chiamare il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> sul controllo <xref:System.Windows.Forms.PrintPreviewDialog> . In genere la chiamata al metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> si esegue dal metodo di gestione degli eventi <xref:System.Windows.Forms.Control.Click> di un pulsante. Chiamando il metodo <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> viene generato l'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> e viene eseguito il rendering dell'output sul controllo <xref:System.Windows.Forms.PrintPreviewDialog> . Quando l'utente fa clic sull'icona di stampa nella finestra di dialogo, l'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> viene generato di nuovo, inviando l'output alla stampante anziché alla finestra di dialogo di anteprima. Questo è il motivo per cui alla fine del processo di rendering nel passaggio 3 la stringa viene reimpostata.  
  
     L'esempio di codice seguente illustra il metodo di gestione degli eventi <xref:System.Windows.Forms.Control.Click> per un pulsante nel form. Questo metodo chiama i metodi per la lettura del documento e la visualizzazione della finestra di dialogo di anteprima.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#4)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#4)]  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Windows.Forms e System.Drawing.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: stampare un file di testo con più pagine in Windows Forms](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [Supporto per la stampa in Windows Forms](windows-forms-print-support.md)
- [Stampa più sicura in Windows Forms](../more-secure-printing-in-windows-forms.md)
