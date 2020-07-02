---
ms.openlocfilehash: 97299ddb9bee89c792ddb3d2b9c37516180996f7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614882"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a>La proprietà ContextMenuStrip.SourceControl contiene un controllo valido in caso di ToolStripMenuItems annidati

#### <a name="details"></a>Dettagli

In .NET Framework 4.7.1 e versioni precedenti, la proprietà <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> restituisce erroneamente Null quando l'utente apre il menu da controlli <xref:System.Windows.Forms.ToolStripMenuItem> annidati. In .NET Framework 4.7.2 e versioni successive, la proprietà <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> è sempre impostata sul controllo del codice sorgente effettivo.

#### <a name="suggestion"></a>Suggerimento

**Come acconsentire esplicitamente o escludere queste modifiche** Affinché un'applicazione tragga vantaggio da queste modifiche, è necessario che venga eseguita nel .NET Framework 4.7.2 o versione successiva. L'applicazione può trarre vantaggio da queste modifiche in uno dei modi seguenti:

- È destinata a .NET Framework 4.7.2. Questa modifica è abilitata per impostazione predefinita nelle applicazioni Windows Forms che usano .NET Framework 4.7.2 o versione successiva.
- È destinata a .NET Framework 4.7.1 o versione precedente e rifiuta esplicitamente i comportamenti di accessibilità legacy aggiungendo l'[opzione AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) seguente alla sezione `<runtime>` del file app.config e impostandola su `false`, come illustrato nell'esempio seguente.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false"/>
</runtime>
```

Le applicazioni destinate a .NET Framework 4.7.2 o versione successiva e che vogliono mantenere il comportamento legacy possono acconsentire esplicitamente all'uso del valore del controllo del codice sorgente legacy impostando in modo esplicito questa opzione AppContext su `true`.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7.2       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>
