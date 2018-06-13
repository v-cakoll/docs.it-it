---
title: "Procedura dettagliata: Esecuzione di un'operazione di trascinamento della selezione in Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 6c78a06e37de491e95d56d29c9d2f3e60b88e8ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529458"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>Procedura dettagliata: Esecuzione di un'operazione di trascinamento della selezione in Windows Form
Per eseguire operazioni di trascinamento e rilascio all'interno delle applicazioni basate su Windows è necessario gestire una serie di eventi, in particolare il <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, e <xref:System.Windows.Forms.Control.DragDrop> eventi. Usando le informazioni disponibili negli argomenti di questi eventi, è possibile facilitare le operazioni di trascinamento della selezione.  
  
## <a name="dragging-data"></a>Trascinamento di dati  
 Tutte le operazioni di trascinamento della selezione iniziano con il trascinamento. La funzionalità che consente di raccogliere quando inizia a trascinare i dati viene implementata nel <xref:System.Windows.Forms.Control.DoDragDrop%2A> metodo.  
  
 Nell'esempio seguente, il <xref:System.Windows.Forms.Control.MouseDown> evento utilizzato per avviare l'operazione di trascinamento perché è più intuitivo (la maggior parte delle operazioni di trascinamento e rilascio iniziano con il pulsante del mouse viene premuto un). Tenere tuttavia presente che, per avviare una procedura di trascinamento della selezione, può essere usato qualsiasi evento.  
  
> [!NOTE]
>  Alcuni controlli hanno eventi specifici per il trascinamento. Il <xref:System.Windows.Forms.ListView> e <xref:System.Windows.Forms.TreeView> controlli, ad esempio, avere un <xref:System.Windows.Forms.TreeView.ItemDrag> evento.  
  
#### <a name="to-start-a-drag-operation"></a>Per avviare un'operazione di trascinamento  
  
1.  Nel <xref:System.Windows.Forms.Control.MouseDown> evento per il controllo in cui inizia il trascinamento, utilizzare il `DoDragDrop` l'effetto consentito e il metodo per impostare i dati da trascinare. Per altre informazioni, vedere <xref:System.Windows.Forms.DragEventArgs.Data%2A> e <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
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
    >  Qualsiasi tipo di dati può essere utilizzati come parametro nel `DoDragDrop` metodo; nell'esempio precedente, il <xref:System.Windows.Forms.Control.Text%2A> proprietà del <xref:System.Windows.Forms.Button> controllo veniva utilizzato (anziché un valore a livello di codice o il recupero dei dati da un set di dati) perché la proprietà è correlata al percorso trascinato da (il <xref:System.Windows.Forms.Button> controllo). Tenerlo presente quando si incorporano operazioni di trascinamento della selezione nelle applicazioni basate su Windows.  
  
 Durante un'operazione di trascinamento è attiva, è possibile gestire il <xref:System.Windows.Forms.Control.QueryContinueDrag> evento, quale "richiede l'autorizzazione" del sistema per continuare l'operazione di trascinamento. Quando si gestisce questo metodo, è anche appropriato chiamare i metodi che avranno effetto sull'operazione di trascinamento, ad esempio di espandere un <xref:System.Windows.Forms.TreeNode> in un <xref:System.Windows.Forms.TreeView> controllare quando il cursore viene spostato su di esso.  
  
## <a name="dropping-data"></a>Rilascio dei dati  
 Dopo avere iniziato a trascinare i dati da una posizione in un Windows Form o in un controllo, sarà ovviamente necessario rilasciarli. Il cursore cambia quando attraversa un'area di un form o di un controllo configurata correttamente per il rilascio dei dati. Qualsiasi area all'interno di un Windows Form o controllo, è possibile eseguire per accettare dati trascinati impostando il <xref:System.Windows.Forms.Control.AllowDrop%2A> proprietà e la gestione di <xref:System.Windows.Forms.Control.DragEnter> e <xref:System.Windows.Forms.Control.DragDrop> eventi.  
  
#### <a name="to-perform-a-drop"></a>Per eseguire un rilascio  
  
1.  Impostare il <xref:System.Windows.Forms.Control.AllowDrop%2A> proprietà su true.  
  
2.  Nel `DragEnter` evento per il controllo in cui verrà eseguita l'eliminazione, assicurarsi che i dati trascinati siano di un tipo accettabile (in questo caso, <xref:System.Windows.Forms.Control.Text%2A>). Il codice imposta quindi l'effetto che si verificherà quando l'eliminazione si verifica in un valore di <xref:System.Windows.Forms.DragDropEffects> enumerazione. Per altre informazioni, vedere <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
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
    >  È possibile definire <xref:System.Windows.Forms.DataFormats> specificando il proprio oggetto come il <xref:System.Object> parametro del <xref:System.Windows.Forms.DataObject.SetData%2A> metodo. Assicurarsi, in tal caso, che l'oggetto specificato sia serializzabile. Per altre informazioni, vedere <xref:System.Runtime.Serialization.ISerializable>.  
  
3.  Nel <xref:System.Windows.Forms.Control.DragDrop> evento per il controllo in cui verrà eseguita l'eliminazione, utilizzare il <xref:System.Windows.Forms.DataObject.GetData%2A> metodo per recuperare i dati trascinati. Per altre informazioni, vedere <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.  
  
     Nell'esempio seguente, un <xref:System.Windows.Forms.TextBox> il controllo viene trascinato a (in cui verrà eseguita l'eliminazione). Il codice imposta il <xref:System.Windows.Forms.Control.Text%2A> proprietà del <xref:System.Windows.Forms.TextBox> controllare uguale per i dati trascinati.  
  
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
    >  Inoltre, è possibile utilizzare il <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> proprietà, in modo che, a seconda di tasti premuti durante l'operazione di trascinamento e rilascio, alcuni effetti si verificano (ad esempio, è standard per copiare i dati trascinati quando viene premuto il tasto CTRL).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Aggiungere dati agli Appunti](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 [Procedura: Recuperare dati dagli Appunti](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 [Drag-and-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md) (Supporto delle operazioni di trascinamento della selezione e degli Appunti)
