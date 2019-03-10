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
ms.openlocfilehash: fb4a492b081cd9f9e3ccc1d47a4120c705058dd0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57712747"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a><span data-ttu-id="05de9-102">Procedura: Definire un'icona per un pulsante della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="05de9-102">How to: Define an Icon for a ToolBar Button</span></span>
> [!NOTE]
>  <span data-ttu-id="05de9-103">Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="05de9-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="05de9-104"><xref:System.Windows.Forms.ToolBar> i pulsanti sono in grado di visualizzare icone all'interno di essi per facilitare l'identificazione da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="05de9-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="05de9-105">Questo risultato viene ottenuto tramite l'aggiunta di immagini per le [componente ImageList](imagelist-component-windows-forms.md) componente e quindi associando il <xref:System.Windows.Forms.ImageList> componente con il <xref:System.Windows.Forms.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="05de9-105">This is achieved through adding images to the [ImageList Component](imagelist-component-windows-forms.md) component and then associating the <xref:System.Windows.Forms.ImageList> component with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a><span data-ttu-id="05de9-106">Per impostare un'icona per un pulsante della barra degli strumenti a livello di codice</span><span class="sxs-lookup"><span data-stu-id="05de9-106">To set an icon for a toolbar button programmatically</span></span>  
  
1.  <span data-ttu-id="05de9-107">In una procedura, creare un'istanza di un <xref:System.Windows.Forms.ImageList> componenti e una <xref:System.Windows.Forms.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="05de9-107">In a procedure, instantiate an <xref:System.Windows.Forms.ImageList> component and a <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
2.  <span data-ttu-id="05de9-108">Nella procedura stessa, assegnare un'immagine per il <xref:System.Windows.Forms.ImageList> componente.</span><span class="sxs-lookup"><span data-stu-id="05de9-108">In the same procedure, assign an image to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
3.  <span data-ttu-id="05de9-109">Nella procedura stessa, assegnare il <xref:System.Windows.Forms.ImageList> il controllo al <xref:System.Windows.Forms.ToolBar> controllano e assegnare il <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> proprietà dei pulsanti della barra degli strumenti individuali.</span><span class="sxs-lookup"><span data-stu-id="05de9-109">In the same procedure, assign the <xref:System.Windows.Forms.ImageList> control to the <xref:System.Windows.Forms.ToolBar> control and assign the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of the individual toolbar buttons.</span></span>  
  
     <span data-ttu-id="05de9-110">Nell'esempio di codice seguente, il percorso impostato per il percorso dell'immagine è il **documenti** cartella.</span><span class="sxs-lookup"><span data-stu-id="05de9-110">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="05de9-111">Questa operazione viene eseguita, perché si presume che la maggior parte dei computer che eseguono il sistema operativo Windows sarà inclusa questa directory.</span><span class="sxs-lookup"><span data-stu-id="05de9-111">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="05de9-112">Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi.</span><span class="sxs-lookup"><span data-stu-id="05de9-112">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="05de9-113">L'esempio seguente si presuppone un form con un <xref:System.Windows.Forms.PictureBox> controllo già aggiunto.</span><span class="sxs-lookup"><span data-stu-id="05de9-113">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
     <span data-ttu-id="05de9-114">Seguendo i passaggi precedenti, consente di scrivere codice simile a quello riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="05de9-114">Following the steps above, you should have written code similar to that displayed below.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="05de9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05de9-115">See also</span></span>
- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="05de9-116">Procedura: Attivare eventi di Menu per i pulsanti della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="05de9-116">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="05de9-117">Controllo ToolBar</span><span class="sxs-lookup"><span data-stu-id="05de9-117">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="05de9-118">Componente ImageList</span><span class="sxs-lookup"><span data-stu-id="05de9-118">ImageList Component</span></span>](imagelist-component-windows-forms.md)
