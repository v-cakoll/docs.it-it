---
title: Controllo RichTextBox (Windows Form)
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- RichTextBox control [Windows Forms]
- rich edit controls
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
ms.openlocfilehash: 2b1a6604df3979e83e4a815cdb4a9397ab4e67ad
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716973"
---
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="c0da0-102">Controllo RichTextBox (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="c0da0-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="c0da0-103">I moduli di Windows `RichTextBox` controllo viene usato per visualizzare, immettere e modificare testo formattato.</span><span class="sxs-lookup"><span data-stu-id="c0da0-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="c0da0-104">Il `RichTextBox` offerte dal controllo di <xref:System.Windows.Forms.TextBox> del controllo, ma può anche visualizzare i tipi di carattere, colori e collegamenti, caricare testo e immagini incorporate da un file; l'annullamento e ripristino; operazioni di modifica e trovare caratteri specificati.</span><span class="sxs-lookup"><span data-stu-id="c0da0-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="c0da0-105">Il `RichTextBox` controllo viene in genere usato per fornire funzionalità simili alle applicazioni di elaborazione di testi, ad esempio Microsoft Word di visualizzazione e modifica di testo.</span><span class="sxs-lookup"><span data-stu-id="c0da0-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="c0da0-106">Ad esempio la <xref:System.Windows.Forms.TextBox> (controllo), il `RichTextBox` controllo può visualizzare le barre di scorrimento; ma a differenza di <xref:System.Windows.Forms.TextBox> (controllo), Visualizza le barre di scorrimento orizzontale e verticale per impostazione predefinita e impostazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="c0da0-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0da0-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="c0da0-107">In This Section</span></span>  
 [<span data-ttu-id="c0da0-108">Panoramica sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="c0da0-108">RichTextBox Control Overview</span></span>](richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="c0da0-109">Introduce i concetti generali del `RichTextBox` controllo, che consente agli utenti di immettere, visualizzare e modificare il testo con le opzioni di formattazione.</span><span class="sxs-lookup"><span data-stu-id="c0da0-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="c0da0-110">Procedura: Determinare quando si formatta modifiche degli attributi nel controllo RichTextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="c0da0-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="c0da0-111">Viene illustrato come tenere traccia delle modifiche nel tipo di carattere e formattazione paragrafo nel `RichTextBox` controllo.</span><span class="sxs-lookup"><span data-stu-id="c0da0-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="c0da0-112">Procedura: Controllo RichTextBox di visualizzare le barre di scorrimento in di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c0da0-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="c0da0-113">Vengono descritte le numerose opzioni disponibili per le barre di scorrimento di `RichTextBox` controllo.</span><span class="sxs-lookup"><span data-stu-id="c0da0-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="c0da0-114">Procedura: Visualizzare i collegamenti ipertestuali con il controllo RichTextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c0da0-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="c0da0-115">Viene illustrato come inserire collegamenti a siti Web dal `RichTextBox` controllo.</span><span class="sxs-lookup"><span data-stu-id="c0da0-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="c0da0-116">Procedura: Abilitare le operazioni di trascinamento e rilascio con il controllo RichTextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c0da0-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="c0da0-117">Vengono fornite istruzioni per il trascinamento dei dati nel `RichTextBox` controllo.</span><span class="sxs-lookup"><span data-stu-id="c0da0-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="c0da0-118">Procedura: Caricare file nel controllo RichTextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="c0da0-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="c0da0-119">Vengono fornite istruzioni per il caricamento di un file esistente nel `RichTextBox` controllo.</span><span class="sxs-lookup"><span data-stu-id="c0da0-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="c0da0-120">Procedura: Salvare i file con il controllo RichTextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c0da0-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="c0da0-121">Vengono fornite istruzioni per salvare il contenuto del `RichTextBox` controllo in un file.</span><span class="sxs-lookup"><span data-stu-id="c0da0-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="c0da0-122">Procedura: Impostare gli attributi dei caratteri per il controllo RichTextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c0da0-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="c0da0-123">Viene descritto come impostare la famiglia di caratteri, dimensioni, stile e il colore del testo nel `RichTextBox` controllo.</span><span class="sxs-lookup"><span data-stu-id="c0da0-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="c0da0-124">Procedura: Impostare rientri, rientri sporgenti e paragrafi puntati con il controllo RichTextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c0da0-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="c0da0-125">Viene descritto come formattare i paragrafi di `RichTextBox` controllo.</span><span class="sxs-lookup"><span data-stu-id="c0da0-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c0da0-126">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="c0da0-126">Reference</span></span>  
 <span data-ttu-id="c0da0-127">Classe <xref:System.Windows.Forms.RichTextBox></span><span class="sxs-lookup"><span data-stu-id="c0da0-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="c0da0-128">Descrive la classe e fornisce i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="c0da0-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c0da0-129">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c0da0-129">Related Sections</span></span>  
 [<span data-ttu-id="c0da0-130">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c0da0-130">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="c0da0-131">Fornisce un elenco completo dei controlli Windows Form, con collegamenti alle informazioni sul relativo uso.</span><span class="sxs-lookup"><span data-stu-id="c0da0-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="c0da0-132">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="c0da0-132">TextBox Control</span></span>](textbox-control-windows-forms.md)  
 <span data-ttu-id="c0da0-133">Introduce i concetti generali del <xref:System.Windows.Forms.TextBox> controllo, che consente l'input modificabile su più righe da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c0da0-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>
