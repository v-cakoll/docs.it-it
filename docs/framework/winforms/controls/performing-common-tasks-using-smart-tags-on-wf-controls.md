---
title: 'Procedura dettagliata: Esecuzione di attività comuni usando gli smart tag nei controlli Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: 1cc854d735ba88a301d6e2f6a83fe5c8bf881380
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211411"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="55639-102">Procedura dettagliata: Esecuzione di attività comuni usando gli smart tag nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="55639-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>

<span data-ttu-id="55639-103">Come si costruisce form e controlli per l'applicazione Windows Forms, esistono molte attività che verranno eseguite più volte.</span><span class="sxs-lookup"><span data-stu-id="55639-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="55639-104">Queste sono alcune delle attività comuni eseguite che si verifica:</span><span class="sxs-lookup"><span data-stu-id="55639-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="55639-105">Aggiunta o rimozione di una scheda in un <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="55639-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="55639-106">Ancoraggio di un controllo all'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="55639-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="55639-107">Modifica dell'orientamento di un <xref:System.Windows.Forms.SplitContainer> controllo.</span><span class="sxs-lookup"><span data-stu-id="55639-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="55639-108">Per velocizzare lo sviluppo, molti controlli dispongono di smart tag, che sono menu sensibili al contesto che consentono di eseguire attività comuni, ad esempio in una singola operazione in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="55639-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="55639-109">Queste attività vengono chiamate *smart tag verbi*.</span><span class="sxs-lookup"><span data-stu-id="55639-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="55639-110">Gli smart tag resta collegato a un'istanza di controllo per la relativa durata nella finestra di progettazione e sono sempre disponibili.</span><span class="sxs-lookup"><span data-stu-id="55639-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

<span data-ttu-id="55639-111">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="55639-111">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="55639-112">Creazione di un progetto Windows Form</span><span class="sxs-lookup"><span data-stu-id="55639-112">Creating a Windows Forms project</span></span>

- <span data-ttu-id="55639-113">Usando gli smart tag</span><span class="sxs-lookup"><span data-stu-id="55639-113">Using smart tags</span></span>

- <span data-ttu-id="55639-114">Abilitazione e disabilitazione degli Smart tag</span><span class="sxs-lookup"><span data-stu-id="55639-114">Enabling and Disabling Smart Tags</span></span>

<span data-ttu-id="55639-115">Al termine, si avrà una migliore comprensione del ruolo svolto da queste importanti funzionalità di layout.</span><span class="sxs-lookup"><span data-stu-id="55639-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="55639-116">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="55639-116">Create the project</span></span>

<span data-ttu-id="55639-117">Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.</span><span class="sxs-lookup"><span data-stu-id="55639-117">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="55639-118">In Visual Studio, creare un progetto di applicazione basata su Windows denominato "SmartTagsExample" (**File** > **New** > **progetto**  >  **Visual C#**  oppure **Visual Basic** > **Desktop classico** > **Windows Form Applicazione**).</span><span class="sxs-lookup"><span data-stu-id="55639-118">In Visual Studio, create a Windows-based application project called "SmartTagsExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="55639-119">Selezionare il form nel **finestra di progettazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="55639-119">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="55639-120">Usare gli smart tag</span><span class="sxs-lookup"><span data-stu-id="55639-120">Use smart tags</span></span>

<span data-ttu-id="55639-121">Gli smart tag sono sempre disponibili in fase di progettazione nei controlli che sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="55639-121">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="55639-122">Trascinare un <xref:System.Windows.Forms.TabControl> dal **casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="55639-122">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="55639-123">Si noti il glifo smart tag (![glifo Smart Tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) che viene visualizzato sul lato del <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="55639-123">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="55639-124">Fare clic sul glifo dello smart tag.</span><span class="sxs-lookup"><span data-stu-id="55639-124">Click the smart-tag glyph.</span></span> <span data-ttu-id="55639-125">Nel menu di scelta rapida che viene visualizzato accanto all'icona, selezionare la **Aggiungi scheda** elemento.</span><span class="sxs-lookup"><span data-stu-id="55639-125">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="55639-126">Si osservi che viene aggiunta una nuova pagina della scheda per il <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="55639-126">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="55639-127">Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="55639-127">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="55639-128">Fare clic sul glifo dello smart tag.</span><span class="sxs-lookup"><span data-stu-id="55639-128">Click the smart-tag glyph.</span></span> <span data-ttu-id="55639-129">Nel menu di scelta rapida che viene visualizzato accanto all'icona, selezionare la **Aggiungi colonna** elemento.</span><span class="sxs-lookup"><span data-stu-id="55639-129">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="55639-130">Si osservi che viene aggiunta una nuova colonna per il <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="55639-130">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="55639-131">Trascinare un controllo <xref:System.Windows.Forms.SplitContainer> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="55639-131">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="55639-132">Fare clic sul glifo dello smart tag.</span><span class="sxs-lookup"><span data-stu-id="55639-132">Click the smart-tag glyph.</span></span> <span data-ttu-id="55639-133">Nel menu di scelta rapida che viene visualizzato accanto all'icona, selezionare la **orientamento divisione orizzontale** elemento.</span><span class="sxs-lookup"><span data-stu-id="55639-133">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="55639-134">Si noti che il <xref:System.Windows.Forms.SplitContainer> barra di divisione del controllo è ora orientamento orizzontale.</span><span class="sxs-lookup"><span data-stu-id="55639-134">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="55639-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55639-135">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- <span data-ttu-id="55639-136">[Procedura dettagliata: Aggiunta di Smart tag per un componente di Windows Form](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="55639-136">[Walkthrough: Adding Smart Tags to a Windows Forms Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span></span>
