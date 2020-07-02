---
ms.openlocfilehash: 3d1dc8dec18212afd815aa3de7fc82c8a1f680dc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616267"
---
### <a name="hwndhost-now-correctly-resizes-child-hwnd-during-dpi-changes"></a><span data-ttu-id="7d729-101">HwndHost ora ridimensiona correttamente l'elemento HWND figlio durante le modifiche DPI</span><span class="sxs-lookup"><span data-stu-id="7d729-101">HwndHost now correctly resizes child-HWND during DPI changes</span></span>

#### <a name="details"></a><span data-ttu-id="7d729-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7d729-102">Details</span></span>

<span data-ttu-id="7d729-103">In .NET Framework 4.7.2 e versioni precedenti, quando WPF viene eseguito in modalità sensibile ai valori DPI del monitor, i controlli ospitati all'interno di <xref:System.Windows.Interop.HwndHost> non vengono ridimensionati correttamente dopo le modifiche DPI, ad esempio quando si passano le applicazioni da un monitor a un altro.</span><span class="sxs-lookup"><span data-stu-id="7d729-103">In .NET Framework 4.7.2 and earlier versions, when WPF was run in Per-Monitor Aware mode, controls hosted within <xref:System.Windows.Interop.HwndHost> were not sized correctly after DPI changes, such as when moving applications from one monitor to another.</span></span> <span data-ttu-id="7d729-104">Questa correzione garantisce il corretto ridimensionamento dei controlli ospitati.</span><span class="sxs-lookup"><span data-stu-id="7d729-104">This fix ensures that hosted controls are sized appropriately.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7d729-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="7d729-105">Suggestion</span></span>

<span data-ttu-id="7d729-106">Perché l'applicazione possa usufruire di queste modifiche, è necessario che sia eseguita in .NET Framework 4.7.2 o versione successiva e che acconsenta esplicitamente a questo comportamento impostando l'[opzione di AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) seguente nella sezione `<runtime>` del file di configurazione dell'app su `false`, come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7d729-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later, and it must opt-in to this behavior by setting the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) in the `<runtime>` section of the app config file to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.DoNotUsePresentationDpiCapabilityTier2OrGreater=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="7d729-107">Nome</span><span class="sxs-lookup"><span data-stu-id="7d729-107">Name</span></span>    | <span data-ttu-id="7d729-108">Valore</span><span class="sxs-lookup"><span data-stu-id="7d729-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7d729-109">Scope</span><span class="sxs-lookup"><span data-stu-id="7d729-109">Scope</span></span>   | <span data-ttu-id="7d729-110">Principale</span><span class="sxs-lookup"><span data-stu-id="7d729-110">Major</span></span>       |
| <span data-ttu-id="7d729-111">Version</span><span class="sxs-lookup"><span data-stu-id="7d729-111">Version</span></span> | <span data-ttu-id="7d729-112">4.8</span><span class="sxs-lookup"><span data-stu-id="7d729-112">4.8</span></span>         |
| <span data-ttu-id="7d729-113">Type</span><span class="sxs-lookup"><span data-stu-id="7d729-113">Type</span></span>    | <span data-ttu-id="7d729-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="7d729-114">Retargeting</span></span> |
