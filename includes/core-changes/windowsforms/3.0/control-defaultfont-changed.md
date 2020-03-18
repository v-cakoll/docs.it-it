---
ms.openlocfilehash: b0c4e9617677cf95e3a059b57f3d50ddfb072f4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937083"
---
### <a name="default-control-font-changed-to-segoe-ui-9-pt"></a>Tipo di carattere di controllo predefinito modificato in Segoe UI 9 pt

#### <a name="change-description"></a>Descrizione modifica:

In .NET Framework <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> la proprietà `Microsoft Sans Serif 8 pt`è stata impostata su . L'immagine seguente mostra una finestra che utilizza il tipo di carattere predefinito.

![Tipo di carattere del controllo predefinito in .NET Framework](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

A partire da .NET Core 3.0, `Segoe UI 9 pt` il tipo <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>di carattere predefinito è impostato su (lo stesso tipo di carattere di ). Come risultato di questa modifica, i moduli e i controlli vengono dimensionati circa il 27% più grandi per tenere conto delle dimensioni maggiori del nuovo tipo di carattere predefinito. Ad esempio:

![Tipo di carattere del controllo predefinito in .NET CoreDefault control font in .NET Core](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

Questa modifica è stata apportata per allinearsi alle [linee guida dell'esperienza utente di Windows.](/windows/win32/uxguide/vis-fonts#fonts-and-colors)

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

A causa della modifica delle dimensioni di form e controlli, assicurarsi che il rendering dell'applicazione venga eseguito correttamente.

Per mantenere il tipo di carattere originale, impostare il tipo di carattere predefinito del modulo su `Microsoft Sans Serif 8 pt`. Ad esempio:

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

No.

<!--

### Affected APIs

- Not detectable via API analysis

-->
