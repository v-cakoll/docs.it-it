---
ms.openlocfilehash: 06c699281c8890ac65be1d282b72b54774acc280
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620473"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a>Gli elementi WPF DataTemplate ora sono visibili per Automazione interfaccia utente (UIA)

#### <a name="details"></a>Dettagli

In precedenza gli elementi <xref:System.Windows.DataTemplate?displayProperty=fullName> erano invisibili per Automazione interfaccia utente. A partire dalla versione 4.5, Automazione interfaccia utente rileva questi elementi. Questo è utile in molti casi, ma può causare problemi per i test che dipendono da alberi di automazione interfaccia utente che non contengono elementi <xref:System.Windows.DataTemplate?displayProperty=fullName>.

#### <a name="suggestion"></a>Suggerimento

Potrebbe essere necessario aggiornare i test di Automazione interfaccia utente per questa app per tenere conto dell'albero di Automazione interfaccia utente che ora include elementi <xref:System.Windows.DataTemplate?displayProperty=fullName> precedentemente invisibili. Ad esempio, nei test che prevedono che alcuni elementi siano adiacenti può essere ora necessario prevedere che possono infrapporsi elementi di Automazione interfaccia utente precedentemente invisibili. Oppure, potrebbe essere necessario aggiornare con nuovi valori i test che si basano su conteggi o indici specifici per gli elementi di Automazione interfaccia utente.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.DataTemplate.%23ctor></li><li><xref:System.Windows.DataTemplate.%23ctor(System.Object)></li></ul>|
