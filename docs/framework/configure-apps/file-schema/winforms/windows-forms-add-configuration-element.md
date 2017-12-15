---
title: Windows Form aggiungere l'elemento di configurazione
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 828a28769e164535d4dde989ef8cce91caf9cb48
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2017
---
# <a name="windows-forms-add-configuration-element"></a>Windows Form aggiungere l'elemento di configurazione

Il `<add>` elemento aggiunge una chiave predefinita che specifica se l'app di Windows Form supporta le funzionalità aggiunte all'app di Windows Form nel 4.7 di .NET Framework o versione successiva.

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
| `key`     | Attributo obbligatorio. Nome chiave predefinito che corrisponde a una particolare funzionalità di Windows Form personalizzabile. |
| `value`   | Attributo obbligatorio. Il valore da assegnare al `key`. |

### <a name="key-attribute-names-and-associated-values"></a>`key`i nomi degli attributi e valori associati

| Nome in `key` | Valori | Descrizione |
| ---------- | ------ | ----------- |
| "AnchorLayout.DisableSinglePassControlScaling" | "true" &#124;" false" | Indica se i controlli ancorati vengono ridimensionati in un unico passaggio. passare "true" per disabilitare una singola scala; in caso contrario, false. Vedere la sezione "Singolo pass scalabilità" nel [osservazioni](#Remarks) per ulteriori informazioni. |
| "DpiAwareness" | "PerMonitorV2" &#124;" false" | Indica se un'applicazione è compatibile con DPI. Impostare la chiave "PerMonitorV2" per supportare il riconoscimento Dpi; in caso contrario, impostarla su "false". Il riconoscimento DPI è una funzionalità di consenso esplicito; Per sfruttare i vantaggi del supporto per valori DPI elevato Windows Form, è necessario impostare il valore su "PerMonitorV2". Vedere il [osservazioni](#remarks) sezione per ulteriori informazioni. |
| "CheckedListBox.DisableHighDpiImprovements" | "true" &#124;" false" | Indica se il <xref:System.Windows.Forms.CheckedListBox> controllo sfrutta i vantaggi di scalabilità e il layout miglioramenti introdotti nel 4.7 di .NET Framework. "true" per rifiutare esplicitamente i miglioramenti di layout e caling; in caso contrario, "false". |
| "DataGridView.DisableHighDpiImprovements" | "true" &#124;" false" | Indica se il <xref:System.Windows.Forms.DataGridView> controllo di layout e ridimensionamento miglioramenti introdotti nel 4.7 di .NET Framework. "true" per rifiutare esplicitamente il riconoscimento DPI; "false" in caso contrario. |
| "DisableDpiChangedMessageHandling" | "true" &#124;" false" | "true" per rifiutare esplicitamente la ricezione di messaggi correlati a DPI scalabilità le modifiche. "false" in caso contrario. Vedere il [osservazioni](#remarks) sezione per ulteriori informazioni. |
| "EnableWindowsFormsHighDpiAutoResizing" | "true" &#124;" false" | Indica se un'applicazione Windows Form viene ridimensionata automaticamente a causa di modifiche di ridimensionamento DPI. "true" per abilitare il ridimensionamento automatico; in caso contrario, false. |
| "Form.DisableSinglePassControlScaling" | "true" &#124;" false" | Indica se il <xref:System.Windows.Forms.Form> viene ridimensionato in un unico passaggio. "true" per disabilitare il passaggio singolo scalabilità; in caso contrario, false. Vedere la sezione "Singolo pass scalabilità" nel [osservazioni](#Remarks) per ulteriori informazioni. |
| "MonthCalendar.DisableSinglePassControlScaling" | "true" &#124;" false" | Indica se il <xref:System.Windows.Forms.MonthCalendar> controllo viene ridimensionato in un unico passaggio. "true" per disabilitare il passaggio singolo scalabilità; in caso contrario, false. Vedere la sezione "Singolo pass scalabilità" nel [osservazioni](#Remarks) per ulteriori informazioni. |
| "Toolstrip.DisableHighDpiImprovements" | "true" &#124;" false" | Indica se il <xref:System.Windows.Forms.ToolStrip> controllo sfrutta i vantaggi di scalabilità e il layout miglioramenti introdotti nel 4.7 di .NET Framework. "true" per rifiutare esplicitamente il riconoscimento DPI; "false" in caso contrario. |

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

| Elemento | Descrizione |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) | Consente di configurare il supporto per le nuove funzionalità di applicazione Windows Form. |

## <a name="a-nameremarks--remarks"></a><a name="remarks" />Sezione Osservazioni

A partire da .NET Framework 4.7, l'elemento `<System.Windows.Forms.ApplicationConfigurationSection>` consente di configurare le applicazioni Windows Form in modo da sfruttare i vantaggi delle funzionalità aggiunte nelle versioni recenti di .NET Framework. 

Il `<System.Windows.Forms.ApplicationConfigurationSection>` elemento consente di aggiungere uno o più figlio `<add>` elementi, ognuno dei quali definisce un'impostazione di configurazione specifico.  

Per una panoramica del supporto di valori DPI alti di Windows Form, vedere [DPI elevata supporta in Windows Form](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).

### <a name="dpiawareness"></a>DpiAwareness

App di Windows Form che vengono eseguiti in versioni di Windows a partire da Windows 10 creatori Edition e nelle versioni di destinazione di .NET Framework a partire dal 4.7 di .NET Framework possono essere configurate per sfruttare i miglioramenti di DPI elevati introdotta in .NET Framework 4.7. tra cui:

- Supporto per scenari di risoluzione dinamici in cui l'utente modifica il fattore di scala o DPI dopo che è stata avviata un'applicazione Windows Form.

- Miglioramenti nella scalabilità e layout di un numero di Windows Form controlli, ad esempio il <xref:System.Windows.Forms.MonthCalendar> controllo e <xref:System.Windows.Forms.CheckedListBox> controllo. 

Il riconoscimento DPI elevato è una funzionalità di consenso esplicito; Per impostazione predefinita, il valore di `DpiAwareness` è `false`. È possibile scegliere nel supporto di Windows Form per il riconoscimento DPI impostando il valore della chiave su `PerMonitorV2` nel file di configurazione dell'applicazione. Se è abilitato il riconoscimento DPI, sono abilitate anche tutte le funzionalità DPI singoli. tra cui:

- DPI modificato, i messaggi sono controllati dal `DisableDpiChangedMessageHandling` chiave.

- Supporto dinamico DPI, controllato dal `EnableWindowsFormsHighDpiAutoResizing` chiave.

- Singola passata controllo ridimensionamento, controllata dal `Form.DisableSinglePassControlScaling` per singoli <xref:System.Windows.Forms.Form> da controlli di `AnchorLayout.DisableSinglePassControlScaling` chiave per i controlli ancorati e dal `MonthCalendar.DisableSinglePassControlScaling` chiave per la <xref:System.Windows.Forms.MonthCalendar> controllo 

- Elevata DPI layout e ridimensionamento miglioramenti, controllato dal `CheckListBox.DisableHighDpiImprovements` chiave per la <xref:System.Windows.Forms.CheckedListBox> da controllare il `DataGridView.DisableHighDpiImprovements` chiave per la <xref:System.Windows.Forms.DataGridView> (controllo) e dal `Toolstrip.DisableHighDpiImprovements` chiave per la <xref:System.Windows.Forms.ToolStrip> controllo.  

L'unico acconsentire esplicitamente impostazione predefinita fornita tramite l'impostazione `DpiAwareness` a `PerMonitorV2` viene in genere sufficiente per le nuove applicazioni di Windows Form. Tuttavia, è possibile quindi rifiutare singoli miglioramenti DPI elevati aggiungendo la chiave corrispondente al file di configurazione dell'applicazione. Ad esempio, per sfruttare tutti i featuers DPI nuovo ad eccezione di supporto per valori DPI dinamico, aggiungere quanto segue al file di configurazione dell'applicazione:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <--! Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```
In genere di rinunciare a una determinata funzionalità perché si è scelto di gestire a livello di codice.

Per ulteriori informazioni su sfruttando del supporto per valori DPI alti in applicazioni Windows Forms, vedere [DPI elevata supporta in Windows Form](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).
 
### <a name="disabledpichangedmessagehandling"></a>DisableDpiChangedMessageHandling

A partire dal 4.7 di .NET Framework, i controlli Windows Form generano un numero di eventi correlati alle modifiche di ridimensionamento DPI. Queste includono la <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, e <xref:System.Windows.Forms.Form.DpiChanged> eventi. Il valore di `DisableDpiChangedMessageHandling` chiave determina se vengono generati in un'applicazione Windows Form. 

### <a name="single-pass-scaling"></a>Singola passata scalabilità

Uno o più passate scalabilità influenza la velocità di risposta percepita dell'interfaccia utente e l'aspetto visivo di elementi dell'interfaccia utente come essi vengono ridimensionati. A partire dal 4.7 di .NET Framework, Windows Form usa il ridimensionamento unico passaggio. Nelle versioni precedenti di .NET Framework, il ridimensionamento è stato eseguito tramite più passaggi, che ha provocato alcuni controlli scalabilità più necessarie. Scalabilità singola passata deve essere disattivata solo se l'applicazione dipende dal comportamento precedente.  

## <a name="see-also"></a>Vedere anche
 
[Sezione di configurazione di Windows Form](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md)   
[Supporto di valori DPI alti in Windows Form](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
