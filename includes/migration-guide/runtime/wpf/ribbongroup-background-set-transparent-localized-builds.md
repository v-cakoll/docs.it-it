---
ms.openlocfilehash: a3ba42868577ac20ea2e082f90fc4973a1bfe108
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622362"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>Viene impostato lo sfondo trasparente per RibbonGroup nelle build localizzate

#### <a name="details"></a>Dettagli

Lo sfondo di <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> nelle build localizzate viene sempre disegnato con il pennello trasparente, causando un'esperienza insoddisfacente per l'interfaccia utente. Questo problema è stato risolto nella correzione di WPF per .NET Framework 4.7 con l'aggiornamento delle risorse localizzate per <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, che a sua volta garantisce che sia selezionato il pennello corretto.

#### <a name="suggestion"></a>Suggerimento

Effettuare l'aggiornamento a .NET Framework 4.7

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.6.2|
|Type|Runtime|
