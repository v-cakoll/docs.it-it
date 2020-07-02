---
ms.openlocfilehash: 9659068304eb208fd6a0a753273453bc669fbc56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621271"
---
### <a name="keytips-behavior-improved-in-wpf"></a>Miglioramento del comportamento dei suggerimenti tasto di scelta in WPF

#### <a name="details"></a>Dettagli

Il comportamento dei suggerimenti tasto di scelta è stato modificato in modo che fosse alla pari con il comportamento in Microsoft Word e in Esplora risorse. Controllando se lo stato dei suggerimenti tasto di scelta corrisponde o meno ad Abilitato in caso di pressione di un <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particolare <xref:System.Windows.Input.Key> o <xref:System.Windows.Input.Key.F11>), WPF gestisce i tasti dei suggerimenti tasto di scelta in modo appropriato. I suggerimenti tasto di scelta ora chiudono un menu anche se è stato aperto tramite mouse.

#### <a name="suggestion"></a>Suggerimento

N/D

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.7.2|
|Type|Runtime|
