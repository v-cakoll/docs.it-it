---
title: Eseguire attività comuni usando gli smart tag nei controlli
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 826313d0a89410f62c034a5fba4dee32e90a1750
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744264"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a><span data-ttu-id="1ee7f-102">Procedura dettagliata: eseguire attività comuni usando gli smart tag</span><span class="sxs-lookup"><span data-stu-id="1ee7f-102">Walkthrough: Perform Common Tasks Using Smart Tags</span></span>

<span data-ttu-id="1ee7f-103">Quando si costruiscono moduli e controlli per la Windows Forms Application, è possibile eseguire ripetutamente diverse attività.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="1ee7f-104">Di seguito sono riportate alcune delle attività comunemente eseguite che si verificheranno:</span><span class="sxs-lookup"><span data-stu-id="1ee7f-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="1ee7f-105">Aggiunta o rimozione di una scheda in un <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="1ee7f-106">Ancoraggio di un controllo al relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="1ee7f-107">Modifica dell'orientamento di un controllo <xref:System.Windows.Forms.SplitContainer>.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="1ee7f-108">Per velocizzare lo sviluppo, molti controlli offrono smart tag, che sono menu sensibili al contesto che consentono di eseguire attività comuni come queste in un singolo gesto in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="1ee7f-109">Queste attività sono denominate *verbi smart tag*.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="1ee7f-110">Gli smart tag rimangono collegati a un'istanza del controllo per la sua durata nella finestra di progettazione e sono sempre disponibili.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="1ee7f-111">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="1ee7f-111">Create the project</span></span>

<span data-ttu-id="1ee7f-112">Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="1ee7f-113">In Visual Studio creare un progetto di applicazione basato su Windows denominato **SmartTagsExample**.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-113">In Visual Studio, create a Windows-based application project called **SmartTagsExample**.</span></span>

2. <span data-ttu-id="1ee7f-114">Selezionare il modulo nella **Progettazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="1ee7f-115">Usa Smart Tag</span><span class="sxs-lookup"><span data-stu-id="1ee7f-115">Use smart tags</span></span>

<span data-ttu-id="1ee7f-116">Gli smart tag sono sempre disponibili in fase di progettazione nei controlli che li offrono.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-116">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="1ee7f-117">Trascinare un <xref:System.Windows.Forms.TabControl> dalla **casella degli strumenti** nel form.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="1ee7f-118">Si noti il glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif)) che viene visualizzato sul lato della <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-118">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="1ee7f-119">Fare clic sul glifo dello smart tag.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-119">Click the smart-tag glyph.</span></span> <span data-ttu-id="1ee7f-120">Nel menu di scelta rapida visualizzato accanto al glifo selezionare la voce **Aggiungi scheda** .</span><span class="sxs-lookup"><span data-stu-id="1ee7f-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="1ee7f-121">Osservare che alla <xref:System.Windows.Forms.TabControl>viene aggiunta una nuova scheda.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="1ee7f-122">Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="1ee7f-123">Fare clic sul glifo dello smart tag.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-123">Click the smart-tag glyph.</span></span> <span data-ttu-id="1ee7f-124">Nel menu di scelta rapida visualizzato accanto al glifo selezionare l'elemento **Aggiungi colonna** .</span><span class="sxs-lookup"><span data-stu-id="1ee7f-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="1ee7f-125">Osservare che una nuova colonna viene aggiunta al controllo <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="1ee7f-126">Trascinare un controllo <xref:System.Windows.Forms.SplitContainer> dalla **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="1ee7f-127">Fare clic sul glifo dello smart tag.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-127">Click the smart-tag glyph.</span></span> <span data-ttu-id="1ee7f-128">Nel menu di scelta rapida visualizzato accanto al glifo selezionare l'elemento di **orientamento della barra di divisione orizzontale** .</span><span class="sxs-lookup"><span data-stu-id="1ee7f-128">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="1ee7f-129">Osservare che la barra di divisione del controllo <xref:System.Windows.Forms.SplitContainer> è ora orientata orizzontalmente.</span><span class="sxs-lookup"><span data-stu-id="1ee7f-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ee7f-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ee7f-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
