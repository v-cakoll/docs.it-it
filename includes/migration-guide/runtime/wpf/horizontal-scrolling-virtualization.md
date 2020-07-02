---
ms.openlocfilehash: 14585b6de3ce02884f8be789930fc8610f73ba7d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621268"
---
### <a name="horizontal-scrolling-and-virtualization"></a>Scorrimento orizzontale e virtualizzazione

#### <a name="details"></a>Dettagli

Questa modifica si applica a un elemento <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> che esegue la propria virtualizzazione in direzione ortogonale alla direzione di scorrimento principale (l'esempio principale è <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> con EnableColumnVirtualization=&quot;True&quot;).  Il risultato di determinate operazioni di scorrimento orizzontale è stato modificato per produrre risultati più intuitivi e simili ai risultati delle operazioni verticali confrontabili.<p/>Le operazioni includono &quot;Scorri fino a qui&quot; e &quot;Margine destro&quot;, per usare i nomi del menu visualizzato facendo clic con il pulsante destro del mouse su una barra di scorrimento orizzontale.  Entrambe le operazioni calcolano un offset candidato ed eseguono una chiamata a <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset(System.Double)>.<p/>Dopo lo scorrimento al nuovo offset, la definizione di &quot;qui&quot; o &quot;margine destro&quot; potrebbe essere stata modificata, poiché il contenuto appena devirtualizzato ha modificato il valore di <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=fullName>.<p/>Nelle versioni precedenti a .NET Framework 4.6.2, l'operazione di scorrimento usa semplicemente l'offset candidato, anche se potrebbe non corrispondere più a &quot;qui&quot; o a &quot;margine destro&quot;.  Ciò potrebbe risultare in effetti come il &quot;rimbalzo&quot; dello scorrimento, illustrato nell'esempio. Si supponga che <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> abbia ExtentWidth = 1000 e Width = 200.  Uno scorrimento al &quot;Bordo destro&quot; usa l'offset candidato 1000-200 = 800.  Durante lo scorrimento all'offset, le nuove colonne vengono devirtualizzate. Si supponga che siano molto ampie, in modo che <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=fullName> venga portato a 2000.  Lo scorrimento termina con HorizontalOffset=800 e il controllo &quot;rimbalza&quot; vicino al centro della barra di scorrimento, esattamente in corrispondenza di 800/2000 = 40%.<p/>La modifica consiste nel ricalcolare un nuovo offset candidato quando si verifica questa situazione e quindi nell'eseguire un nuovo tentativo. (Lo scorrimento verticale funziona già in questo modo.) <p/>La modifica produce un'esperienza più prevedibile e intuitiva per l'utente finale, ma può influire anche su qualsiasi applicazione che dipende dal valore esatto di <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset?displayProperty=fullName> dopo una operazione di scorrimento orizzontale, attivata dall'utente finale o da una chiamata esplicita a <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset(System.Double)>.

#### <a name="suggestion"></a>Suggerimento

Un'app che usa un valore stimato per <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset?displayProperty=fullName> dovrebbe essere modificata per recuperare il valore effettivo (e il valore di <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=fullName>) dopo qualsiasi scorrimento orizzontale in grado di modificare <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=fullName> a causa della devirtualizzazione.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.6.2|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.Controls.Primitives.IScrollInfo?displayProperty=nameWithType></li></ul>|
