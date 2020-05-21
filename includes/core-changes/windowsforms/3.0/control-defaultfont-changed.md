---
ms.openlocfilehash: 0b2d3c1383246d4259c6d906ecf9dab927f4bdb1
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721025"
---
### <a name="default-control-font-changed-to-segoe-ui-9-pt"></a><span data-ttu-id="34385-101">Il tipo di carattere del controllo predefinito è stato modificato in Segoe UI 9 PT</span><span class="sxs-lookup"><span data-stu-id="34385-101">Default control font changed to Segoe UI 9 pt</span></span>

#### <a name="change-description"></a><span data-ttu-id="34385-102">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="34385-102">Change description</span></span>

<span data-ttu-id="34385-103">In .NET Framework la <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> proprietà è stata impostata su `Microsoft Sans Serif 8 pt` .</span><span class="sxs-lookup"><span data-stu-id="34385-103">In .NET Framework, the <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> property was set to `Microsoft Sans Serif 8 pt`.</span></span> <span data-ttu-id="34385-104">La figura seguente mostra una finestra che usa il tipo di carattere predefinito.</span><span class="sxs-lookup"><span data-stu-id="34385-104">The following image shows a window that uses the default font.</span></span>

![Tipo di carattere del controllo predefinito in .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

<span data-ttu-id="34385-106">A partire da .NET Core 3,0, il tipo di carattere predefinito è impostato su `Segoe UI 9 pt` (lo stesso tipo di carattere di <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType> ).</span><span class="sxs-lookup"><span data-stu-id="34385-106">Starting in .NET Core 3.0, the default font is set to `Segoe UI 9 pt` (the same font as <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span></span> <span data-ttu-id="34385-107">In seguito a questa modifica, i form e i controlli vengono ridimensionati circa il 27% più grande per tenere conto della dimensione maggiore del nuovo tipo di carattere predefinito.</span><span class="sxs-lookup"><span data-stu-id="34385-107">As a result of this change, forms and controls are sized about 27% larger to account for the larger size of the new default font.</span></span> <span data-ttu-id="34385-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="34385-108">For example:</span></span>

![Tipo di carattere del controllo predefinito in .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

<span data-ttu-id="34385-110">Questa modifica è stata apportata per allinearsi alle [linee guida sull'esperienza utente di Windows](/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span><span class="sxs-lookup"><span data-stu-id="34385-110">This change was made to align with [Windows user experience (UX) guidelines](/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="34385-111">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="34385-111">Version introduced</span></span>

<span data-ttu-id="34385-112">3.0</span><span class="sxs-lookup"><span data-stu-id="34385-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="34385-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="34385-113">Recommended action</span></span>

<span data-ttu-id="34385-114">A causa della modifica delle dimensioni dei form e dei controlli, assicurarsi che l'applicazione venga correttamente sottoposta a rendering.</span><span class="sxs-lookup"><span data-stu-id="34385-114">Because of the change in the size of forms and controls, ensure that your application renders correctly.</span></span>

<span data-ttu-id="34385-115">Per mantenere il tipo di carattere originale, impostare il tipo di carattere predefinito del form su `Microsoft Sans Serif 8 pt` .</span><span class="sxs-lookup"><span data-stu-id="34385-115">To retain the original font, set your form's default font to `Microsoft Sans Serif 8 pt`.</span></span> <span data-ttu-id="34385-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="34385-116">For example:</span></span>

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a><span data-ttu-id="34385-117">Category</span><span class="sxs-lookup"><span data-stu-id="34385-117">Category</span></span>

- <span data-ttu-id="34385-118">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34385-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="34385-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="34385-119">Affected APIs</span></span>

<span data-ttu-id="34385-120">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="34385-120">None.</span></span>

<!--

#### Affected APIs

- Not detectable via API analysis

-->
