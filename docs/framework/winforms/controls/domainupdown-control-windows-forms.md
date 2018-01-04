---
title: Controllo DomainUpDown (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 485640dc320809e9be5550d380b4fc9a2326e027
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="domainupdown-control-windows-forms"></a><span data-ttu-id="65110-102">Controllo DomainUpDown (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="65110-102">DomainUpDown Control (Windows Forms)</span></span>
<span data-ttu-id="65110-103">Windows Form <xref:System.Windows.Forms.DomainUpDown> controllo simile a una combinazione di una casella di testo e una coppia di pulsanti per spostarsi verso l'alto o verso il basso all'interno di un elenco.</span><span class="sxs-lookup"><span data-stu-id="65110-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control looks like a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="65110-104">Il controllo Visualizza e imposta una stringa di testo da un elenco di scelte.</span><span class="sxs-lookup"><span data-stu-id="65110-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="65110-105">L'utente può selezionare la stringa facendo clic su e giù per spostarsi in un elenco, premendo i tasti freccia su e giù o digitando una stringa che corrisponde a un elemento nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="65110-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="65110-106">Un possibile utilizzo di questo controllo è per la selezione di elementi da un elenco in ordine alfabetico dei nomi.</span><span class="sxs-lookup"><span data-stu-id="65110-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span> <span data-ttu-id="65110-107">(Per ordinare l'elenco, impostare il <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> proprietà `true`.) La funzione di questo controllo è molto simile alla casella di riepilogo o casella combinata, ma richiede poco spazio.</span><span class="sxs-lookup"><span data-stu-id="65110-107">(To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.) The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
 <span data-ttu-id="65110-108">Le proprietà principali del controllo sono <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, e <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span><span class="sxs-lookup"><span data-stu-id="65110-108">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="65110-109">Il <xref:System.Windows.Forms.DomainUpDown.Items%2A> proprietà contiene l'elenco di oggetti i cui valori di testo vengono visualizzati nel controllo.</span><span class="sxs-lookup"><span data-stu-id="65110-109">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="65110-110">Se <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> è impostato su `false`, il controllo completa automaticamente il testo che l'utente digita e a esso corrispondente a un valore nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="65110-110">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="65110-111">Se <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> è impostato su `true`, lo scorrimento oltre l'ultimo elemento verrà visualizzata al primo elemento nell'elenco e viceversa.</span><span class="sxs-lookup"><span data-stu-id="65110-111">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="65110-112">I metodi principali del controllo sono <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> e <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span><span class="sxs-lookup"><span data-stu-id="65110-112">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="65110-113">Questo controllo consente di visualizzare solo le stringhe di testo.</span><span class="sxs-lookup"><span data-stu-id="65110-113">This control displays only text strings.</span></span> <span data-ttu-id="65110-114">Se si desidera un controllo che visualizza i valori numerici, utilizzare il <xref:System.Windows.Forms.NumericUpDown> controllo.</span><span class="sxs-lookup"><span data-stu-id="65110-114">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="65110-115">Per ulteriori informazioni, vedere [controllo NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md) .</span><span class="sxs-lookup"><span data-stu-id="65110-115">For more information, see [NumericUpDown Control](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md) .</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="65110-116">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="65110-116">In This Section</span></span>  
 [<span data-ttu-id="65110-117">Panoramica sul controllo DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="65110-117">DomainUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)  
 <span data-ttu-id="65110-118">Introduce i concetti generali relativi il <xref:System.Windows.Forms.DomainUpDown> controllo, che consente agli utenti di esplorare e selezionare da un elenco di stringhe di testo.</span><span class="sxs-lookup"><span data-stu-id="65110-118">Introduces the general concepts of the <xref:System.Windows.Forms.DomainUpDown> control, which allows users to browse through and select from a list of text strings.</span></span>  
  
 [<span data-ttu-id="65110-119">Procedura: Aggiungere elementi ai controlli DomainUpDown di Windows Form a livello di codice</span><span class="sxs-lookup"><span data-stu-id="65110-119">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>](../../../../docs/framework/winforms/controls/how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 <span data-ttu-id="65110-120">Viene descritto come specificare le stringhe di testo il <xref:System.Windows.Forms.DomainUpDown> controllo devono essere visualizzati.</span><span class="sxs-lookup"><span data-stu-id="65110-120">Describes how to specify the text strings the <xref:System.Windows.Forms.DomainUpDown> control should display.</span></span>  
  
 [<span data-ttu-id="65110-121">Procedura: Rimuovere elementi dai controlli DomainUpDown di Windows Form</span><span class="sxs-lookup"><span data-stu-id="65110-121">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 <span data-ttu-id="65110-122">Viene descritto come eliminare gli elementi di <xref:System.Windows.Forms.DomainUpDown> nel codice.</span><span class="sxs-lookup"><span data-stu-id="65110-122">Describes how to delete items from the <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="65110-123">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="65110-123">Reference</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <span data-ttu-id="65110-124">Descrive la classe e fornisce i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="65110-124">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 <span data-ttu-id="65110-125">Descrive la classe e include collegamenti a tutti i relativi membri...</span><span class="sxs-lookup"><span data-stu-id="65110-125">Describes this class and has links to all its members..</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="65110-126">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="65110-126">Related Sections</span></span>  
 [<span data-ttu-id="65110-127">Controlli utilizzabili in Windows Form</span><span class="sxs-lookup"><span data-stu-id="65110-127">Controls You Can Use On Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="65110-128">Fornisce un elenco completo dei controlli Windows Form, con collegamenti alle informazioni sul relativo uso.</span><span class="sxs-lookup"><span data-stu-id="65110-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
