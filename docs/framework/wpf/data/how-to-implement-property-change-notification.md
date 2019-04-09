---
title: 'Procedura: Implementare la notifica di modifiche alle proprietà'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
ms.openlocfilehash: d37d468acc94470be8c2afdc495b40168932ec83
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204354"
---
# <a name="how-to-implement-property-change-notification"></a>Procedura: Implementare la notifica di modifiche alle proprietà
Per supportare <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> binding per abilitare le proprietà di destinazione di associazione in modo da riflettere automaticamente le modifiche dinamiche dell'origine del binding (ad esempio, per il riquadro di anteprima aggiornata automaticamente quando l'utente modifica un modulo), la classe deve fornire le notifiche di proprietà modificata appropriate. In questo esempio viene illustrato come creare una classe che implementa <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
## <a name="example"></a>Esempio  
 Per implementare <xref:System.ComponentModel.INotifyPropertyChanged> è necessario dichiarare il <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventi e creare il `OnPropertyChanged` (metodo). Quindi, per ogni proprietà per cui si desidera ricevere notifiche per le modifiche, chiamare `OnPropertyChanged` ogni volta che la proprietà viene aggiornata.  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 Per vedere un esempio del modo in cui il `Person` classe può essere utilizzata per supportare <xref:System.Windows.Data.BindingMode.TwoWay> associazione, vedere [controllare quando l'origine viene aggiornato il testo nella casella di testo](how-to-control-when-the-textbox-text-updates-the-source.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle origini del binding](binding-sources-overview.md)
- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative](data-binding-how-to-topics.md)
