---
ms.openlocfilehash: 645df8080abd21e4db95903a301a36b79a698858
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888123"
---
### <a name="modernization-of-the-folderbrowserdialog"></a><span data-ttu-id="6c3a6-101">Modernizzazione di FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="6c3a6-101">Modernization of the FolderBrowserDialog</span></span>

<span data-ttu-id="6c3a6-102">Il <xref:System.Windows.Forms.FolderBrowserDialog> controllo è stato modificato nelle applicazioni Windows Form per .NET Core.The control has changed in Windows Forms applications for .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6c3a6-102">The <xref:System.Windows.Forms.FolderBrowserDialog> control has changed in Windows Forms applications for .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6c3a6-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="6c3a6-103">Change description</span></span>

<span data-ttu-id="6c3a6-104">In .NET Framework Windows Form utilizza la <xref:System.Windows.Forms.FolderBrowserDialog> finestra di dialogo seguente per il controllo:</span><span class="sxs-lookup"><span data-stu-id="6c3a6-104">In the .NET Framework, Windows forms uses the following dialog for the <xref:System.Windows.Forms.FolderBrowserDialog> control:</span></span>

![The FolderBrowserDialogControl in the .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

<span data-ttu-id="6c3a6-106">In .NET Core 3.0, Windows Form utenti un controllo basato su COM più recente che è stato introdotto in Windows Vista:</span><span class="sxs-lookup"><span data-stu-id="6c3a6-106">In .NET Core 3.0, Windows Forms users a newer COM-based control that was introduced in Windows Vista:</span></span>

![Il FolderBrowserDialogControl in .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a><span data-ttu-id="6c3a6-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6c3a6-108">Version introduced</span></span>

<span data-ttu-id="6c3a6-109">3.0</span><span class="sxs-lookup"><span data-stu-id="6c3a6-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6c3a6-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="6c3a6-110">Recommended action</span></span>

<span data-ttu-id="6c3a6-111">La finestra di dialogo verrà aggiornata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6c3a6-111">The dialog will be upgraded automatically.</span></span>

<span data-ttu-id="6c3a6-112">Se si desidera mantenere la finestra <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> di `false` dialogo originale, impostare la proprietà su prima di visualizzare la finestra di dialogo, come illustrato dal frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6c3a6-112">If you desire to retain the original dialog, set the <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> property to `false` before showing the dialog, as illustrated by the following code fragment:</span></span>

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a><span data-ttu-id="6c3a6-113">Category</span><span class="sxs-lookup"><span data-stu-id="6c3a6-113">Category</span></span>

<span data-ttu-id="6c3a6-114">Windows Form</span><span class="sxs-lookup"><span data-stu-id="6c3a6-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6c3a6-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="6c3a6-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

### Affected APIs

- `T:System.Windows.Forms.FolderBrowserDialog`

-->
