---
title: "Procedura: implementare notifiche di modifiche alle proprietà"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6674628acd4ea6b18f98a0ab5e20935220595de5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
 [Cenni preliminari sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
