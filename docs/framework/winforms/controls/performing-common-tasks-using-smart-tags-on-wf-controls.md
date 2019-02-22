---
title: 'Procedura dettagliata: Esecuzione di attività comuni usando gli smart tag nei controlli Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: 93a477bcaed8ebdc2c7cb4daaa1dce1651cccd12
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664315"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="d6b44-102">Procedura dettagliata: Esecuzione di attività comuni usando gli smart tag nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="d6b44-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>
<span data-ttu-id="d6b44-103">Come si costruisce form e controlli per l'applicazione Windows Forms, esistono molte attività che verranno eseguite più volte.</span><span class="sxs-lookup"><span data-stu-id="d6b44-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="d6b44-104">Queste sono alcune delle attività comuni eseguite che si verifica:</span><span class="sxs-lookup"><span data-stu-id="d6b44-104">These are some of the commonly performed tasks you will encounter:</span></span>  
  
-   <span data-ttu-id="d6b44-105">Aggiunta o rimozione di una scheda in un <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="d6b44-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>  
  
-   <span data-ttu-id="d6b44-106">Ancoraggio di un controllo all'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="d6b44-106">Docking a control to its parent.</span></span>  
  
-   <span data-ttu-id="d6b44-107">Modifica dell'orientamento di un <xref:System.Windows.Forms.SplitContainer> controllo.</span><span class="sxs-lookup"><span data-stu-id="d6b44-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>  
  
 <span data-ttu-id="d6b44-108">Per velocizzare lo sviluppo, molti controlli dispongono di smart tag, che sono menu sensibili al contesto che consentono di eseguire attività comuni, ad esempio in una singola operazione in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d6b44-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="d6b44-109">Queste attività vengono chiamate *smart tag verbi*.</span><span class="sxs-lookup"><span data-stu-id="d6b44-109">These tasks are called *smart-tag verbs*.</span></span>  
  
 <span data-ttu-id="d6b44-110">Gli smart tag resta collegato a un'istanza di controllo per la relativa durata nella finestra di progettazione e sono sempre disponibili.</span><span class="sxs-lookup"><span data-stu-id="d6b44-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>  
  
 <span data-ttu-id="d6b44-111">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6b44-111">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="d6b44-112">Creazione di un progetto Windows Form</span><span class="sxs-lookup"><span data-stu-id="d6b44-112">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="d6b44-113">Usando gli smart tag</span><span class="sxs-lookup"><span data-stu-id="d6b44-113">Using smart tags</span></span>  
  
-   <span data-ttu-id="d6b44-114">Abilitazione e disabilitazione degli Smart tag</span><span class="sxs-lookup"><span data-stu-id="d6b44-114">Enabling and Disabling Smart Tags</span></span>  
  
 <span data-ttu-id="d6b44-115">Al termine, si avrà una migliore comprensione del ruolo svolto da queste importanti funzionalità di layout.</span><span class="sxs-lookup"><span data-stu-id="d6b44-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6b44-116">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="d6b44-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d6b44-117">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="d6b44-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d6b44-118">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="d6b44-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="d6b44-119">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="d6b44-119">Creating the Project</span></span>  
 <span data-ttu-id="d6b44-120">Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.</span><span class="sxs-lookup"><span data-stu-id="d6b44-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="d6b44-121">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="d6b44-121">To create the project</span></span>  
  
1.  <span data-ttu-id="d6b44-122">Creare un progetto di applicazione basata su Windows denominato "SmartTagsExample" (**File** > **New** > **progetto**  >   **Visual c#** oppure **Visual Basic** > **Desktop classico** > **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="d6b44-122">Create a Windows-based application project called "SmartTagsExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="d6b44-123">Selezionare il form nel **finestra di progettazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="d6b44-123">Select the form in the **Windows Forms Designer**.</span></span>  
  
## <a name="using-smart-tags"></a><span data-ttu-id="d6b44-124">Usando gli Smart tag</span><span class="sxs-lookup"><span data-stu-id="d6b44-124">Using Smart Tags</span></span>  
 <span data-ttu-id="d6b44-125">Gli smart tag sono sempre disponibili in fase di progettazione nei controlli che sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="d6b44-125">Smart tags are always available at design time on controls that offer them.</span></span>  
  
#### <a name="to-use-smart-tags"></a><span data-ttu-id="d6b44-126">Usare gli smart tag</span><span class="sxs-lookup"><span data-stu-id="d6b44-126">To use smart tags</span></span>  
  
1.  <span data-ttu-id="d6b44-127">Trascinare un <xref:System.Windows.Forms.TabControl> dal **casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="d6b44-127">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="d6b44-128">Si noti il glifo smart tag (![glifo Smart Tag](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) che viene visualizzato sul lato del <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="d6b44-128">Note the smart-tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
2.  <span data-ttu-id="d6b44-129">Fare clic sul glifo dello smart tag.</span><span class="sxs-lookup"><span data-stu-id="d6b44-129">Click the smart-tag glyph.</span></span> <span data-ttu-id="d6b44-130">Nel menu di scelta rapida che viene visualizzato accanto all'icona, selezionare la **Aggiungi scheda** elemento.</span><span class="sxs-lookup"><span data-stu-id="d6b44-130">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="d6b44-131">Si osservi che viene aggiunta una nuova pagina della scheda per il <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="d6b44-131">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
3.  <span data-ttu-id="d6b44-132">Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="d6b44-132">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
4.  <span data-ttu-id="d6b44-133">Fare clic sul glifo dello smart tag.</span><span class="sxs-lookup"><span data-stu-id="d6b44-133">Click the smart-tag glyph.</span></span> <span data-ttu-id="d6b44-134">Nel menu di scelta rapida che viene visualizzato accanto all'icona, selezionare la **Aggiungi colonna** elemento.</span><span class="sxs-lookup"><span data-stu-id="d6b44-134">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="d6b44-135">Si osservi che viene aggiunta una nuova colonna per il <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="d6b44-135">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
5.  <span data-ttu-id="d6b44-136">Trascinare un controllo <xref:System.Windows.Forms.SplitContainer> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="d6b44-136">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>  
  
6.  <span data-ttu-id="d6b44-137">Fare clic sul glifo dello smart tag.</span><span class="sxs-lookup"><span data-stu-id="d6b44-137">Click the smart-tag glyph.</span></span> <span data-ttu-id="d6b44-138">Nel menu di scelta rapida che viene visualizzato accanto all'icona, selezionare la **orientamento divisione orizzontale** elemento.</span><span class="sxs-lookup"><span data-stu-id="d6b44-138">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="d6b44-139">Si noti che il <xref:System.Windows.Forms.SplitContainer> barra di divisione del controllo è ora orientamento orizzontale.</span><span class="sxs-lookup"><span data-stu-id="d6b44-139">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6b44-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6b44-140">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- <span data-ttu-id="d6b44-141">[Procedura dettagliata: Aggiunta di Smart tag per un componente di Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d6b44-141">[Walkthrough: Adding Smart Tags to a Windows Forms Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span></span>
