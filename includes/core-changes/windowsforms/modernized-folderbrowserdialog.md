---
ms.openlocfilehash: a7cf6210e288d3521f1df248927f0e7cfaf45cab
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119324"
---
### <a name="modernization-of-the-folderbrowserdialog"></a>Modernizzazione di FolderBrowserDialog

Il <xref:System.Windows.Forms.FolderBrowserDialog> controllo è stato modificato in Windows Forms applicazioni per .NET Core.

#### <a name="change-description"></a>Descrizione della modifica

Nel .NET Framework, Windows Form utilizza la finestra di dialogo seguente per <xref:System.Windows.Forms.FolderBrowserDialog> il controllo:

![FolderBrowserDialogControl nella .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

In .NET Core 3,0, Windows Forms utenti un nuovo controllo basato su COM che è stato introdotto in Windows Vista:

![FolderBrowserDialogControl in .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

La finestra di dialogo verrà aggiornata automaticamente.

Se si desidera mantenere la finestra di dialogo originale, impostare <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> la proprietà `false` su prima di visualizzare la finestra di dialogo, come illustrato nel frammento di codice seguente:

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