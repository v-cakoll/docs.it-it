---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235561"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>La proprietà CheckForOverflowUnderflow di WinForm ora è true per System.Drawing

|   |   |
|---|---|
|Dettagli|La proprietà CheckForOverflowUnderflow per l'assembly System.Drawing.dll è impostata su true.|
|Suggerimento|In precedenza, quando si verificavano overflow, il risultato veniva automaticamente troncato. Ora viene generata un'eccezione <xref:System.OverflowException?displayProperty=name>.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
