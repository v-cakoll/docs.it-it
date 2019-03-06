---
title: Windows Form aggiungere elemento di configurazione
ms.date: 04/07/2017
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 107de172e523758474bafb3b86a2960b926a010a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371372"
---
# <a name="windows-forms-add-configuration-element"></a>Windows Form aggiungere elemento di configurazione

Il `<add>` elemento aggiunge una chiave predefinita che specifica se l'app di Windows Form supporta le funzionalità aggiunte per le app di Windows Form in .NET Framework 4.7 o versioni successive.

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
| `key`     | Attributo obbligatorio. Nome chiave predefinito che corrisponde a una determinata funzionalità personalizzabili di Windows Form. |
| `value`   | Attributo obbligatorio. Il valore da assegnare a `key`. |

### <a name="key-attribute-names-and-associated-values"></a>`key` i nomi degli attributi e valori associati

| `key` Nome | Valori | Descrizione |
| ---------- | ------ | ----------- |
| "AnchorLayout.DisableSinglePassControlScaling" | "true"&#124;"false" | Indica se i controlli ancorati vengono ridimensionati in un unico passaggio. "true" per disabilitare la singola passare la scalabilità; in caso contrario, false. Vedere la sezione "Singolo pass scalabilità" nel [osservazioni](#Remarks) per altre informazioni. |
| "DpiAwareness" | "PerMonitorV2"&#124;"false" | Indica se un'applicazione è compatibile con DPI. Impostare la chiave per "PerMonitorV2" per supportare la compatibilità con Dpi; in caso contrario, impostarla su "false". Compatibilità con DPI è una funzionalità che prevede il consenso esplicito; Per sfruttare i vantaggi del supporto di valori DPI alti dei moduli di Windows, è necessario impostare il relativo valore su "PerMonitorV2". Vedere le [osservazioni](#remarks) sezione per altre informazioni. |
| "CheckedListBox.DisableHighDpiImprovements" | "true"&#124;"false" | Indica se il <xref:System.Windows.Forms.CheckedListBox> controllo consente di sfruttare la scalabilità e il layout i miglioramenti introdotti con .NET Framework 4.7. "true" per rifiutare esplicitamente i miglioramenti di layout e caling; in caso contrario, "false". |
| "DataGridView.DisableHighDpiImprovements" | "true"&#124;"false" | Indica se il <xref:System.Windows.Forms.DataGridView> controllare la scalabilità e il layout i miglioramenti introdotti con .NET Framework 4.7. "true" rifiutare esplicitamente la compatibilità con DPI; "false" in caso contrario. |
| "DisableDpiChangedMessageHandling" | "true"&#124;"false" | "true" rifiutare esplicitamente la ricezione di messaggi correlati a DPI ridimensionamento le modifiche. "false" in caso contrario. Vedere le [osservazioni](#remarks) sezione per altre informazioni. |
| "EnableWindowsFormsHighDpiAutoResizing" | "true"&#124;"false" | Indica se un'applicazione Windows Form viene ridimensionata automaticamente a causa di modifiche di ridimensionamento DPI. "true" per abilitare il ridimensionamento automatico; in caso contrario, false. |
| "Form.DisableSinglePassControlScaling" | "true"&#124;"false" | Indica se il <xref:System.Windows.Forms.Form> viene ridimensionata in un unico passaggio. single-pass "true" per disabilitare la scalabilità; in caso contrario, false. Vedere la sezione "Singolo pass scalabilità" nel [osservazioni](#Remarks) per altre informazioni. |
| "MonthCalendar.DisableSinglePassControlScaling" | "true"&#124;"false" | Indica se il <xref:System.Windows.Forms.MonthCalendar> controllo viene ridimensionato in un unico passaggio. single-pass "true" per disabilitare la scalabilità; in caso contrario, false. Vedere la sezione "Singolo pass scalabilità" nel [osservazioni](#Remarks) per altre informazioni. |
| "Toolstrip.DisableHighDpiImprovements" | "true"&#124;"false" | Indica se il <xref:System.Windows.Forms.ToolStrip> controllo consente di sfruttare la scalabilità e il layout i miglioramenti introdotti con .NET Framework 4.7. "true" rifiutare esplicitamente la compatibilità con DPI; "false" in caso contrario. |

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

| Elemento | Descrizione |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) | Consente di configurare il supporto per nuove funzionalità delle applicazioni Windows Form. |

## <a name="a-nameremarks--remarks"></a><a name="remarks" /> Sezione Osservazioni

A partire da .NET Framework 4.7, l'elemento `<System.Windows.Forms.ApplicationConfigurationSection>` consente di configurare le applicazioni Windows Form in modo da sfruttare i vantaggi delle funzionalità aggiunte nelle versioni recenti di .NET Framework.

Il `<System.Windows.Forms.ApplicationConfigurationSection>` elemento consente di aggiungere uno o più figlio `<add>` elementi, ognuno dei quali definisce un'impostazione di configurazione specifico.

Per una panoramica del supporto di valori DPI alti di Windows Form, vedere [supporto di valori DPI elevato in Windows Form](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).

### <a name="dpiawareness"></a>DpiAwareness

Le app di Windows Form che vengono eseguiti in versioni di Windows a partire da Windows 10 Creators Edition e destinati a versioni di .NET Framework a partire da .NET Framework 4.7 possono essere configurate per trarre vantaggio dai miglioramenti di DPI elevati introdotta in .NET Framework 4.7. Sono inclusi:

- Supporto per scenari DPI dinamici in cui l'utente modifica il fattore di scala o DPI dopo che un'applicazione Windows Forms è stata avviata.

- Miglioramenti per il ridimensionamento e layout di un numero di Windows Form controlli, ad esempio la <xref:System.Windows.Forms.MonthCalendar> controllo e il <xref:System.Windows.Forms.CheckedListBox> controllo.

Compatibilità con DPI elevato è una funzionalità che prevede il consenso esplicito; Per impostazione predefinita, il valore di `DpiAwareness` è `false`. È possibile scegliere esplicitamente il supporto dei moduli di Windows per la compatibilità con DPI impostando il valore della chiave su `PerMonitorV2` nel file di configurazione dell'applicazione. Se la compatibilità con DPI è abilitata, sono abilitate anche tutte le singole funzionalità DPI. Sono inclusi:

- DPI modificare messaggi, che sono controllati dal `DisableDpiChangedMessageHandling` chiave.

- Supporto di valori DPI dinamico, che viene controllato dal `EnableWindowsFormsHighDpiAutoResizing` chiave.

- Passaggio singolo controllo ridimensionamento, che è controllata dal `Form.DisableSinglePassControlScaling` per singoli <xref:System.Windows.Forms.Form> controlli, per il `AnchorLayout.DisableSinglePassControlScaling` chiave per i controlli ancorati e dal `MonthCalendar.DisableSinglePassControlScaling` chiave per il <xref:System.Windows.Forms.MonthCalendar> controllo

- Elevata DPI ridimensionamento e layout miglioramenti, che viene controllata dal `CheckListBox.DisableHighDpiImprovements` chiave per il <xref:System.Windows.Forms.CheckedListBox> da controllare il `DataGridView.DisableHighDpiImprovements` chiave per il <xref:System.Windows.Forms.DataGridView> (controllo) e dal `Toolstrip.DisableHighDpiImprovements` chiave per il <xref:System.Windows.Forms.ToolStrip> controllo.

L'unico acconsenti esplicitamente impostazione predefinita fornito tramite l'impostazione `DpiAwareness` a `PerMonitorV2` viene in genere adeguati per le nuove applicazioni Windows Form. Tuttavia, è possibile quindi rifiutare singoli miglioramenti DPI elevati aggiungendo la chiave corrispondente nel file di configurazione dell'applicazione. Ad esempio, per poter sfruttare tutte le nuove DPI funzionalità ad eccezione di supporto di valori DPI dinamica, aggiungere quanto segue al file di configurazione dell'applicazione:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <!-- Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```
In genere, consenso esplicito all'esterno di una determinata funzionalità perché si è scelto di gestirla a livello di codice.

Per altre informazioni su sfruttare i vantaggi del supporto di valori DPI alti in applicazioni Windows Forms, vedere [supporto di valori DPI elevato in Windows Form](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).

### <a name="disabledpichangedmessagehandling"></a>DisableDpiChangedMessageHandling

A partire da .NET Framework 4.7, i controlli Windows Form generano un numero di eventi correlati alle modifiche nel ridimensionamento DPI. Sono inclusi i <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, e <xref:System.Windows.Forms.Form.DpiChanged> eventi. Il valore della `DisableDpiChangedMessageHandling` chiave determina se questi eventi vengono generati in un'applicazione Windows Form.

### <a name="single-pass-scaling"></a>Passaggio singolo-ridimensionamento

La scalabilità singolo o a più influenza la velocità di risposta percepita dell'interfaccia utente e l'aspetto visivo degli elementi dell'interfaccia utente come essi vengono ridimensionati. A partire da .NET Framework 4.7, Windows Forms Usa la scalabilità unico passaggio. Nelle versioni precedenti di .NET Framework, la scalabilità è stata eseguita tramite più passaggi, che ha causato alcuni controlli ridimensionare più di era necessario. Passaggio singolo ridimensionamento deve essere disabilitato solo se l'app dipende dal comportamento precedente.

## <a name="see-also"></a>Vedere anche

- [Sezione di configurazione di Windows Form](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md)
- [Supporto di valori DPI alti in Windows Form](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
