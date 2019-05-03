---
ms.openlocfilehash: b761cb699c4677f815835cdab9c6aa3039f5bb38
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804183"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectiontmove"></a>Problema di binding di ListBoxItem IsSelected con ObservableCollection\<T>.Move

|   |   |
|---|---|
|Dettagli|La chiamata di <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> oppure <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> su una raccolta associata a un controllo <xref:System.Windows.Controls.ListBox?displayProperty=name> con elementi selezionati può causare un comportamento imprevedibile per la selezione futura o la deselezione di elementi <xref:System.Windows.Controls.ListBox?displayProperty=name>.|
|Suggerimento|La chiamata di <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=name> e <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=name> invece di <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> risolverà questo problema. In alternativa, questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
