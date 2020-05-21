---
ms.openlocfilehash: 11c04441dcec260f0bfb90f6ed2b919b1545b382
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721312"
---
### <a name="modernization-of-the-folderbrowserdialog"></a><span data-ttu-id="e336d-101">Modernizzazione di FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="e336d-101">Modernization of the FolderBrowserDialog</span></span>

<span data-ttu-id="e336d-102">Il <xref:System.Windows.Forms.FolderBrowserDialog> controllo è stato modificato in Windows Forms applicazioni per .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e336d-102">The <xref:System.Windows.Forms.FolderBrowserDialog> control has changed in Windows Forms applications for .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e336d-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="e336d-103">Change description</span></span>

<span data-ttu-id="e336d-104">Nel .NET Framework, Windows Form utilizza la finestra di dialogo seguente per il <xref:System.Windows.Forms.FolderBrowserDialog> controllo:</span><span class="sxs-lookup"><span data-stu-id="e336d-104">In the .NET Framework, Windows forms uses the following dialog for the <xref:System.Windows.Forms.FolderBrowserDialog> control:</span></span>

![FolderBrowserDialogControl nella .NET Framework](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

<span data-ttu-id="e336d-106">In .NET Core 3,0, Windows Forms utenti un nuovo controllo basato su COM che è stato introdotto in Windows Vista:</span><span class="sxs-lookup"><span data-stu-id="e336d-106">In .NET Core 3.0, Windows Forms users a newer COM-based control that was introduced in Windows Vista:</span></span>

![FolderBrowserDialogControl in .NET Core](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a><span data-ttu-id="e336d-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="e336d-108">Version introduced</span></span>

<span data-ttu-id="e336d-109">3.0</span><span class="sxs-lookup"><span data-stu-id="e336d-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e336d-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="e336d-110">Recommended action</span></span>

<span data-ttu-id="e336d-111">La finestra di dialogo verrà aggiornata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e336d-111">The dialog will be upgraded automatically.</span></span>

<span data-ttu-id="e336d-112">Se si desidera mantenere la finestra di dialogo originale, impostare la <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> proprietà su `false` prima di visualizzare la finestra di dialogo, come illustrato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="e336d-112">If you desire to retain the original dialog, set the <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> property to `false` before showing the dialog, as illustrated by the following code fragment:</span></span>

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a><span data-ttu-id="e336d-113">Category</span><span class="sxs-lookup"><span data-stu-id="e336d-113">Category</span></span>

<span data-ttu-id="e336d-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e336d-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e336d-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="e336d-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

#### Affected APIs

- `T:System.Windows.Forms.FolderBrowserDialog`

-->
