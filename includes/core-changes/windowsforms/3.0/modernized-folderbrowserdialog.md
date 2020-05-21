---
ms.openlocfilehash: 11c04441dcec260f0bfb90f6ed2b919b1545b382
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721312"
---
### <a name="modernization-of-the-folderbrowserdialog"></a>Modernizzazione di FolderBrowserDialog

Il <xref:System.Windows.Forms.FolderBrowserDialog> controllo è stato modificato in Windows Forms applicazioni per .NET Core.

#### <a name="change-description"></a>Descrizione modifica:

Nel .NET Framework, Windows Form utilizza la finestra di dialogo seguente per il <xref:System.Windows.Forms.FolderBrowserDialog> controllo:

![FolderBrowserDialogControl nella .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

In .NET Core 3,0, Windows Forms utenti un nuovo controllo basato su COM che è stato introdotto in Windows Vista:

![FolderBrowserDialogControl in .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

La finestra di dialogo verrà aggiornata automaticamente.

Se si desidera mantenere la finestra di dialogo originale, impostare la <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> proprietà su `false` prima di visualizzare la finestra di dialogo, come illustrato nel frammento di codice seguente:

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a>Category

Windows Forms

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

#### Affected APIs

- `T:System.Windows.Forms.FolderBrowserDialog`

-->
