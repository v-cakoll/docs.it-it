---
ms.openlocfilehash: b0c4e9617677cf95e3a059b57f3d50ddfb072f4a
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937083"
---
### <a name="default-control-font-changed-to-segoe-ui-9-pt"></a>Il tipo di carattere del controllo predefinito è stato modificato in Segoe UI 9 PT

#### <a name="change-description"></a>Descrizione delle modifiche

In .NET Framework la proprietà <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> è stata impostata su `Microsoft Sans Serif 8 pt`. La figura seguente mostra una finestra che usa il tipo di carattere predefinito.

![Tipo di carattere del controllo predefinito in .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

A partire da .NET Core 3,0, il tipo di carattere predefinito è impostato su `Segoe UI 9 pt` (lo stesso tipo di carattere <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>). In seguito a questa modifica, i form e i controlli vengono ridimensionati circa il 27% più grande per tenere conto della dimensione maggiore del nuovo tipo di carattere predefinito. Ad esempio:

![Tipo di carattere del controllo predefinito in .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

Questa modifica è stata apportata per allinearsi alle [linee guida sull'esperienza utente di Windows](/windows/win32/uxguide/vis-fonts#fonts-and-colors).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

A causa della modifica delle dimensioni dei form e dei controlli, assicurarsi che l'applicazione venga correttamente sottoposta a rendering.

Per mantenere il tipo di carattere originale, impostare il tipo di carattere predefinito del modulo su `Microsoft Sans Serif 8 pt`. Ad esempio:

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a>Categoria

- Windows Form

#### <a name="affected-apis"></a>API interessate

nessuna.

<!--

### Affected APIs

- Not detectable via API analysis

-->
