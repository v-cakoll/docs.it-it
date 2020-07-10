---
title: 'Procedura: Creare form padre MDI'
description: Informazioni su come creare un form padre MDI a livello di codice e usando il Progettazione Windows Form.
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
ms.openlocfilehash: d387837a565ca247f62828c19f353990b35117c7
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174705"
---
# <a name="how-to-create-mdi-parent-forms"></a><span data-ttu-id="b418e-103">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="b418e-103">How to: Create MDI Parent Forms</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b418e-104">In questo argomento viene usato il controllo <xref:System.Windows.Forms.MainMenu> che è stato sostituito dal controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="b418e-104">This topic uses the <xref:System.Windows.Forms.MainMenu> control, which has been replaced by the <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="b418e-105">Il controllo <xref:System.Windows.Forms.MainMenu> viene mantenuto per la compatibilità con le versioni precedenti e per l'uso futuro, se si desidera.</span><span class="sxs-lookup"><span data-stu-id="b418e-105">The <xref:System.Windows.Forms.MainMenu> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="b418e-106">Per informazioni sulla creazione di un form padre MDI usando un <xref:System.Windows.Forms.MenuStrip> , vedere [procedura: creare un elenco di finestre MDI con MenuStrip](../controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b418e-106">For information about creating a MDI parent Form by using a <xref:System.Windows.Forms.MenuStrip>, see [How to: Create an MDI Window List with MenuStrip](../controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span></span>

<span data-ttu-id="b418e-107">La base di un'applicazione MDI (interfaccia a documenti multipli, Multiple Document Interface) è il form padre MDI.</span><span class="sxs-lookup"><span data-stu-id="b418e-107">The foundation of a Multiple-Document Interface (MDI) application is the MDI parent form.</span></span> <span data-ttu-id="b418e-108">Si tratta del form che contiene le finestre figlio MDI che rappresentano le sottofinestre in cui l'utente interagisce con l'applicazione MDI.</span><span class="sxs-lookup"><span data-stu-id="b418e-108">This is the form that contains the MDI child windows, which are the sub-windows wherein the user interacts with the MDI application.</span></span> <span data-ttu-id="b418e-109">La creazione di un form padre MDI è semplice sia in Progettazione Windows Form che a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="b418e-109">Creating an MDI parent form is easy, both in the Windows Forms Designer and programmatically.</span></span>

## <a name="create-an-mdi-parent-form-at-design-time"></a><span data-ttu-id="b418e-110">Creazione di un form padre MDI in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="b418e-110">Create an MDI parent form at design time</span></span>

1. <span data-ttu-id="b418e-111">Creare un progetto di applicazione Windows in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b418e-111">Create a Windows Application project in Visual Studio.</span></span>

2. <span data-ttu-id="b418e-112">Nella finestra **Proprietà** impostare la <xref:System.Windows.Forms.Form.IsMdiContainer%2A> proprietà su **true**.</span><span class="sxs-lookup"><span data-stu-id="b418e-112">In the **Properties** window, set the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to **true**.</span></span>

     <span data-ttu-id="b418e-113">Il form viene così designato come contenitore MDI per le finestre figlio.</span><span class="sxs-lookup"><span data-stu-id="b418e-113">This designates the form as an MDI container for child windows.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b418e-114">Quando si impostano le proprietà nella finestra **Proprietà**, se si vuole è anche possibile impostare la proprietà `WindowState` su **Ingrandita** per semplificare la modifica delle finestre figlio MDI ingrandendo il form padre.</span><span class="sxs-lookup"><span data-stu-id="b418e-114">While setting properties in the **Properties** window, you can also set the `WindowState` property to **Maximized**, if you like, as it is easiest to manipulate MDI child windows when the parent form is maximized.</span></span> <span data-ttu-id="b418e-115">Inoltre, tenere presente che il bordo del form padre MDI applica il colore del sistema (impostato nel Pannello di controllo del sistema Windows) e non il colore di sfondo impostato con la proprietà <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b418e-115">Additionally, be aware that the edge of the MDI parent form will pick up the system color (set in the Windows System Control Panel), rather than the back color you set using the <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> property.</span></span>

3. <span data-ttu-id="b418e-116">Dalla **Casella degli strumenti** trascinare un controllo **MenuStrip** nel form.</span><span class="sxs-lookup"><span data-stu-id="b418e-116">From the **Toolbox**, drag a **MenuStrip** control to the form.</span></span> <span data-ttu-id="b418e-117">Creare una voce di menu di primo livello con la proprietà **Testo** impostata su **&File** con voci di sottomenu chiamate **&Nuovo** e **&Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b418e-117">Create a top-level menu item with the **Text** property set to **&File** with submenu items called **&New** and **&Close**.</span></span> <span data-ttu-id="b418e-118">Creare anche una voce di menu di primo livello chiamata **&Finestra**.</span><span class="sxs-lookup"><span data-stu-id="b418e-118">Also create a top-level menu item called **&Window**.</span></span>

     <span data-ttu-id="b418e-119">Il primo menu crea e nasconde le voci di menu al runtime, mentre il secondo tiene traccia delle finestre figlio MDI aperte.</span><span class="sxs-lookup"><span data-stu-id="b418e-119">The first menu will create and hide menu items at run time, and the second menu will keep track of the open MDI child windows.</span></span> <span data-ttu-id="b418e-120">A questo punto è stata creata una finestra padre MDI.</span><span class="sxs-lookup"><span data-stu-id="b418e-120">At this point, you have created an MDI parent window.</span></span>

4. <span data-ttu-id="b418e-121">Premere **F5** per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b418e-121">Press **F5** to run the application.</span></span> <span data-ttu-id="b418e-122">Per informazioni sulla creazione di finestre figlio MDI usate all'interno del form padre MDI, vedere [Procedura: Creare form figlio MDI](how-to-create-mdi-child-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b418e-122">For information about creating MDI child windows that operate within the MDI parent form, see [How to: Create MDI Child Forms](how-to-create-mdi-child-forms.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b418e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b418e-123">See also</span></span>

- [<span data-ttu-id="b418e-124">Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)</span><span class="sxs-lookup"><span data-stu-id="b418e-124">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="b418e-125">Procedura: creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="b418e-125">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="b418e-126">Procedura: determinare il figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="b418e-126">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="b418e-127">Procedura: inviare dati al figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="b418e-127">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="b418e-128">Procedura: Disporre i form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="b418e-128">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
