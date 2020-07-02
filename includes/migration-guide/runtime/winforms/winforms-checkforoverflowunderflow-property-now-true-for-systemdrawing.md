---
ms.openlocfilehash: 4cd06fd02fadbaa9f74e40f850e688ee883454ed
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620446"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>La proprietà CheckForOverflowUnderflow di WinForm ora è true per System.Drawing

#### <a name="details"></a>Dettagli

La proprietà CheckForOverflowUnderflow per l'assembly System.Drawing.dll è impostata su true.

#### <a name="suggestion"></a>Suggerimento

In precedenza, quando si verificavano overflow, il risultato veniva automaticamente troncato. Ora viene generata un'eccezione <xref:System.OverflowException?displayProperty=fullName>.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime|
