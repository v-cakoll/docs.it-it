---
title: "Procedura: visualizzare più righe nel controllo TextBox Windows Form"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dca8d0f869702dee50bf851a2099317c45aa842
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="1fce7-102">Procedura: visualizzare più righe nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="1fce7-102">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="1fce7-103">Per impostazione predefinita, Windows Form <xref:System.Windows.Forms.TextBox> controllo Visualizza una singola riga di testo e non visualizzare le barre di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="1fce7-103">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="1fce7-104">Se il testo è maggiore dello spazio disponibile, è visibile solo una parte del testo.</span><span class="sxs-lookup"><span data-stu-id="1fce7-104">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="1fce7-105">È possibile modificare questo comportamento predefinito impostando il <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, e <xref:System.Windows.Forms.TextBox.ScrollBars%2A> proprietà sui valori appropriati.</span><span class="sxs-lookup"><span data-stu-id="1fce7-105">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="1fce7-106">Per visualizzare un ritorno a capo nel controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="1fce7-106">To display a carriage return in the TextBox control</span></span>  
  
-   <span data-ttu-id="1fce7-107">Per visualizzare un ritorno a capo in una multi-riga di <xref:System.Windows.Forms.TextBox>, utilizzare il <xref:System.Environment.NewLine%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="1fce7-107">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="1fce7-108">Tenere presente che l'interpretazione dei caratteri di escape (\\) è specifico del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="1fce7-108">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="1fce7-109">Visual Basic utilizza `Chr$(13) & Chr$(10)` per la combinazione di caratteri ritorno a capo restituiti e avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="1fce7-109">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="1fce7-110">Per visualizzare più righe nel controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="1fce7-110">To view multiple lines in the TextBox control</span></span>  
  
1.  <span data-ttu-id="1fce7-111">Impostare la proprietà <xref:System.Windows.Forms.TextBox.Multiline%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="1fce7-111">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="1fce7-112">Se <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> è `true` (impostazione predefinita), il testo nel controllo verrà quindi visualizzati come uno o più paragrafi; in caso contrario, verrà visualizzato un elenco, in cui alcune righe potrebbero essere ritagliata in base al bordo del controllo.</span><span class="sxs-lookup"><span data-stu-id="1fce7-112">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2.  <span data-ttu-id="1fce7-113">Impostare la proprietà <xref:System.Windows.Forms.TextBox.ScrollBars%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="1fce7-113">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="1fce7-114">Valore</span><span class="sxs-lookup"><span data-stu-id="1fce7-114">Value</span></span>|<span data-ttu-id="1fce7-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fce7-115">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="1fce7-116">Utilizzare questo valore se il testo sarà un paragrafo che adatta quasi sempre il controllo.</span><span class="sxs-lookup"><span data-stu-id="1fce7-116">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="1fce7-117">L'utente può utilizzare il puntatore del mouse per spostarsi all'interno del controllo se il testo è troppo lungo da visualizzare in una sola volta.</span><span class="sxs-lookup"><span data-stu-id="1fce7-117">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="1fce7-118">Utilizzare questo valore se si desidera visualizzare un elenco di righe, alcuni dei quali può essere più lungo rispetto alla larghezza del <xref:System.Windows.Forms.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="1fce7-118">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="1fce7-119">Utilizzare questo valore se l'elenco può essere più lungo rispetto all'altezza del controllo.</span><span class="sxs-lookup"><span data-stu-id="1fce7-119">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3.  <span data-ttu-id="1fce7-120">Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="1fce7-120">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="1fce7-121">Valore</span><span class="sxs-lookup"><span data-stu-id="1fce7-121">Value</span></span>|<span data-ttu-id="1fce7-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fce7-122">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="1fce7-123">Il testo del controllo non automaticamente inclusi, in modo che verrà scorrere verso destra fino a quando non viene raggiunta un'interruzione di riga.</span><span class="sxs-lookup"><span data-stu-id="1fce7-123">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="1fce7-124">Utilizzare questo valore se si sceglie <xref:System.Windows.Forms.ScrollBars.Horizontal> barre di scorrimento o <xref:System.Windows.Forms.ScrollBars.Both>sopra.</span><span class="sxs-lookup"><span data-stu-id="1fce7-124">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |<span data-ttu-id="1fce7-125">`true` (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="1fce7-125">`true` (default)</span></span>|<span data-ttu-id="1fce7-126">Non verrà visualizzata la barra di scorrimento orizzontale.</span><span class="sxs-lookup"><span data-stu-id="1fce7-126">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="1fce7-127">Utilizzare questo valore se si sceglie <xref:System.Windows.Forms.ScrollBars.Vertical> barre di scorrimento o <xref:System.Windows.Forms.ScrollBars.None>precedente, per visualizzare uno o più paragrafi.</span><span class="sxs-lookup"><span data-stu-id="1fce7-127">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1fce7-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fce7-128">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="1fce7-129">Cenni preliminari sul controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="1fce7-129">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="1fce7-130">Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1fce7-130">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="1fce7-131">Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1fce7-131">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="1fce7-132">Procedura: Creare una casella di testo in sola lettura</span><span class="sxs-lookup"><span data-stu-id="1fce7-132">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="1fce7-133">Procedura: Inserire virgolette in una stringa</span><span class="sxs-lookup"><span data-stu-id="1fce7-133">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="1fce7-134">Procedura: Selezionare testo nel controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1fce7-134">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="1fce7-135">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="1fce7-135">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
