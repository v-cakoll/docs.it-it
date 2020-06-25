---
title: "Procedura dettagliata: eseguire un'operazione di trascinamento della selezione"
description: Informazioni su come eseguire un'operazione di trascinamento della selezione in Windows Forms gestendo una serie di eventi, in particolare gli eventi DragEnter, DragLeave e DragDrop.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 83bfda875e2fdec3981bbcb8f8f7be00db342440
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325813"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>Procedura dettagliata: Esecuzione di un'operazione di trascinamento della selezione in Windows Form
Per eseguire operazioni di trascinamento della selezione nelle applicazioni basate su Windows, è necessario gestire una serie di eventi, in particolare gli <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragLeave> eventi, e <xref:System.Windows.Forms.Control.DragDrop> . Usando le informazioni disponibili negli argomenti di questi eventi, è possibile facilitare le operazioni di trascinamento della selezione.  
  
## <a name="dragging-data"></a>Trascinamento di dati  
 Tutte le operazioni di trascinamento della selezione iniziano con il trascinamento. La funzionalità per consentire la raccolta dei dati quando inizia il trascinamento è implementata nel <xref:System.Windows.Forms.Control.DoDragDrop%2A> metodo.  
  
 Nell'esempio seguente, l' <xref:System.Windows.Forms.Control.MouseDown> evento viene usato per avviare l'operazione di trascinamento perché è il più intuitivo (la maggior parte delle azioni di trascinamento inizia con il pulsante del mouse premuto). Tenere tuttavia presente che, per avviare una procedura di trascinamento della selezione, può essere usato qualsiasi evento.  
  
> [!NOTE]
> Alcuni controlli hanno eventi specifici per il trascinamento. I <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> controlli e, ad esempio, hanno un <xref:System.Windows.Forms.TreeView.ItemDrag> evento.  
  
#### <a name="to-start-a-drag-operation"></a>Per avviare un'operazione di trascinamento  
  
1. Nell' <xref:System.Windows.Forms.Control.MouseDown> evento per il controllo in cui inizierà il trascinamento, utilizzare il `DoDragDrop` metodo per impostare i dati da trascinare e il trascinamento dell'effetto consentito avrà. Per altre informazioni, vedere <xref:System.Windows.Forms.DragEventArgs.Data%2A> e <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     L'esempio seguente illustra come avviare un'operazione di trascinamento. Il controllo in cui inizia il trascinamento è un <xref:System.Windows.Forms.Button> controllo, i dati trascinati sono la stringa che rappresenta la <xref:System.Windows.Forms.Control.Text%2A> proprietà del <xref:System.Windows.Forms.Button> controllo e gli effetti consentiti vengono copiati o spostati.  
  
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
    > I dati possono essere usati come parametro nel `DoDragDrop` metodo. nell'esempio precedente, <xref:System.Windows.Forms.Control.Text%2A> è stata usata la proprietà del controllo, anziché impostare come <xref:System.Windows.Forms.Button> hardcoded un valore o recuperare i dati da un set di dati, perché la proprietà era correlata al percorso da trascinare (il <xref:System.Windows.Forms.Button> controllo). Tenerlo presente quando si incorporano operazioni di trascinamento della selezione nelle applicazioni basate su Windows.  
  
 Mentre è attiva un'operazione di trascinamento, è possibile gestire l' <xref:System.Windows.Forms.Control.QueryContinueDrag> evento, che "chiede l'autorizzazione" del sistema per continuare l'operazione di trascinamento. Quando si gestisce questo metodo, è anche il punto appropriato per chiamare i metodi che avranno effetto sull'operazione di trascinamento, ad esempio l'espansione di un oggetto <xref:System.Windows.Forms.TreeNode> in un <xref:System.Windows.Forms.TreeView> controllo quando il cursore viene spostato su di esso.  
  
## <a name="dropping-data"></a>Rilascio dei dati  
 Dopo avere iniziato a trascinare i dati da una posizione in un Windows Form o in un controllo, sarà ovviamente necessario rilasciarli. Il cursore cambia quando attraversa un'area di un form o di un controllo configurata correttamente per il rilascio dei dati. È possibile fare in modo che qualsiasi area all'interno di un Windows Form o di un controllo accetti i dati rimossi impostando la <xref:System.Windows.Forms.Control.AllowDrop%2A> proprietà e gestendo gli <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragDrop> eventi e.  
  
#### <a name="to-perform-a-drop"></a>Per eseguire un rilascio  
  
1. Impostare la <xref:System.Windows.Forms.Control.AllowDrop%2A> proprietà su true.  
  
2. Nell' `DragEnter` evento per il controllo in cui si verificherà il rilascio, assicurarsi che i dati trascinati siano di un tipo accettabile (in questo caso <xref:System.Windows.Forms.Control.Text%2A> ). Il codice imposta quindi l'effetto che si verificherà quando il rilascio viene eseguito in un valore nell' <xref:System.Windows.Forms.DragDropEffects> enumerazione. Per altre informazioni, vedere <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
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
    > È possibile definirne <xref:System.Windows.Forms.DataFormats> di propri specificando il proprio oggetto come <xref:System.Object> parametro del <xref:System.Windows.Forms.DataObject.SetData%2A> metodo. Assicurarsi, in tal caso, che l'oggetto specificato sia serializzabile. Per altre informazioni, vedere <xref:System.Runtime.Serialization.ISerializable>.  
  
3. Nell' <xref:System.Windows.Forms.Control.DragDrop> evento per il controllo in cui si verificherà il rilascio, utilizzare il <xref:System.Windows.Forms.DataObject.GetData%2A> metodo per recuperare i dati trascinati. Per altre informazioni, vedere <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.  
  
     Nell'esempio seguente un <xref:System.Windows.Forms.TextBox> controllo è il controllo da trascinare (in cui si verificherà il rilascio). Il codice imposta la <xref:System.Windows.Forms.Control.Text%2A> proprietà del <xref:System.Windows.Forms.TextBox> controllo uguale ai dati trascinati.  
  
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
    > Inoltre, è possibile utilizzare la <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> proprietà, in modo che, a seconda delle chiavi deselezionate durante l'operazione di trascinamento della selezione, si verifichino determinati effetti, ad esempio è standard copiare i dati trascinati quando viene premuto il tasto CTRL.  
  
## <a name="see-also"></a>Vedi anche

- [How to: Add Data to the Clipboard](how-to-add-data-to-the-clipboard.md) (Procedura: Aggiungere dati agli Appunti)
- [How to: Retrieve Data from the Clipboard](how-to-retrieve-data-from-the-clipboard.md) (Procedura: Recuperare dati dagli Appunti)
- [Drag-and-Drop Operations and Clipboard Support](drag-and-drop-operations-and-clipboard-support.md) (Supporto delle operazioni di trascinamento della selezione e degli Appunti)
