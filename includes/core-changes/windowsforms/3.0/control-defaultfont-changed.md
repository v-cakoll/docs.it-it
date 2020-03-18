---
ms.openlocfilehash: b0c4e9617677cf95e3a059b57f3d50ddfb072f4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937083"
---
### <a name="default-control-font-changed-to-segoe-ui-9-pt"></a><span data-ttu-id="2a691-101">Tipo di carattere di controllo predefinito modificato in Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="2a691-101">Default control font changed to Segoe UI 9 pt</span></span>

#### <a name="change-description"></a><span data-ttu-id="2a691-102">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="2a691-102">Change description</span></span>

<span data-ttu-id="2a691-103">In .NET Framework <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> la proprietà `Microsoft Sans Serif 8 pt`è stata impostata su .</span><span class="sxs-lookup"><span data-stu-id="2a691-103">In .NET Framework, the <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> property was set to `Microsoft Sans Serif 8 pt`.</span></span> <span data-ttu-id="2a691-104">L'immagine seguente mostra una finestra che utilizza il tipo di carattere predefinito.</span><span class="sxs-lookup"><span data-stu-id="2a691-104">The following image shows a window that uses the default font.</span></span>

![Tipo di carattere del controllo predefinito in .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

<span data-ttu-id="2a691-106">A partire da .NET Core 3.0, `Segoe UI 9 pt` il tipo <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>di carattere predefinito è impostato su (lo stesso tipo di carattere di ).</span><span class="sxs-lookup"><span data-stu-id="2a691-106">Starting in .NET Core 3.0, the default font is set to `Segoe UI 9 pt` (the same font as <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span></span> <span data-ttu-id="2a691-107">Come risultato di questa modifica, i moduli e i controlli vengono dimensionati circa il 27% più grandi per tenere conto delle dimensioni maggiori del nuovo tipo di carattere predefinito.</span><span class="sxs-lookup"><span data-stu-id="2a691-107">As a result of this change, forms and controls are sized about 27% larger to account for the larger size of the new default font.</span></span> <span data-ttu-id="2a691-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2a691-108">For example:</span></span>

![Tipo di carattere del controllo predefinito in .NET CoreDefault control font in .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

<span data-ttu-id="2a691-110">Questa modifica è stata apportata per allinearsi alle [linee guida dell'esperienza utente di Windows.](/windows/win32/uxguide/vis-fonts#fonts-and-colors)</span><span class="sxs-lookup"><span data-stu-id="2a691-110">This change was made to align with [Windows user experience (UX) guidelines](/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2a691-111">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="2a691-111">Version introduced</span></span>

<span data-ttu-id="2a691-112">3.0</span><span class="sxs-lookup"><span data-stu-id="2a691-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2a691-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="2a691-113">Recommended action</span></span>

<span data-ttu-id="2a691-114">A causa della modifica delle dimensioni di form e controlli, assicurarsi che il rendering dell'applicazione venga eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="2a691-114">Because of the change in the size of forms and controls, ensure that your application renders correctly.</span></span>

<span data-ttu-id="2a691-115">Per mantenere il tipo di carattere originale, impostare il tipo di carattere predefinito del modulo su `Microsoft Sans Serif 8 pt`.</span><span class="sxs-lookup"><span data-stu-id="2a691-115">To retain the original font, set your form's default font to `Microsoft Sans Serif 8 pt`.</span></span> <span data-ttu-id="2a691-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2a691-116">For example:</span></span>

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a><span data-ttu-id="2a691-117">Category</span><span class="sxs-lookup"><span data-stu-id="2a691-117">Category</span></span>

- <span data-ttu-id="2a691-118">Windows Form</span><span class="sxs-lookup"><span data-stu-id="2a691-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2a691-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="2a691-119">Affected APIs</span></span>

<span data-ttu-id="2a691-120">No.</span><span class="sxs-lookup"><span data-stu-id="2a691-120">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
