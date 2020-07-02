---
ms.openlocfilehash: 75f176133697056bab9349ba1d18d7a0e1aa7da2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620128"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a>Items.Clear non rimuove i duplicati da SelectedItems

#### <a name="details"></a>Dettagli

Se un selettore con selezione multipla abilitata contiene duplicati nella raccolta <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>, lo stesso elemento viene visualizzato più volte.  L'eliminazione di questi elementi dall'origine dati (ad esempio, chiamando Items.Clear) non li rimuove da <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>; viene rimossa solo la prima istanza. Nell'uso successivo di <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>, ad esempio SelectedItems.Clear(), si possono inoltre verificare errori, ad esempio <xref:System.ArgumentException?displayProperty=fullName>, in quanto <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> contiene elementi che non sono più nell'origine dati.

#### <a name="suggestion"></a>Suggerimento

Se possibile, eseguire l'aggiornamento a .NET Framework 4.6.2.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType></li></ul>|
