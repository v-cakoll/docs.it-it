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
ms.openlocfilehash: 2b85f734a5f8b31531cfe48f87681d98304db09b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929636"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a>Procedura: Definire un'icona per un pulsante della barra degli strumenti
> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 <xref:System.Windows.Forms.ToolBar>i pulsanti sono in grado di visualizzare le icone al loro interno per facilitarne l'identificazione da parte degli utenti. Questa operazione viene eseguita tramite l'aggiunta di immagini al componente [componente ImageList](imagelist-component-windows-forms.md) e l'associazione <xref:System.Windows.Forms.ImageList> del componente <xref:System.Windows.Forms.ToolBar> al controllo.  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a>Per impostare un'icona per un pulsante della barra degli strumenti a livello di codice  
  
1. In una routine creare un'istanza di <xref:System.Windows.Forms.ImageList> un componente e <xref:System.Windows.Forms.ToolBar> di un controllo.  
  
2. Nella stessa procedura assegnare un'immagine al <xref:System.Windows.Forms.ImageList> componente.  
  
3. Nella stessa procedura assegnare il <xref:System.Windows.Forms.ImageList> controllo <xref:System.Windows.Forms.ToolBar> al controllo e assegnare la <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> proprietà dei singoli pulsanti della barra degli strumenti.  
  
     Nell'esempio di codice seguente il percorso impostato per il percorso dell'immagine è la cartella **documenti** . Questa operazione viene eseguita perché è possibile presupporre che la maggior parte dei computer che eseguono il sistema operativo Windows includa questa directory. Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi. Nell'esempio seguente si presuppone che un modulo <xref:System.Windows.Forms.PictureBox> con un controllo sia già stato aggiunto.  
  
     Seguendo i passaggi precedenti, è necessario scrivere codice simile a quello visualizzato di seguito.  
  
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
- [Procedura: Eventi del menu trigger per i pulsanti della barra degli strumenti](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [Controllo ToolBar](toolbar-control-windows-forms.md)
- [Componente ImageList](imagelist-component-windows-forms.md)
