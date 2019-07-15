---
ms.openlocfilehash: 9500907c6a1ba5b27008dcad4c9b47aef9092106
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802553"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>Viene impostato lo sfondo trasparente per RibbonGroup nelle build localizzate

|   |   |
|---|---|
|Dettagli|Lo sfondo di <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> nelle build localizzate viene sempre disegnato con il pennello trasparente, causando un'esperienza insoddisfacente per l'interfaccia utente. Questo problema è stato risolto nella correzione di WPF per .NET Framework 4.7 con l'aggiornamento delle risorse localizzate per <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, che a sua volta garantisce che sia selezionato il pennello corretto.|
|Suggerimento|Effettuare l'aggiornamento a .NET Framework 4.7|
|Ambito|Microsoft Edge|
|Versione|4.6.2|
|Tipo|Runtime|

