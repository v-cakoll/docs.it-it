---
ms.openlocfilehash: 2aa6603e2ed77ffa94fbc6325cd5db50985bda6a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620414"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>PreviewLostKeyboardFocus viene chiamato ripetutamente se il gestore visualizza una finestra di messaggio di Windows Forms

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.5, la chiamata di <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> da un gestore <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> causerà la riattivazione del gestore alla chiusura della finestra di messaggio, con un potenziale ciclo infinito di finestre di messaggio.

#### <a name="suggestion"></a>Suggerimento

Esistono due modi per aggirare questo problema:<ol><li>Può essere evitato chiamando <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> invece di <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</li><li>Può essere evitato visualizzando la finestra di messaggio da un gestore eventi <xref:System.Windows.UIElement.LostKeyboardFocus>, anziché un gestore eventi <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName>.</li></ol>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType></li></ul>|
