---
ms.openlocfilehash: f4ff938b2d0e9ead481fdf239aed8a6b918a99b0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620449"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a>Problema di associazione ListBoxItem IsSelected con ObservableCollection&lt;T&gt;.Move

#### <a name="details"></a>Dettagli

La chiamata di <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> oppure <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> su una raccolta associata a un controllo <xref:System.Windows.Controls.ListBox?displayProperty=fullName> con elementi selezionati può causare un comportamento imprevedibile per la selezione futura o la deselezione di elementi <xref:System.Windows.Controls.ListBox?displayProperty=fullName>.

#### <a name="suggestion"></a>Suggerimento

La chiamata di <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> e <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> invece di <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> risolverà questo problema. In alternativa, questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
