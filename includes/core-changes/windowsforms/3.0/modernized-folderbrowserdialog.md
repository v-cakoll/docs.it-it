---
ms.openlocfilehash: 24141f4b95cda2ae382a923da034e75c329b8555
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643963"
---
### <a name="modernization-of-the-folderbrowserdialog"></a>Modernizzazione di FolderBrowserDialog

Il controllo <xref:System.Windows.Forms.FolderBrowserDialog> è stato modificato in Windows Forms applicazioni per .NET Core.

#### <a name="change-description"></a>Descrizione della modifica

Nel .NET Framework, Windows Forms usa la finestra di dialogo seguente per il controllo <xref:System.Windows.Forms.FolderBrowserDialog>:

![FolderBrowserDialogControl nella .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

In .NET Core 3,0, Windows Forms utenti un nuovo controllo basato su COM che è stato introdotto in Windows Vista:

![FolderBrowserDialogControl in .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

La finestra di dialogo verrà aggiornata automaticamente.

Se si desidera mantenere la finestra di dialogo originale, impostare la proprietà <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> su `false` prima di visualizzare la finestra di dialogo, come illustrato nel frammento di codice seguente:

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
