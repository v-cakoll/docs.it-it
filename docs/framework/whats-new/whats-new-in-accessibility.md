---
title: Nuove funzionalità di accessibilità in .NET Framework
ms.custom: updateeachrelease
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
ms.openlocfilehash: 4243599f44749e7b38ebe78ca88b8ec2a9390650
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249721"
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>Nuove funzionalità di accessibilità in .NET Framework

Uno degli obiettivi di .NET Framework è rendere le applicazioni più accessibili per gli utenti. Le funzionalità di accessibilità consentono a un'applicazione di offrire un'esperienza appropriata per gli utenti di assistive technology. A partire da .NET Framework 4.7.1, .NET Framework include numerosi miglioramenti per l'accessibilità che consentono agli sviluppatori di creare applicazioni accessibili.

## <a name="accessibility-switches"></a>Opzioni di accessibilità

È possibile configurare l'app per acconsentire esplicitamente alle funzionalità di accessibilità se l'app è destinata a .NET Framework 4.7 o a una versione precedente, ma viene eseguita in .NET Framework 4.7.1 o versione successiva. È anche possibile configurare l'app per usare le funzionalità legacy (e rinunciare alle funzionalità di accessibilità) se l'app è destinata a .NET Framework 4.7.1 o versioni successive. Ogni versione del .NET Framework che include funzionalità di accessibilità ha un'opzione di accessibilità specifica della versione, che è possibile aggiungere all' [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento nella [`<runtime>`](../configure-apps/file-schema/runtime/index.md) sezione del file di configurazione dell'applicazione. Le opzioni supportate sono le seguenti:

|Version|Opzione|
|---|---|
|.NET Framework 4.7.1|"Switch.UseLegacyAccessibilityFeatures"|
|.NET Framework 4.7.2|"Switch.UseLegacyAccessibilityFeatures.2"|
|.NET Framework 4.8|"Switch.UseLegacyAccessibilityFeatures.3"|

### <a name="taking-advantage-of-accessibility-enhancements"></a>Sfruttare i vantaggi dei miglioramenti all'accessibilità

Le nuove funzionalità di accessibilità sono abilitate per impostazione predefinita per le applicazioni destinate a .NET Framework 4.7.1 o versioni successive. Inoltre, le applicazioni destinate a una versione precedente del .NET Framework ma sono in esecuzione in .NET Framework 4.7.1 o versioni successive possono rifiutare esplicitamente i comportamenti di accessibilità legacy (e quindi sfruttare i miglioramenti dell'accessibilità) aggiungendo opzioni all' [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento nella [`<runtime>`](../configure-apps/file-schema/runtime/index.md) sezione del file di configurazione dell'applicazione e impostando il relativo valore su `false` . Di seguito viene illustrato come acconsentire esplicitamente ai miglioramenti apportati all'accessibilità introdotti in .NET Framework 4.7.1:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

Se si sceglie di acconsentire esplicitamente alle funzionalità di accessibilità in una versione successiva di .NET Framework, è necessario anche acconsentire esplicitamente alle funzionalità di versioni precedenti di .NET Framework. La configurazione dell'app per sfruttare i miglioramenti dell'accessibilità in .NET Framework 4.7.1 e 4.7.2 richiede l' [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento seguente:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

La configurazione dell'app per sfruttare i miglioramenti dell'accessibilità in .NET Framework 4.7.1, 4.7.2 e 4,8 richiede l' [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento seguente:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a>Ripristino del comportamento legacy

Le applicazioni destinate alle versioni del .NET Framework a partire da 4.7.1 possono disabilitare le funzionalità di accessibilità aggiungendo opzioni all' [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) elemento nella [`<runtime>`](../configure-apps/file-schema/runtime/index.md) sezione del file di configurazione dell'applicazione e impostando il relativo valore su `true` . Ad esempio, la configurazione seguente rifiuta esplicitamente le funzionalità di accessibilità introdotte in .NET Framework 4.7.2:

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-net-framework-48"></a>Nuove funzionalità di accessibilità in .NET Framework 4.8

.NET Framework 4.8 include nuove funzionalità di accessibilità nelle aree seguenti:

- [Windows Forms](#winforms48)

- [Windows Presentation Foundation (WPF)](#wpf48)

- [Progettazione flussi di lavoro di Windows Workflow Foundation (WF)](#wf48)

<a name="winforms48" />

### <a name="windows-forms"></a>Windows Forms

In .NET Framework 4.8 Windows Forms aggiunge il supporto per le aree dinamiche e gli eventi di notifica a numerosi controlli usati di frequente. Aggiunge anche il supporto per le descrizioni comando quando l'utente passa a un controllo usando la tastiera.

**Supporto delle aree dinamiche di automazione interfaccia utente nelle etichette e nelle barre di stato**

Le aree dinamiche di automazione interfaccia utente consentono agli sviluppatori di applicazioni di notificare alle utilità per la lettura dello schermo una modifica del testo in un controllo che si trova in un'altra posizione rispetto alla posizione attuale dell'utente. Questa funzionalità è utile ad esempio per i controlli <xref:System.Windows.Forms.StatusStrip> che visualizzano lo stato di una connessione. Se la connessione viene interrotta e lo stato viene modificato, è possibile che lo sviluppatore voglia inviare una notifica all'utilità per la lettura dello schermo.

A partire da .NET Framework 4.8, Windows Forms implementa le aree dinamiche di automazione interfaccia utente per entrambi i controlli <xref:System.Windows.Forms.Label> e <xref:System.Windows.Forms.StatusStrip>. Ad esempio, il codice seguente usa l'area dinamica in un controllo <xref:System.Windows.Forms.Label> denominato `label1`:

```csharp
public Form1()
{
   InitializeComponent();
   label1.AutomationLiveSetting = AutomationLiveSetting.Polite;
}

…
Label1.Text = “Ready!”;
```

L'Assistente vocale annuncia "Pronto" indipendentemente dalla posizione in cui l'utente interagisce con l'applicazione.

È anche possibile implementare <xref:System.Windows.Forms.UserControl> come area dinamica:

```csharp
using System;
using System.Windows.Forms;
using System.Windows.Forms.Automation;

namespace WindowsFormsApplication
{
   public partial class UserControl1 : UserControl, IAutomationLiveRegion
   {
      public UserControl1()
      {
         InitializeComponent();
      }

      public AutomationLiveSetting AutomationLiveSetting { get; set; }
      private AutomationLiveSetting IAutomationLiveRegion.GetLiveSetting()
      {
         return this.AutomationLiveSetting;
      }

      protected override void OnTextChanged(EventArgs e)
      {
         base.OnTextChanged(e);
         AutomationNotifications.UiaRaiseLiveRegionChangedEvent(this.AccessibilityObject);
      }
   }
}
```

**Eventi di notifica di automazione interfaccia utente**

L'evento di notifica di automazione interfaccia utente, introdotto in Windows 10 Fall Creators Update, consente all'app di generare un evento di automazione interfaccia utente in modo che l'Assistente vocale emetta un annuncio in base al testo immesso con l'evento anche senza un controllo corrispondente nell'interfaccia utente. In alcuni scenari questo è un modo semplice per migliorare notevolmente l'accessibilità dell'app. Può essere utile anche notificare lo stato di avanzamento di un processo che potrebbe richiedere molto tempo. Per altre informazioni sugli eventi di notifica di automazione interfaccia utente, vedere [Can your desktop app leverage the new UI Notification event?](https://docs.microsoft.com/archive/blogs/winuiautomation/can-your-desktop-app-leverage-the-new-uia-notification-event-in-order-to-have-narrator-say-exactly-what-your-customers-need) (L'app desktop può usare il nuovo evento di notifica dell'interfaccia utente?).

L'esempio seguente genera l'[evento di notifica](xref:System.Windows.Forms.AccessibleObject.RaiseAutomationNotification%2A):

```csharp
MethodInfo raiseMethod = typeof(AccessibleObject).GetMethod("RaiseAutomationNotification");
if (raiseMethod != null) {
   raiseMethod.Invoke(progressBar1.AccessibilityObject, new object[3] {/*Other*/ 4, /*All*/ 2, "The progress is 50%." });
}
```

**Descrizioni comando nell'accesso da tastiera**

Nelle applicazioni destinate a .NET Framework 4.7.2 e versioni precedenti un controllo [descrizione comando](xref:System.Windows.Forms.ToolTip) può essere attivato e visualizzato spostando il puntatore del mouse sul controllo. A partire da .NET Framework 4.8 un utente della tastiera può attivare la descrizione comando del controllo evidenziando il controllo tramite il tasto TAB o i tasti di direzione con o senza tasti di modifica. Questo specifico miglioramento dell'accessibilità richiede un'[opzione AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) aggiuntiva:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1"/>
   </startup>
   <runtime>
      <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false  -->
      <!-- Please note that disabling Switch.UseLegacyAccessibilityFeatures, Switch.UseLegacyAccessibilityFeatures.2 and Switch.UseLegacyAccessibilityFeatures.3 is required to disable Switch.System.Windows.Forms.UseLegacyToolTipDisplay -->
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.System.Windows.Forms.UseLegacyToolTipDisplay=false"/>
   </runtime>
</configuration>
```

La figura seguente mostra la descrizione comando visualizzata quando l'utente seleziona un pulsante con la tastiera.

![Screenshot della descrizione comando quando l'utente passa al pulsante con la tastiera.](./media/whats-new-in-accessibility/select-tooltip-with-keyboard.png)

<a name="wpf48" />

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

A partire da .NET Framework 4.8, WPF include una serie di miglioramenti dell'accessibilità.

**Gli assistenti vocali dello schermo non annunciano più gli elementi con visibilità Compresso o Nascosto**

Gli elementi con visibilità Compresso o Nascosto non sono più annunciati dalle utilità per la lettura dello schermo. Le interfacce utente che contengono elementi con visibilità <xref:System.Windows.Visibility.Collapsed?displayProperty=nameWithType> o <xref:System.Windows.Visibility.Hidden?displayProperty=nameWithType> possono essere interpretate erroneamente dalle utilità per la lettura dello schermo se vengono annunciate all'utente. A partire da .NET Framework 4.8, poiché WPF non include più gli elementi compressi o nascosti nella visualizzazione dei controlli dell'albero di automazione interfaccia utente, le utilità per la lettura dello schermo non possono più annunciare questi elementi.

**Proprietà SelectionTextBrush da usare con una selezione testo non basata su Adorner**

In .NET Framework 4.7.2, WPF ha aggiunto la possibilità di disegnare una selezione testo <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.PasswordBox> senza usare il livello Adorner. Il colore primo piano del testo selezionato in questo scenario è determinato da <xref:System.Windows.SystemColors.HighlightTextBrush?displayProperty=nameWithType>.

.NET Framework 4.8 aggiunge una nuova proprietà, `SelectionTextBrush`, che consente agli sviluppatori di selezionare il pennello specifico per il testo selezionato durante l'uso di una selezione testo non basata su Adorner. Questa proprietà funziona solo nei controlli derivati da <xref:System.Windows.Controls.Primitives.TextBoxBase> e nel controllo <xref:System.Windows.Controls.PasswordBox> nelle applicazioni in WPF con una selezione testo non basata su Adorner abilitata. Non funziona nel controllo <xref:System.Windows.Controls.RichTextBox>. Se non è abilitata una selezione testo non basata su Adorner, questa proprietà viene ignorata.

Per usare questa proprietà, è sufficiente aggiungerla al codice XAML e usare il pennello o l'associazione appropriata. La selezione testo risultante è simile alla seguente:

![Screenshot dell'app in esecuzione con le parole Hello World selezionate.](./media/whats-new-in-accessibility/selectiontextbrush-property.png)

È possibile usare insieme le proprietà `SelectionBrush` e `SelectionTextBrush` per generare qualsiasi combinazione di colore primo piano e colore di sfondo che si ritiene appropriata.

**Supporto per la proprietà ControllerFor di automazione interfaccia utente**

La proprietà `ControllerFor` di automazione interfaccia utente restituisce una matrice di elementi di automazione che vengono modificati dall'elemento di automazione che supporta la proprietà. Questa proprietà viene in genere usata per l'accessibilità dei suggerimenti automatici. La proprietà `ControllerFor` viene usata quando un elemento di automazione ha effetto su uno o più segmenti dell'interfaccia utente dell'applicazione e del desktop. In caso contrario, è difficile associare l'impatto del controllo sugli elementi dell'interfaccia utente. Questa funzionalità aggiunge ai controlli la capacità di specificare un valore per la proprietà `ControllerFor`.

.NET Framework 4.8 aggiunge il nuovo metodo virtuale <xref:System.Windows.Automation.Peers.AutomationPeer.GetControlledPeersCore?displayProperty=nameWithType?displayProperty=nameWithType>. Per specificare un valore per la proprietà `ControllerFor`, è sufficiente eseguire l'override del metodo e restituire `List<AutomationPeer>` per i controlli modificati da <xref:System.Windows.Automation.Peers.AutomationPeer>:

```csharp
public class AutoSuggestTextBox: TextBox
{
   protected override AutomationPeer OnCreateAutomationPeer()
   {
      return new AutoSuggestTextBoxAutomationPeer(this);
   }

   public ListBox SuggestionListBox;
}

internal class AutoSuggestTextBoxAutomationPeer : TextBoxAutomationPeer
{
   public AutoSuggestTextBoxAutomationPeer(AutoSuggestTextBox owner) : base(owner)
   {
   }

   protected override List<AutomationPeer> GetControlledPeersCore()
   {
      List<AutomationPeer> controlledPeers = new List<AutomationPeer>();
      AutoSuggestTextBox owner = Owner as AutoSuggestTextBox;
      controlledPeers.Add(UIElementAutomationPeer.CreatePeerForElement(owner.SuggestionListBox));
      return controlledPeers;
   }
}
```

**Descrizioni comando per l'accesso tramite tastiera**

In .NET Framework 4.7.2 e versioni precedenti le descrizioni comando vengono visualizzate solo quando l'utente posiziona il cursore del mouse su un controllo. In .NET Framework 4.8 le descrizioni comando vengono visualizzate anche con lo stato attivo della tastiera e tramite un tasto di scelta rapida.

Per abilitare questa funzionalità, è necessario che l'applicazione sia destinata a .NET Framework 4.8 o venga abilitata esplicitamente tramite le opzioni  [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)`Switch.UseLegacyAccessibilityFeatures.3` e `Switch.UseLegacyToolTipDisplay`. Di seguito è riportato un file di configurazione dell'applicazione di esempio:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
   </startup>
   <runtime>
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false;Switch.UseLegacyToolTipDisplay=false" />
   </runtime>
</configuration>
```

Dopo l'abilitazione, tutti i controlli che contengono una descrizione comando visualizzano la descrizione quando il controllo ottiene lo stato attivo della tastiera. La descrizione comando può essere nascosta dopo un determinato periodo di tempo o quando viene modificato lo stato attivo della tastiera. Gli utenti possono anche nascondere la descrizione comando manualmente usando i nuovi tasti di scelta rapida CTRL+MAIUSC+F10. Dopo aver nascosto la descrizione comando è possibile visualizzarla nuovamente usando gli stessi tasti di scelta rapida.

> [!NOTE]
> Le [descrizioni comando della barra multifunzione](xref:System.Windows.Controls.Ribbon.RibbonToolTip) nei controlli <xref:System.Windows.Controls.Ribbon.Ribbon> non verranno visualizzate nello stato attivo della tastiera, ma soltanto tramite i tasti di scelta rapida.

**Aggiunta del supporto per le proprietà di automazione interfaccia utente SizeOfSet e PositionInSet**

In Windows 10 sono state introdotte due nuove proprietà di automazione interfaccia utente, `SizeOfSet` e `PositionInSet`, che vengono usate dalle applicazioni per descrivere il conteggio degli elementi in un set. Le applicazioni client di automazione interfaccia utente, ad esempio le utilità per la lettura dello schermo, possono quindi ricercare queste proprietà in un'applicazione e annunciare una rappresentazione accurata dell'interfaccia utente dell'applicazione.

A partire da .NET Framework 4.8, WPF espone queste due proprietà per l'automazione interfaccia utente nelle applicazioni WPF. Questa operazione può essere eseguita in due modi:

- Usando le proprietà di dipendenza.

  WPF aggiunge due nuove proprietà di dipendenza, <xref:System.Windows.Automation.AutomationProperties.SizeOfSet?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationProperties.PositionInSet?displayProperty=nameWithType>. Gli sviluppatori possono impostarne i valori usando XAML:

  ```xaml
  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="1">Button 1</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="2">Button 2</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="3">Button 3</Button>
  ```

- Eseguendo l'override di metodi virtuali di AutomationPeer.

  I metodi virtuali <xref:System.Windows.Automation.Peers.AutomationPeer.GetSizeOfSetCore> e <xref:System.Windows.Automation.Peers.AutomationPeer.GetPositionInSetCore> sono stati aggiunti alla classe AutomationPeer. Gli sviluppatori possono specificare i valori di `SizeOfSet` e `PositionInSet` eseguendo l'override di questi metodi, come illustrato nell'esempio seguente:

  ```csharp
  public class MyButtonAutomationPeer : ButtonAutomationPeer
  {
    protected override int GetSizeOfSetCore()
    {
        // Call into your own logic to provide a value for SizeOfSet
        return CalculateSizeOfSet();
    }

    protected override int GetPositionInSetCore()
    {
        // Call into your own logic to provide a value for PositionInSet
        return CalculatePositionInSet();
    }
  }
  ```

Inoltre, gli elementi nelle istanze <xref:System.Windows.Controls.ItemsControl> specificano automaticamente un valore per queste proprietà senza ulteriori azioni da parte dello sviluppatore. Se <xref:System.Windows.Controls.ItemsControl> è raggruppato, la raccolta di gruppi è rappresentata come set e ogni gruppo viene conteggiato come set separato in cui ogni elemento all'interno del gruppo specifica la propria posizione all'interno del gruppo e le dimensioni del gruppo. La virtualizzazione non ha effetto sui valori automatici. Anche se un elemento non è realizzato, viene comunque conteggiato nelle dimensioni totali del set e influisce sulla posizione dei relativi elementi di pari livello nel set.

I valori automatici vengono forniti solo se l'applicazione è destinata a .NET Framework 4.8. Per le applicazioni destinate a una versione precedente di .NET Framework, è possibile impostare l' [opzione AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)`Switch.UseLegacyAccessibilityFeatures.3`, come illustrato nel file App.config seguente:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
   </startup>
   <runtime>
      <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
   </runtime>
</configuration>
```

<a name="wf48" />

### <a name="windows-workflow-foundation-wf-workflow-designer"></a>Progettazione dei flussi di lavoro di Windows Workflow Foundation (WF)

La finestra di progettazione dei flussi di lavoro include le modifiche seguenti in .NET Framework 4.8:

- Gli utenti che usano l'Assistente vocale noteranno miglioramenti nelle etichette case FlowSwitch.

- Gli utenti che usano l'Assistente vocale noteranno miglioramenti nelle descrizioni dei pulsanti.

- Gli utenti che usano i temi a contrasto elevato noteranno miglioramenti nella visibilità di Progettazione flussi di lavoro e nei relativi controlli, ad esempio rapporti di contrasto più definiti tra gli elementi e caselle di selezione più evidenti per gli elementi con lo stato attivo.

Se l'applicazione è destinata a .NET Framework 4.7.2 o versione precedente, è possibile scegliere esplicitamente queste modifiche impostando l' [opzione AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)`Switch.UseLegacyAccessibilityFeatures.3` su `false` nel file di configurazione dell'applicazione. Per altre informazioni, vedere la sezione [Sfruttare i vantaggi dei miglioramenti all'accessibilità](#taking-advantage-of-accessibility-enhancements) in questo articolo.

## <a name="whats-new-in-accessibility-in-net-framework-472"></a>Nuove funzionalità di accessibilità in .NET Framework 4.7.2

.NET Framework 4.7.2 include nuove funzionalità di accessibilità nelle aree seguenti:

- [Windows Forms](#winforms472)

- [Windows Presentation Foundation (WPF)](#wpf472)

<a name="winforms472"></a>

### <a name="windows-forms"></a>Windows Forms

**Colori definiti dal sistema operativo nei temi a contrasto elevato**

A partire da .NET Framework 4.7.2, Windows Forms usa colori definiti dal sistema operativo dei temi di contrasto elevato. Ciò influisce sui controlli seguenti:

- La freccia a discesa del controllo <xref:System.Windows.Forms.ToolStripDropDownButton>.

- I controlli <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> e <xref:System.Windows.Forms.CheckBox> con <xref:System.Windows.Forms.ButtonBase.FlatStyle> impostato su <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> o <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>. In precedenza, i colori dello sfondo e del testo selezionato non erano in contrasto e risultavano di difficile lettura.

- I controlli contenuti in un oggetto <xref:System.Windows.Forms.GroupBox> con la proprietà relativa <xref:System.Windows.Forms.Control.Enabled> impostata su `false`.

- I controlli <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> e <xref:System.Windows.Forms.ToolStripDropDownButton> che hanno un maggiore rapporto del contrasto di luminosità nella modalità a contrasto elevato.

- La proprietà <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> di <xref:System.Windows.Forms.DataGridViewLinkCell>.

**Miglioramenti di Assistente vocale**

A partire da .NET Framework 4.7.2, il supporto dell'Assistente vocale è stato migliorato come segue:

- Annuncia il valore della proprietà <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> mentre annuncia il testo di una classe <xref:System.Windows.Forms.ToolStripMenuItem>.

- Indica quando una classe <xref:System.Windows.Forms.ToolStripMenuItem> ha la proprietà <xref:System.Windows.Forms.Control.Enabled> impostata su `false`.

- Offre un feedback sullo stato di una casella di controllo quando la proprietà <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> è impostata su `true`.

- L'ordine di attivazione nella modalità di analisi dell'Assistente vocale rispetta l'ordine degli oggetti visivi dei controlli nella finestra di dialogo di download ClickOnce.

**Miglioramenti apportati a DataGridView**

A partire da .NET Framework 4.7.2, il controllo <xref:System.Windows.Forms.DataGridView> ha introdotto i miglioramenti di accessibilità seguenti:

- Le righe possono essere ordinate usando la tastiera. È possibile usare F3 per ordinare in base alla colonna corrente.

- Quando la proprietà <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, l'intestazione di colonna cambia colore per indicare la colonna corrente man mano che l'utente si sposta tra le celle nella riga corrente tramite tabulazione.

- La proprietà <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> di un oggetto <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> restituisce il controllo padre corretto.

**Suggerimenti visivi migliorati**

- I controlli <xref:System.Windows.Forms.RadioButton> e <xref:System.Windows.Forms.CheckBox> con proprietà <xref:System.Windows.Forms.ButtonBase.Text> vuota visualizzano un indicatore di stato attivo quando ricevono lo stato attivo.

**Supporto migliorato per PropertyGrid**

- Gli elementi figlio del controllo <xref:System.Windows.Forms.PropertyGrid> ora restituiscono `true` per la proprietà <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> solo quando è abilitato un elemento PropertyGrid.

- Gli elementi figlio del controllo <xref:System.Windows.Forms.PropertyGrid> restituiscono `false` per la proprietà <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> solo quando un elemento PropertyGrid può essere modificato dall'utente.

**Navigazione tramite tastiera migliorata**

- Il controllo <xref:System.Windows.Forms.ToolStripButton> consente lo stato attivo quando è contenuto all'interno di una classe <xref:System.Windows.Forms.ToolStripPanel> con la proprietà <xref:System.Windows.Forms.ToolStripPanel.TabStop> impostata su `true`

<a name="wpf472"></a>

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Modifiche ai controlli CheckBox e RadioButton**

In .NET Framework 4.7.1 e versioni precedenti i controlli <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> e <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> di WPF contengono oggetti visivi dello stato attivo incoerenti e non corretti nei temi classico e a contrasto elevato.  Questi problemi si verificano se i controlli non hanno impostato un contenuto.  La transizione tra i temi può risultare quindi confusa e diventa difficile visualizzare l'oggetto visivo con stato attivo.

In .NET Framework 4.7.2 questi oggetti visivi sono più coerenti tra i temi e possono essere visualizzati più facilmente nei temi classico e a contrasto elevato.

**Controlli WinForms ospitati in un'applicazione WPF**

Nel caso di un controllo WinForms ospitato in un'applicazione WPF in .NET Framework 4.7.1 e versioni precedenti, gli utenti non potevano uscire dal livello WinForms se il primo o l'ultimo controllo nel livello era il controllo <xref:System.Windows.Forms.Integration.ElementHost> di WPF. In .NET Framework 4.7.2 gli utenti possono uscire dal livello di WinForms.

Tuttavia, le applicazioni automatiche che si basano sullo stato attivo che non esce mai dal livello di WinForms potrebbero non funzionare più come previsto.

## <a name="whats-new-in-accessibility-in-net-framework-471"></a>Nuove funzionalità di accessibilità in .NET Framework 4.7.1

.NET Framework 4.7.1 include nuove funzionalità di accessibilità nelle aree seguenti:

- [Windows Presentation Foundation (WPF)](#wpf471)

- [Windows Forms](#winforms471)

- [Controlli Web ASP.NET](#aspnet471)

- [Strumenti .NET SDK](#tools471)

- [Progettazione flussi di lavoro Windows Workflow Foundation (WF)](#wf471)

<a name="wpf471"></a>

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Miglioramenti per le utilità per la lettura dello schermo**

Se sono abilitati i miglioramenti per l'accessibilità, .NET Framework 4.7.1 include i miglioramenti seguenti che riguardano le utilità per la lettura dello schermo:

- In .NET Framework 4.7 e versioni precedenti i controlli <xref:System.Windows.Controls.Expander> vengono annunciati come pulsanti dalle utilità per la lettura dello schermo. A partire da .NET Framework 4.7.1, sono annunciati correttamente come gruppi espandibili/comprimibili.

- In .NET Framework 4.7 e versioni precedenti i controlli <xref:System.Windows.Controls.DataGridCell> vengono annunciati come "personalizzati" dalle utilità per la lettura dello schermo. A partire da .NET Framework 4.7.1, sono annunciati correttamente come cella di griglia dati (localizzati).

- A partire da .NET Framework 4.7.1, le utilità per la lettura dello schermo annunciano il nome di un controllo <xref:System.Windows.Controls.ComboBox> modificabile.

- In .NET Framework 4.7 e versioni precedenti i controlli <xref:System.Windows.Controls.PasswordBox> vengono annunciati come "Nessun elemento visualizzato" o il comportamento è in altro modo non corretto. Questo problema è stato risolto a partire da .NET Framework 4.7.1.

**Supporto di aree dinamiche UIAutomation**

Le utilità per la lettura dello schermo, come Assistente vocale, consentono di leggere il contenuto dell'interfaccia utente di un'applicazione, in genere annunciando tramite sintesi vocale il contenuto dell'interfaccia utente con lo stato attivo. Tuttavia, se un elemento dell'interfaccia utente viene modificato e non ha lo stato attivo, l'utente potrebbe non ricevere notifica e perdere informazioni importanti. Le aree dinamiche sono progettate per risolvere questo problema. Uno sviluppatore può usarle per informare l'utilità per la lettura dello schermo o qualsiasi altro client UIAutomation di un'importante modifica apportata a un elemento dell'interfaccia utente. L'utilità per la lettura dello schermo può quindi decidere come e quando informare l'utente di questa modifica.

Per supportare le aree dinamiche sono state aggiunte le API seguenti a WPF:

- I campi <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> che identificano la proprietà **LiveSetting** e l'evento **LiveRegionChanged**. Questi campi possono essere impostati tramite XAML.

- La proprietà associata **AutomationProperties.LiveSetting**, che segnala all'utilità per la lettura dello schermo l'importanza della modifica dell'interfaccia utente per l'utente.

- La proprietà <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>, che identifica la proprietà associata **AutomationProperties.LiveSetting**.

- Il metodo <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>, di cui è possibile eseguire l'override per specificare un valore **LiveSetting**.

- I metodi <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>, che consentono di ottenere e impostare un valore **LiveSetting**.

- L'enumerazione <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>, che definisce le i valori **LiveSetting** possibili seguenti:

  - <xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>. L'elemento non invia notifiche se il contenuto dell'area dinamica è stato modificato.
  - <xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>. L'elemento invia notifiche che non causano interruzioni se il contenuto dell'area dinamica è stato modificato.

  - <xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>. L'elemento invia notifiche con interruzioni se il contenuto dell'area dinamica è stato modificato.

È possibile creare un'area dinamica impostando la proprietà **AutomationProperties.LiveSetting** sull'elemento di interesse, come illustrato nell'esempio seguente:

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

Quando vengono modificati i dati nell'area dinamica ed è necessario informarne un'utilità per la lettura dello schermo, deve essere generato un evento in modo esplicito, come illustrato nell'esempio seguente.

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```

```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

**High contrast**

A partire da .NET Framework 4.7.1, sono stati apportati miglioramenti relativi al contrasto elevato per vari controlli WPF, che sono ora visibili quando viene impostato il tema <xref:System.Windows.SystemParameters.HighContrast%2A>. incluse le seguenti:

- Controllo <xref:System.Windows.Controls.Expander>

  L'oggetto visivo per lo stato attivo per il controllo <xref:System.Windows.Controls.Expander> è ora visibile. Anche gli oggetti visivi della tastiera per i controlli <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.RadioButton> sono visibili. Ad esempio:

  Prima di:

  ![Screenshot del controllo Expander con lo stato attivo e nessun oggetto visivo dello stato attivo.](./media/whats-new-in-accessibility/expander-control-before.png)

  Dopo:

  ![Screenshot del controllo Expander con lo stato attivo che mostra una linea tratteggiata intorno al testo del controllo.](./media/whats-new-in-accessibility/expander-control-after.png)

- Controlli <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.RadioButton>

  Il testo nei controlli <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.RadioButton> è ora più semplice da vedere quando viene selezionato nei temi a contrasto elevato. Ad esempio:

  Prima di:

  ![Screenshot dei pulsanti di opzione e controllo con visibilità del testo insufficiente sui temi a contrasto elevato.](./media/whats-new-in-accessibility/high-contrast-radio-button-before.png)

  Dopo:

  ![Screenshot dei pulsanti di opzione e controllo con visibilità del testo migliore sui temi a contrasto elevato.](./media/whats-new-in-accessibility/high-contrast-radio-button-after.png)

- Controllo <xref:System.Windows.Controls.ComboBox>

  A partire da .NET Framework 4.7.1, il bordo di un controllo <xref:System.Windows.Controls.ComboBox> disabilitato ha lo stesso colore del testo disabilitato. Ad esempio:

  Prima di:

  ![Screenshot di un controllo ComboBox disabilitato con il testo del bordo e del controllo in colori diversi.](./media/whats-new-in-accessibility/combo-disabled-before.png)

  Dopo:

  ![Screenshot di un controllo ComboBox disabilitato con bordo con lo stesso colore del testo del controllo.](./media/whats-new-in-accessibility/combo-disabled-after.png)

  Inoltre, i pulsanti con lo stato attivo e disabilitati usano il colore del tema corretto.

  Prima di:

  ![Screenshot di un pulsante nero con testo grigio che afferma lo stato attivo.](./media/whats-new-in-accessibility/button-theme-colors-before.png)

  Dopo:

  ![Screenshot di un pulsante blu con testo nero che indica lo stato attivo.](./media/whats-new-in-accessibility/button-theme-colors-after.png)

  Infine, in .NET Framework 4.7 e versioni precedenti, l'impostazione dello stile di un controllo <xref:System.Windows.Controls.ComboBox> su `Toolbar.ComboBoxStyleKey` rende invisibile la freccia a discesa. Questo problema è stato risolto a partire da .NET Framework 4.7.1. Ad esempio:

  Prima di:

  ![Screenshot di un controllo ComboBox con una freccia a discesa invisibile.](./media/whats-new-in-accessibility/combo-box-style-key-before.png)

  Dopo:

  ![Screenshot di un controllo ComBoxBox che visualizza la freccia a discesa.](./media/whats-new-in-accessibility/combo-box-style-key-after.png)

- Controllo <xref:System.Windows.Controls.DataGrid>

  A partire da .NET Framework 4.7.1, la freccia dell'indicatore di ordinamento nei controlli <xref:System.Windows.Controls.DataGrid> usa ora i colori del tema corretti. Ad esempio:

  Prima di:

  ![Screenshot della freccia dell'indicatore di ordinamento prima dei miglioramenti.](./media/whats-new-in-accessibility/sort-indicator-before.png)

  Dopo:

  ![Screenshot della freccia dell'indicatore di ordinamento dopo i miglioramenti.](./media/whats-new-in-accessibility/sort-indicator-after.png)

  Inoltre, in .NET Framework 4.7 e versioni precedenti, per lo stile di collegamento predefinito viene usato un colore non corretto al passaggio del mouse in modalità a contrasto elevato. Questo problema è stato risolto a partire da .NET Framework 4.7.1. Analogamente, le colonne della casella di controllo per i controlli <xref:System.Windows.Controls.DataGrid> usano i colori previsti per il riscontro dello stato attivo della tastiera a partire da .NET Framework 4.7.1.

  Prima di:

  ![Screenshot di un collegamento che dice clic su me. in rosso.](./media/whats-new-in-accessibility/default-link-style-before.png)

  Dopo:

  ![Screenshot di un collegamento che dice clic su me. in giallo.](./media/whats-new-in-accessibility/default-link-style-after.png)

Per altre informazioni sui miglioramenti per l'accessibilità di WPF in .NET Framework 4.7.1, vedere [Miglioramenti di accessibilità in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).

<a name="winforms471"></a>

### <a name="windows-forms-accessibility-improvements"></a>Miglioramenti per l'accessibilità di Windows Form

In .NET Framework 4.7.1 Windows Forms (WinForms) include modifiche per l'accessibilità nelle aree seguenti.

**Miglioramento della visualizzazione in modalità a contrasto elevato**

A partire da .NET Framework 4.7.1, vari controlli WinForms offrono un rendering migliorato nelle modalità a contrasto elevato disponibili nel sistema operativo. Windows 10 ha cambiato i valori di alcuni colori di sistema a contrasto elevato e Windows Form si basa sul framework Win32 di Windows 10. Per risultati ottimali, usare la versione più recente di Windows e accettare le modifiche del sistema operativo più recenti aggiungendo un file app.manifest in un'applicazione di test e rimuovere il commento dalla riga del sistema operativo supportato Windows 10, in modo che abbia l'aspetto seguente:

```xml
<!-- Windows 10 -->
<supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
```

Alcuni esempi di modifiche per il contrasto elevato includono:

- I segni di spunta negli elementi <xref:System.Windows.Forms.MenuStrip> sono più facili da visualizzare.

- Gli elementi <xref:System.Windows.Forms.MenuStrip> disabilitati sono più facili da visualizzare quando sono selezionati.

- Il testo in un controllo <xref:System.Windows.Forms.Button> selezionato è contrastato rispetto al colore della selezione.

- Il testo disabilitato è più facile da leggere. Ad esempio:

  Prima di:

  ![Screenshot di un'app che usa diversi controlli eseguiti in modalità a contrasto elevato prima dei miglioramenti dell'accessibilità.](./media/whats-new-in-accessibility/high-contrast-mode-menu-items-before.png)

  Dopo:

  ![Screenshot di un'app che usa diversi controlli eseguiti in modalità a contrasto elevato dopo i miglioramenti dell'accessibilità.](./media/whats-new-in-accessibility/high-contrast-mode-menu-items-after.png)

- Miglioramenti per il contrasto elevato nella finestra di dialogo di eccezione del thread.

**Supporto migliorato di Assistente vocale**

Windows Forms in .NET Framework 4.7.1 include i seguenti miglioramenti per l'accessibilità per l'Assistente vocale:

- Il controllo <xref:System.Windows.Forms.MonthCalendar> è accessibile per l'Assistente vocale, così come da altri strumenti di automazione dell'interfaccia utente.

- Il controllo <xref:System.Windows.Forms.CheckedListBox> segnala all'Assistente vocale lo stato di selezione di un elemento, in modo che l'utente riceva notifica della modifica del valore di un elemento di elenco.

- Il controllo <xref:System.Windows.Forms.DataGridViewCell> segnala lo stato di sola lettura corretto all'Assistente vocale.

- Assistente vocale può ora leggere il testo <xref:System.Windows.Forms.ToolStripMenuItem> disabilitato, mentre in precedenza ignorava le voci di menu disabilitate.

**Supporto avanzato per i modelli di accessibilità UIAutomation**

A partire da .NET Framework 4.7.1, gli sviluppatori di strumenti di tecnologia per l'accessibilità possono sfruttare i modelli e le proprietà di accessibilità delle API comuni per numerosi controlli WinForms. Questi miglioramenti per l'accessibilità includono:

- <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ToolStripSplitButton> ora supportano il [modello di espansione/compressione](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- <xref:System.Windows.Forms.DataGridViewCheckBoxCell> supporta ora il [modello di attivazione/disattivazione](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).

- Il controllo <xref:System.Windows.Forms.ToolStripItem> supporta la proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> e il [modello di espansione/compressione](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).

- I controlli <xref:System.Windows.Forms.NumericUpDown> e <xref:System.Windows.Forms.DomainUpDown> supportano la proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>.

**Esperienza migliorata per il visualizzatore proprietà**

A partire da .NET Framework 4.7.1, Windows Forms include:

- Migliori spostamenti tramite tastiera tra le varie finestre di selezione a discesa.
- Riduzione dei punti di tabulazione non necessari.
- Segnalazione migliore dei tipi di controllo.
- Comportamento migliorato dell'Assistente vocale.

<a name="aspnet471"></a>

### <a name="aspnet-web-controls"></a>Controlli Web ASP.NET

A partire da .NET Framework 4.7.1 e Visual Studio 2017 versione 15,3, ASP.NET migliora il funzionamento dei controlli Web ASP.NET con la tecnologia di accessibilità in Visual Studio. Le modifiche includono quanto segue:

- Modifiche per implementare modelli di accessibilità dell'interfaccia utente mancanti nei controlli, ad esempio la finestra di dialogo **Aggiungi campo** nella creazione guidata **visualizzazione dettagli** o la finestra di dialogo **Configura ListView** della procedura guidata **ListView** .

- Modifiche per migliorare la visualizzazione in modalità Contrasto elevato, ad esempio l' **editor campi del pager di dati**.

- Modifiche per migliorare le esperienze di navigazione da tastiera per i controlli, ad esempio la finestra di dialogo **campi** nella procedura guidata **modifica campi cercapersone** del controllo DataPager, la finestra di dialogo **Configura ObjectContext** o la finestra di dialogo **Configura selezione dati** della **Configurazione guidata origine dati** .

<a name="tools471"></a>

### <a name="net-sdk-tools"></a>Strumenti .NET SDK

Lo [strumento Editor di configurazione (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) e lo [strumento Visualizzatore di tracce (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) sono stati migliorati correggendo vari problemi di accessibilità. Molti erano problemi di lieve entità, come ad esempio un nome non definito o alcuni criteri dell'automazione interfaccia utente non implementati correttamente. È possibile che molti utenti non si siano accorti di questi valori non corretti. I clienti che usano le assistive technology, ad esempio le utilità per la lettura dello schermo, troveranno invece questi strumenti SDK più accessibili.

Tali miglioramenti modificano alcuni comportamenti precedenti, ad esempio l'ordine di attivazione della tastiera.

<a name="wf471"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a>Progettazione flussi di lavoro di Windows Workflow Foundation (WF)

Le modifiche all'accessibilità in Progettazione flussi di lavoro includono quanto segue:

- L'ordine di tabulazione viene modificato da sinistra a destra e dall'alto verso il basso in alcuni controlli:

  - La finestra di inizializzazione della correlazione in cui impostare i dati di correlazione per l'attività <xref:System.ServiceModel.Activities.InitializeCorrelation>.

  - La finestra di definizione del contenuto per le attività <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> e <xref:System.ServiceModel.Activities.ReceiveReply>.

- Altre funzioni sono disponibili tramite tastiera:

  - Quando vengono modificate le proprietà di un'attività, i gruppi delle proprietà possono essere compressi tramite tastiera la prima volta che hanno lo stato attivo.

  - Le icone di avviso sono accessibili dalla tastiera.

  - Il pulsante **Altre proprietà** nella finestra **Proprietà** è accessibile dalla tastiera.

  - Tramite tastiera gli utenti possono accedere agli elementi dell'intestazione nei riquadri **Argomenti** e **Variabili** in Progettazione flussi di lavoro.

- Maggiore visibilità degli elementi con stato attivo, ad esempio quando:

  - Aggiunta di righe alle griglie di dati usate in Progettazione flussi di lavoro e in ActivityDesigner.

  - Tabulazione all'interno dei campi nelle attività <xref:System.ServiceModel.Activities.ReceiveReply> e <xref:System.ServiceModel.Activities.SendReply>.

  - Impostazione di valori predefiniti per variabili o argomenti

- Le utilità per la lettura dello schermo ora possono riconoscere correttamente:

  - Set di punti di interruzione in Progettazione flussi di lavoro.

  - Attività <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> e <xref:System.ServiceModel.Activities.CorrelationScope>.
  - Contenuto dell'attività <xref:System.ServiceModel.Activities.Receive>.

  - Tipo di destinazione per l'attività <xref:System.Activities.Statements.InvokeMethod>.

  - Casella combinata Eccezione e sezione Finally nell'attività <xref:System.Activities.Statements.TryCatch>.

  - Casella combinata Tipo di messaggio, barra di divisione nella finestra Aggiungi inizializzatori di correlazione, finestra Content Definition (Definizione contenuto) e finestra Definizione di CorrelatesOn nelle attività di messaggistica (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> e <xref:System.ServiceModel.Activities.ReceiveReply>).

  - Transizioni della macchina a uno stato e destinazioni delle transazioni.

  - Annotazioni e connettori nelle attività <xref:System.Activities.Statements.FlowDecision>.

  - Menu di scelta rapida per le attività.

  - Editor di valori di proprietà, pulsante Cancella ricerca, pulsanti di ordinamento Per categoria e In ordine alfabetico e finestra di dialogo Editor espressioni nella griglia delle proprietà.

  - Percentuale di zoom in Progettazione flussi di lavoro.

  - Separatore nelle attività <xref:System.Activities.Statements.Parallel> e <xref:System.Activities.Statements.Pick>.

  - Attività <xref:System.Activities.Statements.InvokeDelegate>.

  - Finestra Seleziona tipi per le attività di dizionario (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>` e così via).

  - Finestra Cerca e seleziona un tipo .NET.

  - Navigazioni in Progettazione flussi di lavoro.

- Gli utenti che usano i temi a contrasto elevato noteranno molti miglioramenti nella visibilità di Progettazione flussi di lavoro e nei relativi controlli, ad esempio rapporti di contrasto più definiti tra gli elementi e caselle di selezione più evidenti per gli elementi con lo stato attivo.

## <a name="see-also"></a>Vedere anche

- [Novità di .NET Framework](index.md)
