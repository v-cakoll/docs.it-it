---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 3e66b2306c11c54db14eb05cc6860257635cc653
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460363"
---
# <a name="datepicker"></a>DatePicker
Il controllo <xref:System.Windows.Controls.DatePicker> consente all'utente di selezionare una data digitando l'oggetto in un campo di testo o utilizzando un controllo <xref:System.Windows.Controls.Calendar> a discesa.  
  
 Nella figura seguente viene illustrato un <xref:System.Windows.Controls.DatePicker>.  
  
 ![Controllo DatePicker](./media/ndp-datepicker.png "NDP_DatePicker")  
Controllo DatePicker  
  
 Molte delle proprietà di un controllo <xref:System.Windows.Controls.DatePicker> sono per la gestione dei <xref:System.Windows.Controls.Calendar>predefiniti e funzionano in modo identico alla proprietà equivalente in <xref:System.Windows.Controls.Calendar>. In particolare, le proprietà <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>e <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> funzionano in modo identico alle relative controparti di <xref:System.Windows.Controls.Calendar>. Per ulteriori informazioni, vedere <xref:System.Windows.Controls.Calendar>.  
  
 Gli utenti possono digitare una data direttamente in un campo di testo, che imposta la proprietà <xref:System.Windows.Controls.DatePicker.Text%2A>. Se il <xref:System.Windows.Controls.DatePicker> non è in grado di convertire la stringa immessa in una data valida, verrà generato l'evento <xref:System.Windows.Controls.DatePicker.DateValidationError>. Per impostazione predefinita, viene generata un'eccezione, ma un gestore eventi per <xref:System.Windows.Controls.DatePicker.DateValidationError> può impostare la proprietà <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> su `false` ed evitare che venga generata un'eccezione.  
  
## <a name="see-also"></a>Vedere anche

- [Controlli](index.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
