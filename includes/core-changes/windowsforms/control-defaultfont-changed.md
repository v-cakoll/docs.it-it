---
ms.openlocfilehash: 02dbf5ccca97f5e7d2e1fada39bdf601cf37906f
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119359"
---
### <a name="controldefaultfont-changed-to-segoe-ui-9pt"></a>`Control.DefaultFont`modificato in`Segoe UI 9pt` 

#### <a name="change-description"></a>Descrizione della modifica

Nella .NET Framework la <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> proprietà è stata impostata su `Microsoft Sans Serif 8pt`. Nella figura seguente è illustrata una finestra che utilizza il tipo di carattere predefinito.

![tipo di carattere del controllo predefinito in .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

In .NET Core, a partire da .NET Core 3,0, viene impostato `Segoe UI 9pt` su (lo stesso tipo <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>di carattere di). In seguito a questa modifica, i form e i controlli verranno ridimensionati circa il 27% più grande per tenere conto della dimensione maggiore del nuovo tipo di carattere predefinito. Ad esempio:

![tipo di carattere del controllo predefinito-in .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

Questa modifica è stata apportata per allinearsi alle [linee guida di Windows UX](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

A causa della modifica delle dimensioni dei form e dei controlli, assicurarsi che l'applicazione venga correttamente sottoposta a rendering.

Per mantenere il tipo di carattere originale, impostare il tipo di carattere `Microsoft Sans Serif 8pt`predefinito del form su. Ad esempio:

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a>Category

- Windows Form

#### <a name="affected-apis"></a>API interessate

Nessuno.

<!--

### Affected APIs

- Not detectable via API analysis

-->