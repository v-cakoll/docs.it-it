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
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="86fa2-102">Supporto di valori DPI alti in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="86fa2-102">High DPI support in Windows Forms</span></span>

<span data-ttu-id="86fa2-103">A partire da .NET Framework 4,7, Windows Forms include miglioramenti per gli scenari con valori DPI più comuni e DPI dinamici.</span><span class="sxs-lookup"><span data-stu-id="86fa2-103">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="86fa2-104">tra cui:</span><span class="sxs-lookup"><span data-stu-id="86fa2-104">These include:</span></span>

- <span data-ttu-id="86fa2-105">Miglioramenti apportati alla scalabilità e al layout di un numero di controlli di Windows Forms, ad esempio il controllo <xref:System.Windows.Forms.MonthCalendar> e il controllo <xref:System.Windows.Forms.CheckedListBox>.</span><span class="sxs-lookup"><span data-stu-id="86fa2-105">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span>

- <span data-ttu-id="86fa2-106">Scalabilità single-pass.</span><span class="sxs-lookup"><span data-stu-id="86fa2-106">Single-pass scaling.</span></span>  <span data-ttu-id="86fa2-107">In .NET Framework 4,6 e versioni precedenti, il ridimensionamento veniva eseguito attraverso più passaggi, causando la scalabilità di alcuni controlli più di quanto fosse necessario.</span><span class="sxs-lookup"><span data-stu-id="86fa2-107">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="86fa2-108">Supporto per scenari con valori DPI dinamici in cui l'utente modifica il valore DPI o il fattore di scala dopo l'avvio di un Windows Forms Application.</span><span class="sxs-lookup"><span data-stu-id="86fa2-108">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="86fa2-109">Nelle versioni del .NET Framework a partire dal .NET Framework 4,7, il supporto avanzato per DPI è una funzionalità di consenso esplicito.</span><span class="sxs-lookup"><span data-stu-id="86fa2-109">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="86fa2-110">È necessario configurare l'applicazione per sfruttarne i vantaggi.</span><span class="sxs-lookup"><span data-stu-id="86fa2-110">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="86fa2-111">Configurazione dell'app Windows Forms per il supporto di valori DPI elevati</span><span class="sxs-lookup"><span data-stu-id="86fa2-111">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="86fa2-112">Le nuove funzionalità di Windows Forms che supportano la consapevolezza DPI elevata sono disponibili solo nelle applicazioni destinate al .NET Framework 4,7 e sono in esecuzione su sistemi operativi Windows a partire da Windows 10 Creators Update.</span><span class="sxs-lookup"><span data-stu-id="86fa2-112">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span>

<span data-ttu-id="86fa2-113">Inoltre, per configurare il supporto di valori DPI alti nella Windows Forms Application, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="86fa2-113">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="86fa2-114">Dichiara la compatibilità con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="86fa2-114">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="86fa2-115">A tale scopo, aggiungere il codice seguente al file manifesto:</span><span class="sxs-lookup"><span data-stu-id="86fa2-115">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="86fa2-116">Abilitare la consapevolezza DPI per monitor nel file *app. config* .</span><span class="sxs-lookup"><span data-stu-id="86fa2-116">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="86fa2-117">Windows Forms introduce un nuovo elemento [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) per supportare le nuove funzionalità e le personalizzazioni aggiunte a partire da .NET Framework 4,7.</span><span class="sxs-lookup"><span data-stu-id="86fa2-117">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="86fa2-118">Per sfruttare i vantaggi delle nuove funzionalità che supportano valori DPI alti, aggiungere il codice seguente al file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86fa2-118">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > <span data-ttu-id="86fa2-119">Nelle versioni precedenti del .NET Framework è stato usato il manifesto per aggiungere il supporto di valori DPI alti.</span><span class="sxs-lookup"><span data-stu-id="86fa2-119">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="86fa2-120">Questo approccio non è più consigliato, poiché sostituisce le impostazioni definite nel file app. config.</span><span class="sxs-lookup"><span data-stu-id="86fa2-120">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>

- <span data-ttu-id="86fa2-121">Chiamare il metodo statico <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="86fa2-121">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>

  <span data-ttu-id="86fa2-122">Questa deve essere la prima chiamata al metodo nel punto di ingresso dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86fa2-122">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="86fa2-123">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="86fa2-123">For example:</span></span>

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="86fa2-124">Rifiutare esplicitamente le singole funzionalità DPI elevate</span><span class="sxs-lookup"><span data-stu-id="86fa2-124">Opting out of individual high DPI features</span></span>

<span data-ttu-id="86fa2-125">Impostando il valore `DpiAwareness` su `PerMonitorV2` si abilitano tutte le funzionalità di riconoscimento DPI elevato supportate dalle versioni .NET Framework a partire dal .NET Framework 4,7.</span><span class="sxs-lookup"><span data-stu-id="86fa2-125">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="86fa2-126">Questa operazione è in genere adeguata per la maggior parte delle applicazioni Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="86fa2-126">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="86fa2-127">Tuttavia, potrebbe essere necessario rifiutare esplicitamente una o più funzionalità singole.</span><span class="sxs-lookup"><span data-stu-id="86fa2-127">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="86fa2-128">Il motivo più importante per questa operazione è che il codice dell'applicazione esistente gestisce già tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="86fa2-128">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="86fa2-129">Se, ad esempio, l'applicazione gestisce la scalabilità automatica, potrebbe essere necessario disabilitare la funzionalità di ridimensionamento automatico come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="86fa2-129">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

<span data-ttu-id="86fa2-130">Per un elenco delle singole chiavi e dei relativi valori, vedere [Windows Forms Aggiungi elemento di configurazione](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span><span class="sxs-lookup"><span data-stu-id="86fa2-130">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="86fa2-131">Nuovi eventi di modifica DPI</span><span class="sxs-lookup"><span data-stu-id="86fa2-131">New DPI change events</span></span>

<span data-ttu-id="86fa2-132">A partire da .NET Framework 4,7, tre nuovi eventi consentono di gestire a livello di codice le modifiche a DPI dinamici:</span><span class="sxs-lookup"><span data-stu-id="86fa2-132">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="86fa2-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, che viene generato quando l'impostazione DPI per un controllo viene modificata a livello di codice dopo che si è verificato un evento di modifica DPI per il relativo controllo o form padre.</span><span class="sxs-lookup"><span data-stu-id="86fa2-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="86fa2-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, che viene generato quando l'impostazione DPI per un controllo viene modificata a livello di codice prima che si verifichi un evento di modifica DPI per il relativo controllo o form padre.</span><span class="sxs-lookup"><span data-stu-id="86fa2-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="86fa2-135"><xref:System.Windows.Forms.Form.DpiChanged>, che viene generato quando viene modificata l'impostazione DPI sul dispositivo di visualizzazione in cui è attualmente visualizzato il form.</span><span class="sxs-lookup"><span data-stu-id="86fa2-135"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="86fa2-136">Nuovi metodi e proprietà Helper</span><span class="sxs-lookup"><span data-stu-id="86fa2-136">New helper methods and properties</span></span>

<span data-ttu-id="86fa2-137">Il .NET Framework 4,7 aggiunge anche una serie di nuove proprietà e metodi helper che forniscono informazioni sul ridimensionamento DPI e consentono di eseguire la scalabilità DPI.</span><span class="sxs-lookup"><span data-stu-id="86fa2-137">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="86fa2-138">tra cui:</span><span class="sxs-lookup"><span data-stu-id="86fa2-138">These include:</span></span>

- <span data-ttu-id="86fa2-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, che converte un valore da Logical a Device pixel.</span><span class="sxs-lookup"><span data-stu-id="86fa2-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="86fa2-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, che consente di ridimensionare un'immagine bitmap in DPI logici per un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="86fa2-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="86fa2-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, che restituisce il valore DPI per il dispositivo corrente.</span><span class="sxs-lookup"><span data-stu-id="86fa2-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="86fa2-142">Considerazioni sul controllo delle versioni</span><span class="sxs-lookup"><span data-stu-id="86fa2-142">Versioning considerations</span></span>

<span data-ttu-id="86fa2-143">Oltre a essere in esecuzione in .NET Framework 4,7 e Windows 10 Creators Update, l'applicazione può essere eseguita anche in un ambiente in cui non è compatibile con i miglioramenti a DPI elevati.</span><span class="sxs-lookup"><span data-stu-id="86fa2-143">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="86fa2-144">In questo caso, sarà necessario sviluppare un fallback per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86fa2-144">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="86fa2-145">Questa operazione può essere eseguita per eseguire un [disegno personalizzato](./controls/user-drawn-controls.md) per gestire la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="86fa2-145">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="86fa2-146">A tale scopo, è necessario anche determinare il sistema operativo in cui è in esecuzione l'app.</span><span class="sxs-lookup"><span data-stu-id="86fa2-146">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="86fa2-147">Questa operazione può essere eseguita con codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="86fa2-147">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="86fa2-148">Si noti che l'applicazione non rileva correttamente Windows 10 se non è stato elencato come sistema operativo supportato nel manifesto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86fa2-148">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="86fa2-149">È anche possibile controllare la versione del .NET Framework in base alla quale è stata compilata l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="86fa2-149">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="86fa2-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86fa2-150">See also</span></span>

- [<span data-ttu-id="86fa2-151">Windows Forms Aggiungi elemento di configurazione</span><span class="sxs-lookup"><span data-stu-id="86fa2-151">Windows Forms Add Configuration Element</span></span>](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [<span data-ttu-id="86fa2-152">Regolazione delle dimensioni e della scala di Windows Form</span><span class="sxs-lookup"><span data-stu-id="86fa2-152">Adjusting the Size and Scale of Windows Forms</span></span>](adjusting-the-size-and-scale-of-windows-forms.md)
