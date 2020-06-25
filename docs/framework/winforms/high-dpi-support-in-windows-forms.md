---
title: Supporto di valori DPI alti
description: Informazioni sul supporto di in Windows Forms per gli scenari comuni con DPI elevato e DPI dinamici. Viene inoltre illustrato come configurare Windows Forms applicazioni per il supporto di valori DPI alti.
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
ms.openlocfilehash: a9e0766307095da447c772de5a3065c18b7b7154
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325654"
---
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="0701b-104">Supporto di valori DPI alti in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0701b-104">High DPI support in Windows Forms</span></span>

<span data-ttu-id="0701b-105">A partire da .NET Framework 4,7, Windows Forms include miglioramenti per gli scenari con valori DPI più comuni e DPI dinamici.</span><span class="sxs-lookup"><span data-stu-id="0701b-105">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="0701b-106">incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="0701b-106">These include:</span></span>

- <span data-ttu-id="0701b-107">Miglioramenti apportati alla scalabilità e al layout di un numero di controlli di Windows Forms, ad esempio il <xref:System.Windows.Forms.MonthCalendar> controllo e il <xref:System.Windows.Forms.CheckedListBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="0701b-107">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span>

- <span data-ttu-id="0701b-108">Scalabilità single-pass.</span><span class="sxs-lookup"><span data-stu-id="0701b-108">Single-pass scaling.</span></span>  <span data-ttu-id="0701b-109">In .NET Framework 4,6 e versioni precedenti, il ridimensionamento veniva eseguito attraverso più passaggi, causando la scalabilità di alcuni controlli più di quanto fosse necessario.</span><span class="sxs-lookup"><span data-stu-id="0701b-109">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="0701b-110">Supporto per scenari con valori DPI dinamici in cui l'utente modifica il valore DPI o il fattore di scala dopo l'avvio di un Windows Forms Application.</span><span class="sxs-lookup"><span data-stu-id="0701b-110">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="0701b-111">Nelle versioni del .NET Framework a partire dal .NET Framework 4,7, il supporto avanzato per DPI è una funzionalità di consenso esplicito.</span><span class="sxs-lookup"><span data-stu-id="0701b-111">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="0701b-112">È necessario configurare l'applicazione per sfruttarne i vantaggi.</span><span class="sxs-lookup"><span data-stu-id="0701b-112">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="0701b-113">Configurazione dell'app Windows Forms per il supporto di valori DPI elevati</span><span class="sxs-lookup"><span data-stu-id="0701b-113">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="0701b-114">Le nuove funzionalità di Windows Forms che supportano la consapevolezza DPI elevata sono disponibili solo nelle applicazioni destinate al .NET Framework 4,7 e sono in esecuzione su sistemi operativi Windows a partire da Windows 10 Creators Update.</span><span class="sxs-lookup"><span data-stu-id="0701b-114">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span>

<span data-ttu-id="0701b-115">Inoltre, per configurare il supporto di valori DPI alti nella Windows Forms Application, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0701b-115">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="0701b-116">Dichiara la compatibilità con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0701b-116">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="0701b-117">A tale scopo, aggiungere il codice seguente al file manifesto:</span><span class="sxs-lookup"><span data-stu-id="0701b-117">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft-com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="0701b-118">Abilitare la consapevolezza DPI per monitor nel file di *app.config* .</span><span class="sxs-lookup"><span data-stu-id="0701b-118">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="0701b-119">Windows Forms introduce un nuovo [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) elemento per supportare nuove funzionalità e personalizzazioni aggiunte a partire dal .NET Framework 4,7.</span><span class="sxs-lookup"><span data-stu-id="0701b-119">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](../configure-apps/file-schema/winforms/index.md) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="0701b-120">Per sfruttare i vantaggi delle nuove funzionalità che supportano valori DPI alti, aggiungere il codice seguente al file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0701b-120">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>
  ```

  > [!IMPORTANT]
  > <span data-ttu-id="0701b-121">Nelle versioni precedenti del .NET Framework è stato usato il manifesto per aggiungere il supporto di valori DPI alti.</span><span class="sxs-lookup"><span data-stu-id="0701b-121">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="0701b-122">Questo approccio non è più consigliato, in quanto sostituisce le impostazioni definite nel file di app.config.</span><span class="sxs-lookup"><span data-stu-id="0701b-122">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>

- <span data-ttu-id="0701b-123">Chiamare il <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> metodo statico.</span><span class="sxs-lookup"><span data-stu-id="0701b-123">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>

  <span data-ttu-id="0701b-124">Questa deve essere la prima chiamata al metodo nel punto di ingresso dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0701b-124">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="0701b-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0701b-125">For example:</span></span>

  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="0701b-126">Rifiutare esplicitamente le singole funzionalità DPI elevate</span><span class="sxs-lookup"><span data-stu-id="0701b-126">Opting out of individual high DPI features</span></span>

<span data-ttu-id="0701b-127">Impostando il `DpiAwareness` valore su si `PerMonitorV2` abilitano tutte le funzionalità di riconoscimento dpi elevato supportate dalle versioni .NET Framework a partire dal .NET Framework 4,7.</span><span class="sxs-lookup"><span data-stu-id="0701b-127">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="0701b-128">Questa operazione è in genere adeguata per la maggior parte delle applicazioni Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0701b-128">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="0701b-129">Tuttavia, potrebbe essere necessario rifiutare esplicitamente una o più funzionalità singole.</span><span class="sxs-lookup"><span data-stu-id="0701b-129">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="0701b-130">Il motivo più importante per questa operazione è che il codice dell'applicazione esistente gestisce già tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0701b-130">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="0701b-131">Se, ad esempio, l'applicazione gestisce la scalabilità automatica, potrebbe essere necessario disabilitare la funzionalità di ridimensionamento automatico come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0701b-131">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

<span data-ttu-id="0701b-132">Per un elenco delle singole chiavi e dei relativi valori, vedere [Windows Forms Aggiungi elemento di configurazione](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span><span class="sxs-lookup"><span data-stu-id="0701b-132">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="0701b-133">Nuovi eventi di modifica DPI</span><span class="sxs-lookup"><span data-stu-id="0701b-133">New DPI change events</span></span>

<span data-ttu-id="0701b-134">A partire da .NET Framework 4,7, tre nuovi eventi consentono di gestire a livello di codice le modifiche a DPI dinamici:</span><span class="sxs-lookup"><span data-stu-id="0701b-134">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="0701b-135"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, che viene generato quando l'impostazione DPI per un controllo viene modificata a livello di codice dopo che si è verificato un evento di modifica DPI per il relativo controllo o form padre.</span><span class="sxs-lookup"><span data-stu-id="0701b-135"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="0701b-136"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, che viene generato quando l'impostazione DPI per un controllo viene modificata a livello di codice prima che si verifichi un evento di modifica DPI per il relativo controllo o form padre.</span><span class="sxs-lookup"><span data-stu-id="0701b-136"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="0701b-137"><xref:System.Windows.Forms.Form.DpiChanged>, che viene generato quando viene modificata l'impostazione DPI sul dispositivo di visualizzazione in cui è attualmente visualizzato il form.</span><span class="sxs-lookup"><span data-stu-id="0701b-137"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="0701b-138">Nuovi metodi e proprietà Helper</span><span class="sxs-lookup"><span data-stu-id="0701b-138">New helper methods and properties</span></span>

<span data-ttu-id="0701b-139">Il .NET Framework 4,7 aggiunge anche una serie di nuove proprietà e metodi helper che forniscono informazioni sul ridimensionamento DPI e consentono di eseguire la scalabilità DPI.</span><span class="sxs-lookup"><span data-stu-id="0701b-139">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="0701b-140">incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="0701b-140">These include:</span></span>

- <span data-ttu-id="0701b-141"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, che converte un valore da Logical a Device pixel.</span><span class="sxs-lookup"><span data-stu-id="0701b-141"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="0701b-142"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, che consente di ridimensionare un'immagine bitmap in DPI logici per un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0701b-142"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="0701b-143"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, che restituisce il valore DPI per il dispositivo corrente.</span><span class="sxs-lookup"><span data-stu-id="0701b-143"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="0701b-144">Considerazioni sul controllo delle versioni</span><span class="sxs-lookup"><span data-stu-id="0701b-144">Versioning considerations</span></span>

<span data-ttu-id="0701b-145">Oltre a essere in esecuzione in .NET Framework 4,7 e Windows 10 Creators Update, l'applicazione può essere eseguita anche in un ambiente in cui non è compatibile con i miglioramenti a DPI elevati.</span><span class="sxs-lookup"><span data-stu-id="0701b-145">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="0701b-146">In questo caso, sarà necessario sviluppare un fallback per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0701b-146">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="0701b-147">Questa operazione può essere eseguita per eseguire un [disegno personalizzato](./controls/user-drawn-controls.md) per gestire la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="0701b-147">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="0701b-148">A tale scopo, è necessario anche determinare il sistema operativo in cui è in esecuzione l'app.</span><span class="sxs-lookup"><span data-stu-id="0701b-148">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="0701b-149">Questa operazione può essere eseguita con codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0701b-149">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="0701b-150">Si noti che l'applicazione non rileva correttamente Windows 10 se non è stato elencato come sistema operativo supportato nel manifesto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0701b-150">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="0701b-151">È anche possibile controllare la versione del .NET Framework in base alla quale è stata compilata l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="0701b-151">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="0701b-152">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="0701b-152">See also</span></span>

- [<span data-ttu-id="0701b-153">Windows Forms Aggiungi elemento di configurazione</span><span class="sxs-lookup"><span data-stu-id="0701b-153">Windows Forms Add Configuration Element</span></span>](../configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [<span data-ttu-id="0701b-154">Regolazione delle dimensioni e della scala di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0701b-154">Adjusting the Size and Scale of Windows Forms</span></span>](adjusting-the-size-and-scale-of-windows-forms.md)
