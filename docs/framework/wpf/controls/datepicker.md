---
title: DatePicker
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bd2a1755ae076369661b2c9a7a2b744961cdb129
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="datepicker"></a><span data-ttu-id="20094-102">DatePicker</span><span class="sxs-lookup"><span data-stu-id="20094-102">DatePicker</span></span>
<span data-ttu-id="20094-103">Il <xref:System.Windows.Controls.DatePicker> controllo consente all'utente di selezionare una data digitandola in un campo di testo o utilizzando un elenco a discesa <xref:System.Windows.Controls.Calendar> controllo.</span><span class="sxs-lookup"><span data-stu-id="20094-103">The <xref:System.Windows.Controls.DatePicker> control allows the user to select a date by either typing it into a text field or by using a drop-down <xref:System.Windows.Controls.Calendar> control.</span></span>  
  
 <span data-ttu-id="20094-104">La figura seguente mostra un <xref:System.Windows.Controls.DatePicker>.</span><span class="sxs-lookup"><span data-stu-id="20094-104">The following illustration shows a <xref:System.Windows.Controls.DatePicker>.</span></span>  
  
 <span data-ttu-id="20094-105">![Controllo DatePicker](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP_DatePicker")</span><span class="sxs-lookup"><span data-stu-id="20094-105">![DatePicker control](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP_DatePicker")</span></span>  
<span data-ttu-id="20094-106">Controllo DatePicker</span><span class="sxs-lookup"><span data-stu-id="20094-106">DatePicker Control</span></span>  
  
 <span data-ttu-id="20094-107">Numero di un <xref:System.Windows.Controls.DatePicker> sono proprietà del controllo per la gestione relativo predefinito <xref:System.Windows.Controls.Calendar>e la funzione in modo identico alla proprietà equivalenti in <xref:System.Windows.Controls.Calendar>.</span><span class="sxs-lookup"><span data-stu-id="20094-107">Many of a <xref:System.Windows.Controls.DatePicker> control's properties are for managing its built-in <xref:System.Windows.Controls.Calendar>, and function identically to the equivalent property in <xref:System.Windows.Controls.Calendar>.</span></span> <span data-ttu-id="20094-108">In particolare, il <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, e <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> le proprietà funzionano in modo identico alle loro <xref:System.Windows.Controls.Calendar> controparti.</span><span class="sxs-lookup"><span data-stu-id="20094-108">In particular, the <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, and <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> properties function identically to their <xref:System.Windows.Controls.Calendar> counterparts.</span></span> <span data-ttu-id="20094-109">Per altre informazioni, vedere <xref:System.Windows.Controls.Calendar>.</span><span class="sxs-lookup"><span data-stu-id="20094-109">For more information, see <xref:System.Windows.Controls.Calendar>.</span></span>  
  
 <span data-ttu-id="20094-110">Gli utenti possono immettere una data direttamente in un campo di testo, che imposta il <xref:System.Windows.Controls.DatePicker.Text%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="20094-110">Users can type a date directly into a text field, which sets the <xref:System.Windows.Controls.DatePicker.Text%2A> property.</span></span> <span data-ttu-id="20094-111">Se il <xref:System.Windows.Controls.DatePicker> non è possibile convertire la stringa immessa una data valida, il <xref:System.Windows.Controls.DatePicker.DateValidationError> verrà generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="20094-111">If the <xref:System.Windows.Controls.DatePicker> cannot convert the entered string to a valid date, the <xref:System.Windows.Controls.DatePicker.DateValidationError> event will be raised.</span></span> <span data-ttu-id="20094-112">Per impostazione predefinita, questo causa un'eccezione, ma un gestore eventi per <xref:System.Windows.Controls.DatePicker.DateValidationError> possibile impostare il <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> proprietà `false` e impedire la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="20094-112">By default, this causes an exception, but an event handler for <xref:System.Windows.Controls.DatePicker.DateValidationError> can set the <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> property to `false` and prevent an exception from being raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20094-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20094-113">See Also</span></span>  
 [<span data-ttu-id="20094-114">Controlli</span><span class="sxs-lookup"><span data-stu-id="20094-114">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
 [<span data-ttu-id="20094-115">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="20094-115">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
