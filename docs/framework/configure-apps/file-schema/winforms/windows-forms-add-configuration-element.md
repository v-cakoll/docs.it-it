---
title: Windows Forms Aggiungi elemento di configurazione
ms.date: 04/07/2017
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
ms.openlocfilehash: 26b806f84c3e1bc44e0437a8f8806316b14897b8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73109654"
---
# <a name="windows-forms-add-configuration-element"></a>Windows Forms Aggiungi elemento di configurazione

L' `<add>` elemento aggiunge una chiave predefinita che specifica se l'app Windows Form supporta le funzionalità aggiunte alle app Windows Forms in .NET Framework 4,7 o versione successiva.

## <a name="syntax"></a>Sintassi

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="key-name" value="key-value" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

| Attributo | Descrizione |
| --------- | ----------- |
| `key`     | Attributo obbligatorio. Nome di chiave predefinito che corrisponde a un particolare Windows Forms funzionalità personalizzabile. |
| `value`   | Attributo obbligatorio. Valore da assegnare a `key`. |

### <a name="key-attribute-names-and-associated-values"></a>`key`nomi di attributi e valori associati

| Nome in `key` | Valori | Descrizione |
| ---------- | ------ | ----------- |
| "AnchorLayout.DisableSinglePassControlScaling" | "true" &#124; "false" | Indica se i controlli ancorati vengono ridimensionati in un singolo passaggio. "true" per disabilitare il ridimensionamento del singolo passaggio; in caso contrario, false. Per ulteriori informazioni, vedere la sezione relativa alla scalabilità singola nelle [Note](#remarks) . |
| "DpiAwareness" | "PerMonitorV2" &#124; "false" | Indica se un'applicazione è compatibile con DPI. Impostare la chiave su "PerMonitorV2" per supportare la consapevolezza dpi; in caso contrario, impostarlo su "false". La consapevolezza DPI è una funzionalità di consenso esplicito; per sfruttare i vantaggi del supporto di Windows Forms DPI elevato, è necessario impostarne il valore su "PerMonitorV2". Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) . |
| "CheckedListBox. DisableHighDpiImprovements" | "true" &#124; "false" | Indica se il <xref:System.Windows.Forms.CheckedListBox> controllo sfrutta i miglioramenti apportati alla scalabilità e al layout introdotti nella .NET Framework 4,7. "vero" per rifiutare esplicitamente il ridimensionamento e i miglioramenti del layout; in caso contrario, "false". |
| "DataGridView. DisableHighDpiImprovements" | "true" &#124; "false" | Indica se i <xref:System.Windows.Forms.DataGridView> miglioramenti del layout e del ridimensionamento del controllo introdotti nella .NET Framework 4,7. "true" per rifiutare esplicitamente la consapevolezza DPI; "false" in caso contrario. |
| "DisableDpiChangedMessageHandling" | "true" &#124; "false" | "true" per rifiutare esplicitamente la ricezione di messaggi correlati alle modifiche di ridimensionamento DPI; "false" in caso contrario. Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) . |
| "EnableWindowsFormsHighDpiAutoResizing" | "true" &#124; "false" | Indica se un Windows Forms Application viene ridimensionato automaticamente a causa delle modifiche di ridimensionamento DPI. "true" per abilitare il ridimensionamento automatico; in caso contrario, false. |
| "Form. DisableSinglePassControlScaling" | "true" &#124; "false" | Indica se l'oggetto <xref:System.Windows.Forms.Form> viene ridimensionato in un singolo passaggio. "true" per disabilitare il ridimensionamento a passaggio singolo; in caso contrario, false. Per ulteriori informazioni, vedere la sezione relativa alla scalabilità singola nelle [Note](#remarks) . |
| "MonthCalendar. DisableSinglePassControlScaling" | "true" &#124; "false" | Indica se il <xref:System.Windows.Forms.MonthCalendar> controllo viene ridimensionato in un singolo passaggio. "true" per disabilitare il ridimensionamento a passaggio singolo; in caso contrario, false. Per ulteriori informazioni, vedere la sezione relativa alla scalabilità singola nelle [Note](#remarks) . |
| "ToolStrip. DisableHighDpiImprovements" | "true" &#124; "false" | Indica se il <xref:System.Windows.Forms.ToolStrip> controllo sfrutta i miglioramenti apportati alla scalabilità e al layout introdotti nella .NET Framework 4,7. "true" per rifiutare esplicitamente la consapevolezza DPI; "false" in caso contrario. |

### <a name="child-elements"></a>Elementi figlio

No.

### <a name="parent-elements"></a>Elementi padre

| Elemento | Descrizione |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](index.md) | Configura il supporto per le nuove funzionalità di Windows Forms Application. |

## <a name="remarks"></a>Commenti

A partire da .NET Framework 4.7, l'elemento `<System.Windows.Forms.ApplicationConfigurationSection>` consente di configurare le applicazioni Windows Form in modo da sfruttare i vantaggi delle funzionalità aggiunte nelle versioni recenti di .NET Framework.

L' `<System.Windows.Forms.ApplicationConfigurationSection>` elemento consente di aggiungere uno o più elementi figlio `<add>` , ognuno dei quali definisce un'impostazione di configurazione specifica.

Per una panoramica del supporto di Windows Forms DPI elevato, vedere Supporto di valori [DPI alti in Windows Forms](../../../winforms/high-dpi-support-in-windows-forms.md).

### <a name="dpiawareness"></a>DpiAwareness

Windows Forms app eseguite in versioni di Windows a partire da Windows 10 Creators Edition e versioni di destinazione di .NET Framework a partire da .NET Framework 4,7 possono essere configurate per sfruttare i miglioramenti a DPI elevati introdotti nella .NET Framework 4,7. incluse le seguenti:

- Supporto per scenari con valori DPI dinamici in cui l'utente modifica il valore DPI o il fattore di scala dopo l'avvio di un Windows Forms Application.

- Miglioramenti apportati alla scalabilità e al layout di un numero di controlli di Windows Forms, ad esempio il <xref:System.Windows.Forms.MonthCalendar> controllo e il <xref:System.Windows.Forms.CheckedListBox> controllo.

La consapevolezza DPI elevata è una funzionalità di consenso esplicito; per impostazione predefinita, il valore di `DpiAwareness` è `false` . È possibile acconsentire esplicitamente al supporto Windows Forms per la consapevolezza DPI impostando il valore di questa chiave su `PerMonitorV2` nel file di configurazione dell'applicazione. Se la funzionalità DPI Awareness è abilitata, vengono abilitate anche tutte le funzionalità DPI singole. incluse le seguenti:

- DPI modificati messaggi, che sono controllati dalla `DisableDpiChangedMessageHandling` chiave.

- Supporto di DPI dinamici, controllato dalla `EnableWindowsFormsHighDpiAutoResizing` chiave.

- Ridimensionamento del controllo a passaggio singolo, che è controllato da `Form.DisableSinglePassControlScaling` per i singoli <xref:System.Windows.Forms.Form> controlli, dalla `AnchorLayout.DisableSinglePassControlScaling` chiave per i controlli ancorati e dalla `MonthCalendar.DisableSinglePassControlScaling` chiave per il <xref:System.Windows.Forms.MonthCalendar> controllo.

- Miglioramenti del layout e della scalabilità DPI elevati, controllati dalla `CheckListBox.DisableHighDpiImprovements` chiave per il <xref:System.Windows.Forms.CheckedListBox> controllo, dalla `DataGridView.DisableHighDpiImprovements` chiave per il <xref:System.Windows.Forms.DataGridView> controllo e dalla `Toolstrip.DisableHighDpiImprovements` chiave per il <xref:System.Windows.Forms.ToolStrip> controllo.

La singola impostazione di consenso esplicito predefinita fornita impostando `DpiAwareness` su `PerMonitorV2` è generalmente adatta per le nuove applicazioni Windows Forms. Tuttavia, è possibile rifiutare esplicitamente i singoli miglioramenti a DPI elevati aggiungendo la chiave corrispondente al file di configurazione dell'applicazione. Ad esempio, per sfruttare tutte le nuove funzionalità DPI ad eccezione del supporto di DPI dinamici, è necessario aggiungere il codice seguente al file di configurazione dell'applicazione:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <!-- Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

In genere si rifiuta esplicitamente una particolare funzionalità perché si è scelto di gestirla a livello di codice.

Per ulteriori informazioni su come sfruttare i vantaggi del supporto di valori DPI elevati nelle applicazioni Windows Forms, vedere Supporto di valori [DPI elevati nel Windows Forms](../../../winforms/high-dpi-support-in-windows-forms.md).

### <a name="disabledpichangedmessagehandling"></a>DisableDpiChangedMessageHandling

A partire da .NET Framework 4,7, i controlli Windows Forms generano una serie di eventi correlati alle modifiche nel ridimensionamento DPI. Sono inclusi gli <xref:System.Windows.Forms.Control.DpiChangedAfterParent> <xref:System.Windows.Forms.Control.DpiChangedBeforeParent> eventi, e <xref:System.Windows.Forms.Form.DpiChanged> . Il valore della `DisableDpiChangedMessageHandling` chiave determina se questi eventi vengono generati in un Windows Forms Application.

### <a name="single-pass-scaling"></a>Scalabilità a passaggio singolo

La scalabilità singola o MultiPASS influisce sulla velocità di risposta percepita dell'interfaccia utente e sull'aspetto visivo degli elementi dell'interfaccia utente man mano che vengono ridimensionati. A partire da .NET Framework 4,7, Windows Forms usa la scalabilità con singolo passaggio. Nelle versioni precedenti del .NET Framework il ridimensionamento veniva eseguito attraverso più passaggi, il che causava la scalabilità di alcuni controlli più del necessario. La scalabilità a passaggio singolo dovrebbe essere disabilitata solo se l'app dipende dal comportamento precedente.

## <a name="see-also"></a>Vedi anche

- [Sezione di configurazione di Windows Form](index.md)
- [Supporto di valori DPI alti in Windows Forms](../../../winforms/high-dpi-support-in-windows-forms.md)
