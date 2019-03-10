---
title: "Procedura dettagliata: Esecuzione di un'operazione di trascinamento e rilascio in Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 664c78ce3fff9651acf6ad720360cdb077f23108
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715243"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>Procedura dettagliata: Esecuzione di un'operazione di trascinamento e rilascio in Windows Form
Per eseguire operazioni di trascinamento e rilascio all'interno di applicazioni basate su Windows è necessario gestire una serie di eventi, in particolare il <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, e <xref:System.Windows.Forms.Control.DragDrop> eventi. Usando le informazioni disponibili negli argomenti di questi eventi, è possibile facilitare le operazioni di trascinamento della selezione.  
  
## <a name="dragging-data"></a>Trascinamento di dati  
 Tutte le operazioni di trascinamento della selezione iniziano con il trascinamento. La funzionalità per abilitare i dati da raccogliere quando inizia il trascinamento viene implementata nel <xref:System.Windows.Forms.Control.DoDragDrop%2A> (metodo).  
  
 Nell'esempio seguente, il <xref:System.Windows.Forms.Control.MouseDown> eventi viene usato per avviare l'operazione di trascinamento perché è il più intuitivo (la maggior parte delle operazioni di trascinamento e rilascio iniziano con la pressione del pulsante del mouse). Tenere tuttavia presente che, per avviare una procedura di trascinamento della selezione, può essere usato qualsiasi evento.  
  
> [!NOTE]
>  Alcuni controlli hanno eventi specifici per il trascinamento. Il <xref:System.Windows.Forms.ListView> e <xref:System.Windows.Forms.TreeView> controlli, ad esempio, avere un <xref:System.Windows.Forms.TreeView.ItemDrag> evento.  
  
#### <a name="to-start-a-drag-operation"></a>Per avviare un'operazione di trascinamento  
  
1.  Nel <xref:System.Windows.Forms.Control.MouseDown> evento per il controllo in cui inizierà il trascinamento, usare il `DoDragDrop` metodo per impostare i dati da trascinare e l'effetto consentito il trascinamento avrà. Per altre informazioni, vedere <xref:System.Windows.Forms.DragEventArgs.Data%2A> e <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     L'esempio seguente illustra come avviare un'operazione di trascinamento. Il controllo in cui inizia il trascinamento è un <xref:System.Windows.Forms.Button> (controllo), i dati trascinati è la stringa che rappresenta il <xref:System.Windows.Forms.Control.Text%2A> proprietà del <xref:System.Windows.Forms.Button> controllo e gli effetti consentiti sono la copia o spostamento.  
  
    ```vb  
    Private Sub Button1_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles Button1.MouseDown  
       Button1.DoDragDrop(Button1.Text, DragDropEffects.Copy Or DragDropEffects.Move)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_MouseDown(object sender,   
    System.Windows.Forms.MouseEventArgs e)  
    {  
       button1.DoDragDrop(button1.Text, DragDropEffects.Copy |   
          DragDropEffects.Move);  
    }  
    ```  
  
    > [!NOTE]
    >  Tutti i dati possono essere utilizzati come parametro nel `DoDragDrop` (metodo); nell'esempio precedente, il <xref:System.Windows.Forms.Control.Text%2A> proprietà del <xref:System.Windows.Forms.Button> controllo veniva utilizzato (anziché codificare un valore o il recupero dei dati da un set di dati) perché la proprietà era correlata al percorso che viene trascinato dalla (il <xref:System.Windows.Forms.Button> controllo). Tenerlo presente quando si incorporano operazioni di trascinamento della selezione nelle applicazioni basate su Windows.  
  
 Mentre un'operazione di trascinamento è attiva, è possibile gestire il <xref:System.Windows.Forms.Control.QueryContinueDrag> evento che "chiede l'autorizzazione" del sistema a continuare l'operazione di trascinamento. Quando si gestisce questo metodo, è anche opportuno chiamare i metodi che avranno effetto sull'operazione di trascinamento, ad esempio l'espansione una <xref:System.Windows.Forms.TreeNode> in un <xref:System.Windows.Forms.TreeView> controllare quando il cursore viene spostato su di esso.  
  
## <a name="dropping-data"></a>Rilascio dei dati  
 Dopo avere iniziato a trascinare i dati da una posizione in un Windows Form o in un controllo, sarà ovviamente necessario rilasciarli. Il cursore cambia quando attraversa un'area di un form o di un controllo configurata correttamente per il rilascio dei dati. Qualsiasi area all'interno di un Windows Form o controllo può essere configurata per accettare i dati rilasciati impostando il <xref:System.Windows.Forms.Control.AllowDrop%2A> proprietà e la gestione di <xref:System.Windows.Forms.Control.DragEnter> e <xref:System.Windows.Forms.Control.DragDrop> eventi.  
  
#### <a name="to-perform-a-drop"></a>Per eseguire un rilascio  
  
1.  Impostare il <xref:System.Windows.Forms.Control.AllowDrop%2A> proprietà su true.  
  
2.  Nel `DragEnter` evento per il controllo in cui verrà eseguito il rilascio, assicurarsi che i dati trascinati siano di un tipo accettabile (in questo caso, <xref:System.Windows.Forms.Control.Text%2A>). Il codice imposta quindi l'effetto che verrà eseguito quando viene eseguito il rilascio in un valore di <xref:System.Windows.Forms.DragDropEffects> enumerazione. Per altre informazioni, vedere <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
    ```vb  
    Private Sub TextBox1_DragEnter(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
         e.Effect = DragDropEffects.Copy  
       Else  
         e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    > [!NOTE]
    >  È possibile definire il proprio <xref:System.Windows.Forms.DataFormats> specificando il proprio oggetto come i <xref:System.Object> parametro del <xref:System.Windows.Forms.DataObject.SetData%2A> (metodo). Assicurarsi, in tal caso, che l'oggetto specificato sia serializzabile. Per altre informazioni, vedere <xref:System.Runtime.Serialization.ISerializable>.  
  
3.  Nel <xref:System.Windows.Forms.Control.DragDrop> evento per il controllo in cui verrà eseguito il rilascio, usare il <xref:System.Windows.Forms.DataObject.GetData%2A> metodo per recuperare i dati trascinati. Per altre informazioni, vedere <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.  
  
     Nell'esempio seguente, un <xref:System.Windows.Forms.TextBox> è il controllo che viene trascinato per (in cui verrà eseguito il rilascio). Il codice imposta la <xref:System.Windows.Forms.Control.Text%2A> proprietà del <xref:System.Windows.Forms.TextBox> controllare uguale ai dati trascinati.  
  
    ```vb  
    Private Sub TextBox1_DragDrop(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragDrop  
       TextBox1.Text = e.Data.GetData(DataFormats.Text).ToString  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       textBox1.Text = e.Data.GetData(DataFormats.Text).ToString();  
    }  
    ```  
  
    > [!NOTE]
    >  Inoltre, è possibile utilizzare il <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> proprietà, in modo che, a seconda dei tasti premuti durante l'operazione di trascinamento e rilascio, si verifichino determinati effetti (ad esempio, è standard per copiare i dati trascinati quando viene premuto il tasto CTRL).  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Aggiungere dati agli Appunti](how-to-add-data-to-the-clipboard.md)
- [Procedura: Recuperare i dati dagli Appunti](how-to-retrieve-data-from-the-clipboard.md)
- [Drag-and-Drop Operations and Clipboard Support](drag-and-drop-operations-and-clipboard-support.md) (Supporto delle operazioni di trascinamento della selezione e degli Appunti)
