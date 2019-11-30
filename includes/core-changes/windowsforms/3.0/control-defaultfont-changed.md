---
ms.openlocfilehash: 843007ac6467584fbe6350b6ea19ef67609d73e2
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643949"
---
### <a name="controldefaultfont-changed-to-segoe-ui-9pt"></a>`Control.DefaultFont` modificato in `Segoe UI 9pt`

#### <a name="change-description"></a>Descrizione della modifica

Nella .NET Framework la proprietà <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> è stata impostata su `Microsoft Sans Serif 8pt`. Nella figura seguente è illustrata una finestra che utilizza il tipo di carattere predefinito.

![tipo di carattere del controllo predefinito in .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

In .NET Core, a partire da .NET Core 3,0, è impostato su `Segoe UI 9pt` (lo stesso tipo di carattere <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>). In seguito a questa modifica, i form e i controlli verranno ridimensionati circa il 27% più grande per tenere conto della dimensione maggiore del nuovo tipo di carattere predefinito. Ad esempio:

![tipo di carattere del controllo predefinito-in .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

Questa modifica è stata apportata per allinearsi alle [linee guida di Windows UX](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

A causa della modifica delle dimensioni dei form e dei controlli, assicurarsi che l'applicazione venga correttamente sottoposta a rendering.

Per mantenere il tipo di carattere originale, impostare il tipo di carattere predefinito del modulo su `Microsoft Sans Serif 8pt`. Ad esempio:

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

nessuna.

<!--

### Affected APIs

- Not detectable via API analysis

-->
