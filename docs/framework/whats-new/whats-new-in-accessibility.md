---
title: Nuove funzionalità di accessibilità in .NET Framework
ms.custom: updateeachrelease
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
ms.openlocfilehash: 6f17cb0fb6e5b0457af745ea0d089f3e51d4706c
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938152"
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="0f6dc-102">Nuove funzionalità di accessibilità in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0f6dc-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="0f6dc-103">Uno degli obiettivi di .NET Framework è rendere le applicazioni più accessibili per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-103">The .NET Framework aims at making applications more accessible for your users.</span></span> <span data-ttu-id="0f6dc-104">Le funzionalità di accessibilità consentono a un'applicazione di offrire un'esperienza appropriata per gli utenti di assistive technology.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="0f6dc-105">A partire da .NET Framework 4.7.1, .NET Framework include numerosi miglioramenti per l'accessibilità che consentono agli sviluppatori di creare applicazioni accessibili.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-105">Starting with .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span>

## <a name="accessibility-switches"></a><span data-ttu-id="0f6dc-106">Opzioni di accessibilità</span><span class="sxs-lookup"><span data-stu-id="0f6dc-106">Accessibility switches</span></span>

<span data-ttu-id="0f6dc-107">È possibile configurare l'app per acconsentire esplicitamente alle funzionalità di accessibilità se l'app è destinata a .NET Framework 4.7 o a una versione precedente, ma viene eseguita in .NET Framework 4.7.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-107">You can configure your app to opt into accessibility features if it targets .NET Framework 4.7 or an earlier version but is running on .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="0f6dc-108">È anche possibile configurare l'app per usare le funzionalità legacy (e rinunciare alle funzionalità di accessibilità) se l'app è destinata a .NET Framework 4.7.1 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-108">You can also configure your app to use legacy features (and not take advantage of accessibility features) if it targets .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="0f6dc-109">Ogni versione di .NET Framework che include funzionalità di accessibilità ha un'opzione di accessibilità specifica per la versione, che è possibile aggiungere all'elemento [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [`<runtime>`](../configure-apps/file-schema/runtime/index.md) del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-109">Each version of the .NET Framework that includes accessibility features has a version-specific accessibility switch, which you add to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> <span data-ttu-id="0f6dc-110">Le opzioni supportate sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-110">The following are the supported switches:</span></span>

|<span data-ttu-id="0f6dc-111">Versione</span><span class="sxs-lookup"><span data-stu-id="0f6dc-111">Version</span></span>|<span data-ttu-id="0f6dc-112">Opzione</span><span class="sxs-lookup"><span data-stu-id="0f6dc-112">Switch</span></span>|
|---|---|
|<span data-ttu-id="0f6dc-113">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="0f6dc-113">.NET Framework 4.7.1</span></span>|<span data-ttu-id="0f6dc-114">"Switch.UseLegacyAccessibilityFeatures"</span><span class="sxs-lookup"><span data-stu-id="0f6dc-114">"Switch.UseLegacyAccessibilityFeatures"</span></span>|
|<span data-ttu-id="0f6dc-115">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="0f6dc-115">.NET Framework 4.7.2</span></span>|<span data-ttu-id="0f6dc-116">"Switch.UseLegacyAccessibilityFeatures.2"</span><span class="sxs-lookup"><span data-stu-id="0f6dc-116">"Switch.UseLegacyAccessibilityFeatures.2"</span></span>|
|<span data-ttu-id="0f6dc-117">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="0f6dc-117">.NET Framework 4.8</span></span>|<span data-ttu-id="0f6dc-118">"Switch.UseLegacyAccessibilityFeatures.3"</span><span class="sxs-lookup"><span data-stu-id="0f6dc-118">"Switch.UseLegacyAccessibilityFeatures.3"</span></span>|

### <a name="taking-advantage-of-accessibility-enhancements"></a><span data-ttu-id="0f6dc-119">Sfruttare i vantaggi dei miglioramenti all'accessibilità</span><span class="sxs-lookup"><span data-stu-id="0f6dc-119">Taking advantage of accessibility enhancements</span></span>

<span data-ttu-id="0f6dc-120">Le nuove funzionalità di accessibilità sono abilitate per impostazione predefinita per le applicazioni destinate a .NET Framework 4.7.1 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-120">The new accessibility features are enabled by default for applications that target .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="0f6dc-121">Inoltre, le applicazioni destinate a una versione precedente di .NET Framework ma eseguite in .NET Framework 4.7.1 o versioni successive possono rifiutare esplicitamente comportamenti di accessibilità legacy (potendo così sfruttare i miglioramenti dell'accessibilità) aggiungendo opzioni all'elemento [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [`<runtime>`](../configure-apps/file-schema/runtime/index.md) del file di configurazione dell'applicazione e impostandone il valore su `false`.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-121">In addition, applications that target an earlier version of the .NET Framework but are running on .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby take advantage of accessibility improvements) by adding switches to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `false`.</span></span> <span data-ttu-id="0f6dc-122">Di seguito viene illustrato come acconsentire esplicitamente ai miglioramenti apportati all'accessibilità introdotti in .NET Framework 4.7.1:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-122">The following shows how to opt in to accessibility enhancements introduced in .NET Framework 4.7.1:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="0f6dc-123">Se si sceglie di acconsentire esplicitamente alle funzionalità di accessibilità in una versione successiva di .NET Framework, è necessario anche acconsentire esplicitamente alle funzionalità di versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-123">If you choose to opt in to accessibility features in a later version of the .NET Framework, you must also explicitly opt in to the features from earlier versions of the .NET Framework.</span></span> <span data-ttu-id="0f6dc-124">La configurazione dell'app per sfruttare i miglioramenti all'accessibilità in .NET Framework 4.7.1 e 4.7.2 richiede l'elemento [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-124">Configuring your app to take advantage of accessibility improvements in both .NET Framework 4.7.1 and 4.7.2 requires the following [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

<span data-ttu-id="0f6dc-125">La configurazione dell'app per sfruttare i miglioramenti all'accessibilità in .NET Framework 4.7.1, 4.7.2 e 4.8 richiede l'elemento [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguente:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-125">Configuring your app to take advantage of accessibility improvements in .NET Framework 4.7.1, 4.7.2, and 4.8 requires the following [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;Switch.UseLegacyAccessibilityFeatures.3=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a><span data-ttu-id="0f6dc-126">Ripristino del comportamento legacy</span><span class="sxs-lookup"><span data-stu-id="0f6dc-126">Restoring legacy behavior</span></span>

<span data-ttu-id="0f6dc-127">Le applicazioni destinate alle versioni di .NET Framework a partire dalla 4.7.1 possono disabilitare le funzionalità di accessibilità aggiungendo opzioni all'elemento [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [`<runtime>`](../configure-apps/file-schema/runtime/index.md) del file di configurazione dell'applicazione e impostandone il valore su `true`.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-127">Applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding switches to the [`<AppContextSwitchOverrides>`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](../configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `true`.</span></span> <span data-ttu-id="0f6dc-128">Ad esempio, la configurazione seguente rifiuta esplicitamente le funzionalità di accessibilità introdotte in .NET Framework 4.7.2:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-128">For example, the following configuration opts out of accessibility features introduced in .NET Framework 4.7.2:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-net-framework-48"></a><span data-ttu-id="0f6dc-129">Nuove funzionalità di accessibilità in .NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="0f6dc-129">What's new in accessibility in .NET Framework 4.8</span></span>

<span data-ttu-id="0f6dc-130">.NET Framework 4.8 include nuove funzionalità di accessibilità nelle aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-130">.NET Framework 4.8 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="0f6dc-131">Windows Form</span><span class="sxs-lookup"><span data-stu-id="0f6dc-131">Windows Forms</span></span>](#winforms48)

- [<span data-ttu-id="0f6dc-132">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="0f6dc-132">Windows Presentation Foundation (WPF)</span></span>](#wpf48)

- [<span data-ttu-id="0f6dc-133">Progettazione flussi di lavoro di Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="0f6dc-133">Windows Workflow Foundation (WF) workflow designer</span></span>](#wf48)

<a name="winforms48" />

### <a name="windows-forms"></a><span data-ttu-id="0f6dc-134">Windows Form</span><span class="sxs-lookup"><span data-stu-id="0f6dc-134">Windows Forms</span></span>

<span data-ttu-id="0f6dc-135">In .NET Framework 4.8 Windows Forms aggiunge il supporto per le aree dinamiche e gli eventi di notifica a numerosi controlli usati di frequente.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-135">In .NET Framework 4.8, Windows Forms adds support for LiveRegions and Notification Events to many commonly used controls.</span></span> <span data-ttu-id="0f6dc-136">Aggiunge anche il supporto per le descrizioni comando quando l'utente passa a un controllo usando la tastiera.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-136">It also adds support for ToolTips when a user navigates to a control by using the keyboard.</span></span>

<span data-ttu-id="0f6dc-137">**Supporto delle aree dinamiche di automazione interfaccia utente nelle etichette e nelle barre di stato**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-137">**UIA LiveRegions Support in Labels and StatusStrips**</span></span>

<span data-ttu-id="0f6dc-138">Le aree dinamiche di automazione interfaccia utente consentono agli sviluppatori di applicazioni di notificare alle utilità per la lettura dello schermo una modifica del testo in un controllo che si trova in un'altra posizione rispetto alla posizione attuale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-138">UIA LiveRegions allow application developers to notify screen readers of a text change in a control that is located apart from the location where the user is working.</span></span> <span data-ttu-id="0f6dc-139">Questa funzionalità è utile ad esempio per i controlli <xref:System.Windows.Forms.StatusStrip> che visualizzano lo stato di una connessione.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-139">This is useful, for example, for a <xref:System.Windows.Forms.StatusStrip> control that shows a connection status.</span></span> <span data-ttu-id="0f6dc-140">Se la connessione viene interrotta e lo stato viene modificato, è possibile che lo sviluppatore voglia inviare una notifica all'utilità per la lettura dello schermo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-140">If the connection is dropped and the status changes, the developer might want to notify the screen reader.</span></span>

<span data-ttu-id="0f6dc-141">A partire da .NET Framework 4.8, Windows Forms implementa le aree dinamiche di automazione interfaccia utente per entrambi i controlli <xref:System.Windows.Forms.Label> e <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-141">Starting with .NET Framework 4.8, Windows Forms implements UIA LiveRegions for both the <xref:System.Windows.Forms.Label> and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="0f6dc-142">Ad esempio, il codice seguente usa l'area dinamica in un controllo <xref:System.Windows.Forms.Label> denominato `label1`:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-142">For example, the following code uses the LiveRegion in a <xref:System.Windows.Forms.Label> control named `label1`:</span></span>

```csharp
public Form1()
{
   InitializeComponent();
   label1.AutomationLiveSetting = AutomationLiveSetting.Polite;
}

…
Label1.Text = “Ready!”;
```

<span data-ttu-id="0f6dc-143">L'Assistente vocale annuncia "Pronto" indipendentemente dalla posizione in cui l'utente interagisce con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-143">Narrator announces “Ready” regardless of where the user is interacting with the application.</span></span>

<span data-ttu-id="0f6dc-144">È anche possibile implementare <xref:System.Windows.Forms.UserControl> come area dinamica:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-144">You can also implement your <xref:System.Windows.Forms.UserControl> as a LiveRegion:</span></span>

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

<span data-ttu-id="0f6dc-145">**Eventi di notifica di automazione interfaccia utente**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-145">**UIA notification events**</span></span>

<span data-ttu-id="0f6dc-146">L'evento di notifica di automazione interfaccia utente, introdotto in Windows 10 Fall Creators Update, consente all'app di generare un evento di automazione interfaccia utente in modo che l'Assistente vocale emetta un annuncio in base al testo immesso con l'evento anche senza un controllo corrispondente nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-146">The UIA Notification event, introduced in Windows 10 Fall Creators Update, allows your app to raise a UIA event, which leads to Narrator simply making an announcement based on text you supply with the event, without the need to have a corresponding control in the UI.</span></span> <span data-ttu-id="0f6dc-147">In alcuni scenari questo è un modo semplice per migliorare notevolmente l'accessibilità dell'app.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-147">In some scenarios, this is a straightforward way to dramatically improve the accessibility of your app.</span></span> <span data-ttu-id="0f6dc-148">Può essere utile anche notificare lo stato di avanzamento di un processo che potrebbe richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-148">In can also be useful to notify of the progress of some process that may take a long time.</span></span> <span data-ttu-id="0f6dc-149">Per altre informazioni sugli eventi di notifica di automazione interfaccia utente, vedere [Can your desktop app leverage the new UI Notification event?](https://docs.microsoft.com/archive/blogs/winuiautomation/can-your-desktop-app-leverage-the-new-uia-notification-event-in-order-to-have-narrator-say-exactly-what-your-customers-need) (L'app desktop può usare il nuovo evento di notifica dell'interfaccia utente?).</span><span class="sxs-lookup"><span data-stu-id="0f6dc-149">For more information about UIA Notification Events, see [Can your desktop app leverage the new UI Notification event?](https://docs.microsoft.com/archive/blogs/winuiautomation/can-your-desktop-app-leverage-the-new-uia-notification-event-in-order-to-have-narrator-say-exactly-what-your-customers-need).</span></span>

<span data-ttu-id="0f6dc-150">L'esempio seguente genera l'[evento di notifica](xref:System.Windows.Forms.AccessibleObject.RaiseAutomationNotification%2A):</span><span class="sxs-lookup"><span data-stu-id="0f6dc-150">The following example raises the [Notification event](xref:System.Windows.Forms.AccessibleObject.RaiseAutomationNotification%2A):</span></span>

```csharp
MethodInfo raiseMethod = typeof(AccessibleObject).GetMethod("RaiseAutomationNotification");
if (raiseMethod != null) {
   raiseMethod.Invoke(progressBar1.AccessibilityObject, new object[3] {/*Other*/ 4, /*All*/ 2, "The progress is 50%." });
}
```

<span data-ttu-id="0f6dc-151">**Descrizioni comando nell'accesso da tastiera**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-151">**ToolTips on keyboard access**</span></span>

<span data-ttu-id="0f6dc-152">Nelle applicazioni destinate a .NET Framework 4.7.2 e versioni precedenti un controllo [descrizione comando](xref:System.Windows.Forms.ToolTip) può essere attivato e visualizzato spostando il puntatore del mouse sul controllo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-152">In applications that target .NET Framework 4.7.2 and earlier versions, a control [tooltip](xref:System.Windows.Forms.ToolTip) can only be triggered to pop up by moving a mouse pointer into the control.</span></span> <span data-ttu-id="0f6dc-153">A partire da .NET Framework 4.8 un utente della tastiera può attivare la descrizione comando del controllo evidenziando il controllo tramite il tasto TAB o i tasti di direzione con o senza tasti di modifica.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-153">Starting with .NET Framework 4.8, a keyboard user can trigger a control’s tooltip by focusing the control using a Tab key or arrow keys with or without modifier keys.</span></span> <span data-ttu-id="0f6dc-154">Questo specifico miglioramento dell'accessibilità richiede un'[opzione AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) aggiuntiva:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-154">This particular accessibility enhancement requires an additional [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md):</span></span>

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

<span data-ttu-id="0f6dc-155">La figura seguente mostra la descrizione comando visualizzata quando l'utente seleziona un pulsante con la tastiera.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-155">The following figure shows the tooltip when the user has selected a button with the keyboard.</span></span>

![Screenshot della descrizione comando quando l'utente passa al pulsante con la tastiera.](./media/whats-new-in-accessibility/select-tooltip-with-keyboard.png)

<a name="wpf48" />

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="0f6dc-157">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="0f6dc-157">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="0f6dc-158">A partire da .NET Framework 4.8, WPF include una serie di miglioramenti dell'accessibilità.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-158">Starting with .NET Framework 4.8, WPF includes a number of accessibility improvements.</span></span>

<span data-ttu-id="0f6dc-159">**Gli assistenti vocali dello schermo non annunciano più gli elementi con visibilità Compresso o Nascosto**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-159">**Screen narrators no longer announce elements with Collapsed or Hidden visibility**</span></span>

<span data-ttu-id="0f6dc-160">Gli elementi con visibilità Compresso o Nascosto non sono più annunciati dalle utilità per la lettura dello schermo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-160">Elements with collapsed or hidden visibility are no longer announced by screen reader.</span></span> <span data-ttu-id="0f6dc-161">Le interfacce utente che contengono elementi con visibilità <xref:System.Windows.Visibility.Collapsed?displayProperty=nameWithType> o <xref:System.Windows.Visibility.Hidden?displayProperty=nameWithType> possono essere interpretate erroneamente dalle utilità per la lettura dello schermo se vengono annunciate all'utente.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-161">User interfaces that contain elements with a Visibility of <xref:System.Windows.Visibility.Collapsed?displayProperty=nameWithType> or <xref:System.Windows.Visibility.Hidden?displayProperty=nameWithType> can be misrepresented by screen readers if they are announced to the user.</span></span> <span data-ttu-id="0f6dc-162">A partire da .NET Framework 4.8, poiché WPF non include più gli elementi compressi o nascosti nella visualizzazione dei controlli dell'albero di automazione interfaccia utente, le utilità per la lettura dello schermo non possono più annunciare questi elementi.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-162">Starting with .NET Framework 4.8, WPF no longer includes collapsed or hidden elements in the Control View of the UIAutomation tree, so the screen readers can no longer announce these elements.</span></span>

<span data-ttu-id="0f6dc-163">**Proprietà SelectionTextBrush da usare con una selezione testo non basata su Adorner**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-163">**SelectionTextBrush property for use with non-Adorner based text selection**</span></span>

<span data-ttu-id="0f6dc-164">In .NET Framework 4.7.2, WPF ha aggiunto la possibilità di disegnare una selezione testo <xref:System.Windows.Controls.TextBox> e <xref:System.Windows.Controls.PasswordBox> senza usare il livello Adorner.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-164">In the .NET Framework 4.7.2, WPF added the ability to draw <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.PasswordBox> text selection without using the Adorner layer.</span></span> <span data-ttu-id="0f6dc-165">Il colore primo piano del testo selezionato in questo scenario è determinato da <xref:System.Windows.SystemColors.HighlightTextBrush?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-165">The foreground color of the selected text in this scenario was dictated by <xref:System.Windows.SystemColors.HighlightTextBrush?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="0f6dc-166">.NET Framework 4.8 aggiunge una nuova proprietà, `SelectionTextBrush`, che consente agli sviluppatori di selezionare il pennello specifico per il testo selezionato durante l'uso di una selezione testo non basata su Adorner.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-166">.NET Framework 4.8 adds a new property, `SelectionTextBrush`, that allows developers to select the specific brush for the selected text when using non-Adorner based text selection.</span></span> <span data-ttu-id="0f6dc-167">Questa proprietà funziona solo nei controlli derivati da <xref:System.Windows.Controls.Primitives.TextBoxBase> e nel controllo <xref:System.Windows.Controls.PasswordBox> nelle applicazioni in WPF con una selezione testo non basata su Adorner abilitata.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-167">This property works only on <xref:System.Windows.Controls.Primitives.TextBoxBase>-derived controls and the <xref:System.Windows.Controls.PasswordBox> control in WPF applications with non-Adorner-based text selection enabled.</span></span> <span data-ttu-id="0f6dc-168">Non funziona nel controllo <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-168">It does not work on the <xref:System.Windows.Controls.RichTextBox> control.</span></span> <span data-ttu-id="0f6dc-169">Se non è abilitata una selezione testo non basata su Adorner, questa proprietà viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-169">If non-Adorner-based text selection is not enabled, this property is ignored.</span></span>

<span data-ttu-id="0f6dc-170">Per usare questa proprietà, è sufficiente aggiungerla al codice XAML e usare il pennello o l'associazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-170">To use this property, simply add it to your XAML code and use the appropriate brush or binding.</span></span> <span data-ttu-id="0f6dc-171">La selezione testo risultante è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-171">The resulting text selection looks like this:</span></span>

![Screenshot dell'app in esecuzione con le parole Hello World selezionate.](./media/whats-new-in-accessibility/selectiontextbrush-property.png)

<span data-ttu-id="0f6dc-173">È possibile usare insieme le proprietà `SelectionBrush` e `SelectionTextBrush` per generare qualsiasi combinazione di colore primo piano e colore di sfondo che si ritiene appropriata.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-173">You can combine the use of the `SelectionBrush` and `SelectionTextBrush` properties to generate any background and foreground color combination that you deem appropriate.</span></span>

<span data-ttu-id="0f6dc-174">**Supporto per la proprietà ControllerFor di automazione interfaccia utente**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-174">**Support for the UIAutomation ControllerFor property**</span></span>

<span data-ttu-id="0f6dc-175">La proprietà `ControllerFor` di automazione interfaccia utente restituisce una matrice di elementi di automazione che vengono modificati dall'elemento di automazione che supporta la proprietà.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-175">UIAutomation’s `ControllerFor` property returns an array of automation elements that are manipulated by the automation element that supports this property.</span></span> <span data-ttu-id="0f6dc-176">Questa proprietà viene in genere usata per l'accessibilità dei suggerimenti automatici.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-176">This property is commonly used for Auto-suggest accessibility.</span></span> <span data-ttu-id="0f6dc-177">La proprietà `ControllerFor` viene usata quando un elemento di automazione ha effetto su uno o più segmenti dell'interfaccia utente dell'applicazione e del desktop.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-177">`ControllerFor` is used when an automation element affects one or more segments of the application UI or the desktop.</span></span> <span data-ttu-id="0f6dc-178">In caso contrario, è difficile associare l'impatto del controllo sugli elementi dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-178">Otherwise, it is hard to associate the impact of the control operation with UI elements.</span></span> <span data-ttu-id="0f6dc-179">Questa funzionalità aggiunge ai controlli la capacità di specificare un valore per la proprietà `ControllerFor`.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-179">This feature adds the ability for controls to provide a value for the `ControllerFor` property.</span></span>

<span data-ttu-id="0f6dc-180">.NET Framework 4.8 aggiunge il nuovo metodo virtuale <xref:System.Windows.Automation.Peers.AutomationPeer.GetControlledPeersCore?displayProperty=nameWithType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-180">.NET Framework 4.8 adds a new virtual method, <xref:System.Windows.Automation.Peers.AutomationPeer.GetControlledPeersCore?displayProperty=nameWithType?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0f6dc-181">Per specificare un valore per la proprietà `ControllerFor`, è sufficiente eseguire l'override del metodo e restituire `List<AutomationPeer>` per i controlli modificati da <xref:System.Windows.Automation.Peers.AutomationPeer>:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-181">To provide a value for the `ControllerFor` property, simply override this method and return a `List<AutomationPeer>` for the controls being manipulated by this <xref:System.Windows.Automation.Peers.AutomationPeer>:</span></span>

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

<span data-ttu-id="0f6dc-182">**Descrizioni comando nell'accesso da tastiera**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-182">**Tooltips on keyboard access**</span></span>

<span data-ttu-id="0f6dc-183">In .NET Framework 4.7.2 e versioni precedenti le descrizioni comando vengono visualizzate solo quando l'utente posiziona il cursore del mouse su un controllo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-183">In .NET Framework 4.7.2 and earlier versions, tooltips display only when the user hovers the mouse cursor over a control.</span></span> <span data-ttu-id="0f6dc-184">In .NET Framework 4.8 le descrizioni comando vengono visualizzate anche con lo stato attivo della tastiera e tramite un tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-184">In .NET Framework 4.8, tooltips also display on keyboard focus, as well as via a keyboard shortcut.</span></span>

<span data-ttu-id="0f6dc-185">Per abilitare questa funzionalità, un'applicazione deve avere come destinazione .NET Framework 4,8 o acconsentire esplicitamente usando le opzioni di `Switch.UseLegacyAccessibilityFeatures.3` e `Switch.UseLegacyToolTipDisplay` [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) .</span><span class="sxs-lookup"><span data-stu-id="0f6dc-185">To enable this feature, an application needs to target .NET Framework 4.8 or opt-in by using the `Switch.UseLegacyAccessibilityFeatures.3` and `Switch.UseLegacyToolTipDisplay` [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switches.</span></span> <span data-ttu-id="0f6dc-186">Di seguito è riportato un file di configurazione dell'applicazione di esempio:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-186">The following is a sample application configuration file:</span></span>

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

<span data-ttu-id="0f6dc-187">Dopo l'abilitazione, tutti i controlli che contengono una descrizione comando visualizzano la descrizione quando il controllo ottiene lo stato attivo della tastiera.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-187">Once enabled, all controls that contain a tooltip display it once the control receives keyboard focus.</span></span> <span data-ttu-id="0f6dc-188">La descrizione comando può essere nascosta dopo un determinato periodo di tempo o quando viene modificato lo stato attivo della tastiera.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-188">The tooltip can be dismissed over time or when the keyboard focus changes.</span></span> <span data-ttu-id="0f6dc-189">Gli utenti possono anche nascondere la descrizione comando manualmente usando i nuovi tasti di scelta rapida CTRL+MAIUSC+F10.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-189">Users can also dismiss the tooltip manually by using a new keyboard shortcut, Ctrl + Shift + F10.</span></span> <span data-ttu-id="0f6dc-190">Dopo aver nascosto la descrizione comando è possibile visualizzarla nuovamente usando gli stessi tasti di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-190">Once the tooltip has been dismissed it can be displayed again by using the same keyboard shortcut.</span></span>

> [!NOTE]
> <span data-ttu-id="0f6dc-191">Le [descrizioni comando della barra multifunzione](xref:System.Windows.Controls.Ribbon.RibbonToolTip) nei controlli <xref:System.Windows.Controls.Ribbon.Ribbon> non verranno visualizzate nello stato attivo della tastiera, ma soltanto tramite i tasti di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-191">[Ribbon tooltips](xref:System.Windows.Controls.Ribbon.RibbonToolTip) on <xref:System.Windows.Controls.Ribbon.Ribbon> controls won’t show on keyboard focus; they only show via the keyboard shortcut.</span></span>

<span data-ttu-id="0f6dc-192">**Aggiunta del supporto per le proprietà di automazione interfaccia utente SizeOfSet e PositionInSet**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-192">**Added Support for SizeOfSet and PositionInSet UIAutomation properties**</span></span>

<span data-ttu-id="0f6dc-193">In Windows 10 sono state introdotte due nuove proprietà di automazione interfaccia utente, `SizeOfSet` e `PositionInSet`, che vengono usate dalle applicazioni per descrivere il conteggio degli elementi in un set.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-193">Windows 10 introduced two new UIAutomation properties, `SizeOfSet` and `PositionInSet`, which are used by applications to describe the count of items in a set.</span></span> <span data-ttu-id="0f6dc-194">Le applicazioni client di automazione interfaccia utente, ad esempio le utilità per la lettura dello schermo, possono quindi ricercare queste proprietà in un'applicazione e annunciare una rappresentazione accurata dell'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-194">UIAutomation client applications such as screen readers can then query an application for these properties and announce an accurate representation of the application’s UI.</span></span>

<span data-ttu-id="0f6dc-195">A partire da .NET Framework 4.8, WPF espone queste due proprietà per l'automazione interfaccia utente nelle applicazioni WPF.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-195">Starting with .NET Framework 4.8, WPF  exposes these two properties to UIAutomation in WPF applications.</span></span> <span data-ttu-id="0f6dc-196">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-196">This can be accomplished in two ways:</span></span>

- <span data-ttu-id="0f6dc-197">Usando le proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-197">By using dependency properties.</span></span>

  <span data-ttu-id="0f6dc-198">WPF aggiunge due nuove proprietà di dipendenza, <xref:System.Windows.Automation.AutomationProperties.SizeOfSet?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationProperties.PositionInSet?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-198">WPF adds two new dependency properties, <xref:System.Windows.Automation.AutomationProperties.SizeOfSet?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.PositionInSet?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0f6dc-199">Gli sviluppatori possono impostarne i valori usando XAML:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-199">A developer can use XAML to set their values:</span></span>

  ```xaml
  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="1">Button 1</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="2">Button 2</Button>

  <Button AutomationProperties.SizeOfSet="3"
    AutomationProperties.PositionInSet="3">Button 3</Button>
  ```

- <span data-ttu-id="0f6dc-200">Eseguendo l'override di metodi virtuali di AutomationPeer.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-200">By overriding AutomationPeer virtual methods.</span></span>

  <span data-ttu-id="0f6dc-201">I metodi virtuali <xref:System.Windows.Automation.Peers.AutomationPeer.GetSizeOfSetCore> e <xref:System.Windows.Automation.Peers.AutomationPeer.GetPositionInSetCore> sono stati aggiunti alla classe AutomationPeer.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-201">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetSizeOfSetCore> and <xref:System.Windows.Automation.Peers.AutomationPeer.GetPositionInSetCore> virtual methods been added to the AutomationPeer class.</span></span> <span data-ttu-id="0f6dc-202">Gli sviluppatori possono specificare i valori di `SizeOfSet` e `PositionInSet` eseguendo l'override di questi metodi, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-202">A developer can provide values for `SizeOfSet` and `PositionInSet` by overriding these methods, as shown in the following example:</span></span>

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

<span data-ttu-id="0f6dc-203">Inoltre, gli elementi nelle istanze <xref:System.Windows.Controls.ItemsControl> specificano automaticamente un valore per queste proprietà senza ulteriori azioni da parte dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-203">In addition, items in <xref:System.Windows.Controls.ItemsControl> instances provide a value for these properties automatically without additional action from the developer.</span></span> <span data-ttu-id="0f6dc-204">Se <xref:System.Windows.Controls.ItemsControl> è raggruppato, la raccolta di gruppi è rappresentata come set e ogni gruppo viene conteggiato come set separato in cui ogni elemento all'interno del gruppo specifica la propria posizione all'interno del gruppo e le dimensioni del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-204">If an <xref:System.Windows.Controls.ItemsControl> is grouped, the collection of groups is represented as a set, and each group is counted as a separate set, with each item inside that group providing its position inside that group as well as the size of the group.</span></span> <span data-ttu-id="0f6dc-205">La virtualizzazione non ha effetto sui valori automatici.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-205">Automatic values are not affected by virtualization.</span></span> <span data-ttu-id="0f6dc-206">Anche se un elemento non è realizzato, viene comunque conteggiato nelle dimensioni totali del set e influisce sulla posizione dei relativi elementi di pari livello nel set.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-206">Even if an item is not realized, it is still counted toward the total size of the set and affects the position in the set of its sibling items.</span></span>

<span data-ttu-id="0f6dc-207">I valori automatici vengono forniti solo se l'applicazione è destinata a .NET Framework 4.8.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-207">Automatic values are only provided if the application targets .NET Framework 4.8.</span></span> <span data-ttu-id="0f6dc-208">Per le applicazioni destinate a una versione precedente del .NET Framework, è possibile impostare l' [opzione `Switch.UseLegacyAccessibilityFeatures.3` AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md), come illustrato nel file app. config seguente:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-208">For applications that target an earlier version of the .NET Framework, you can set the `Switch.UseLegacyAccessibilityFeatures.3` [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md), as shown in the following App.config file:</span></span>

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

### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="0f6dc-209">Progettazione dei flussi di lavoro di Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="0f6dc-209">Windows Workflow Foundation (WF) workflow designer</span></span>

<span data-ttu-id="0f6dc-210">La finestra di progettazione dei flussi di lavoro include le modifiche seguenti in .NET Framework 4.8:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-210">The workflow designer includes the following changes in .NET Framework 4.8:</span></span>

- <span data-ttu-id="0f6dc-211">Gli utenti che usano l'Assistente vocale noteranno miglioramenti nelle etichette case FlowSwitch.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-211">Users using Narrator will see improvements in FlowSwitch case labels.</span></span>

- <span data-ttu-id="0f6dc-212">Gli utenti che usano l'Assistente vocale noteranno miglioramenti nelle descrizioni dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-212">Users using Narrator will see improvements in button descriptions.</span></span>

- <span data-ttu-id="0f6dc-213">Gli utenti che usano i temi a contrasto elevato noteranno miglioramenti nella visibilità di Progettazione flussi di lavoro e nei relativi controlli, ad esempio rapporti di contrasto più definiti tra gli elementi e caselle di selezione più evidenti per gli elementi con lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-213">Users who choose High Contrast themes will see improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

<span data-ttu-id="0f6dc-214">Se l'applicazione è destinata a .NET Framework 4.7.2 o a una versione precedente, è possibile acconsentire esplicitamente a queste modifiche impostando l' [opzione `Switch.UseLegacyAccessibilityFeatures.3` AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) su `false` nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-214">If your application targets .NET Framework 4.7.2 or an earlier version, you can opt into these changes by setting the `Switch.UseLegacyAccessibilityFeatures.3` [AppContext switch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to `false` in your application configuration file.</span></span> <span data-ttu-id="0f6dc-215">Per altre informazioni, vedere la sezione [Sfruttare i vantaggi dei miglioramenti all'accessibilità](#taking-advantage-of-accessibility-enhancements) in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-215">For more information, see the [Taking advantage of accessibility enhancements](#taking-advantage-of-accessibility-enhancements) section in this article.</span></span>

## <a name="whats-new-in-accessibility-in-net-framework-472"></a><span data-ttu-id="0f6dc-216">Nuove funzionalità di accessibilità in .NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="0f6dc-216">What's new in accessibility in .NET Framework 4.7.2</span></span>

<span data-ttu-id="0f6dc-217">.NET Framework 4.7.2 include nuove funzionalità di accessibilità nelle aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-217">.NET Framework 4.7.2 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="0f6dc-218">Windows Form</span><span class="sxs-lookup"><span data-stu-id="0f6dc-218">Windows Forms</span></span>](#winforms472)

- [<span data-ttu-id="0f6dc-219">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="0f6dc-219">Windows Presentation Foundation (WPF)</span></span>](#wpf472)

<a name="winforms472"></a>

### <a name="windows-forms"></a><span data-ttu-id="0f6dc-220">Windows Form</span><span class="sxs-lookup"><span data-stu-id="0f6dc-220">Windows Forms</span></span>

<span data-ttu-id="0f6dc-221">**Colori definiti dal sistema operativo nei temi a contrasto elevato**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-221">**OS-defined colors in High Contrast themes**</span></span>

<span data-ttu-id="0f6dc-222">A partire da .NET Framework 4.7.2, Windows Forms usa colori definiti dal sistema operativo dei temi di contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-222">Starting with .NET Framework 4.7.2, Windows Forms uses colors defined by the operating system in High Contrast themes.</span></span> <span data-ttu-id="0f6dc-223">Ciò influisce sui controlli seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-223">This affects the following controls:</span></span>

- <span data-ttu-id="0f6dc-224">La freccia a discesa del controllo <xref:System.Windows.Forms.ToolStripDropDownButton>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-224">The drop-down arrow of the <xref:System.Windows.Forms.ToolStripDropDownButton> control.</span></span>

- <span data-ttu-id="0f6dc-225">I controlli <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> e <xref:System.Windows.Forms.CheckBox> con <xref:System.Windows.Forms.ButtonBase.FlatStyle> impostato su <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> o <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-225">The <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with <xref:System.Windows.Forms.ButtonBase.FlatStyle> set to <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> or <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0f6dc-226">In precedenza, i colori dello sfondo e del testo selezionato non erano in contrasto e risultavano di difficile lettura.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-226">Previously, selected text and background colors were not contrasting and were hard to read.</span></span>

- <span data-ttu-id="0f6dc-227">I controlli contenuti in un oggetto <xref:System.Windows.Forms.GroupBox> con la proprietà relativa <xref:System.Windows.Forms.Control.Enabled> impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-227">Controls contained within a <xref:System.Windows.Forms.GroupBox> that has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="0f6dc-228">I controlli <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox> e <xref:System.Windows.Forms.ToolStripDropDownButton> che hanno un maggiore rapporto del contrasto di luminosità nella modalità a contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-228">The <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox>, and <xref:System.Windows.Forms.ToolStripDropDownButton> controls, which have an increased luminosity contrast ratio in High Contrast Mode.</span></span>

- <span data-ttu-id="0f6dc-229">La proprietà <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> di <xref:System.Windows.Forms.DataGridViewLinkCell>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-229">The <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> property of the <xref:System.Windows.Forms.DataGridViewLinkCell>.</span></span>

<span data-ttu-id="0f6dc-230">**Miglioramenti di Assistente vocale**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-230">**Narrator improvements**</span></span>

<span data-ttu-id="0f6dc-231">A partire da .NET Framework 4.7.2, il supporto dell'Assistente vocale è stato migliorato come segue:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-231">Starting with .NET Framework 4.7.2, Narrator support is enhanced as follows:</span></span>

- <span data-ttu-id="0f6dc-232">Annuncia il valore della proprietà <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> mentre annuncia il testo di una classe <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-232">It announces the value of the <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> property when announcing the text of a <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

- <span data-ttu-id="0f6dc-233">Indica quando una classe <xref:System.Windows.Forms.ToolStripMenuItem> ha la proprietà <xref:System.Windows.Forms.Control.Enabled> impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-233">It indicates when a <xref:System.Windows.Forms.ToolStripMenuItem> has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="0f6dc-234">Offre un feedback sullo stato di una casella di controllo quando la proprietà <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> è impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-234">It gives feedback on the state of a check box when the <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> property is set to `true`.</span></span>

- <span data-ttu-id="0f6dc-235">L'ordine di attivazione nella modalità di analisi dell'Assistente vocale rispetta l'ordine degli oggetti visivi dei controlli nella finestra di dialogo di download ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-235">Narrator's Scan Mode focus order is consistent with the visual order of the controls on the ClickOnce download dialog window.</span></span>

<span data-ttu-id="0f6dc-236">**Miglioramenti apportati a DataGridView**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-236">**DataGridView improvements**</span></span>

<span data-ttu-id="0f6dc-237">A partire da .NET Framework 4.7.2, il controllo <xref:System.Windows.Forms.DataGridView> ha introdotto i miglioramenti di accessibilità seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-237">Starting with .NET Framework 4.7.2, the <xref:System.Windows.Forms.DataGridView> control has introduced the following accessibility improvements:</span></span>

- <span data-ttu-id="0f6dc-238">Le righe possono essere ordinate usando la tastiera.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-238">Rows can be sorted using the keyboard.</span></span> <span data-ttu-id="0f6dc-239">È possibile usare F3 per ordinare in base alla colonna corrente.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-239">A user can use the F3 key in order to sort by the current column.</span></span>

- <span data-ttu-id="0f6dc-240">Quando la proprietà <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, l'intestazione di colonna cambia colore per indicare la colonna corrente man mano che l'utente si sposta tra le celle nella riga corrente tramite tabulazione.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-240">When the <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> is set to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, the column header changes color to indicate the current column as the user tabs through the cells in the current row.</span></span>

- <span data-ttu-id="0f6dc-241">La proprietà <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> di un oggetto <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> restituisce il controllo padre corretto.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-241">The <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> property of a  <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> returns the correct parent control.</span></span>

<span data-ttu-id="0f6dc-242">**Segnali visivi migliorati**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-242">**Improved visual cues**</span></span>

- <span data-ttu-id="0f6dc-243">I controlli <xref:System.Windows.Forms.RadioButton> e <xref:System.Windows.Forms.CheckBox> con proprietà <xref:System.Windows.Forms.ButtonBase.Text> vuota visualizzano un indicatore di stato attivo quando ricevono lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-243">The <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with an empty <xref:System.Windows.Forms.ButtonBase.Text> property  display a focus indicator when they receive the focus.</span></span>

<span data-ttu-id="0f6dc-244">**Supporto migliorato per PropertyGrid**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-244">**Improved Property Grid Support**</span></span>

- <span data-ttu-id="0f6dc-245">Gli elementi figlio del controllo <xref:System.Windows.Forms.PropertyGrid> ora restituiscono `true` per la proprietà <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> solo quando è abilitato un elemento PropertyGrid.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-245">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `true` for the  <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> property only when a PropertyGrid element is enabled.</span></span>

- <span data-ttu-id="0f6dc-246">Gli elementi figlio del controllo <xref:System.Windows.Forms.PropertyGrid> restituiscono `false` per la proprietà <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> solo quando un elemento PropertyGrid può essere modificato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-246">The <xref:System.Windows.Forms.PropertyGrid> control child elements return a `false` for the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> property only when a PropertyGrid element can be changed by the user.</span></span>

<span data-ttu-id="0f6dc-247">**Navigazione tramite tastiera migliorata**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-247">**Improved keyboard navigation**</span></span>

- <span data-ttu-id="0f6dc-248">Il controllo <xref:System.Windows.Forms.ToolStripButton> consente lo stato attivo quando è contenuto all'interno di una classe <xref:System.Windows.Forms.ToolStripPanel> con la proprietà <xref:System.Windows.Forms.ToolStripPanel.TabStop> impostata su `true`</span><span class="sxs-lookup"><span data-stu-id="0f6dc-248">The <xref:System.Windows.Forms.ToolStripButton> control allows focus when contained within a <xref:System.Windows.Forms.ToolStripPanel> that has the <xref:System.Windows.Forms.ToolStripPanel.TabStop> property set to `true`</span></span>

<a name="wpf472"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="0f6dc-249">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="0f6dc-249">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="0f6dc-250">**Modifiche ai controlli CheckBox e RadioButton**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-250">**Changes to the CheckBox and RadioButton controls**</span></span>

<span data-ttu-id="0f6dc-251">In .NET Framework 4.7.1 e versioni precedenti i controlli <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> e <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> di WPF contengono oggetti visivi dello stato attivo incoerenti e non corretti nei temi classico e a contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-251">In .NET Framework 4.7.1 and earlier versions, the WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> and <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> controls have inconsistent and, in Classic and High Contrast themes, incorrect focus visuals.</span></span>  <span data-ttu-id="0f6dc-252">Questi problemi si verificano se i controlli non hanno impostato un contenuto.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-252">These issues occur in cases where the controls do not have any content set.</span></span>  <span data-ttu-id="0f6dc-253">La transizione tra i temi può risultare quindi confusa e diventa difficile visualizzare l'oggetto visivo con stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-253">This can make the transition between themes confusing and the focus visual hard to see.</span></span>

<span data-ttu-id="0f6dc-254">In .NET Framework 4.7.2 questi oggetti visivi sono più coerenti tra i temi e possono essere visualizzati più facilmente nei temi classico e a contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-254">In .NET Framework 4.7.2, these visuals are now more consistent across themes and more easily visible in Classic and High Contrast themes.</span></span>

<span data-ttu-id="0f6dc-255">**Controlli WinForms ospitati in un'applicazione WPF**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-255">**WinForms controls hosted in a WPF application**</span></span>

<span data-ttu-id="0f6dc-256">Nel caso di un controllo WinForms ospitato in un'applicazione WPF in .NET Framework 4.7.1 e versioni precedenti, gli utenti non potevano uscire dal livello WinForms se il primo o l'ultimo controllo nel livello era il controllo <xref:System.Windows.Forms.Integration.ElementHost> di WPF.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-256">For WinForms control hosted in a WPF application in .NET Framework 4.7.1 and earlier versions, users couldn't tab out of the WinForms layer if the first or last control in that layer is the WPF <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span> <span data-ttu-id="0f6dc-257">In .NET Framework 4.7.2 gli utenti possono uscire dal livello di WinForms.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-257">In .NET Framework 4.7.2, users are now able to tab out of the WinForms layer.</span></span>

<span data-ttu-id="0f6dc-258">Tuttavia, le applicazioni automatiche che si basano sullo stato attivo che non esce mai dal livello di WinForms potrebbero non funzionare più come previsto.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-258">However, automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

## <a name="whats-new-in-accessibility-in-net-framework-471"></a><span data-ttu-id="0f6dc-259">Nuove funzionalità di accessibilità in .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="0f6dc-259">What's new in accessibility in .NET Framework 4.7.1</span></span>

<span data-ttu-id="0f6dc-260">.NET Framework 4.7.1 include nuove funzionalità di accessibilità nelle aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-260">.NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="0f6dc-261">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="0f6dc-261">Windows Presentation Foundation (WPF)</span></span>](#wpf471)

- [<span data-ttu-id="0f6dc-262">Windows Form</span><span class="sxs-lookup"><span data-stu-id="0f6dc-262">Windows Forms</span></span>](#winforms471)

- [<span data-ttu-id="0f6dc-263">Controlli Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0f6dc-263">ASP.NET web controls</span></span>](#aspnet471)

- [<span data-ttu-id="0f6dc-264">Strumenti .NET SDK</span><span class="sxs-lookup"><span data-stu-id="0f6dc-264">.NET SDK Tools</span></span>](#tools471)

- [<span data-ttu-id="0f6dc-265">Progettazione flussi di lavoro di Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="0f6dc-265">Windows Workflow Foundation (WF) Workflow Designer</span></span>](#wf471)

<a name="wpf471"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="0f6dc-266">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="0f6dc-266">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="0f6dc-267">**Miglioramenti per le utilità per la lettura dello schermo**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-267">**Screen reader improvements**</span></span>

<span data-ttu-id="0f6dc-268">Se sono abilitati i miglioramenti per l'accessibilità, .NET Framework 4.7.1 include i miglioramenti seguenti che riguardano le utilità per la lettura dello schermo:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-268">If accessibility improvements are enabled, .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="0f6dc-269">In .NET Framework 4.7 e versioni precedenti i controlli <xref:System.Windows.Controls.Expander> vengono annunciati come pulsanti dalle utilità per la lettura dello schermo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-269">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="0f6dc-270">A partire da .NET Framework 4.7.1, sono annunciati correttamente come gruppi espandibili/comprimibili.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-270">Starting with .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="0f6dc-271">In .NET Framework 4.7 e versioni precedenti i controlli <xref:System.Windows.Controls.DataGridCell> vengono annunciati come "personalizzati" dalle utilità per la lettura dello schermo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-271">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="0f6dc-272">A partire da .NET Framework 4.7.1, sono annunciati correttamente come cella di griglia dati (localizzati).</span><span class="sxs-lookup"><span data-stu-id="0f6dc-272">Starting with .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>

- <span data-ttu-id="0f6dc-273">A partire da .NET Framework 4.7.1, le utilità per la lettura dello schermo annunciano il nome di un controllo <xref:System.Windows.Controls.ComboBox> modificabile.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-273">Starting with .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="0f6dc-274">In .NET Framework 4.7 e versioni precedenti i controlli <xref:System.Windows.Controls.PasswordBox> vengono annunciati come "Nessun elemento visualizzato" o il comportamento è in altro modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-274">In .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="0f6dc-275">Questo problema è stato risolto a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-275">This issue is fixed starting with .NET Framework 4.7.1.</span></span>

<span data-ttu-id="0f6dc-276">**Supporto di aree dinamiche UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-276">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="0f6dc-277">Le utilità per la lettura dello schermo, come Assistente vocale, consentono di leggere il contenuto dell'interfaccia utente di un'applicazione, in genere annunciando tramite sintesi vocale il contenuto dell'interfaccia utente con lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-277">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="0f6dc-278">Tuttavia, se un elemento dell'interfaccia utente viene modificato e non ha lo stato attivo, l'utente potrebbe non ricevere notifica e perdere informazioni importanti.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-278">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="0f6dc-279">Le aree dinamiche sono progettate per risolvere questo problema.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-279">Live regions aim at solving this problem.</span></span> <span data-ttu-id="0f6dc-280">Uno sviluppatore può usarle per informare l'utilità per la lettura dello schermo o qualsiasi altro client UIAutomation di un'importante modifica apportata a un elemento dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-280">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="0f6dc-281">L'utilità per la lettura dello schermo può quindi decidere come e quando informare l'utente di questa modifica.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-281">The screen reader can then decide how and when to inform the user of this change.</span></span>

<span data-ttu-id="0f6dc-282">Per supportare le aree dinamiche sono state aggiunte le API seguenti a WPF:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-282">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="0f6dc-283">I campi <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> che identificano la proprietà **LiveSetting** e l'evento **LiveRegionChanged**.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-283">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="0f6dc-284">Questi campi possono essere impostati tramite XAML.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-284">They can be set by using XAML.</span></span>

- <span data-ttu-id="0f6dc-285">La proprietà associata **AutomationProperties.LiveSetting** che segnala all'utilità per la lettura dello schermo l'importanza della modifica dell'interfaccia utente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-285">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="0f6dc-286">La proprietà <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>, che identifica la proprietà associata **AutomationProperties.LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-286">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>

- <span data-ttu-id="0f6dc-287">Il metodo <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>, di cui è possibile eseguire l'override per specificare un valore **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-287">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="0f6dc-288">I metodi <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> e <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>, che consentono di ottenere e impostare un valore **LiveSetting**.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-288">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>

- <span data-ttu-id="0f6dc-289">L'enumerazione <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>, che definisce le i valori **LiveSetting** possibili seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-289">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

  - <span data-ttu-id="0f6dc-290"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-290"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0f6dc-291">L'elemento non invia notifiche se il contenuto dell'area dinamica è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-291">The element does not send notifications if the content of the live region has changed.</span></span>
  - <span data-ttu-id="0f6dc-292"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-292"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0f6dc-293">L'elemento invia notifiche che non causano interruzioni se il contenuto dell'area dinamica è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-293">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>

  - <span data-ttu-id="0f6dc-294"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-294"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0f6dc-295">L'elemento invia notifiche con interruzioni se il contenuto dell'area dinamica è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-295">The element sends interruptive notifications if the content of the live region has changed.</span></span>

<span data-ttu-id="0f6dc-296">È possibile creare un'area dinamica impostando la proprietà **AutomationProperties.LiveSetting** sull'elemento di interesse, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-296">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="0f6dc-297">Quando vengono modificati i dati nell'area dinamica ed è necessario informarne un'utilità per la lettura dello schermo, deve essere generato un evento in modo esplicito, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-297">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```

```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="0f6dc-298">**Contrasto elevato**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-298">**High contrast**</span></span>

<span data-ttu-id="0f6dc-299">A partire da .NET Framework 4.7.1, sono stati apportati miglioramenti relativi al contrasto elevato per vari controlli WPF,</span><span class="sxs-lookup"><span data-stu-id="0f6dc-299">Starting with .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="0f6dc-300">che sono ora visibili quando viene impostato il tema <xref:System.Windows.SystemParameters.HighContrast%2A>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-300">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="0f6dc-301">Sono inclusi:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-301">These include:</span></span>

- <span data-ttu-id="0f6dc-302">Controllo <xref:System.Windows.Controls.Expander></span><span class="sxs-lookup"><span data-stu-id="0f6dc-302"><xref:System.Windows.Controls.Expander> control</span></span>

  <span data-ttu-id="0f6dc-303">L'oggetto visivo per lo stato attivo per il controllo <xref:System.Windows.Controls.Expander> è ora visibile.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-303">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="0f6dc-304">Anche gli oggetti visivi della tastiera per i controlli <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.RadioButton> sono visibili.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-304">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="0f6dc-305">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-305">For example:</span></span>

  <span data-ttu-id="0f6dc-306">Prima:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-306">Before:</span></span> 

  ![Screenshot del controllo Expander con lo stato attivo e nessun oggetto visivo dello stato attivo.](./media/whats-new-in-accessibility/expander-control-before.png)

  <span data-ttu-id="0f6dc-308">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-308">After:</span></span> 

  ![Screenshot del controllo Expander con lo stato attivo che mostra una linea tratteggiata intorno al testo del controllo.](./media/whats-new-in-accessibility/expander-control-after.png)

- <span data-ttu-id="0f6dc-310">Controlli <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.RadioButton></span><span class="sxs-lookup"><span data-stu-id="0f6dc-310"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>

  <span data-ttu-id="0f6dc-311">Il testo nei controlli <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.RadioButton> è ora più semplice da vedere quando viene selezionato nei temi a contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-311">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="0f6dc-312">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-312">For example:</span></span>

  <span data-ttu-id="0f6dc-313">Prima:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-313">Before:</span></span> 

  ![Screenshot dei pulsanti di opzione e controllo con visibilità del testo insufficiente sui temi a contrasto elevato.](./media/whats-new-in-accessibility/high-contrast-radio-button-before.png)

  <span data-ttu-id="0f6dc-315">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-315">After:</span></span> 

  ![Screenshot dei pulsanti di opzione e controllo con visibilità del testo migliore sui temi a contrasto elevato.](./media/whats-new-in-accessibility/high-contrast-radio-button-after.png)

- <span data-ttu-id="0f6dc-317">Controllo <xref:System.Windows.Controls.ComboBox></span><span class="sxs-lookup"><span data-stu-id="0f6dc-317"><xref:System.Windows.Controls.ComboBox> control</span></span>

  <span data-ttu-id="0f6dc-318">A partire da .NET Framework 4.7.1, il bordo di un controllo <xref:System.Windows.Controls.ComboBox> disabilitato ha lo stesso colore del testo disabilitato.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-318">Starting with .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="0f6dc-319">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-319">For example:</span></span>

  <span data-ttu-id="0f6dc-320">Prima:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-320">Before:</span></span> 

  ![Screenshot di un controllo ComboBox disabilitato con il testo del bordo e del controllo in colori diversi.](./media/whats-new-in-accessibility/combo-disabled-before.png)

  <span data-ttu-id="0f6dc-322">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-322">After:</span></span>   

  ![Screenshot di un controllo ComboBox disabilitato con bordo con lo stesso colore del testo del controllo.](./media/whats-new-in-accessibility/combo-disabled-after.png)

  <span data-ttu-id="0f6dc-324">Inoltre, i pulsanti con lo stato attivo e disabilitati usano il colore del tema corretto.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-324">In addition, disabled and focused buttons use the correct theme color.</span></span>

  <span data-ttu-id="0f6dc-325">Prima:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-325">Before:</span></span>

  ![Screenshot di un pulsante nero con testo grigio che afferma lo stato attivo.](./media/whats-new-in-accessibility/button-theme-colors-before.png) 

  <span data-ttu-id="0f6dc-327">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-327">After:</span></span> 

  ![Screenshot di un pulsante blu con testo nero che indica lo stato attivo.](./media/whats-new-in-accessibility/button-theme-colors-after.png) 

  <span data-ttu-id="0f6dc-329">Infine, in .NET Framework 4.7 e versioni precedenti, l'impostazione dello stile di un controllo <xref:System.Windows.Controls.ComboBox> su `Toolbar.ComboBoxStyleKey` rende invisibile la freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-329">Finally, in .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="0f6dc-330">Questo problema è stato risolto a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-330">This issue is fixed starting with .NET Framework 4.7.1.</span></span> <span data-ttu-id="0f6dc-331">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-331">For example:</span></span>

  <span data-ttu-id="0f6dc-332">Prima:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-332">Before:</span></span> 

  ![Screenshot di un controllo ComboBox con una freccia a discesa invisibile.](./media/whats-new-in-accessibility/combo-box-style-key-before.png) 

  <span data-ttu-id="0f6dc-334">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-334">After:</span></span> 

  ![Screenshot di un controllo ComBoxBox che visualizza la freccia a discesa.](./media/whats-new-in-accessibility/combo-box-style-key-after.png) 

- <span data-ttu-id="0f6dc-336">Controllo <xref:System.Windows.Controls.DataGrid></span><span class="sxs-lookup"><span data-stu-id="0f6dc-336"><xref:System.Windows.Controls.DataGrid> control</span></span>

  <span data-ttu-id="0f6dc-337">A partire da .NET Framework 4.7.1, la freccia dell'indicatore di ordinamento nei controlli <xref:System.Windows.Controls.DataGrid> usa ora i colori del tema corretti.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-337">Starting with .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="0f6dc-338">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-338">For example:</span></span>

  <span data-ttu-id="0f6dc-339">Prima:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-339">Before:</span></span> 

  ![Screenshot della freccia dell'indicatore di ordinamento prima dei miglioramenti.](./media/whats-new-in-accessibility/sort-indicator-before.png) 

  <span data-ttu-id="0f6dc-341">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-341">After:</span></span>   

  ![Screenshot della freccia dell'indicatore di ordinamento dopo i miglioramenti.](./media/whats-new-in-accessibility/sort-indicator-after.png) 

  <span data-ttu-id="0f6dc-343">Inoltre, in .NET Framework 4.7 e versioni precedenti, per lo stile di collegamento predefinito viene usato un colore non corretto al passaggio del mouse in modalità a contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-343">In addition, in .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="0f6dc-344">Questo problema è stato risolto a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-344">This is resolved starting with .NET Framework 4.7.1.</span></span> <span data-ttu-id="0f6dc-345">Analogamente, le colonne della casella di controllo per i controlli <xref:System.Windows.Controls.DataGrid> usano i colori previsti per il riscontro dello stato attivo della tastiera a partire da .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-345">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with .NET Framework 4.7.1.</span></span>

  <span data-ttu-id="0f6dc-346">Prima:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-346">Before:</span></span> 

  ![Screenshot di un collegamento che dice clic su me.](./media/whats-new-in-accessibility/default-link-style-before.png) 

  <span data-ttu-id="0f6dc-349">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-349">After:</span></span>    

  ![Screenshot di un collegamento che dice clic su me.](./media/whats-new-in-accessibility/default-link-style-after.png) 

<span data-ttu-id="0f6dc-352">Per altre informazioni sui miglioramenti per l'accessibilità di WPF in .NET Framework 4.7.1, vedere [Miglioramenti di accessibilità in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span><span class="sxs-lookup"><span data-stu-id="0f6dc-352">For more information on WPF accessibility improvements in .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

<a name="winforms471"></a>

### <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="0f6dc-353">Miglioramenti per l'accessibilità di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0f6dc-353">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="0f6dc-354">In .NET Framework 4.7.1 Windows Forms (WinForms) include modifiche per l'accessibilità nelle aree seguenti.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-354">In .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="0f6dc-355">**Miglioramento della visualizzazione in modalità a contrasto elevato**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-355">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="0f6dc-356">A partire da .NET Framework 4.7.1, vari controlli WinForms offrono un rendering migliorato nelle modalità a contrasto elevato disponibili nel sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-356">Starting with .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="0f6dc-357">Windows 10 ha cambiato i valori di alcuni colori di sistema a contrasto elevato e Windows Form si basa sul framework Win32 di Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-357">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="0f6dc-358">Per risultati ottimali, usare la versione più recente di Windows e accettare le modifiche del sistema operativo più recenti aggiungendo un file app.manifest in un'applicazione di test e rimuovere il commento dalla riga del sistema operativo supportato Windows 10, in modo che abbia l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-358">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```

<span data-ttu-id="0f6dc-359">Alcuni esempi di modifiche per il contrasto elevato includono:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-359">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="0f6dc-360">I segni di spunta negli elementi <xref:System.Windows.Forms.MenuStrip> sono più facili da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-360">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="0f6dc-361">Gli elementi <xref:System.Windows.Forms.MenuStrip> disabilitati sono più facili da visualizzare quando sono selezionati.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-361">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="0f6dc-362">Il testo in un controllo <xref:System.Windows.Forms.Button> selezionato è contrastato rispetto al colore della selezione.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-362">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="0f6dc-363">Il testo disabilitato è più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-363">Disabled text is easier to read.</span></span> <span data-ttu-id="0f6dc-364">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-364">For example:</span></span>

  <span data-ttu-id="0f6dc-365">Prima:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-365">Before:</span></span>

  ![Screenshot di un'app che usa diversi controlli eseguiti in modalità a contrasto elevato prima dei miglioramenti dell'accessibilità.](./media/whats-new-in-accessibility/high-contrast-mode-menu-items-before.png) 

  <span data-ttu-id="0f6dc-367">Dopo:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-367">After:</span></span>

  ![Screenshot di un'app che usa diversi controlli eseguiti in modalità a contrasto elevato dopo i miglioramenti dell'accessibilità.](./media/whats-new-in-accessibility/high-contrast-mode-menu-items-after.png) 

- <span data-ttu-id="0f6dc-369">Miglioramenti per il contrasto elevato nella finestra di dialogo di eccezione del thread.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-369">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="0f6dc-370">**Supporto migliorato di Assistente vocale**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-370">**Improved Narrator support**</span></span>

<span data-ttu-id="0f6dc-371">Windows Forms in .NET Framework 4.7.1 include i seguenti miglioramenti per l'accessibilità per l'Assistente vocale:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-371">Windows Forms in .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="0f6dc-372">Il controllo <xref:System.Windows.Forms.MonthCalendar> è accessibile per l'Assistente vocale, così come da altri strumenti di automazione dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-372">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="0f6dc-373">Il controllo <xref:System.Windows.Forms.CheckedListBox> segnala all'Assistente vocale lo stato di selezione di un elemento, in modo che l'utente riceva notifica della modifica del valore di un elemento di elenco.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-373">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>

- <span data-ttu-id="0f6dc-374">Il controllo <xref:System.Windows.Forms.DataGridViewCell> segnala lo stato di sola lettura corretto all'Assistente vocale.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-374">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>

- <span data-ttu-id="0f6dc-375">Assistente vocale può ora leggere il testo <xref:System.Windows.Forms.ToolStripMenuItem> disabilitato, mentre in precedenza ignorava le voci di menu disabilitate.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-375">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="0f6dc-376">**Supporto avanzato per i modelli di accessibilità UIAutomation**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-376">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="0f6dc-377">A partire da .NET Framework 4.7.1, gli sviluppatori di strumenti di tecnologia per l'accessibilità possono sfruttare i modelli e le proprietà di accessibilità delle API comuni per numerosi controlli WinForms.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-377">Starting with .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="0f6dc-378">Questi miglioramenti per l'accessibilità includono:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-378">These accessibility improvements include:</span></span>

- <span data-ttu-id="0f6dc-379"><xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.ToolStripSplitButton> ora supportano il [modello di espansione/compressione](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="0f6dc-379">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="0f6dc-380"><xref:System.Windows.Forms.DataGridViewCheckBoxCell> supporta ora il [modello di attivazione/disattivazione](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="0f6dc-380">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>

- <span data-ttu-id="0f6dc-381">Il controllo <xref:System.Windows.Forms.ToolStripItem> supporta la proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> e il [modello di espansione/compressione](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="0f6dc-381">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="0f6dc-382">I controlli <xref:System.Windows.Forms.NumericUpDown> e <xref:System.Windows.Forms.DomainUpDown> supportano la proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-382">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="0f6dc-383">**Esperienza migliorata per il visualizzatore proprietà**</span><span class="sxs-lookup"><span data-stu-id="0f6dc-383">**Improved property browser experience**</span></span>

<span data-ttu-id="0f6dc-384">A partire da .NET Framework 4.7.1, Windows Forms include:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-384">Starting with .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="0f6dc-385">Migliori spostamenti tramite tastiera tra le varie finestre di selezione a discesa.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-385">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="0f6dc-386">Riduzione dei punti di tabulazione non necessari.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-386">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="0f6dc-387">Segnalazione migliore dei tipi di controllo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-387">Better reporting of control types.</span></span>
- <span data-ttu-id="0f6dc-388">Comportamento migliorato dell'Assistente vocale.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-388">Improved narrator behavior.</span></span>

<a name="aspnet471"></a>

### <a name="aspnet-web-controls"></a><span data-ttu-id="0f6dc-389">Controlli Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0f6dc-389">ASP.NET web controls</span></span>

<span data-ttu-id="0f6dc-390">A partire da .NET Framework 4.7.1 e Visual Studio 2017 versione 15,3, ASP.NET migliora il funzionamento dei controlli Web ASP.NET con la tecnologia di accessibilità in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-390">Starting with .NET Framework 4.7.1 and Visual Studio 2017 version 15.3, ASP.NET improves how ASP.NET web controls work with accessibility technology in Visual Studio.</span></span> <span data-ttu-id="0f6dc-391">Le modifiche includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-391">Changes include the following:</span></span>

- <span data-ttu-id="0f6dc-392">Modifiche per implementare criteri di accessibilità dell'interfaccia utente mancanti nei controlli, come la finestra di dialogo **Aggiungi campo** nella procedura guidata **Visualizzazione dettagli** o la finestra di dialogo **Configura ListView** nella procedura guidata **ListView**.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-392">Changes to implement missing UI accessibility patterns in controls, like the **Add Field** dialog in the **Details View** wizard, or the **Configure ListView** dialog of the **ListView** wizard.</span></span>

- <span data-ttu-id="0f6dc-393">Modifiche per migliorare la visualizzazione nella modalità a contrasto elevato, ad esempio l'**Editor campi del pager di dati**.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-393">Changes to improve the display in High Contrast mode, like the **Data Pager Fields Editor**.</span></span>

- <span data-ttu-id="0f6dc-394">Modifiche per migliorare la navigazione tramite tastiera per controlli, come la finestra di dialogo **Campi** nella procedura guidata **Modifica campi del pager** del controllo DataPager, la finestra di dialogo **Configura ObjectContext** o la finestra di dialogo **Configura selezione dati** della procedura guidata **Configura origine dati**.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-394">Changes to improve the keyboard navigation experiences for controls, like the **Fields** dialog in the **Edit Pager Fields** wizard of the DataPager control, the **Configure ObjectContext** dialog, or the **Configure Data Selection** dialog of the **Configure Data Source** wizard.</span></span>

<a name="tools471"></a>

### <a name="net-sdk-tools"></a><span data-ttu-id="0f6dc-395">Strumenti .NET SDK</span><span class="sxs-lookup"><span data-stu-id="0f6dc-395">.NET SDK Tools</span></span>

<span data-ttu-id="0f6dc-396">Lo [strumento Editor di configurazione (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) e lo [strumento Visualizzatore di tracce (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) sono stati migliorati correggendo vari problemi di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-396">The [Configuration Editor Tool (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) and [Service Trace Viewer Tool (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="0f6dc-397">Molti erano problemi di lieve entità, come ad esempio un nome non definito o alcuni criteri dell'automazione interfaccia utente non implementati correttamente.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-397">Most of these were small issues, like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="0f6dc-398">È possibile che molti utenti non si siano accorti di questi valori non corretti. I clienti che usano le assistive technology, ad esempio le utilità per la lettura dello schermo, troveranno invece questi strumenti SDK più accessibili.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-398">While many users won’t be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span>

<span data-ttu-id="0f6dc-399">Tali miglioramenti modificano alcuni comportamenti precedenti, ad esempio l'ordine di attivazione della tastiera.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-399">These enhancements change some previous behaviors, such as keyboard focus order.</span></span>

<a name="wf471"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="0f6dc-400">Progettazione flussi di lavoro di Windows Workflow Foundation (WF)</span><span class="sxs-lookup"><span data-stu-id="0f6dc-400">Windows Workflow Foundation (WF) Workflow Designer</span></span>

<span data-ttu-id="0f6dc-401">Le modifiche all'accessibilità in Progettazione flussi di lavoro includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-401">Accessibility changes in the Workflow Designer include the following:</span></span>

- <span data-ttu-id="0f6dc-402">L'ordine di tabulazione viene modificato da sinistra a destra e dall'alto verso il basso in alcuni controlli:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-402">The tab order changes to left to right and top to bottom in some controls:</span></span>

  - <span data-ttu-id="0f6dc-403">La finestra di inizializzazione della correlazione in cui impostare i dati di correlazione per l'attività <xref:System.ServiceModel.Activities.InitializeCorrelation>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-403">The initialize correlation window for setting correlation data for the <xref:System.ServiceModel.Activities.InitializeCorrelation> activity.</span></span>

  - <span data-ttu-id="0f6dc-404">La finestra di definizione del contenuto per le attività <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> e <xref:System.ServiceModel.Activities.ReceiveReply>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-404">The content definition window for the <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities.</span></span>

- <span data-ttu-id="0f6dc-405">Altre funzioni sono disponibili tramite tastiera:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-405">More functions are available via the keyboard:</span></span>

  - <span data-ttu-id="0f6dc-406">Quando vengono modificate le proprietà di un'attività, i gruppi delle proprietà possono essere compressi tramite tastiera la prima volta che hanno lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-406">When editing the properties of an activity, property groups can be collapsed by keyboard the first time they are focused.</span></span>

  - <span data-ttu-id="0f6dc-407">Le icone di avviso sono accessibili dalla tastiera.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-407">Warning icons are accessible by keyboard.</span></span>

  - <span data-ttu-id="0f6dc-408">Il pulsante **Altre proprietà** nella finestra **Proprietà** è accessibile dalla tastiera.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-408">The **More Properties** button in the **Properties** window is accessible by keyboard.</span></span>

  - <span data-ttu-id="0f6dc-409">Tramite tastiera gli utenti possono accedere agli elementi dell'intestazione nei riquadri **Argomenti** e **Variabili** in Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-409">Keyboard users can access the header items in the **Arguments** and **Variables** panes of the Workflow Designer.</span></span>

- <span data-ttu-id="0f6dc-410">Maggiore visibilità degli elementi con stato attivo, ad esempio quando:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-410">Improved visibility of items with focus, such as when:</span></span>

  - <span data-ttu-id="0f6dc-411">Aggiunta di righe alle griglie di dati usate in Progettazione flussi di lavoro e in ActivityDesigner.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-411">Adding rows to data grids used by the Workflow Designer and activity designers.</span></span>

  - <span data-ttu-id="0f6dc-412">Tabulazione all'interno dei campi nelle attività <xref:System.ServiceModel.Activities.ReceiveReply> e <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-412">Tabbing through fields in the <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>

  - <span data-ttu-id="0f6dc-413">Impostazione di valori predefiniti per variabili o argomenti</span><span class="sxs-lookup"><span data-stu-id="0f6dc-413">Setting default values for variables or arguments</span></span>

- <span data-ttu-id="0f6dc-414">Le utilità per la lettura dello schermo ora possono riconoscere correttamente:</span><span class="sxs-lookup"><span data-stu-id="0f6dc-414">Screen readers can now correctly recognize:</span></span>

  - <span data-ttu-id="0f6dc-415">Set di punti di interruzione in Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-415">Breakpoints set in the workflow designer.</span></span>

  - <span data-ttu-id="0f6dc-416">Attività <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision> e <xref:System.ServiceModel.Activities.CorrelationScope>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-416">The <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, and <xref:System.ServiceModel.Activities.CorrelationScope> activities.</span></span>
  - <span data-ttu-id="0f6dc-417">Contenuto dell'attività <xref:System.ServiceModel.Activities.Receive>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-417">The contents of the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>

  - <span data-ttu-id="0f6dc-418">Tipo di destinazione per l'attività <xref:System.Activities.Statements.InvokeMethod>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-418">The Target Type for the <xref:System.Activities.Statements.InvokeMethod> activity.</span></span>

  - <span data-ttu-id="0f6dc-419">Casella combinata Eccezione e sezione Finally nell'attività <xref:System.Activities.Statements.TryCatch>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-419">The Exception combo box and the Finally section in the <xref:System.Activities.Statements.TryCatch> activity.</span></span>

  - <span data-ttu-id="0f6dc-420">Casella combinata Tipo di messaggio, barra di divisione nella finestra Aggiungi inizializzatori di correlazione, finestra Content Definition (Definizione contenuto) e finestra Definizione di CorrelatesOn nelle attività di messaggistica (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply> e <xref:System.ServiceModel.Activities.ReceiveReply>).</span><span class="sxs-lookup"><span data-stu-id="0f6dc-420">The Message Type combo box, the splitter in the Add Correlation Initializers window, the Content Definition window, and the CorrelatesOn Definition window in the messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>

  - <span data-ttu-id="0f6dc-421">Transizioni della macchina a uno stato e destinazioni delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-421">State machine transitions and transitions destinations.</span></span>

  - <span data-ttu-id="0f6dc-422">Annotazioni e connettori nelle attività <xref:System.Activities.Statements.FlowDecision>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-422">Annotations and connectors on <xref:System.Activities.Statements.FlowDecision> activities.</span></span>

  - <span data-ttu-id="0f6dc-423">Menu di scelta rapida per le attività.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-423">The context (right-click) menus for activities.</span></span>

  - <span data-ttu-id="0f6dc-424">Editor di valori di proprietà, pulsante Cancella ricerca, pulsanti di ordinamento Per categoria e In ordine alfabetico e finestra di dialogo Editor espressioni nella griglia delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-424">The property value editors, the Clear Search button, the By Category and Alphabetical sort buttons, and the Expression Editor dialog in the properties grid.</span></span>

  - <span data-ttu-id="0f6dc-425">Percentuale di zoom in Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-425">The zoom percentage in the Workflow Designer.</span></span>

  - <span data-ttu-id="0f6dc-426">Separatore nelle attività <xref:System.Activities.Statements.Parallel> e <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-426">The separator in <xref:System.Activities.Statements.Parallel> and <xref:System.Activities.Statements.Pick> activities.</span></span>

  - <span data-ttu-id="0f6dc-427">Attività <xref:System.Activities.Statements.InvokeDelegate>.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-427">The <xref:System.Activities.Statements.InvokeDelegate> activity.</span></span>

  - <span data-ttu-id="0f6dc-428">Finestra Seleziona tipi per le attività di dizionario (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>` e così via).</span><span class="sxs-lookup"><span data-stu-id="0f6dc-428">The Select Types window for dictionary activities (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`, etc.).</span></span>

  - <span data-ttu-id="0f6dc-429">Finestra Cerca e seleziona un tipo .NET.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-429">The Browse and Select .NET Type window.</span></span>

  - <span data-ttu-id="0f6dc-430">Navigazioni in Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-430">Breadcrumbs in the Workflow Designer.</span></span>

- <span data-ttu-id="0f6dc-431">Gli utenti che usano i temi a contrasto elevato noteranno molti miglioramenti nella visibilità di Progettazione flussi di lavoro e nei relativi controlli, ad esempio rapporti di contrasto più definiti tra gli elementi e caselle di selezione più evidenti per gli elementi con lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0f6dc-431">Users who choose High Contrast themes will see many improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f6dc-432">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f6dc-432">See also</span></span>

- [<span data-ttu-id="0f6dc-433">Novità di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0f6dc-433">What's new in the .NET Framework</span></span>](index.md)
