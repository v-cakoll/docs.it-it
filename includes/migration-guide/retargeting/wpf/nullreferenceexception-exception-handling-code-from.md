---
ms.openlocfilehash: 9c9c4ec55143ef991e9b69a389e0f3368263bb4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614845"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a><span data-ttu-id="c5d76-101">NullReferenceException nel codice di gestione delle eccezioni da ImageSourceConverter.ConvertFrom</span><span class="sxs-lookup"><span data-stu-id="c5d76-101">NullReferenceException in exception handling code from ImageSourceConverter.ConvertFrom</span></span>

#### <a name="details"></a><span data-ttu-id="c5d76-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c5d76-102">Details</span></span>

<span data-ttu-id="c5d76-103">Un errore nel codice di gestione delle eccezioni per <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> ha causato la generazione di un oggetto <xref:System.NullReferenceException?displayProperty=fullName> non corretto anziché dell'eccezione prevista (<xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> o <xref:System.IO.FileNotFoundException?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="c5d76-103">An error in the exception handling code for <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> caused an incorrect <xref:System.NullReferenceException?displayProperty=fullName> to be thrown instead of the intended exception ( <xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> or <xref:System.IO.FileNotFoundException?displayProperty=fullName>).</span></span> <span data-ttu-id="c5d76-104">Questa modifica corregge tale errore e quindi il metodo ora genera l'eccezione appropriata.</span><span class="sxs-lookup"><span data-stu-id="c5d76-104">This change corrects that error so that the method now throws the right exception.</span></span> <p/><span data-ttu-id="c5d76-105">Per impostazione predefinita, tutte le applicazioni destinate a .NET Framework 4.6.2 e versioni precedenti continuano a generare <xref:System.NullReferenceException?displayProperty=fullName> per la compatibilità.</span><span class="sxs-lookup"><span data-stu-id="c5d76-105">By default all applications targeting .NET Framework 4.6.2 and earlier continue to throw <xref:System.NullReferenceException?displayProperty=fullName> for compatibility.</span></span> <span data-ttu-id="c5d76-106">Gli sviluppatori di applicazioni destinate a.NET Framework 4.7 e versioni precedenti visualizzano le eccezioni corrette.</span><span class="sxs-lookup"><span data-stu-id="c5d76-106">Developers targeting .NET Framework 4.7 and above should see the right exceptions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c5d76-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="c5d76-107">Suggestion</span></span>

<span data-ttu-id="c5d76-108">Gli sviluppatori che preferiscono tornare al recupero di <xref:System.NullReferenceException?displayProperty=fullName> quando usano .NET Framework 4.7 o versione successiva come destinazione possono aggiungere o unire il codice seguente al file App.config della propria applicazione:</span><span class="sxs-lookup"><span data-stu-id="c5d76-108">Developers who wish to revert to getting <xref:System.NullReferenceException?displayProperty=fullName> when targeting .NET Framework 4.7 or later can add/merge the following to their application's App.config file:</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="c5d76-109">Nome</span><span class="sxs-lookup"><span data-stu-id="c5d76-109">Name</span></span>    | <span data-ttu-id="c5d76-110">Valore</span><span class="sxs-lookup"><span data-stu-id="c5d76-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c5d76-111">Scope</span><span class="sxs-lookup"><span data-stu-id="c5d76-111">Scope</span></span>   | <span data-ttu-id="c5d76-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c5d76-112">Edge</span></span>        |
| <span data-ttu-id="c5d76-113">Version</span><span class="sxs-lookup"><span data-stu-id="c5d76-113">Version</span></span> | <span data-ttu-id="c5d76-114">4.7</span><span class="sxs-lookup"><span data-stu-id="c5d76-114">4.7</span></span>         |
| <span data-ttu-id="c5d76-115">Type</span><span class="sxs-lookup"><span data-stu-id="c5d76-115">Type</span></span>    | <span data-ttu-id="c5d76-116">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="c5d76-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="c5d76-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="c5d76-117">Affected APIs</span></span>

- <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType>
