---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802553"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>Viene impostato lo sfondo trasparente per RibbonGroup nelle build localizzate

|   |   |
|---|---|
|Dettagli|Lo sfondo di <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> nelle build localizzate viene sempre disegnato con il pennello trasparente, causando un'esperienza insoddisfacente per l'interfaccia utente. Questo problema è stato risolto nella correzione di WPF per .NET Framework 4.7 con l'aggiornamento delle risorse localizzate per <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, che a sua volta garantisce che sia selezionato il pennello corretto.|
|Suggerimento|Effettuare l'aggiornamento a .NET Framework 4.7|
|Scope|Microsoft Edge|
|Versione|4.6.2|
|Type|Runtime|
