---
ms.openlocfilehash: cc3c2c2be179842f87be8892d057a6c4138086cb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614873"
---
### <a name="accessibility-improvements-in-windows-forms-controls-for-net-472"></a>Miglioramenti di accessibilità nei controlli Windows Form per .NET 4.7.2

#### <a name="details"></a>Dettagli

In Windows Forms Framework è stato migliorato il funzionamento con le tecnologie di accessibilità per supportare al meglio i clienti Windows Form. Sono incluse le modifiche seguenti:

- Modifiche per migliorare la visualizzazione durante la modalità a contrasto elevato.
- Modifiche per migliorare la navigazione tramite tastiera nei controlli DataGridView e MenuStrip.
- Modifiche all'interazione con l'Assistente vocale.

#### <a name="suggestion"></a>Suggerimento

**Come acconsentire esplicitamente o escludere queste modifiche** Per consentire all'applicazione di trarre vantaggio da queste modifiche, è necessario eseguirla nel .NET Framework 4.7.2 o versione successiva. L'applicazione può trarre vantaggio da queste modifiche in uno dei modi seguenti:

- Viene ricompilata in modo da essere destinata a .NET Framework 4.7.2. Queste modifiche di accessibilità sono abilitate per impostazione predefinita nelle applicazioni Windows Forms che usano .NET Framework 4.7.2 o versione successiva.
- È destinata a .NET Framework 4.7.1 o versione precedente e rifiuta esplicitamente i comportamenti di accessibilità legacy aggiungendo l'[opzione di AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) seguente alla sezione `<runtime>` del file app.config e impostandola su `false`, come illustrato nell'esempio seguente.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7"/>
  </startup>
  <runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
  </runtime>
</configuration>
```

Si noti che per accettare le funzionalità di accessibilità aggiunte in .NET Framework 4.7.2 è anche necessario accettare le funzionalità di accessibilità di .NET Framework 4.7.1. Le applicazioni destinate a .NET Framework 4.7.2 o versioni successive e vogliono mantenere il comportamento di accessibilità legacy possono acconsentire esplicitamente all'uso di funzionalità di accessibilità legacy impostando in modo esplicito questa opzione AppContext su `true` .

**Uso di colori definiti dal sistema operativo nei temi a contrasto elevato**

- La freccia a discesa relativa a <xref:System.Windows.Forms.ToolStripDropDownButton> usa ora i colori definiti dal sistema operativo nel tema Contrasto elevato.
- I controlli <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> e <xref:System.Windows.Forms.CheckBox> con <xref:System.Windows.Forms.ButtonBase.FlatStyle> impostata su <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> o <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType> ora usano i colori definiti dal sistema operativo nel tema a contrasto elevato quando selezionato. In precedenza, i colori di sfondo e testo non erano in contrasto e risultavano di difficile lettura.
- I controlli contenuti in una classe <xref:System.Windows.Forms.GroupBox> con la proprietà <xref:System.Windows.Forms.Control.Enabled> impostata su `false` ora usano i colori definiti dal sistema operativo nel tema a contrasto elevato.
- I controlli <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> e <xref:System.Windows.Forms.ToolStripDropDownButton> hanno un maggiore rapporto del contrasto di luminosità nella modalità a contrasto elevato.
- <xref:System.Windows.Forms.DataGridViewLinkCell> userà per impostazione predefinita i colori definiti del sistema operativo in modalità a contrasto elevato per la proprietà <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor?displayProperty=nameWithType>.
NOTA: in Windows 10 sono stati modificati i valori per alcuni colori di sistema a contrasto elevato. Il framework di Windows Form Framework si basa sul framework Win32. Per un'esperienza ottimale, eseguire nella versione più recente di Windows e acconsentire esplicitamente alle modifiche del sistema operativo più recenti aggiungendo un file app. manifest in un'applicazione di test e annullando il commento del codice seguente:

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

**Supporto migliorato di Assistente vocale**

- L'Assistente vocale ora annuncia il valore della proprietà <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> mentre annuncia il testo di una classe <xref:System.Windows.Forms.ToolStripMenuItem>.
- L'Assistente vocale ora indica quando una classe <xref:System.Windows.Forms.ToolStripMenuItem> ha la proprietà <xref:System.Windows.Forms.Control.Enabled> impostata su `false`.
- L'Assistente vocale ora offre un commento sullo stato di una casella di controllo quando la proprietà <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> è impostata su `true`.
- L'ordine di focus nella modalità di analisi dell'Assistente vocale ora rispetta l'ordine degli oggetti visivi dei controlli nella finestra di dialogo di download ClickOnce.

**Supporto migliorato per l'accessibilità di DataGridView**

- Le righe in una classe <xref:System.Windows.Forms.DataGridView> ora possono essere ordinate usando la tastiera. Ora è possibile usare F3 per ordinare per colonna corrente.
- Quando la proprietà <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, l'intestazione di colonna cambia colore per indicare la colonna corrente man mano che l'utente si sposta tra le celle nella riga corrente tramite tabulazione.
- La proprietà <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Parent?displayProperty=nameWithType> ora restituisce il controllo padre corretto.

**Segnali visivi migliorati**

- I controlli <xref:System.Windows.Forms.RadioButton> e <xref:System.Windows.Forms.CheckBox> con una proprietà <xref:System.Windows.Forms.ButtonBase.Text> vuota ora visualizzano un indicatore di stato attivo quando ricevono lo stato attivo.

**Supporto migliorato per PropertyGrid**

- Gli elementi figlio del controllo <xref:System.Windows.Forms.PropertyGrid> ora restituiscono `true` per la proprietà <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> solo quando è abilitato un elemento PropertyGrid.
- Gli elementi figlio del controllo <xref:System.Windows.Forms.PropertyGrid> ora restituiscono `false` per la proprietà <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> solo quando un elemento PropertyGrid può essere modificato dall'utente.
Per una panoramica dell'automazione interfaccia utente, vedere [Panoramica di automazione interfaccia utente](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview).</p>**Navigazione tramite tastiera migliorata**

- <xref:System.Windows.Forms.ToolStripButton>consente ora lo stato attivo quando è contenuto in un oggetto <xref:System.Windows.Forms.ToolStripPanel> la cui <xref:System.Windows.Forms.ToolStripPanel.TabStop> proprietà è impostata su `true` .

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Principale       |
| Version | 4.7.2       |
| Type    | Ridestinazione |
