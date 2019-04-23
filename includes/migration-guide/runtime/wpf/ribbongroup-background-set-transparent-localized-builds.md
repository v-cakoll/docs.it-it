---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236049"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>Viene impostato lo sfondo trasparente per RibbonGroup nelle build localizzate

|   |   |
|---|---|
|Dettagli|<xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> Lo sfondo di RibbonGroup nelle build localizzate viene sempre disegnato con il pennello trasparente, causando un'esperienza insoddisfacente per l'interfaccia utente. Questo problema è stato risolto nella correzione di WPF per .NET Framework 4.7 con l'aggiornamento delle risorse localizzate per <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, che a sua volta garantisce che sia selezionato il pennello corretto.|
|Suggerimento|Effettuare l'aggiornamento a .NET Framework 4.7|
|Ambito|Microsoft Edge|
|Versione|4.6.2|
|Tipo|Runtime|
