---
ms.openlocfilehash: 3a82822aae281ea7e873ba649f05b1d68686ec69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "70997640"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a>Scorrimento per elementi in un elenco semplice con elementi la cui altezza in pixel è diversa

|   |   |
|---|---|
|Dettagli|Quando <xref:System.Windows.Controls.ItemsControl?displayProperty=name> visualizza una raccolta mediante la virtualizzazione (<code>IsVirtualizing=true</code>) e lo scorrimento per elementi (<code>ScrollUnit=Item</code>) e quando si scorre il controllo per visualizzare un elemento la cui altezza in pixel è diversa dagli elementi adiacenti, <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> esegue l'iterazione in tutti gli elementi nella raccolta. L'interfaccia utente non risponde durante questa iterazione. se la raccolta è di grandi dimensioni, questo può essere percepito come un blocco. L'iterazione si verifica in altre circostanze, anche nelle versioni precedenti di .NET Framework. Si verifica, ad esempio, quando lo scorrimento pixel (<code>ScrollUnit=Pixel</code>) incontra un elemento con un'altezza di pixel diversa e quando lo scorrimento per elementi di dati gerarchici (ad esempio in <xref:System.Windows.Controls.TreeView?displayProperty=name> o in <xref:System.Windows.Controls.ItemsControl?displayProperty=name> con raggruppamento abilitato) incontra un elemento con un numero diverso di elementi discendenti rispetto agli elementi adiacenti. Nel caso dello scorrimento per elementi e le altezze di pixel diverse, in .NET Framework 4.6.1 è stata introdotta l'iterazione per correggere i bug nel layout dei dati gerarchici.  Non è necessaria se i dati sono flat (senza gerarchia) e .NET Framework 4.6.2 non la esegue in questo caso.|
|Suggerimento|Se l'iterazione avviene in .NET Framework 4.6.1 ma non nelle versioni precedenti, ovvero se <xref:System.Windows.Controls.ItemsControl?displayProperty=name> esegue lo scorrimento per elementi di un elenco semplice con elementi con altezze diverse in pixel, esistono due soluzioni:<ol><li>Installare .NET Framework 4.6.2.</li><li>Installare l'hotfix HR 1605 per .NET Framework 4.6.1.</li></ol>|
|Scope|Minorenne|
|Versione|4.6.1|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType></li></ul>|
