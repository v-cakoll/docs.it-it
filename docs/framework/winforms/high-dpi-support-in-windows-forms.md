---
title: Supporto di valori DPI alti
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
ms.openlocfilehash: a5c3125475c2de2cf83a3d97e356b26c0acdde99
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741892"
---
# <a name="high-dpi-support-in-windows-forms"></a>Supporto di valori DPI alti in Windows Forms

A partire da .NET Framework 4,7, Windows Forms include miglioramenti per gli scenari con valori DPI più comuni e DPI dinamici. tra cui:

- Miglioramenti apportati alla scalabilità e al layout di un numero di controlli di Windows Forms, ad esempio il controllo <xref:System.Windows.Forms.MonthCalendar> e il controllo <xref:System.Windows.Forms.CheckedListBox>.

- Scalabilità single-pass.  In .NET Framework 4,6 e versioni precedenti, il ridimensionamento veniva eseguito attraverso più passaggi, causando la scalabilità di alcuni controlli più di quanto fosse necessario.

- Supporto per scenari con valori DPI dinamici in cui l'utente modifica il valore DPI o il fattore di scala dopo l'avvio di un Windows Forms Application.

Nelle versioni del .NET Framework a partire dal .NET Framework 4,7, il supporto avanzato per DPI è una funzionalità di consenso esplicito. È necessario configurare l'applicazione per sfruttarne i vantaggi.

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a>Configurazione dell'app Windows Forms per il supporto di valori DPI elevati

Le nuove funzionalità di Windows Forms che supportano la consapevolezza DPI elevata sono disponibili solo nelle applicazioni destinate al .NET Framework 4,7 e sono in esecuzione su sistemi operativi Windows a partire da Windows 10 Creators Update.

Inoltre, per configurare il supporto di valori DPI alti nella Windows Forms Application, è necessario eseguire le operazioni seguenti:

- Dichiara la compatibilità con Windows 10.

  A tale scopo, aggiungere il codice seguente al file manifesto:

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- Abilitare la consapevolezza DPI per monitor nel file *app. config* .

  Windows Forms introduce un nuovo elemento [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) per supportare le nuove funzionalità e le personalizzazioni aggiunte a partire da .NET Framework 4,7. Per sfruttare i vantaggi delle nuove funzionalità che supportano valori DPI alti, aggiungere il codice seguente al file di configurazione dell'applicazione.

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > Nelle versioni precedenti del .NET Framework è stato usato il manifesto per aggiungere il supporto di valori DPI alti. Questo approccio non è più consigliato, poiché sostituisce le impostazioni definite nel file app. config.

- Chiamare il metodo statico <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.

  Questa deve essere la prima chiamata al metodo nel punto di ingresso dell'applicazione. Ad esempio,

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a>Rifiutare esplicitamente le singole funzionalità DPI elevate

Impostando il valore `DpiAwareness` su `PerMonitorV2` si abilitano tutte le funzionalità di riconoscimento DPI elevato supportate dalle versioni .NET Framework a partire dal .NET Framework 4,7. Questa operazione è in genere adeguata per la maggior parte delle applicazioni Windows Forms. Tuttavia, potrebbe essere necessario rifiutare esplicitamente una o più funzionalità singole. Il motivo più importante per questa operazione è che il codice dell'applicazione esistente gestisce già tale funzionalità.  Se, ad esempio, l'applicazione gestisce la scalabilità automatica, potrebbe essere necessario disabilitare la funzionalità di ridimensionamento automatico come indicato di seguito:

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

Per un elenco delle singole chiavi e dei relativi valori, vedere [Windows Forms Aggiungi elemento di configurazione](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).

## <a name="new-dpi-change-events"></a>Nuovi eventi di modifica DPI

A partire da .NET Framework 4,7, tre nuovi eventi consentono di gestire a livello di codice le modifiche a DPI dinamici:

- <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, che viene generato quando l'impostazione DPI per un controllo viene modificata a livello di codice dopo che si è verificato un evento di modifica DPI per il relativo controllo o form padre.
- <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, che viene generato quando l'impostazione DPI per un controllo viene modificata a livello di codice prima che si verifichi un evento di modifica DPI per il relativo controllo o form padre.
- <xref:System.Windows.Forms.Form.DpiChanged>, che viene generato quando viene modificata l'impostazione DPI sul dispositivo di visualizzazione in cui è attualmente visualizzato il form.

## <a name="new-helper-methods-and-properties"></a>Nuovi metodi e proprietà Helper

Il .NET Framework 4,7 aggiunge anche una serie di nuove proprietà e metodi helper che forniscono informazioni sul ridimensionamento DPI e consentono di eseguire la scalabilità DPI. tra cui:

- <xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, che converte un valore da Logical a Device pixel.

- <xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, che consente di ridimensionare un'immagine bitmap in DPI logici per un dispositivo.

- <xref:System.Windows.Forms.Control.DeviceDpi%2A>, che restituisce il valore DPI per il dispositivo corrente.

## <a name="versioning-considerations"></a>Considerazioni sul controllo delle versioni

Oltre a essere in esecuzione in .NET Framework 4,7 e Windows 10 Creators Update, l'applicazione può essere eseguita anche in un ambiente in cui non è compatibile con i miglioramenti a DPI elevati. In questo caso, sarà necessario sviluppare un fallback per l'applicazione. Questa operazione può essere eseguita per eseguire un [disegno personalizzato](./controls/user-drawn-controls.md) per gestire la scalabilità.

A tale scopo, è necessario anche determinare il sistema operativo in cui è in esecuzione l'app. Questa operazione può essere eseguita con codice simile al seguente:

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

Si noti che l'applicazione non rileva correttamente Windows 10 se non è stato elencato come sistema operativo supportato nel manifesto dell'applicazione.

È anche possibile controllare la versione del .NET Framework in base alla quale è stata compilata l'applicazione:

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a>Vedere anche

- [Windows Forms Aggiungi elemento di configurazione](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [Regolazione delle dimensioni e della scala di Windows Form](adjusting-the-size-and-scale-of-windows-forms.md)
