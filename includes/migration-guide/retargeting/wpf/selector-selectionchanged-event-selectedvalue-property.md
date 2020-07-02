---
ms.openlocfilehash: 0ef39d67cd4335658658f5772b5bce49d827cad0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614938"
---
### <a name="selector-selectionchanged-event-and-selectedvalue-property"></a><span data-ttu-id="033d4-101">Evento SelectionChanged e proprietà SelectedValue di Selector</span><span class="sxs-lookup"><span data-stu-id="033d4-101">Selector SelectionChanged event and SelectedValue property</span></span>

#### <a name="details"></a><span data-ttu-id="033d4-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="033d4-102">Details</span></span>

<span data-ttu-id="033d4-103">A partire da .NET Framework 4.7.1, un <xref:System.Windows.Controls.Primitives.Selector> aggiorna sempre il valore della relativa proprietà <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> prima di generare l'evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> quando la selezione cambia.</span><span class="sxs-lookup"><span data-stu-id="033d4-103">Starting with the .NET Framework 4.7.1, a <xref:System.Windows.Controls.Primitives.Selector> always updates the value of its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property before raising the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event, when its selection changes.</span></span> <span data-ttu-id="033d4-104">In questo modo la proprietà SelectedValue è coerente con le altre proprietà di selezione (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> e <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>), che vengono aggiornate prima della generazione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="033d4-104">This makes the SelectedValue property consistent with the other selection properties (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> and <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>), which are updated before raising the event.</span></span><p/><span data-ttu-id="033d4-105">In .NET Framework 4.7 e versioni precedenti, l'aggiornamento di SelectedValue avveniva prima dell'evento nella maggior parte dei casi, ma si verificava dopo l'evento se la modifica della selezione era causata dalla modifica della proprietà <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="033d4-105">In the .NET Framework 4.7 and earlier versions, the update to SelectedValue happened before the event in most cases, but it happened after the event if the selection change was caused by changing the <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="033d4-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="033d4-106">Suggestion</span></span>

<span data-ttu-id="033d4-107">Le app destinate a .NET Framework 4.7.1 o versioni successive possono rifiutare esplicitamente questa modifica e usare il comportamento legacy aggiungendo il codice seguente alla sezione `<runtime>` del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="033d4-107">Apps that target the .NET Framework 4.7.1 or later can opt out of this change and use legacy behavior by adding the following to the `<runtime>` section of the application configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="033d4-108">Le app destinate a .NET Framework 4.7 o versioni precedenti ma in esecuzione su .NET Framework 4.7.1 o versioni successive possono abilitare il nuovo comportamento aggiungendo la riga seguente alla sezione `<runtime>` del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="033d4-108">Apps that target the .NET Framework 4.7 or earlier but are running on the .NET Framework 4.7.1 or later can enable the new behavior by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="033d4-109">Nome</span><span class="sxs-lookup"><span data-stu-id="033d4-109">Name</span></span>    | <span data-ttu-id="033d4-110">Valore</span><span class="sxs-lookup"><span data-stu-id="033d4-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="033d4-111">Scope</span><span class="sxs-lookup"><span data-stu-id="033d4-111">Scope</span></span>   | <span data-ttu-id="033d4-112">Minorenne</span><span class="sxs-lookup"><span data-stu-id="033d4-112">Minor</span></span>       |
| <span data-ttu-id="033d4-113">Version</span><span class="sxs-lookup"><span data-stu-id="033d4-113">Version</span></span> | <span data-ttu-id="033d4-114">4.7.1</span><span class="sxs-lookup"><span data-stu-id="033d4-114">4.7.1</span></span>       |
| <span data-ttu-id="033d4-115">Type</span><span class="sxs-lookup"><span data-stu-id="033d4-115">Type</span></span>    | <span data-ttu-id="033d4-116">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="033d4-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="033d4-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="033d4-117">Affected APIs</span></span>

- <xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType>
