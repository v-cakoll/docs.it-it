---
title: 'Procedura: implementare notifiche di modifiche alle proprietà'
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
ms.openlocfilehash: a9c0fb433e2fa65e28db3b793e038b49f9d6353b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555990"
---
# <a name="how-to-implement-property-change-notification"></a>Procedura: implementare notifiche di modifiche alle proprietà
Per supportare <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> binding per abilitare le proprietà di destinazione di associazione in modo da riflettere automaticamente le modifiche dinamiche dell'origine di associazione (ad esempio, per il riquadro di anteprima aggiornata automaticamente quando l'utente modifica un form), la classe deve fornire le notifiche di modifica delle proprietà appropriata. In questo esempio viene illustrato come creare una classe che implementa <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
## <a name="example"></a>Esempio  
 Per implementare <xref:System.ComponentModel.INotifyPropertyChanged> è necessario dichiarare il <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> evento e creare il `OnPropertyChanged` metodo. Quindi, per ogni proprietà per cui si desidera ricevere notifiche per le modifiche, chiamare `OnPropertyChanged` ogni volta che la proprietà viene aggiornata.  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 Per vedere un esempio di utilizzo del `Person` classe può essere utilizzata per supportare <xref:System.Windows.Data.BindingMode.TwoWay> binding, vedere [controllare quando il testo della casella di testo Aggiorna l'origine](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica delle origini di associazione](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
