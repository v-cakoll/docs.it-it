---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 555bf31b27ba233ffa54438077984b02b5e3084a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161337"
---
# <a name="datepicker"></a>DatePicker
Il <xref:System.Windows.Controls.DatePicker> controllo consente all'utente di selezionare una data digitandola in un campo di testo o utilizzando un elenco a discesa <xref:System.Windows.Controls.Calendar> controllo.  
  
 La figura seguente mostra un <xref:System.Windows.Controls.DatePicker>.  
  
 ![Controllo DatePicker](./media/ndp-datepicker.png "NDP_DatePicker")  
Controllo DatePicker  
  
 Molti di una <xref:System.Windows.Controls.DatePicker> sono di proprietà del controllo per la gestione relativo predefinito <xref:System.Windows.Controls.Calendar>e la funzione in modo identico alla proprietà equivalente in <xref:System.Windows.Controls.Calendar>. In particolare, il <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType>, e <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> proprietà funzionano in modo identico alle loro <xref:System.Windows.Controls.Calendar> controparti. Per altre informazioni, vedere <xref:System.Windows.Controls.Calendar>.  
  
 Gli utenti possono digitare una data direttamente in un campo di testo, che imposta il <xref:System.Windows.Controls.DatePicker.Text%2A> proprietà. Se il <xref:System.Windows.Controls.DatePicker> non è possibile convertire la stringa immessa una data valida, il <xref:System.Windows.Controls.DatePicker.DateValidationError> verrà generato l'evento. Per impostazione predefinita, verrà generata un'eccezione, ma un gestore eventi per <xref:System.Windows.Controls.DatePicker.DateValidationError> possibile impostare il <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> proprietà `false` e impedire un'eccezione generata.  
  
## <a name="see-also"></a>Vedere anche

- [Controlli](index.md)
- [Applicazione di stili e modelli](styling-and-templating.md)
