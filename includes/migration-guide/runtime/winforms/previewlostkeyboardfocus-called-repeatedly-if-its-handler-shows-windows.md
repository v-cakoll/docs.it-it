---
ms.openlocfilehash: addfd55fd01b13e9088e4706ff846fc624aafa68
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804264"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>PreviewLostKeyboardFocus viene chiamato ripetutamente se il gestore visualizza una finestra di messaggio di Windows Forms

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.5, la chiamata di <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> da un gestore <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> causerà la riattivazione del gestore alla chiusura della finestra di messaggio, con un potenziale ciclo infinito di finestre di messaggio.|
|Suggerimento|Esistono due modi per aggirare questo problema:<ol><li>Può essere evitato chiamando <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> invece di <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</li><li>Può essere evitato visualizzando la finestra di messaggio da un gestore eventi <xref:System.Windows.UIElement.LostKeyboardFocus?displayProperty=nameWithType>, anziché un gestore eventi <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=name>.</li></ol>|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType></li></ul>|
