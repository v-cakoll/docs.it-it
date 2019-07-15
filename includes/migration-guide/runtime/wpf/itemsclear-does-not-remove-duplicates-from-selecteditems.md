---
ms.openlocfilehash: 2f94ec58e6fdb56cfc5147e74b6ffd6bb657228d
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857598"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a>Items.Clear non rimuove i duplicati da SelectedItems

|   |   |
|---|---|
|Dettagli|Se un selettore con selezione multipla abilitata contiene duplicati nella raccolta <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>, lo stesso elemento viene visualizzato più volte.  L'eliminazione di questi elementi dall'origine dati (ad esempio, chiamando Items.Clear) non li rimuove da <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>; viene rimossa solo la prima istanza. Nell'uso successivo di <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>, ad esempio SelectedItems.Clear(), si possono inoltre verificare errori, ad esempio <xref:System.ArgumentException?displayProperty=name>, in quanto <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> contiene elementi che non sono più nell'origine dati.|
|Suggerimento|Se possibile, eseguire l'aggiornamento a .NET Framework 4.6.2.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType></li></ul>|

