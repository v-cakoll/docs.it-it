---
ms.openlocfilehash: a82b720fd4e771481ea1142a88a095443afa0d5b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614943"
---
### <a name="keyboard-focus-now-moves-correctly-across-multiple-layers-of-winformswpf-hosting"></a><span data-ttu-id="388f6-101">Stato attivo della tastiera ora consente di spostarsi correttamente su più livelli di hosting di Windows Form/WPF</span><span class="sxs-lookup"><span data-stu-id="388f6-101">Keyboard focus now moves correctly across multiple layers of WinForms/WPF hosting</span></span>

#### <a name="details"></a><span data-ttu-id="388f6-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="388f6-102">Details</span></span>

<span data-ttu-id="388f6-103">Si consideri un'applicazione WPF che ospita un controllo Windows Form che a sua volta ospita i controlli WPF.</span><span class="sxs-lookup"><span data-stu-id="388f6-103">Consider a WPF application hosting a WinForms control which in turn hosts WPF controls.</span></span> <span data-ttu-id="388f6-104">Può accadere che gli utenti non possano uscire dal livello di Windows Form tramite tabulazione se il primo o l'ultimo controllo in tale livello è `System.Windows.Forms.Integration.ElementHost` di WPF.</span><span class="sxs-lookup"><span data-stu-id="388f6-104">Users may not be able to tab out of the WinForms layer if the first or last control in that layer is the WPF `System.Windows.Forms.Integration.ElementHost`.</span></span> <span data-ttu-id="388f6-105">Questa modifica consente di correggere tale problema. Gli utenti ora possono uscire dal livello di Windows Form tramite tabulazione. Le applicazioni automatiche che si basano su uno stato attivo che non esce mai dal livello di Windows Form potrebbero non funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="388f6-105">This change fixes this issue, and users are now able to tab out of the WinForms layer.Automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="388f6-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="388f6-106">Suggestion</span></span>

<span data-ttu-id="388f6-107">Uno sviluppatore che vuole usare questa modifica per una versione del framework precedente a .NET 4.7.2 può impostare i flag AppContext seguenti su False per disabilitare la modifica.</span><span class="sxs-lookup"><span data-stu-id="388f6-107">A developer who wants to utilize this change while targeting a framework version below .NET 4.7.2 can set the following set of AppContext flags to false for the change to be enabled.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

<span data-ttu-id="388f6-108">Le applicazioni WPF devono accettare tutti i miglioramenti di accessibilità precedenti per ottenere i miglioramenti successivi.</span><span class="sxs-lookup"><span data-stu-id="388f6-108">WPF applications must opt in to all early accessibility improvements to get the later improvements.</span></span> <span data-ttu-id="388f6-109">In altre parole, è necessario impostare entrambe le due opzioni `Switch.UseLegacyAccessibilityFeatures` e `Switch.UseLegacyAccessibilityFeatures.2`. Uno sviluppatore che richiede la funzionalità precedente per .NET 4.7.2 o versione successiva può impostare il flag AppContext seguente su True per disabilitare la modifica.</span><span class="sxs-lookup"><span data-stu-id="388f6-109">In other words, both the `Switch.UseLegacyAccessibilityFeatures` and the `Switch.UseLegacyAccessibilityFeatures.2` switches must be setA developer who requires the previous functionality while targeting .NET 4.7.2 or greater can set the following AppContext flag to true for the change to be disabled.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="388f6-110">Nome</span><span class="sxs-lookup"><span data-stu-id="388f6-110">Name</span></span>    | <span data-ttu-id="388f6-111">Valore</span><span class="sxs-lookup"><span data-stu-id="388f6-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="388f6-112">Scope</span><span class="sxs-lookup"><span data-stu-id="388f6-112">Scope</span></span>   | <span data-ttu-id="388f6-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="388f6-113">Edge</span></span>        |
| <span data-ttu-id="388f6-114">Version</span><span class="sxs-lookup"><span data-stu-id="388f6-114">Version</span></span> | <span data-ttu-id="388f6-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="388f6-115">4.7.2</span></span>       |
| <span data-ttu-id="388f6-116">Type</span><span class="sxs-lookup"><span data-stu-id="388f6-116">Type</span></span>    | <span data-ttu-id="388f6-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="388f6-117">Retargeting</span></span> |
