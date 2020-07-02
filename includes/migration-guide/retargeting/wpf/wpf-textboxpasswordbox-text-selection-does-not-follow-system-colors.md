---
ms.openlocfilehash: 7c2e80669d9ef27f87cde9442d8eeab0ee31a524
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614980"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a><span data-ttu-id="745b1-101">La selezione di testo di TextBox/PasswordBox WPF non rispetta i colori di sistema</span><span class="sxs-lookup"><span data-stu-id="745b1-101">WPF TextBox/PasswordBox Text Selection Does Not Follow System Colors</span></span>

#### <a name="details"></a><span data-ttu-id="745b1-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="745b1-102">Details</span></span>

<span data-ttu-id="745b1-103">In .NET Framework 4.7.1 e versioni precedenti i controlli `System.Windows.Controls.TextBox` e `System.Windows.Controls.PasswordBox` WPF eseguono solo il rendering di una selezione di testo a livello di Adorner.</span><span class="sxs-lookup"><span data-stu-id="745b1-103">In .NET Framework 4.7.1 and earlier versions, WPF `System.Windows.Controls.TextBox` and `System.Windows.Controls.PasswordBox` could only render a text selection in the Adorner layer.</span></span> <span data-ttu-id="745b1-104">In alcuni temi di sistema il testo appare poco chiaro e di difficile lettura.</span><span class="sxs-lookup"><span data-stu-id="745b1-104">In some system themes this would occlude text, making it hard to read.</span></span>  <span data-ttu-id="745b1-105">In .NET Framework 4.7.2 e versioni successive gli sviluppatori possono abilitare uno schema di rendering di una selezione che non si basa su Adorner in modo da limitare questo problema.</span><span class="sxs-lookup"><span data-stu-id="745b1-105">In .NET Framework 4.7.2 and later, developers have an option of enabling a non-Adorner-based selection rendering scheme that alleviates this issue.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="745b1-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="745b1-106">Suggestion</span></span>

<span data-ttu-id="745b1-107">Gli sviluppatori che vogliono usare questa modifica devono impostare il flag AppContext seguente in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="745b1-107">A developer who wants to utilize this change must set the following AppContext flag appropriately.</span></span>  <span data-ttu-id="745b1-108">Per usare questa funzionalità, è necessario installare la versione .NET Framework 4.7.2 o versione successiva. Per abilitare la selezione non basata su Adorner, usare il flag AppContext seguente.</span><span class="sxs-lookup"><span data-stu-id="745b1-108">To utilize this feature, the installed .NET Framework version must be 4.7.2 or greater.To enabled the non-adorner-based selection, use the following AppContext flag.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="745b1-109">Nome</span><span class="sxs-lookup"><span data-stu-id="745b1-109">Name</span></span>    | <span data-ttu-id="745b1-110">Valore</span><span class="sxs-lookup"><span data-stu-id="745b1-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="745b1-111">Scope</span><span class="sxs-lookup"><span data-stu-id="745b1-111">Scope</span></span>   | <span data-ttu-id="745b1-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="745b1-112">Edge</span></span>        |
| <span data-ttu-id="745b1-113">Version</span><span class="sxs-lookup"><span data-stu-id="745b1-113">Version</span></span> | <span data-ttu-id="745b1-114">4.7.2</span><span class="sxs-lookup"><span data-stu-id="745b1-114">4.7.2</span></span>       |
| <span data-ttu-id="745b1-115">Type</span><span class="sxs-lookup"><span data-stu-id="745b1-115">Type</span></span>    | <span data-ttu-id="745b1-116">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="745b1-116">Retargeting</span></span> |
