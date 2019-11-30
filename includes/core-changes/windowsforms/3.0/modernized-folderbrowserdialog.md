---
ms.openlocfilehash: 24141f4b95cda2ae382a923da034e75c329b8555
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643963"
---
### <a name="modernization-of-the-folderbrowserdialog"></a><span data-ttu-id="f4a97-101">Modernizzazione di FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="f4a97-101">Modernization of the FolderBrowserDialog</span></span>

<span data-ttu-id="f4a97-102">Il controllo <xref:System.Windows.Forms.FolderBrowserDialog> è stato modificato in Windows Forms applicazioni per .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f4a97-102">The <xref:System.Windows.Forms.FolderBrowserDialog> control has changed in Windows Forms applications for .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f4a97-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="f4a97-103">Change description</span></span>

<span data-ttu-id="f4a97-104">Nel .NET Framework, Windows Forms usa la finestra di dialogo seguente per il controllo <xref:System.Windows.Forms.FolderBrowserDialog>:</span><span class="sxs-lookup"><span data-stu-id="f4a97-104">In the .NET Framework, Windows forms uses the following dialog for the <xref:System.Windows.Forms.FolderBrowserDialog> control:</span></span>

![FolderBrowserDialogControl nella .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

<span data-ttu-id="f4a97-106">In .NET Core 3,0, Windows Forms utenti un nuovo controllo basato su COM che è stato introdotto in Windows Vista:</span><span class="sxs-lookup"><span data-stu-id="f4a97-106">In .NET Core 3.0, Windows Forms users a newer COM-based control that was introduced in Windows Vista:</span></span>

![FolderBrowserDialogControl in .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a><span data-ttu-id="f4a97-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="f4a97-108">Version introduced</span></span>

<span data-ttu-id="f4a97-109">3.0</span><span class="sxs-lookup"><span data-stu-id="f4a97-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f4a97-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="f4a97-110">Recommended action</span></span>

<span data-ttu-id="f4a97-111">La finestra di dialogo verrà aggiornata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f4a97-111">The dialog will be upgraded automatically.</span></span>

<span data-ttu-id="f4a97-112">Se si desidera mantenere la finestra di dialogo originale, impostare la proprietà <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> su `false` prima di visualizzare la finestra di dialogo, come illustrato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f4a97-112">If you desire to retain the original dialog, set the <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> property to `false` before showing the dialog, as illustrated by the following code fragment:</span></span>

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a><span data-ttu-id="f4a97-113">Category</span><span class="sxs-lookup"><span data-stu-id="f4a97-113">Category</span></span>

<span data-ttu-id="f4a97-114">Windows Form</span><span class="sxs-lookup"><span data-stu-id="f4a97-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f4a97-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="f4a97-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

### Affected APIs

- `System.Windows.Forms.FolderBrowserDialog`

-->
