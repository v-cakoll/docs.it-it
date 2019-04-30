---
title: 'Procedura: Creare form padre MDI'
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
ms.openlocfilehash: d3ec2e16f06169790711c92c9d445ae93ee50c95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937592"
---
# <a name="how-to-create-mdi-parent-forms"></a><span data-ttu-id="7f1ee-102">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="7f1ee-102">How to: Create MDI Parent Forms</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="7f1ee-103">In questo argomento viene usato il controllo <xref:System.Windows.Forms.MainMenu> che è stato sostituito dal controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-103">This topic uses the <xref:System.Windows.Forms.MainMenu> control, which has been replaced by the <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="7f1ee-104">Il controllo <xref:System.Windows.Forms.MainMenu> viene mantenuto per la compatibilità con le versioni precedenti e per l'uso futuro, se si desidera.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-104">The <xref:System.Windows.Forms.MainMenu> control is retained for both backward compatibility and future use, if you choose.</span></span>  <span data-ttu-id="7f1ee-105">Per informazioni sulla creazione di una MDI Form padre tramite un <xref:System.Windows.Forms.MenuStrip>, vedere [come: Creare un elenco di finestre MDI con MenuStrip](../controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="7f1ee-105">For information about creating a MDI parent Form by using a <xref:System.Windows.Forms.MenuStrip>, see [How to: Create an MDI Window List with MenuStrip](../controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span></span>  
  
 <span data-ttu-id="7f1ee-106">La base di un'applicazione MDI (interfaccia a documenti multipli, Multiple Document Interface) è il form padre MDI.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-106">The foundation of a Multiple-Document Interface (MDI) application is the MDI parent form.</span></span> <span data-ttu-id="7f1ee-107">Si tratta del form che contiene le finestre figlio MDI che rappresentano le sottofinestre in cui l'utente interagisce con l'applicazione MDI.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-107">This is the form that contains the MDI child windows, which are the sub-windows wherein the user interacts with the MDI application.</span></span> <span data-ttu-id="7f1ee-108">La creazione di un form padre MDI è semplice sia in Progettazione Windows Form che a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-108">Creating an MDI parent form is easy, both in the Windows Forms Designer and programmatically.</span></span>  
  
### <a name="to-create-an-mdi-parent-form-at-design-time"></a><span data-ttu-id="7f1ee-109">Per creare un form padre MDI in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="7f1ee-109">To create an MDI parent form at design time</span></span>  
  
1. <span data-ttu-id="7f1ee-110">Creare un progetto Applicazione Windows.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-110">Create a Windows Application project.</span></span>  
  
2. <span data-ttu-id="7f1ee-111">Nel **le proprietà** impostare nella finestra di <xref:System.Windows.Forms.Form.IsMdiContainer%2A> proprietà **true**.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-111">In the **Properties** window, set the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to **true**.</span></span>  
  
     <span data-ttu-id="7f1ee-112">Il form viene così designato come contenitore MDI per le finestre figlio.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-112">This designates the form as an MDI container for child windows.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7f1ee-113">Quando si impostano le proprietà nella finestra **Proprietà**, se si vuole è anche possibile impostare la proprietà `WindowState` su **Ingrandita** per semplificare la modifica delle finestre figlio MDI ingrandendo il form padre.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-113">While setting properties in the **Properties** window, you can also set the `WindowState` property to **Maximized**, if you like, as it is easiest to manipulate MDI child windows when the parent form is maximized.</span></span> <span data-ttu-id="7f1ee-114">Inoltre, tenere presente che il bordo del form padre MDI applica il colore del sistema (impostato nel Pannello di controllo del sistema Windows) e non il colore di sfondo impostato con la proprietà <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-114">Additionally, be aware that the edge of the MDI parent form will pick up the system color (set in the Windows System Control Panel), rather than the back color you set using the <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> property.</span></span>  
  
3. <span data-ttu-id="7f1ee-115">Dalla **Casella degli strumenti** trascinare un controllo **MenuStrip** nel form.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-115">From the **Toolbox**, drag a **MenuStrip** control to the form.</span></span> <span data-ttu-id="7f1ee-116">Creare una voce di menu di primo livello con la proprietà **Testo** impostata su **&File** con voci di sottomenu chiamate **&Nuovo** e **&Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-116">Create a top-level menu item with the **Text** property set to **&File** with submenu items called **&New** and **&Close**.</span></span> <span data-ttu-id="7f1ee-117">Creare anche una voce di menu di primo livello chiamata **&Finestra**.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-117">Also create a top-level menu item called **&Window**.</span></span>  
  
     <span data-ttu-id="7f1ee-118">Il primo menu crea e nasconde le voci di menu al runtime, mentre il secondo tiene traccia delle finestre figlio MDI aperte.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-118">The first menu will create and hide menu items at run time, and the second menu will keep track of the open MDI child windows.</span></span> <span data-ttu-id="7f1ee-119">A questo punto è stata creata una finestra padre MDI.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-119">At this point, you have created an MDI parent window.</span></span>  
  
4. <span data-ttu-id="7f1ee-120">Premere **F5** per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7f1ee-120">Press **F5** to run the application.</span></span> <span data-ttu-id="7f1ee-121">Per informazioni sulla creazione di finestre usate all'interno del form padre MDI figlio MDI, vedere [come: Creare form figlio MDI](how-to-create-mdi-child-forms.md).</span><span class="sxs-lookup"><span data-stu-id="7f1ee-121">For information about creating MDI child windows that operate within the MDI parent form, see [How to: Create MDI Child Forms](how-to-create-mdi-child-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f1ee-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f1ee-122">See also</span></span>

- [<span data-ttu-id="7f1ee-123">Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)</span><span class="sxs-lookup"><span data-stu-id="7f1ee-123">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="7f1ee-124">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="7f1ee-124">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="7f1ee-125">Procedura: Determinare il figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="7f1ee-125">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="7f1ee-126">Procedura: Inviare dati al figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="7f1ee-126">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="7f1ee-127">Procedura: Disporre i form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="7f1ee-127">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
