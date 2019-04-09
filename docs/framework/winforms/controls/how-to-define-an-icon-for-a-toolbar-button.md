---
title: "Procedura: Definire un'icona per un pulsante della barra degli strumenti"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- buttons [Windows Forms], icons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: 84db98b4-8566-49ce-b2c8-1fd66a5eb3a0
ms.openlocfilehash: 0d4a17528ca3eb81f93419491766e370be551b1e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153127"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a>Procedura: Definire un'icona per un pulsante della barra degli strumenti
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 <xref:System.Windows.Forms.ToolBar> i pulsanti sono in grado di visualizzare icone all'interno di essi per facilitare l'identificazione da parte degli utenti. Questo risultato viene ottenuto tramite l'aggiunta di immagini per le [componente ImageList](imagelist-component-windows-forms.md) componente e quindi associando il <xref:System.Windows.Forms.ImageList> componente con il <xref:System.Windows.Forms.ToolBar> controllo.  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a>Per impostare un'icona per un pulsante della barra degli strumenti a livello di codice  
  
1.  In una procedura, creare un'istanza di un <xref:System.Windows.Forms.ImageList> componenti e una <xref:System.Windows.Forms.ToolBar> controllo.  
  
2.  Nella procedura stessa, assegnare un'immagine per il <xref:System.Windows.Forms.ImageList> componente.  
  
3.  Nella procedura stessa, assegnare il <xref:System.Windows.Forms.ImageList> il controllo al <xref:System.Windows.Forms.ToolBar> controllano e assegnare il <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> proprietà dei pulsanti della barra degli strumenti individuali.  
  
     Nell'esempio di codice seguente, il percorso impostato per il percorso dell'immagine è il **documenti** cartella. Questa operazione viene eseguita, perché si presume che la maggior parte dei computer che eseguono il sistema operativo Windows sarà inclusa questa directory. Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi. L'esempio seguente si presuppone un form con un <xref:System.Windows.Forms.PictureBox> controllo già aggiunto.  
  
     Seguendo i passaggi precedenti, consente di scrivere codice simile a quello riportato di seguito.  
  
    ```vb  
    Public Sub InitializeMyToolBar()  
    ' Instantiate an ImageList component and a ToolBar control.  
       Dim ToolBar1 as New ToolBar  
       Dim ImageList1 as New ImageList  
    ' Assign an image to the ImageList component.  
    ' You should replace the bold image  
    ' in the sample below with an icon of your own choosing.  
       Dim myImage As System.Drawing.Image = _   
          Image.FromFile Image.FromFile _  
          (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.Personal) _  
          & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    ' Create a ToolBarButton.  
       Dim ToolBarButton1 As New ToolBarButton()  
    ' Add the ToolBarButton to the ToolBar.  
       ToolBar1.Buttons.Add(toolBarButton1)  
    ' Assign an ImageList to the ToolBar.  
       ToolBar1.ImageList = ImageList1  
    ' Assign the ImageIndex property of the ToolBarButton.  
       ToolBarButton1.ImageIndex = 0  
    End Sub  
    ```  
  
    ```csharp  
    public void InitializeMyToolBar()  
    {  
       // Instantiate an ImageList component and a ToolBar control.  
       ToolBar toolBar1 = new  ToolBar();   
       ImageList imageList1 = new ImageList();  
       // Assign an image to the ImageList component.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       Image myImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
       // Create a ToolBarButton.  
       ToolBarButton toolBarButton1 = new ToolBarButton();  
       // Add the ToolBarButton to the ToolBar.  
       toolBar1.Buttons.Add(toolBarButton1);  
       // Assign an ImageList to the ToolBar.  
       toolBar1.ImageList = imageList1;  
       // Assign ImageIndex property of the ToolBarButton.  
       toolBarButton1.ImageIndex = 0;  
    }  
    ```  
  
    ```cpp  
    public:  
       void InitializeMyToolBar()  
       {  
          // Instantiate an ImageList component and a ToolBar control.  
          ToolBar ^ toolBar1 = gcnew  ToolBar();   
          ImageList ^ imageList1 = gcnew ImageList();  
          // Assign an image to the ImageList component.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          Image ^ myImage = Image::FromFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
          // Create a ToolBarButton.  
          ToolBarButton ^ toolBarButton1 = gcnew ToolBarButton();  
          // Add the ToolBarButton to the ToolBar.  
          toolBar1->Buttons->Add(toolBarButton1);  
          // Assign an ImageList to the ToolBar.  
          toolBar1->ImageList = imageList1;  
          // Assign ImageIndex property of the ToolBarButton.  
          toolBarButton1->ImageIndex = 0;  
       }  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolBar>
- [Procedura: Attivare eventi di menu per i pulsanti della barra degli strumenti](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [Controllo ToolBar](toolbar-control-windows-forms.md)
- [Componente ImageList](imagelist-component-windows-forms.md)
