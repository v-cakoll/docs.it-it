---
ms.openlocfilehash: 6da589057cebfbf3f67a46b8d49d3a61f037c4c7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622252"
---
### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a>Arresto anomalo del sistema nel selettore quando si rimuove un elemento da una raccolta INCC personalizzata

#### <a name="details"></a>Dettagli

Un'eccezione <code>T:System.InvalidOperationException</code> può verificarsi negli scenari seguenti:<ul><li>ItemsSource per un <code>T:System.Windows.Controls.Primitives.Selector</code> è una raccolta con un'implementazione personalizzata di <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</li><li>L'elemento selezionato viene rimosso dalla raccolta.</li><li><code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> ha <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = -1 (indica una posizione sconosciuta).</li></ul>Lo stack di chiamate dell'eccezione inizia in corrispondenza di System.Windows.Threading.Dispatcher.VerifyAccess() in System.Windows.DependencyObject.GetValue(DependencyProperty dp) in System.Windows.Controls.Primitives.Selector.GetIsSelected(elemento DependencyObject) Questa eccezione si può verificare in .NET Framework 4.5 se l'applicazione ha più di un thread di Dispatcher. In .NET Framework 4.7 l'eccezione può verificarsi anche in applicazioni con un singolo thread di Dispatcher. Il problema è stato corretto in .NET Framework 4.7.1.

#### <a name="suggestion"></a>Suggerimento

Effettuare l'aggiornamento a .NET Framework 4.7.1.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.7|
|Type|Runtime|
