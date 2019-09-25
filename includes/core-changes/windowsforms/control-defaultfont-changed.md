---
ms.openlocfilehash: 843007ac6467584fbe6350b6ea19ef67609d73e2
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71217031"
---
### <a name="controldefaultfont-changed-to-segoe-ui-9pt"></a><span data-ttu-id="a6c72-101">`Control.DefaultFont`modificato in`Segoe UI 9pt`</span><span class="sxs-lookup"><span data-stu-id="a6c72-101">`Control.DefaultFont` changed to `Segoe UI 9pt`</span></span>

#### <a name="change-description"></a><span data-ttu-id="a6c72-102">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="a6c72-102">Change description</span></span>

<span data-ttu-id="a6c72-103">Nella .NET Framework la <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> proprietà è stata impostata su `Microsoft Sans Serif 8pt`.</span><span class="sxs-lookup"><span data-stu-id="a6c72-103">In the .NET Framework, the <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> property was set to `Microsoft Sans Serif 8pt`.</span></span> <span data-ttu-id="a6c72-104">Nella figura seguente è illustrata una finestra che utilizza il tipo di carattere predefinito.</span><span class="sxs-lookup"><span data-stu-id="a6c72-104">The following figure shows a window that uses the default font.</span></span>

![tipo di carattere del controllo predefinito in .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

<span data-ttu-id="a6c72-106">In .NET Core, a partire da .NET Core 3,0, viene impostato `Segoe UI 9pt` su (lo stesso tipo <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>di carattere di).</span><span class="sxs-lookup"><span data-stu-id="a6c72-106">In .NET Core starting with .NET Core 3.0, it is set to `Segoe UI 9pt` (the same font as <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span></span> <span data-ttu-id="a6c72-107">In seguito a questa modifica, i form e i controlli verranno ridimensionati circa il 27% più grande per tenere conto della dimensione maggiore del nuovo tipo di carattere predefinito.</span><span class="sxs-lookup"><span data-stu-id="a6c72-107">As a result of this change, forms and controls will be sized about 27% larger to account for the larger size of the new default font.</span></span> <span data-ttu-id="a6c72-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a6c72-108">For example:</span></span>

![tipo di carattere del controllo predefinito-in .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

<span data-ttu-id="a6c72-110">Questa modifica è stata apportata per allinearsi alle [linee guida di Windows UX](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span><span class="sxs-lookup"><span data-stu-id="a6c72-110">This change was made to align with [Windows UX guidelines](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a6c72-111">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="a6c72-111">Version introduced</span></span>

<span data-ttu-id="a6c72-112">3.0</span><span class="sxs-lookup"><span data-stu-id="a6c72-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a6c72-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="a6c72-113">Recommended action</span></span>

<span data-ttu-id="a6c72-114">A causa della modifica delle dimensioni dei form e dei controlli, assicurarsi che l'applicazione venga correttamente sottoposta a rendering.</span><span class="sxs-lookup"><span data-stu-id="a6c72-114">Because of the change in the size of forms and controls, ensure that your application renders correctly.</span></span>

<span data-ttu-id="a6c72-115">Per mantenere il tipo di carattere originale, impostare il tipo di carattere `Microsoft Sans Serif 8pt`predefinito del form su.</span><span class="sxs-lookup"><span data-stu-id="a6c72-115">To retain the original font, set your form's default font to `Microsoft Sans Serif 8pt`.</span></span> <span data-ttu-id="a6c72-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a6c72-116">For example:</span></span>

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a><span data-ttu-id="a6c72-117">Category</span><span class="sxs-lookup"><span data-stu-id="a6c72-117">Category</span></span>

- <span data-ttu-id="a6c72-118">Windows Form</span><span class="sxs-lookup"><span data-stu-id="a6c72-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a6c72-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="a6c72-119">Affected APIs</span></span>

<span data-ttu-id="a6c72-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a6c72-120">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
