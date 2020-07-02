---
title: "Procedura: implementare la convalida dell'associazione"
description: Informazioni su come usare la convalida dell'associazione per fornire un feedback visivo all'utente quando viene immesso un valore non valido in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 0813be9f79a83a9dae26db1dadb58b5e973339fd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617882"
---
# <a name="how-to-implement-binding-validation"></a>Procedura: implementare la convalida dell'associazione

Questo esempio illustra come usare un <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> trigger di stile e per fornire commenti visivi per informare l'utente quando viene immesso un valore non valido, in base a una regola di convalida personalizzata.

## <a name="example"></a>Esempio

Il contenuto di testo di <xref:System.Windows.Controls.TextBox> nell'esempio seguente è associato alla `Age` Proprietà (di tipo int) di un oggetto di origine del binding denominato `ods` . Il binding è configurato per l'uso di una regola di convalida denominata `AgeRangeRule` in modo che, se l'utente immette un carattere non numerico o un valore minore di 21 o maggiore di 130, appare un punto esclamativo rosso accanto alla casella di testo e viene visualizzata una descrizione comando con il messaggio di errore quando l'utente sposta il puntatore del mouse sulla casella di testo.

[!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]

Nell'esempio seguente viene illustrata l'implementazione di `AgeRangeRule` , che eredita da <xref:System.Windows.Controls.ValidationRule> ed esegue l'override del <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo. Il `Int32.Parse` metodo viene chiamato sul valore per assicurarsi che non contenga caratteri non validi. Il <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo restituisce un <xref:System.Windows.Controls.ValidationResult> valore che indica se il valore è valido in base al fatto che un'eccezione venga intercettata durante l'analisi e se il valore di età è esterno ai limiti inferiore e superiore.

[!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]
[!code-vb[BindValidation#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindValidation/VisualBasic/AgeRangeRule.vb#3)]

Nell'esempio seguente viene illustrato l'oggetto personalizzato <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` che crea un punto esclamativo rosso per notificare all'utente un errore di convalida. Vengono usati modelli specifici per ridefinire l'aspetto di un controllo.

[!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]

Come illustrato nell'esempio seguente, l'oggetto <xref:System.Windows.Controls.ToolTip> che mostra il messaggio di errore viene creato usando lo stile denominato `textBoxInError` . Se il valore di <xref:System.Windows.Controls.Validation.HasError%2A> è `true` , il trigger imposta la descrizione comando dell'oggetto corrente sul <xref:System.Windows.Controls.TextBox> primo errore di convalida. <xref:System.Windows.Data.Binding.RelativeSource%2A>È impostato su <xref:System.Windows.Data.RelativeSourceMode.Self> , facendo riferimento all'elemento corrente.

[!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]

Per l'esempio completo, vedere [esempio di convalida di binding](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).
  
Si noti che se non si specifica un oggetto personalizzato <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> , il modello di errore predefinito sembra fornire un feedback visivo all'utente quando si verifica un errore di convalida. Per altre informazioni, vedere "Convalida dei dati" in [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce anche una regola di convalida integrata che controlla le eccezioni generate durante l'aggiornamento della proprietà di origine del binding. Per altre informazioni, vedere <xref:System.Windows.Controls.ExceptionValidationRule>.

## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure](data-binding-how-to-topics.md)
