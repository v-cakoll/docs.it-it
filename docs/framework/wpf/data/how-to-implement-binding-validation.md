---
title: 'Procedura: implementare la convalida dell''associazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d57fb099fa364d34b7df5c5fce792eb42079a31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-binding-validation"></a>Procedura: implementare la convalida dell'associazione
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> e un trigger di stile per fornire indicazioni visive per informare l'utente quando viene immesso un valore non valido, in base a una regola di convalida personalizzata.  
  
## <a name="example"></a>Esempio  
 Il contenuto di testo di <xref:System.Windows.Controls.TextBox> nell'esempio seguente viene associato al `Age` proprietà (di tipo int di un oggetto di origine di associazione denominato) `ods`. Il binding è configurato per l'uso di una regola di convalida denominata `AgeRangeRule` in modo che, se l'utente immette un carattere non numerico o un valore minore di 21 o maggiore di 130, appare un punto esclamativo rosso accanto alla casella di testo e viene visualizzata una descrizione comando con il messaggio di errore quando l'utente sposta il puntatore del mouse sulla casella di testo.  
  
 [!code-xaml[BindValidation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 Nell'esempio seguente viene illustrata l'implementazione di `AgeRangeRule`, che eredita da <xref:System.Windows.Controls.ValidationRule> ed esegue l'override di <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo. Il metodo Int32.Parse() viene chiamato sul valore per verificare che non contenga caratteri non validi. Il <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo restituisce un <xref:System.Windows.Controls.ValidationResult> che indica se il valore è valido in base se viene intercettata un'eccezione durante l'analisi e indica se il valore di durata di fuori di limiti inferiore e superiore.  
  
 [!code-csharp[BindValidation#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 Nell'esempio seguente viene personalizzata <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` che crea un punto esclamativo rosso per notificare all'utente di un errore di convalida. Vengono usati modelli specifici per ridefinire l'aspetto di un controllo.  
  
 [!code-xaml[BindValidation#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 Come illustrato nell'esempio seguente, il <xref:System.Windows.Controls.ToolTip> che visualizza il messaggio di errore viene creato utilizzando lo stile denominato `textBoxInError`. Se il valore di <xref:System.Windows.Controls.Validation.HasError%2A> è `true`, il trigger imposta la descrizione dell'oggetto corrente <xref:System.Windows.Controls.TextBox> sul primo errore di convalida. Il <xref:System.Windows.Data.Binding.RelativeSource%2A> è impostato su <xref:System.Windows.Data.RelativeSourceMode.Self>, che fa riferimento all'elemento corrente.  
  
 [!code-xaml[BindValidation#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 Per l'esempio completo, vedere [Binding Validation Sample (Esempio di convalida binding)](http://go.microsoft.com/fwlink/?LinkID=159972).  
  
 Si noti che se non si specifica un oggetto personalizzato <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> viene visualizzato il modello di errore predefinita per fornire feedback visivo all'utente quando si verifica un errore di convalida. Per altre informazioni, vedere "Convalida dei dati" in [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce anche una regola di convalida integrata che controlla le eccezioni generate durante l'aggiornamento della proprietà di origine del binding. Per altre informazioni, vedere <xref:System.Windows.Controls.ExceptionValidationRule>.  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
