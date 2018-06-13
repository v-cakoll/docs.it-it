---
title: Supporto per valori DPI elevato in Windows Form
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbf2d7b61b34a2cd4641a77ee1f2fcdff7f3c3fe
ms.sourcegitcommit: b7763f3435635850a76d4cbcf09bdce6c019208a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2018
ms.locfileid: "34483541"
---
# <a name="high-dpi-support-in-windows-forms"></a>Supporto per valori DPI elevato in Windows Form

A partire dal 4.7 di .NET Framework, Windows Form include miglioramenti per valori DPI alti comuni e scenari di risoluzione dinamici. Sono inclusi: 

- Miglioramenti nella scalabilità e layout di un numero di Windows Form controlli, ad esempio il <xref:System.Windows.Forms.MonthCalendar> controllo e <xref:System.Windows.Forms.CheckedListBox> controllo. 

- Scalabilità-passaggio singolo.  In .NET Framework 4.6 e versioni precedenti, la scalabilità è stata eseguita tramite più passaggi, che ha provocato alcuni controlli scalabilità più necessarie.

- Supporto per scenari di risoluzione dinamici in cui l'utente modifica il fattore di scala o DPI dopo che è stata avviata un'applicazione Windows Form.

Nelle versioni di .NET Framework a partire dal 4.7 di .NET Framework, supporto avanzato per valori DPI elevato è una funzionalità di consenso esplicito. È necessario configurare l'applicazione per sfruttare i vantaggi.

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a>Configurare l'app di Windows Form per il supporto per valori DPI elevato

Le nuove funzionalità di Windows Form che supportano il riconoscimento DPI elevato sono disponibili solo nelle applicazioni destinate al 4.7 di .NET Framework e sono in esecuzione nei sistemi operativi Windows a partire da Windows 10 creatori di aggiornamento. 

Inoltre, per configurare il supporto DPI elevato nell'applicazione Windows Form, è necessario eseguire le operazioni seguenti:

- Dichiarare la compatibilità con Windows 10.

  A tale scopo, aggiungere quanto segue al file manifesto:

  ```xml
  <compatibility xmlns="urn:schemas-microsoft.com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- Abilitare la consapevolezza DPI monitor il *app* file.

  Introduce un nuovo Windows Form [ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../../../docs/framework/configure-apps/file-schema/winforms/index.md) elemento per supportare nuove funzionalità e le personalizzazioni aggiunte a partire dal 4.7 di .NET Framework. Per sfruttare i vantaggi delle nuove funzionalità che supportano valori DPI alti, aggiungere quanto segue al file di configurazione dell'applicazione.   

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>      
  ```
   
  > [!IMPORTANT]
  > Nelle versioni precedenti di .NET Framework, il manifesto è utilizzato per aggiungere supporto per valori DPI elevato. Questo approccio non è più consigliato, perché esegue l'override delle impostazioni definite nel file app. config.
   
- Chiamare il metodo statico <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> metodo.
   
  Deve essere la prima chiamata al metodo nel punto di ingresso dell'applicazione. Ad esempio:
   
  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());   
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a>Rifiuto esplicito singole funzionalità DPI elevata

L'impostazione di `DpiAwareness` valore `PerMonitorV2` Abilita le funzionalità di riconoscimento DPI elevate tutti supportate da versioni di .NET Framework a partire dal 4.7 di .NET Framework. In genere, questo è sufficiente per la maggior parte delle applicazioni Windows Form. Tuttavia, è consigliabile escludere uno o più delle singole funzionalità. Il motivo per eseguire questa operazione più importante è che il codice dell'applicazione esistente già gestisce tale funzionalità.  Ad esempio, se l'applicazione gestisce il ridimensionamento automatico, è consigliabile disabilitare la funzionalità di ridimensionamento automatico, come indicato di seguito:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" /> 
</System.Windows.Forms.ApplicationConfigurationSection>    
```

Per un elenco di singole chiavi e i relativi valori, vedere [elemento configurazione di Windows Form Add](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).

## <a name="new-dpi-change-events"></a>Nuovi eventi di modifica DPI

A partire dal 4.7 di .NET Framework, tre nuovi eventi consentono di gestire a livello di programmazione le modifiche dinamiche DPI:

- <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, che viene generato quando l'impostazione DPI per un controllo viene modificato a livello di codice dopo un evento di modifica DPI, DOTS per il relativo controllo padre o si è verificato un modulo.
- <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, che viene generato quando l'impostazione DPI per un controllo viene modificato a livello di codice prima di un evento di modifica DPI, DOTS per relativo controllo padre o si è verificato un modulo.
- <xref:System.Windows.Forms.Form.DpiChanged>, che viene attivato quando viene modificato l'impostazione DPI sul dispositivo di visualizzazione in cui il modulo è attualmente visualizzato.

## <a name="new-helper-methods-and-properties"></a>Le proprietà e nuovi metodi di supporto

Il 4.7 di .NET Framework aggiunge anche il numero di nuovi metodi di supporto e le proprietà che forniscono informazioni sul ridimensionamento DPI e consentono di eseguire il ridimensionamento DPI. Sono inclusi:

- <xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, che consente di convertire un valore da coordinate logiche ai pixel del dispositivo.

- <xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, che ridimensiona un'immagine bitmap in DPI logico per un dispositivo.

- <xref:System.Windows.Forms.Control.DeviceDpi%2A>, che restituisce il valore di DPI per il dispositivo corrente.

## <a name="versioning-considerations"></a>Considerazioni sulla gestione delle versioni

Oltre a eseguire in .NET Framework 4.7 e creatori di aggiornamento di Windows 10, l'applicazione possono essere eseguite anche in un ambiente in cui non è compatibile con i miglioramenti di DPI elevati. In questo caso, è necessario sviluppare un fallback per l'applicazione. A tale scopo eseguire [disegno personalizzato](./controls/user-drawn-controls.md) per gestire la scalabilità.

A tale scopo, è necessario anche determinare il sistema operativo in cui l'app è in esecuzione. È possibile farlo con codice simile al seguente:

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

Si noti che l'applicazione non correttamente rileva Windows 10, se non è stato elencato come un sistema operativo supportato nel manifesto dell'applicazione.

È inoltre possibile controllare la versione di .NET Framework è stata creata l'applicazione:

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a>Vedere anche

[Windows Form aggiungere l'elemento di configurazione](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)  
[Regolazione delle dimensioni e della scala di Windows Form](../../../docs/framework/winforms/adjusting-the-size-and-scale-of-windows-forms.md)
