---
ms.openlocfilehash: 1545c807e3bef675e63e14d01ab82c1131600f39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857598"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a>Items.Clear non rimuove i duplicati da SelectedItems

|   |   |
|---|---|
|Dettagli|Se un selettore con selezione multipla abilitata contiene duplicati nella raccolta <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>, lo stesso elemento viene visualizzato più volte.  L'eliminazione di questi elementi dall'origine dati (ad esempio, chiamando Items.Clear) non li rimuove da <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>; viene rimossa solo la prima istanza. Nell'uso successivo di <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>, ad esempio SelectedItems.Clear(), si possono inoltre verificare errori, ad esempio <xref:System.ArgumentException?displayProperty=name>, in quanto <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> contiene elementi che non sono più nell'origine dati.|
|Suggerimento|Se possibile, eseguire l'aggiornamento a .NET Framework 4.6.2.|
|Scope|Minorenne|
|Versione|4.5|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType></li></ul>|
