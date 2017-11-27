---
title: 'Procedura: impostare notifiche relative ad aggiornamenti di associazioni'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- notifications [WPF], binding updates
- data binding [WPF], notification of binding updates
- binding [WPF], updates [WPF], notifications of
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0e75ec53a769099e199b60f5466eeb4037b86862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-up-notification-of-binding-updates"></a>Procedura: impostare notifiche relative ad aggiornamenti di associazioni
Questo esempio spiega come impostare una notifica quando viene aggiornata la proprietà della destinazione di binding (destinazione) o dell'origine di binding (origine).  
  
## <a name="example"></a>Esempio  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] genera un evento di aggiornamento dati ogni volta che l'origine o la destinazione di binding viene aggiornata. Internamente, questo evento viene usato per indicare la necessità di un aggiornamento per [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], poiché sono cambiati i dati associati. Si noti che per utilizzare questi eventi, nonché per l'associazione unidirezionale o bidirezionale per il corretto funzionamento, è necessario implementare la classe di dati utilizzando il <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia. Per altre informazioni, vedere [Implementare la notifica di modifiche alle proprietà](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
 Impostare il <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> o <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> proprietà (o entrambi) per `true` nell'associazione. Il gestore fornito per l'ascolto di questo evento deve essere associato direttamente all'elemento in cui si desidera essere informati delle modifiche oppure al contesto dati complessivo se si desidera conoscere eventuali modifiche nel contesto.  
  
 Ecco un esempio che illustra come configurare le notifiche quando viene aggiornata una proprietà di destinazione.  
  
 [!code-xaml[DirectionalBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 Sarà quindi possibile assegnare un gestore basato sul delegato EventHandler\<T>, *OnTargetUpdated* in questo esempio, per gestire l'evento:  
  
 [!code-csharp[DirectionalBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 I parametri dell'evento possono essere usati per determinare i dettagli sulla proprietà modificata (ad esempio, il tipo o l'elemento specifico se lo stesso gestore è associato a più elementi). Questa condizione può risultare utile in presenza di più proprietà associate in un singolo elemento.  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
