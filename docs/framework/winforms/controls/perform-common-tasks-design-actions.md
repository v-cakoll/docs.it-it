---
title: Eseguire attività comuni usando le azioni della finestra di progettazione sui controlli
ms.date: 02/13/2019
helpviewer_keywords:
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 342741b9ce032b1b8ec50a6c689d9109d12f5b3b
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77634883"
---
# <a name="walkthrough-perform-common-tasks-using-designer-actions"></a><span data-ttu-id="ca38c-102">Procedura dettagliata: eseguire attività comuni utilizzando le azioni della finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="ca38c-102">Walkthrough: Perform common tasks using designer actions</span></span>

<span data-ttu-id="ca38c-103">Quando si costruiscono moduli e controlli per la Windows Forms Application, le attività eseguite più volte sono numerose.</span><span class="sxs-lookup"><span data-stu-id="ca38c-103">As you construct forms and controls for your Windows Forms application, there are many tasks you'll perform repeatedly.</span></span> <span data-ttu-id="ca38c-104">Nell'elenco seguente vengono illustrate alcune delle attività comunemente eseguite:</span><span class="sxs-lookup"><span data-stu-id="ca38c-104">The following list shows some of the commonly performed tasks you'll come across:</span></span>

- <span data-ttu-id="ca38c-105">Aggiunta o rimozione di una scheda in un <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="ca38c-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>
- <span data-ttu-id="ca38c-106">Ancoraggio di un controllo al relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="ca38c-106">Docking a control to its parent.</span></span>
- <span data-ttu-id="ca38c-107">Modifica dell'orientamento di un controllo <xref:System.Windows.Forms.SplitContainer>.</span><span class="sxs-lookup"><span data-stu-id="ca38c-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="ca38c-108">Per velocizzare lo sviluppo, molti controlli offrono azioni di progettazione, che sono menu sensibili al contesto che consentono di eseguire attività comuni come queste in un singolo gesto in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="ca38c-108">To speed development, many controls offer designer actions, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="ca38c-109">Queste attività sono denominate *verbi di azioni della finestra di progettazione*.</span><span class="sxs-lookup"><span data-stu-id="ca38c-109">These tasks are called *designer actions verbs*.</span></span>

<span data-ttu-id="ca38c-110">Le azioni della finestra di progettazione rimangono associate a un'istanza del controllo per la sua durata nella finestra di progettazione e sono sempre disponibili.</span><span class="sxs-lookup"><span data-stu-id="ca38c-110">Designer actions remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="ca38c-111">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="ca38c-111">Create the project</span></span>

<span data-ttu-id="ca38c-112">Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.</span><span class="sxs-lookup"><span data-stu-id="ca38c-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="ca38c-113">In Visual Studio creare un progetto di applicazione basato su Windows denominato **DesignerActionsExample**.</span><span class="sxs-lookup"><span data-stu-id="ca38c-113">In Visual Studio, create a Windows-based application project called **DesignerActionsExample**.</span></span>

2. <span data-ttu-id="ca38c-114">Selezionare il modulo nella **Progettazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="ca38c-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-designer-actions"></a><span data-ttu-id="ca38c-115">Usare le azioni di progettazione</span><span class="sxs-lookup"><span data-stu-id="ca38c-115">Use designer actions</span></span>

<span data-ttu-id="ca38c-116">Le azioni della finestra di progettazione sono sempre disponibili in fase di progettazione nei controlli che li offrono.</span><span class="sxs-lookup"><span data-stu-id="ca38c-116">Designer actions are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="ca38c-117">Trascinare un <xref:System.Windows.Forms.TabControl> dalla **casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="ca38c-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="ca38c-118">Si noti il glifo delle azioni della finestra di progettazione (![piccola freccia nera](./media/designer-actions-glyph.gif)) che viene visualizzato sul lato della <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="ca38c-118">Note the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="ca38c-119">Fare clic sul glifo azioni della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="ca38c-119">Click the designer actions glyph.</span></span> <span data-ttu-id="ca38c-120">Nel menu di scelta rapida visualizzato accanto al glifo selezionare la voce **Aggiungi scheda** .</span><span class="sxs-lookup"><span data-stu-id="ca38c-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="ca38c-121">Osservare che alla <xref:System.Windows.Forms.TabControl>viene aggiunta una nuova scheda.</span><span class="sxs-lookup"><span data-stu-id="ca38c-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="ca38c-122">Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="ca38c-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="ca38c-123">Fare clic sul glifo azioni della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="ca38c-123">Click the designer actions glyph.</span></span> <span data-ttu-id="ca38c-124">Nel menu di scelta rapida visualizzato accanto al glifo selezionare l'elemento **Aggiungi colonna** .</span><span class="sxs-lookup"><span data-stu-id="ca38c-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="ca38c-125">Osservare che una nuova colonna viene aggiunta al controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="ca38c-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="ca38c-126">Trascinare un controllo <xref:System.Windows.Forms.SplitContainer> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="ca38c-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="ca38c-127">Fare clic sul glifo azioni della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="ca38c-127">Click the designer actions glyph.</span></span> <span data-ttu-id="ca38c-128">Nel menu di scelta rapida visualizzato accanto al glifo selezionare l'elemento di **orientamento della barra di divisione orizzontale** .</span><span class="sxs-lookup"><span data-stu-id="ca38c-128">In the shortcut menu that appears next to the glyph, select the **Horizontal Splitter Orientation** item.</span></span> <span data-ttu-id="ca38c-129">Osservare che la barra di divisione del controllo <xref:System.Windows.Forms.SplitContainer> è ora orientata orizzontalmente.</span><span class="sxs-lookup"><span data-stu-id="ca38c-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca38c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca38c-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
