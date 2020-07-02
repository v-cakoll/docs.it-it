---
ms.openlocfilehash: fbf3c0c8f1d11f9f5997a4d1027242c4710c7107
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621802"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a>Scorrimento per elementi in un elenco semplice con elementi la cui altezza in pixel è diversa

#### <a name="details"></a>Dettagli

Quando <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> visualizza una raccolta mediante la virtualizzazione (<code>IsVirtualizing=true</code>) e lo scorrimento per elementi (<code>ScrollUnit=Item</code>) e quando si scorre il controllo per visualizzare un elemento la cui altezza in pixel è diversa dagli elementi adiacenti, <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> esegue l'iterazione in tutti gli elementi nella raccolta. L'interfaccia utente non risponde durante questa iterazione. Se la raccolta è di grandi dimensioni, può essere percepita come un blocco. L'iterazione si verifica in altre circostanze, anche nelle versioni precedenti del .NET Framework. Si verifica, ad esempio, quando lo scorrimento pixel (<code>ScrollUnit=Pixel</code>) incontra un elemento con un'altezza di pixel diversa e quando lo scorrimento per elementi di dati gerarchici (ad esempio in <xref:System.Windows.Controls.TreeView?displayProperty=fullName> o in <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> con raggruppamento abilitato) incontra un elemento con un numero diverso di elementi discendenti rispetto agli elementi adiacenti. Nel caso dello scorrimento per elementi e le altezze di pixel diverse, in .NET Framework 4.6.1 è stata introdotta l'iterazione per correggere i bug nel layout dei dati gerarchici.  Non è necessaria se i dati sono flat (senza gerarchia) e .NET Framework 4.6.2 non la esegue in questo caso.

#### <a name="suggestion"></a>Suggerimento

Se l'iterazione avviene in .NET Framework 4.6.1 ma non nelle versioni precedenti, ovvero se <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> esegue lo scorrimento per elementi di un elenco semplice con elementi con altezze diverse in pixel, esistono due soluzioni:<ol><li>Installare .NET Framework 4.6.2.</li><li>Installare l'hotfix HR 1605 per .NET Framework 4.6.1.</li></ol>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.6.1|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType></li></ul>|
