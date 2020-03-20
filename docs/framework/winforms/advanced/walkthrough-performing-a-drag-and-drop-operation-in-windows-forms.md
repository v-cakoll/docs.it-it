---
title: "Procedura dettagliata: Eseguire un'operazione di trascinamento della selezioneWalkthrough: Perform a drag-and-drop operation"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: b5e4bf753733cb9bd010672f40e8fbeb0cf036bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182435"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>Procedura dettagliata: Esecuzione di un'operazione di trascinamento della selezione in Windows Form
Per eseguire operazioni di trascinamento della selezione all'interno di applicazioni basate <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragLeave>su <xref:System.Windows.Forms.Control.DragDrop> Windows, è necessario gestire una serie di eventi, in particolare gli eventi , e . Usando le informazioni disponibili negli argomenti di questi eventi, è possibile facilitare le operazioni di trascinamento della selezione.  
  
## <a name="dragging-data"></a>Trascinamento di dati  
 Tutte le operazioni di trascinamento della selezione iniziano con il trascinamento. La funzionalità per consentire la raccolta dei dati <xref:System.Windows.Forms.Control.DoDragDrop%2A> all'inizio del trascinamento viene implementata nel metodo.  
  
 Nell'esempio seguente, <xref:System.Windows.Forms.Control.MouseDown> l'evento viene utilizzato per avviare l'operazione di trascinamento perché è il più intuitivo (la maggior parte delle azioni di trascinamento della selezione inizia con il pulsante del mouse premuto). Tenere tuttavia presente che, per avviare una procedura di trascinamento della selezione, può essere usato qualsiasi evento.  
  
> [!NOTE]
> Alcuni controlli hanno eventi specifici per il trascinamento. I <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> controlli e, ad <xref:System.Windows.Forms.TreeView.ItemDrag> esempio, dispongono di un evento.  
  
#### <a name="to-start-a-drag-operation"></a>Per avviare un'operazione di trascinamento  
  
1. Nel <xref:System.Windows.Forms.Control.MouseDown> caso in cui inizierà il controllo `DoDragDrop` in cui inizierà il trascinamento, utilizzare il metodo per impostare i dati da trascinare e l'effetto consentito trascinamento avrà. Per altre informazioni, vedere <xref:System.Windows.Forms.DragEventArgs.Data%2A> e <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     L'esempio seguente illustra come avviare un'operazione di trascinamento. Il controllo in cui <xref:System.Windows.Forms.Button> inizia il trascinamento è un controllo, <xref:System.Windows.Forms.Control.Text%2A> i <xref:System.Windows.Forms.Button> dati trascinati è la stringa che rappresenta la proprietà del controllo e gli effetti consentiti sono la copia o lo spostamento.  
  
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
    > Qualsiasi dato può essere utilizzato `DoDragDrop` come parametro nel metodo ; nell'esempio precedente, <xref:System.Windows.Forms.Control.Text%2A> è <xref:System.Windows.Forms.Button> stata utilizzata la proprietà del controllo (anziché hard-codificare un valore o recuperare dati da <xref:System.Windows.Forms.Button> un set di dati) perché la proprietà era correlata alla posizione da cui viene trascinata (il controllo). Tenerlo presente quando si incorporano operazioni di trascinamento della selezione nelle applicazioni basate su Windows.  
  
 Mentre è attiva un'operazione di <xref:System.Windows.Forms.Control.QueryContinueDrag> trascinamento, è possibile gestire l'evento, che "chiede l'autorizzazione" del sistema per continuare l'operazione di trascinamento. Quando si gestisce questo metodo, è anche il punto appropriato per chiamare i metodi che <xref:System.Windows.Forms.TreeNode> avranno un effetto sull'operazione di trascinamento, ad esempio l'espansione di un in un <xref:System.Windows.Forms.TreeView> controllo quando il cursore passa su di esso.  
  
## <a name="dropping-data"></a>Rilascio dei dati  
 Dopo avere iniziato a trascinare i dati da una posizione in un Windows Form o in un controllo, sarà ovviamente necessario rilasciarli. Il cursore cambia quando attraversa un'area di un form o di un controllo configurata correttamente per il rilascio dei dati. Qualsiasi area all'interno di un Windows Form o <xref:System.Windows.Forms.Control.AllowDrop%2A> di un <xref:System.Windows.Forms.Control.DragEnter> controllo <xref:System.Windows.Forms.Control.DragDrop> può essere impostata per accettare i dati eliminati impostando la proprietà e gestendo gli eventi e .  
  
#### <a name="to-perform-a-drop"></a>Per eseguire un rilascio  
  
1. Impostare <xref:System.Windows.Forms.Control.AllowDrop%2A> la proprietà su true.  
  
2. Nel `DragEnter` caso in cui si verifichi il controllo, assicurarsi che i dati trascinati <xref:System.Windows.Forms.Control.Text%2A>siano di un tipo accettabile (in questo caso, ). Il codice imposta quindi l'effetto che si verificherà <xref:System.Windows.Forms.DragDropEffects> quando si verifica il rilascio su un valore nell'enumerazione. Per altre informazioni, vedere <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
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
    > È possibile definire <xref:System.Windows.Forms.DataFormats> il proprio specificando il <xref:System.Object> proprio <xref:System.Windows.Forms.DataObject.SetData%2A> oggetto come parametro del metodo. Assicurarsi, in tal caso, che l'oggetto specificato sia serializzabile. Per altre informazioni, vedere <xref:System.Runtime.Serialization.ISerializable>.  
  
3. Nel <xref:System.Windows.Forms.Control.DragDrop> caso in cui si verifichi il <xref:System.Windows.Forms.DataObject.GetData%2A> controllo in cui si verificherà il rilascio, utilizzare il metodo per recuperare i dati trascinati. Per altre informazioni, vedere <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.  
  
     Nell'esempio seguente, <xref:System.Windows.Forms.TextBox> un controllo è il controllo trascinato in (dove si verificherà il rilascio). Il codice <xref:System.Windows.Forms.Control.Text%2A> imposta la <xref:System.Windows.Forms.TextBox> proprietà del controllo uguale ai dati trascinati.  
  
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
    > Inoltre, è possibile utilizzare <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> la proprietà , in modo che, a seconda dei tasti premuti durante l'operazione di trascinamento della selezione, si verificano determinati effetti (ad esempio, è standard copiare i dati trascinati quando viene premuto il tasto CTRL).  
  
## <a name="see-also"></a>Vedere anche

- [How to: Add Data to the Clipboard](how-to-add-data-to-the-clipboard.md) (Procedura: Aggiungere dati agli Appunti)
- [How to: Retrieve Data from the Clipboard](how-to-retrieve-data-from-the-clipboard.md) (Procedura: Recuperare dati dagli Appunti)
- [Drag-and-Drop Operations and Clipboard Support](drag-and-drop-operations-and-clipboard-support.md) (Supporto delle operazioni di trascinamento della selezione e degli Appunti)
