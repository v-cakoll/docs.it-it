---
ms.openlocfilehash: 24141f4b95cda2ae382a923da034e75c329b8555
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74643963"
---
### <a name="modernization-of-the-folderbrowserdialog"></a>Modernizzazione di FolderBrowserDialog

Il <xref:System.Windows.Forms.FolderBrowserDialog> controllo è stato modificato nelle applicazioni Windows Form per .NET Core.The control has changed in Windows Forms applications for .NET Core.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Framework Windows Form utilizza la <xref:System.Windows.Forms.FolderBrowserDialog> finestra di dialogo seguente per il controllo:

![The FolderBrowserDialogControl in the .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

In .NET Core 3.0, Windows Form utenti un controllo basato su COM più recente che è stato introdotto in Windows Vista:

![Il FolderBrowserDialogControl in .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

La finestra di dialogo verrà aggiornata automaticamente.

Se si desidera mantenere la finestra <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> di `false` dialogo originale, impostare la proprietà su prima di visualizzare la finestra di dialogo, come illustrato dal frammento di codice seguente:

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

### Affected APIs

- `System.Windows.Forms.FolderBrowserDialog`

-->
