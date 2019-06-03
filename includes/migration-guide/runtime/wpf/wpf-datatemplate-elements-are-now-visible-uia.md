---
ms.openlocfilehash: 51691ced3f05201f784ccdeffbc130e34748b7c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379574"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a>Gli elementi WPF DataTemplate ora sono visibili per Automazione interfaccia utente (UIA)

|   |   |
|---|---|
|Dettagli|In precedenza gli elementi <xref:System.Windows.DataTemplate?displayProperty=name> erano invisibili per Automazione interfaccia utente. A partire dalla versione 4.5, Automazione interfaccia utente rileva questi elementi. Questo è utile in molti casi, ma può causare problemi per i test che dipendono da alberi di automazione interfaccia utente che non contengono elementi <xref:System.Windows.DataTemplate?displayProperty=name>.|
|Suggerimento|Potrebbe essere necessario aggiornare i test di Automazione interfaccia utente per questa app per tenere conto dell'albero di Automazione interfaccia utente che ora include elementi <xref:System.Windows.DataTemplate?displayProperty=name> precedentemente invisibili. Ad esempio, nei test che prevedono che alcuni elementi siano adiacenti può essere ora necessario prevedere che possono infrapporsi elementi di Automazione interfaccia utente precedentemente invisibili. Oppure, potrebbe essere necessario aggiornare con nuovi valori i test che si basano su conteggi o indici specifici per gli elementi di Automazione interfaccia utente.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.DataTemplate.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.DataTemplate.%23ctor(System.Object)?displayProperty=nameWithType></li></ul>|
