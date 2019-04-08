---
ms.openlocfilehash: 8f4ee44e8432bae3537c6f064f564b9f044a7c33
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761470"
---
### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a>Arresto anomalo del sistema nel selettore quando si rimuove un elemento da una raccolta INCC personalizzata

|   |   |
|---|---|
|Dettagli|Un'eccezione <code>T:System.InvalidOperationException</code> può verificarsi negli scenari seguenti:<ul><li>ItemsSource per un <code>T:System.Windows.Controls.Primitives.Selector</code> è una raccolta con un'implementazione personalizzata di <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</li><li>L'elemento selezionato viene rimosso dalla raccolta.</li><li><code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> ha <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = -1 (indica una posizione sconosciuta).</li></ul>Lo stack di chiamate dell'eccezione inizia in corrispondenza di System.Windows.Threading.Dispatcher.VerifyAccess() in System.Windows.DependencyObject.GetValue(DependencyProperty dp) in System.Windows.Controls.Primitives.Selector.GetIsSelected(elemento DependencyObject) Questa eccezione si può verificare in .NET Framework 4.5 se l'applicazione ha più di un thread di Dispatcher. In .NET Framework 4.7 l'eccezione può verificarsi anche in applicazioni con un singolo thread di Dispatcher. Il problema è stato corretto in .NET Framework 4.7.1.|
|Suggerimento|Effettuare l'aggiornamento a .NET Framework 4.7.1.|
|Ambito|Secondario|
|Versione|4.7|
|Tipo|Runtime|

