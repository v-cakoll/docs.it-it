---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: a135188b2c573a578aa5b6be4910e6d02471aee1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362253"
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
