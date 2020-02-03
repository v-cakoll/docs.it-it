---
title: Controllo ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolBar control [Windows Forms]
ms.assetid: 6b40e9ce-6a7a-4784-bfc9-7f1d36b7462e
ms.openlocfilehash: 027c96bb49e9446244e4b08ba93c551ef043b3c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735461"
---
# <a name="toolbar-control-windows-forms"></a><span data-ttu-id="b7039-102">Controllo ToolBar (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="b7039-102">ToolBar Control (Windows Forms)</span></span>
> [!NOTE]
> <span data-ttu-id="b7039-103">Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo `ToolBar` aggiungendovi funzionalità, il controllo `ToolBar` viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="b7039-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the `ToolBar` control; however, the `ToolBar` control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="b7039-104">Il controllo `ToolBar` Windows Form viene usato nei form come barra di controllo sulla quale viene visualizzata una riga di menu a discesa e pulsanti bitmap per l'attivazione dei comandi.</span><span class="sxs-lookup"><span data-stu-id="b7039-104">The Windows Forms `ToolBar` control is used on forms as a control bar that displays a row of drop-down menus and bitmapped buttons that activate commands.</span></span> <span data-ttu-id="b7039-105">Fare clic su un pulsante della barra degli strumenti equivale pertanto a scegliere un comando di menu.</span><span class="sxs-lookup"><span data-stu-id="b7039-105">Thus, clicking a toolbar button is equivalent to choosing a menu command.</span></span> <span data-ttu-id="b7039-106">È possibile configurare i pulsanti affinché abbiano l'aspetto e il comportamento di pulsanti di comando, menu a discesa o separatori.</span><span class="sxs-lookup"><span data-stu-id="b7039-106">The buttons can be configured to appear and behave as push buttons, drop-down menus, or separators.</span></span> <span data-ttu-id="b7039-107">In genere, una barra degli strumenti contiene pulsanti e menu che corrispondono alle voci della struttura di menu di un'applicazione e forniscono un rapido accesso alle funzioni e ai comandi usati più di frequente in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b7039-107">Typically, a toolbar contains buttons and menus that correspond to items in an application's menu structure, providing quick access to an application's most frequently used functions and commands.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b7039-108">La proprietà `ToolBar` del controllo <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> accetta un'istanza della classe <xref:System.Windows.Forms.ContextMenu> come riferimento.</span><span class="sxs-lookup"><span data-stu-id="b7039-108">The `ToolBar` control's <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> property takes an instance of the <xref:System.Windows.Forms.ContextMenu> class as a reference.</span></span> <span data-ttu-id="b7039-109">Prestare particolare attenzione al riferimento che viene passato quando si implementa questo tipo di pulsanti sulle barre degli strumenti dell'applicazione, poiché la proprietà accetterà qualsiasi oggetto che eredita dalla classe <xref:System.Windows.Forms.Menu>.</span><span class="sxs-lookup"><span data-stu-id="b7039-109">Carefully consider the reference you pass when implementing this sort of button on toolbars in your application, as the property will accept any object that inherits from the <xref:System.Windows.Forms.Menu> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b7039-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b7039-110">In This Section</span></span>  
 [<span data-ttu-id="b7039-111">Panoramica sul controllo ToolBar</span><span class="sxs-lookup"><span data-stu-id="b7039-111">ToolBar Control Overview</span></span>](toolbar-control-overview-windows-forms.md)  
 <span data-ttu-id="b7039-112">Introduce i concetti generali relativi al controllo `ToolBar`, che consente di creare barre degli strumenti personalizzate che possono essere usate dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="b7039-112">Introduces the general concepts of the `ToolBar` control, which allows you to design custom toolbars that your users can work with.</span></span>  
  
 [<span data-ttu-id="b7039-113">Procedura: Aggiungere pulsanti a un controllo ToolBar</span><span class="sxs-lookup"><span data-stu-id="b7039-113">How to: Add Buttons to a ToolBar Control</span></span>](how-to-add-buttons-to-a-toolbar-control.md)  
 <span data-ttu-id="b7039-114">Descrive come aggiungere pulsanti a un controllo `ToolBar`.</span><span class="sxs-lookup"><span data-stu-id="b7039-114">Describes how to add buttons to a `ToolBar` control.</span></span>  
  
 [<span data-ttu-id="b7039-115">Procedura: Definire un'icona per un pulsante ToolBar</span><span class="sxs-lookup"><span data-stu-id="b7039-115">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)  
 <span data-ttu-id="b7039-116">Descrive come visualizzare icone all'interno dei pulsanti di un controllo `ToolBar`.</span><span class="sxs-lookup"><span data-stu-id="b7039-116">Describes how to display icons within a `ToolBar` control's buttons.</span></span>  
  
 [<span data-ttu-id="b7039-117">Procedura: Attivare eventi di menu per i pulsanti di una barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="b7039-117">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)  
 <span data-ttu-id="b7039-118">Illustra come scrivere il codice che consente di identificare il pulsante su cui l'utente ha fatto clic in un controllo `ToolBar`.</span><span class="sxs-lookup"><span data-stu-id="b7039-118">Gives directions on writing code to interpret which button the user clicks in a `ToolBar` control.</span></span>  
  
 <span data-ttu-id="b7039-119">Vedere anche [procedura: definire un'icona per un pulsante della barra degli strumenti usando la finestra di progettazione](how-to-define-an-icon-for-a-toolbar-button-using-the-designer.md), [procedura: aggiungere pulsanti a un controllo Toolbar usando la finestra di progettazione](how-to-add-buttons-to-a-toolbar-control-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="b7039-119">Also see [How to: Define an Icon for a ToolBar Button Using the Designer](how-to-define-an-icon-for-a-toolbar-button-using-the-designer.md), [How to: Add Buttons to a ToolBar Control Using the Designer](how-to-add-buttons-to-a-toolbar-control-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b7039-120">Riferimento</span><span class="sxs-lookup"><span data-stu-id="b7039-120">Reference</span></span>  
 <span data-ttu-id="b7039-121">Classe <xref:System.Windows.Forms.ToolBar></span><span class="sxs-lookup"><span data-stu-id="b7039-121"><xref:System.Windows.Forms.ToolBar> class</span></span>  
 <span data-ttu-id="b7039-122">Fornisce informazioni di riferimento sulla classe e sui relativi membri.</span><span class="sxs-lookup"><span data-stu-id="b7039-122">Provides reference information on the class and its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b7039-123">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="b7039-123">Related Sections</span></span>  
 [<span data-ttu-id="b7039-124">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="b7039-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="b7039-125">Fornisce un elenco completo dei controlli Windows Form, con collegamenti alle informazioni sul relativo uso.</span><span class="sxs-lookup"><span data-stu-id="b7039-125">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="b7039-126">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="b7039-126">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)  
 <span data-ttu-id="b7039-127">Descrive barre degli strumenti che possono ospitare menu, controlli e controlli utente nelle applicazioni Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b7039-127">Describes toolbars that can host menus, controls, and user controls in Windows Forms applications.</span></span>
