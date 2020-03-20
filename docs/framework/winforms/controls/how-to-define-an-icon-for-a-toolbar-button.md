---
title: "Procedura: definire un'icona per un pulsante ToolBar"
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
ms.openlocfilehash: 84c67c7d2584390ba3e48cb83820c65c6bb45d1f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182202"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a><span data-ttu-id="e4c05-102">Procedura: definire un'icona per un pulsante ToolBar</span><span class="sxs-lookup"><span data-stu-id="e4c05-102">How to: Define an Icon for a ToolBar Button</span></span>
> [!NOTE]
> <span data-ttu-id="e4c05-103">Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="e4c05-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="e4c05-104"><xref:System.Windows.Forms.ToolBar>sono in grado di visualizzare le icone al loro interno per una facile identificazione da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="e4c05-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="e4c05-105">Ciò si ottiene aggiungendo immagini al componente [Componente ImageList](imagelist-component-windows-forms.md) e quindi associando il <xref:System.Windows.Forms.ImageList> componente al <xref:System.Windows.Forms.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="e4c05-105">This is achieved through adding images to the [ImageList Component](imagelist-component-windows-forms.md) component and then associating the <xref:System.Windows.Forms.ImageList> component with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a><span data-ttu-id="e4c05-106">Per impostare un'icona per un pulsante della barra degli strumenti a livello di codiceTo set an icon for a toolbar button programmatically</span><span class="sxs-lookup"><span data-stu-id="e4c05-106">To set an icon for a toolbar button programmatically</span></span>  
  
1. <span data-ttu-id="e4c05-107">In una routine <xref:System.Windows.Forms.ImageList> creare un'istanza di un componente e di un <xref:System.Windows.Forms.ToolBar> controllo.</span><span class="sxs-lookup"><span data-stu-id="e4c05-107">In a procedure, instantiate an <xref:System.Windows.Forms.ImageList> component and a <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
2. <span data-ttu-id="e4c05-108">Nella stessa procedura, assegnare <xref:System.Windows.Forms.ImageList> un'immagine al componente.</span><span class="sxs-lookup"><span data-stu-id="e4c05-108">In the same procedure, assign an image to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
3. <span data-ttu-id="e4c05-109">Nella stessa routine assegnare <xref:System.Windows.Forms.ImageList> il <xref:System.Windows.Forms.ToolBar> controllo al <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> controllo e la proprietà dei singoli pulsanti della barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="e4c05-109">In the same procedure, assign the <xref:System.Windows.Forms.ImageList> control to the <xref:System.Windows.Forms.ToolBar> control and assign the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of the individual toolbar buttons.</span></span>  
  
     <span data-ttu-id="e4c05-110">Nell'esempio di codice seguente, il percorso impostato per il percorso dell'immagine è la cartella **Documenti.**</span><span class="sxs-lookup"><span data-stu-id="e4c05-110">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="e4c05-111">Questo viene fatto, perché si può supporre che la maggior parte dei computer che eseguono il sistema operativo Windows includerà questa directory.</span><span class="sxs-lookup"><span data-stu-id="e4c05-111">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="e4c05-112">Ciò consente inoltre agli utenti del sistema con livelli di accesso minimo di eseguire l'applicazione senza problemi.</span><span class="sxs-lookup"><span data-stu-id="e4c05-112">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="e4c05-113">Nell'esempio riportato di <xref:System.Windows.Forms.PictureBox> seguito si presuppone che un form con un controllo sia già stato aggiunto.</span><span class="sxs-lookup"><span data-stu-id="e4c05-113">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
     <span data-ttu-id="e4c05-114">Seguendo i passaggi precedenti, si dovrebbe avere scritto codice simile a quello visualizzato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e4c05-114">Following the steps above, you should have written code similar to that displayed below.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e4c05-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4c05-115">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="e4c05-116">Procedura: Attivare eventi di menu per i pulsanti di una barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="e4c05-116">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="e4c05-117">Controllo ToolBar</span><span class="sxs-lookup"><span data-stu-id="e4c05-117">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="e4c05-118">Componente ImageList</span><span class="sxs-lookup"><span data-stu-id="e4c05-118">ImageList Component</span></span>](imagelist-component-windows-forms.md)
