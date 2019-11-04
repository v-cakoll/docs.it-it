---
title: 'Procedura: impostare notifiche relative ad aggiornamenti di associazioni'
ms.date: 03/30/2017
helpviewer_keywords:
- notifications [WPF], binding updates
- data binding [WPF], notification of binding updates
- binding [WPF], updates [WPF], notifications of
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
ms.openlocfilehash: dfa0f9264247f7585c1743e40fd980906556efd0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454945"
---
# <a name="how-to-set-up-notification-of-binding-updates"></a>Procedura: impostare notifiche relative ad aggiornamenti di associazioni
Questo esempio spiega come impostare una notifica quando viene aggiornata la proprietà della destinazione di binding (destinazione) o dell'origine di binding (origine).  
  
## <a name="example"></a>Esempio  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] genera un evento di aggiornamento dati ogni volta che l'origine o la destinazione di binding viene aggiornata. Internamente, questo evento viene usato per indicare la necessità di un aggiornamento per [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], poiché sono cambiati i dati associati. Si noti che per il corretto funzionamento di questi eventi e anche per il corretto funzionamento dell'associazione unidirezionale o bidirezionale, è necessario implementare la classe di dati usando l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>. Per altre informazioni, vedere [Implementare la notifica di modifiche alle proprietà](how-to-implement-property-change-notification.md).  
  
 Impostare la proprietà <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> o <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> (o entrambe) su `true` nell'associazione. Il gestore fornito per l'ascolto di questo evento deve essere associato direttamente all'elemento in cui si desidera essere informati delle modifiche oppure al contesto dati complessivo se si desidera conoscere eventuali modifiche nel contesto.  
  
 Ecco un esempio che illustra come configurare le notifiche quando viene aggiornata una proprietà di destinazione.  
  
 [!code-xaml[DirectionalBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 Sarà quindi possibile assegnare un gestore basato sul delegato EventHandler\<T>, *OnTargetUpdated* in questo esempio, per gestire l'evento:  
  
 [!code-csharp[DirectionalBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 I parametri dell'evento possono essere usati per determinare i dettagli sulla proprietà modificata (ad esempio, il tipo o l'elemento specifico se lo stesso gestore è associato a più elementi). Questa condizione può risultare utile in presenza di più proprietà associate in un singolo elemento.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
