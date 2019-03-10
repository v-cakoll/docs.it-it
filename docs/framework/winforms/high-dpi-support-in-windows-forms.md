---
title: Supporto di valori DPI alti in Windows Form
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dbb5af9c5cf1d8796544592602c645584d21a04
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711792"
---
# <a name="high-dpi-support-in-windows-forms"></a>Supporto di valori DPI alti in Windows Form

A partire da .NET Framework 4.7, Windows Form include miglioramenti per valori DPI alti comuni e scenari DPI dinamici. Sono inclusi: 

- Miglioramenti per il ridimensionamento e layout di un numero di Windows Form controlli, ad esempio la <xref:System.Windows.Forms.MonthCalendar> controllo e il <xref:System.Windows.Forms.CheckedListBox> controllo. 

- Scalabilità-passaggio singolo.  In .NET Framework 4.6 e versioni precedenti, la scalabilità è stata eseguita tramite più passaggi, che ha causato alcuni controlli ridimensionare più di era necessario.

- Supporto per scenari DPI dinamici in cui l'utente modifica il fattore di scala o DPI dopo che un'applicazione Windows Forms è stata avviata.

Nelle versioni di .NET Framework a partire da .NET Framework 4.7, supporto di valori DPI elevato avanzato è una funzionalità che prevede il consenso esplicito. È necessario configurare l'applicazione possa sfruttare i vantaggi di esso.

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a>Configurazione dell'app di Windows Form per il supporto di valori DPI alti

Le nuove funzionalità di Windows Form che supportano la compatibilità con DPI elevato sono disponibili solo nelle applicazioni destinate a .NET Framework 4.7 e sono in esecuzione nei sistemi operativi Windows a partire da Windows 10 Creators Update. 

Inoltre, per configurare il supporto di valori DPI alti in un'applicazione Windows Form, è necessario eseguire le operazioni seguenti:

- Dichiarare la compatibilità con Windows 10.

  A tale scopo, aggiungere quanto segue al file manifesto:

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- Abilitare il riconoscimento DPI per monitor nel *app. config* file.

  Introduce un nuovo Windows Form [ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../configure-apps/file-schema/winforms/index.md) elemento per supportare le nuove funzionalità e le personalizzazioni aggiunte a partire da .NET Framework 4.7. Per sfruttare i vantaggi delle nuove funzionalità che supportano valori DPI alti, aggiungere quanto segue al file di configurazione dell'applicazione.   

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>      
  ```
   
  > [!IMPORTANT]
  > Nelle versioni precedenti di .NET Framework, il manifesto è utilizzato per aggiungere il supporto di valori DPI alti. Questo approccio non è più consigliato, poiché viene eseguito l'override delle impostazioni definite nel file app. config.
   
- Chiamare il metodo statico <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> (metodo).
   
  Deve essere la prima chiamata al metodo nel punto di ingresso dell'applicazione. Ad esempio:
   
  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());   
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a>Rifiuto esplicito le singole funzionalità DPI elevata

Impostando il `DpiAwareness` valore `PerMonitorV2` Abilita le funzionalità di riconoscimento DPI tutto elevate supportate dalle versioni di .NET Framework a partire da .NET Framework 4.7. Si tratta in genere adeguato per la maggior parte delle applicazioni di Windows Form. Tuttavia, è possibile rifiutare esplicitamente una o più singole funzionalità. Il motivo principale per eseguire questa operazione è che il codice dell'applicazione esistente gestisce già questa funzionalità.  Ad esempio, se l'applicazione gestisce la scalabilità automatica, è possibile disabilitare la funzionalità di ridimensionamento automatico come indicato di seguito:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" /> 
</System.Windows.Forms.ApplicationConfigurationSection>    
```

Per un elenco di singole chiavi e i relativi valori, vedere [elemento configurazione di Windows Form Add](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).

## <a name="new-dpi-change-events"></a>Nuovi eventi di modifica DPI

A partire da .NET Framework 4.7, tre nuovi eventi consentono di gestire a livello di programmazione dinamica DPI modifiche:

- <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, che viene generato quando l'impostazione DPI per un controllo viene modificata a livello di codice dopo un evento di modifica DPI per il relativo controllo padre o si è verificato un form.
- <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, che viene generato quando l'impostazione DPI per un controllo viene modificata a livello di codice prima di un evento di modifica DPI per il relativo controllo padre o si è verificato un form.
- <xref:System.Windows.Forms.Form.DpiChanged>, che viene generato quando l'impostazione DPI viene modificata nella periferica di visualizzazione in cui il modulo è attualmente visualizzato.

## <a name="new-helper-methods-and-properties"></a>Le proprietà e nuovi metodi di supporto

.NET Framework 4.7 aggiunge anche il numero di nuovi metodi di supporto e le proprietà che forniscono informazioni sul ridimensionamento DPI e consentono di eseguire il ridimensionamento DPI. Sono inclusi:

- <xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, che consente di convertire un valore da coordinate logiche ai pixel del dispositivo.

- <xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, che offre una scalabilità un'immagine bitmap per il valore DPI logico per un dispositivo.

- <xref:System.Windows.Forms.Control.DeviceDpi%2A>, che restituisce il valore DPI per il dispositivo corrente.

## <a name="versioning-considerations"></a>Considerazioni sul controllo delle versioni

Oltre a essere eseguito in .NET Framework 4.7 e Windows 10 Creators Update, l'applicazione possono essere eseguite anche in un ambiente in cui non è compatibile con i miglioramenti di DPI elevati. In questo caso, è necessario sviluppare un fallback per l'applicazione. È possibile farlo per eseguire [disegno personalizzato](./controls/user-drawn-controls.md) per gestire la scalabilità.

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

Si noti che l'applicazione non rileverà correttamente Windows 10 se non è stato elencato come un sistema operativo nel manifesto dell'applicazione.

È anche possibile controllare la versione di .NET Framework è stata creata l'applicazione:

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a>Vedere anche

- [Windows Form aggiungere elemento di configurazione](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [Regolazione delle dimensioni e della scala di Windows Form](adjusting-the-size-and-scale-of-windows-forms.md)
