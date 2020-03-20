---
title: 'Procedura: aggiungere pulsanti a un controllo ToolBar'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: 78a58a8d-1041-4e38-9219-4096fa6a5c5c
ms.openlocfilehash: 1bb6de58010e70a4edafacafe3dc00b511fc63de
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182333"
---
# <a name="how-to-add-buttons-to-a-toolbar-control"></a><span data-ttu-id="d31d3-102">Procedura: aggiungere pulsanti a un controllo ToolBar</span><span class="sxs-lookup"><span data-stu-id="d31d3-102">How to: Add Buttons to a ToolBar Control</span></span>
> [!NOTE]
> <span data-ttu-id="d31d3-103">Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="d31d3-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="d31d3-104">Una parte integrante del <xref:System.Windows.Forms.ToolBar> controllo è costituita dai pulsanti aggiunti.</span><span class="sxs-lookup"><span data-stu-id="d31d3-104">An integral part of the <xref:System.Windows.Forms.ToolBar> control is the buttons you add to it.</span></span> <span data-ttu-id="d31d3-105">Questi possono essere utilizzati per fornire un facile accesso ai comandi di menu o, in alternativa, possono essere posizionati in un'altra area dell'interfaccia utente dell'applicazione per esporre i comandi agli utenti che non sono disponibili nella struttura di menu.</span><span class="sxs-lookup"><span data-stu-id="d31d3-105">These can be used to provide easy access to menu commands or, alternately, they can be placed in another area of the user interface of your application to expose commands to your users that are not available in the menu structure.</span></span>  
  
 <span data-ttu-id="d31d3-106">Negli esempi riportati <xref:System.Windows.Forms.ToolBar> di seguito si presuppone`Form1`che un controllo sia stato aggiunto a un Windows Form ( ).</span><span class="sxs-lookup"><span data-stu-id="d31d3-106">The examples below assume that a <xref:System.Windows.Forms.ToolBar> control has been added to a Windows Form (`Form1`).</span></span>  
  
### <a name="to-add-buttons-programmatically"></a><span data-ttu-id="d31d3-107">Per aggiungere pulsanti a livello di codiceTo add buttons programmatically</span><span class="sxs-lookup"><span data-stu-id="d31d3-107">To add buttons programmatically</span></span>  
  
1. <span data-ttu-id="d31d3-108">In una procedura, creare i pulsanti della barra degli strumenti aggiungendoli alla <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> raccolta.</span><span class="sxs-lookup"><span data-stu-id="d31d3-108">In a procedure, create toolbar buttons by adding them to the <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> collection.</span></span>  
  
2. <span data-ttu-id="d31d3-109">Specificare le impostazioni delle proprietà per un singolo <xref:System.Windows.Forms.ToolBar.Buttons%2A> pulsante passando l'indice del pulsante tramite la proprietà .</span><span class="sxs-lookup"><span data-stu-id="d31d3-109">Specify property settings for an individual button by passing the button's index via the <xref:System.Windows.Forms.ToolBar.Buttons%2A> property.</span></span>  
  
     <span data-ttu-id="d31d3-110">Nell'esempio riportato di <xref:System.Windows.Forms.ToolBar> seguito si presuppone che un form con un controllo sia già stato aggiunto.</span><span class="sxs-lookup"><span data-stu-id="d31d3-110">The example below assumes a form with a <xref:System.Windows.Forms.ToolBar> control already added.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d31d3-111">La <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> raccolta è una raccolta in base zero, pertanto il codice deve procedere di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="d31d3-111">The <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> collection is a zero-based collection, so code should proceed accordingly.</span></span>  
  
    ```vb  
    Public Sub CreateToolBarButtons()  
    ' Create buttons and set text property.  
       ToolBar1.Buttons.Add("One")  
       ToolBar1.Buttons.Add("Two")  
       ToolBar1.Buttons.Add("Three")  
       ToolBar1.Buttons.Add("Four")  
    ' Set properties of StatusBar panels.  
    ' Set Style property.  
       ToolBar1.Buttons(0).Style = ToolBarButtonStyle.PushButton  
       ToolBar1.Buttons(1).Style = ToolBarButtonStyle.Separator  
       ToolBar1.Buttons(2).Style = ToolBarButtonStyle.ToggleButton  
       ToolBar1.Buttons(3).Style = ToolBarButtonStyle.DropDownButton  
    ' Set the ToggleButton's PartialPush property.  
       ToolBar1.Buttons(2).PartialPush = True  
    ' Instantiate a ContextMenu component and menu items.  
    ' Set the DropDownButton's DropDownMenu property to the context menu.  
       Dim cm As New ContextMenu()  
       Dim miOne As New MenuItem("One")  
       Dim miTwo As New MenuItem("Two")  
       Dim miThree As New MenuItem("Three")  
       cm.MenuItems.Add(miOne)  
       cm.MenuItems.Add(miTwo)  
       cm.MenuItems.Add(miThree)  
       ToolBar1.Buttons(3).DropDownMenu = cm  
    ' Set the PushButton's Pushed property.  
       ToolBar1.Buttons(0).Pushed = True  
    ' Set the ToolTipText property of one of the buttons.  
       ToolBar1.Buttons(1).ToolTipText = "Button 2"  
    End Sub  
    ```  
  
    ```csharp  
    public void CreateToolBarButtons()  
    {  
       // Create buttons and set text property.  
       toolBar1.Buttons.Add("One");  
       toolBar1.Buttons.Add("Two");  
       toolBar1.Buttons.Add("Three");  
       toolBar1.Buttons.Add("Four");  
  
       // Set properties of StatusBar panels.  
       // Set Style property.  
       toolBar1.Buttons[0].Style = ToolBarButtonStyle.PushButton;  
       toolBar1.Buttons[1].Style = ToolBarButtonStyle.Separator;  
       toolBar1.Buttons[2].Style = ToolBarButtonStyle.ToggleButton;  
       toolBar1.Buttons[3].Style = ToolBarButtonStyle.DropDownButton;  
  
       // Set the ToggleButton's PartialPush property.  
       toolBar1.Buttons[2].PartialPush = true;  
  
       // Instantiate a ContextMenu component and menu items.  
       // Set the DropDownButton's DropDownMenu property to
       // the context menu.  
       ContextMenu cm = new ContextMenu();  
       MenuItem miOne = new MenuItem("One");  
       MenuItem miTwo = new MenuItem("Two");  
       MenuItem miThree = new MenuItem("Three");  
       cm.MenuItems.Add(miOne);  
       cm.MenuItems.Add(miTwo);  
       cm.MenuItems.Add(miThree);  
  
       toolBar1.Buttons[3].DropDownMenu = cm;  
       // Set the PushButton's Pushed property.  
       toolBar1.Buttons[0].Pushed = true;  
       // Set the ToolTipText property of 1 of the buttons.  
       toolBar1.Buttons[1].ToolTipText = "Button 2";  
    }  
    ```  
  
    ```cpp  
    public:  
       void CreateToolBarButtons()  
       {  
          // Create buttons and set text property.  
          toolBar1->Buttons->Add( "One" );  
          toolBar1->Buttons->Add( "Two" );  
          toolBar1->Buttons->Add( "Three" );  
          toolBar1->Buttons->Add( "Four" );  
  
          // Set properties of StatusBar panels.  
          // Set Style property.  
          toolBar1->Buttons[0]->Style = ToolBarButtonStyle::PushButton;  
          toolBar1->Buttons[1]->Style = ToolBarButtonStyle::Separator;  
          toolBar1->Buttons[2]->Style = ToolBarButtonStyle::ToggleButton;  
          toolBar1->Buttons[3]->Style = ToolBarButtonStyle::DropDownButton;  
  
          // Set the ToggleButton's PartialPush property.  
          toolBar1->Buttons[2]->PartialPush = true;  
  
          // Instantiate a ContextMenu component and menu items.  
          // Set the DropDownButton's DropDownMenu property to
          // the context menu.  
          System::Windows::Forms::ContextMenu^ cm = gcnew System::Windows::Forms::ContextMenu;  
          MenuItem^ miOne = gcnew MenuItem( "One" );  
          MenuItem^ miTwo = gcnew MenuItem( "Two" );  
          MenuItem^ miThree = gcnew MenuItem( "Three" );  
          cm->MenuItems->Add( miOne );  
          cm->MenuItems->Add( miTwo );  
          cm->MenuItems->Add( miThree );  
          toolBar1->Buttons[3]->DropDownMenu = cm;  
  
          // Set the PushButton's Pushed property.  
          toolBar1->Buttons[0]->Pushed = true;  
  
          // Set the ToolTipText property of 1 of the buttons.  
          toolBar1->Buttons[1]->ToolTipText = "Button 2";  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d31d3-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d31d3-112">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="d31d3-113">Procedura: definire un'icona per un pulsante ToolBar</span><span class="sxs-lookup"><span data-stu-id="d31d3-113">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)
- [<span data-ttu-id="d31d3-114">Procedura: Attivare eventi di menu per i pulsanti di una barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="d31d3-114">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="d31d3-115">Cenni preliminari sul controllo ToolBar</span><span class="sxs-lookup"><span data-stu-id="d31d3-115">ToolBar Control Overview</span></span>](toolbar-control-overview-windows-forms.md)
- [<span data-ttu-id="d31d3-116">Controllo ToolBar</span><span class="sxs-lookup"><span data-stu-id="d31d3-116">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
