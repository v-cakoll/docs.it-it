---
ms.openlocfilehash: 06f4186e8f233f5c769dfc5e05d2de5eacd9b053
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621991"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a><span data-ttu-id="69e57-101">Modifica del contrasto elevato di ComboBox in svcTraceViewer</span><span class="sxs-lookup"><span data-stu-id="69e57-101">svcTraceViewer ComboBox high contrast change</span></span>

#### <a name="details"></a><span data-ttu-id="69e57-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="69e57-102">Details</span></span>

<span data-ttu-id="69e57-103">Nello [strumento Visualizzatore di tracce dei servizi Microsoft](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) i controlli ComboBox non venivano visualizzati nel colore corretto in alcuni temi a contrasto elevato.</span><span class="sxs-lookup"><span data-stu-id="69e57-103">In the [Microsoft Service Trace Viewer tool](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md), ComboBox controls were not displayed in the correct color in certain high contrast themes.</span></span> <span data-ttu-id="69e57-104">Il problema è stato risolto in .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="69e57-104">The issue was fixed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="69e57-105">Tuttavia, a causa dei requisiti di compatibilità con le versioni precedenti di .NET Framework SDK, la correzione non risultava visibile ai clienti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="69e57-105">However, due to .NET Framework SDK backward compatibility requirements, the fix was not visible to customers by default.</span></span> <span data-ttu-id="69e57-106">.NET 4.8 espone questa modifica aggiungendo le [opzioni di configurazione di AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) seguenti al file svcTraceViewer.exe.config:</span><span class="sxs-lookup"><span data-stu-id="69e57-106">.NET 4.8 surfaces this change by adding the following [AppContext configuration switches](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the svcTraceViewer.exe.config file:</span></span><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

#### <a name="suggestion"></a><span data-ttu-id="69e57-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="69e57-107">Suggestion</span></span>

<ul><li><span data-ttu-id="69e57-108">Come rifiutare esplicitamente la modifica: se non si vuole avere la modifica funzionale relativa al contrasto elevato, è possibile disabilitarla rimuovendo la sezione seguente dal file svcTraceViewer.exe.config:</span><span class="sxs-lookup"><span data-stu-id="69e57-108">How to opt out of the change If you don't want to have the high contrast behavior change, you can disable it by removing the following section from the svcTraceViewer.exe.config file:</span></span></li></ul><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="69e57-109">Nome</span><span class="sxs-lookup"><span data-stu-id="69e57-109">Name</span></span>    | <span data-ttu-id="69e57-110">Valore</span><span class="sxs-lookup"><span data-stu-id="69e57-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="69e57-111">Scope</span><span class="sxs-lookup"><span data-stu-id="69e57-111">Scope</span></span>   |<span data-ttu-id="69e57-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="69e57-112">Edge</span></span>|
|<span data-ttu-id="69e57-113">Version</span><span class="sxs-lookup"><span data-stu-id="69e57-113">Version</span></span>|<span data-ttu-id="69e57-114">4.8</span><span class="sxs-lookup"><span data-stu-id="69e57-114">4.8</span></span>|
|<span data-ttu-id="69e57-115">Type</span><span class="sxs-lookup"><span data-stu-id="69e57-115">Type</span></span>|<span data-ttu-id="69e57-116">Runtime</span><span class="sxs-lookup"><span data-stu-id="69e57-116">Runtime</span></span>|
