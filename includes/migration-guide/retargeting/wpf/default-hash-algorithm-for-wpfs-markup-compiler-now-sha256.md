---
ms.openlocfilehash: 4303b177ffe01328965c909a5a3809414fcead91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614929"
---
### <a name="the-default-hash-algorithm-for-wpfs-markup-compiler-is-now-sha256"></a><span data-ttu-id="7d9c7-101">SHA256 usato come nuovo algoritmo hash predefinito per il compilatore di markup di WPF</span><span class="sxs-lookup"><span data-stu-id="7d9c7-101">The default hash algorithm for WPF's Markup Compiler is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="7d9c7-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7d9c7-102">Details</span></span>

<span data-ttu-id="7d9c7-103">MarkupCompiler WPF offre servizi di compilazione per i file di markup XAML.</span><span class="sxs-lookup"><span data-stu-id="7d9c7-103">The WPF MarkupCompiler provides compilation services for XAML markup files.</span></span>  <span data-ttu-id="7d9c7-104">In .NET Framework 4.7.1 e versioni precedenti, l'algoritmo hash predefinito usato per i checksum era SHA1.</span><span class="sxs-lookup"><span data-stu-id="7d9c7-104">In the .NET Framework 4.7.1 and earlier versions, the default hash algorithm used for checksums was SHA1.</span></span> <span data-ttu-id="7d9c7-105">A causa di problemi di sicurezza recenti con SHA1, questa impostazione predefinita è stata cambiata in SHA256 a partire da .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="7d9c7-105">Due to recent security concerns with SHA1, this default has been changed to SHA256 starting with the .NET Framework 4.7.2.</span></span>  <span data-ttu-id="7d9c7-106">Questa modifica interessa la generazione di tutti i checksum per i file di markup durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="7d9c7-106">This change affects all checksum generation for markup files during compilation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7d9c7-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="7d9c7-107">Suggestion</span></span>

<span data-ttu-id="7d9c7-108">Uno sviluppatore che ha come destinazione .NET Framework 4.7.2 o versione successiva e vuole ripristinare SHA1 come comportamento hash deve impostare il flag AppContext seguente.</span><span class="sxs-lookup"><span data-stu-id="7d9c7-108">A developer who targets .NET Framework 4.7.2 or greater and wants to revert to SHA1 hashing behavior must set the following AppContext flag.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

<span data-ttu-id="7d9c7-109">Uno sviluppatore che vuole utilizzare l'hash SHA256 con una versione di .NET Framework precedente alla versione 4.7.2 come destinazione deve impostare il flag AppContext seguente.</span><span class="sxs-lookup"><span data-stu-id="7d9c7-109">A developer who wants to utilize SHA256 hashing while targeting a framework version below .NET 4.7.2 must set the below AppContext flag.</span></span>  <span data-ttu-id="7d9c7-110">Si noti che la versione installata di .NET Framework deve corrispondere alla versione 4.7.2 o successiva.</span><span class="sxs-lookup"><span data-stu-id="7d9c7-110">Note that the installed version of the .NET Framework must be 4.7.2 or greater.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=false&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="7d9c7-111">Nome</span><span class="sxs-lookup"><span data-stu-id="7d9c7-111">Name</span></span>    | <span data-ttu-id="7d9c7-112">Valore</span><span class="sxs-lookup"><span data-stu-id="7d9c7-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7d9c7-113">Scope</span><span class="sxs-lookup"><span data-stu-id="7d9c7-113">Scope</span></span>   | <span data-ttu-id="7d9c7-114">Modalità trasparente</span><span class="sxs-lookup"><span data-stu-id="7d9c7-114">Transparent</span></span> |
| <span data-ttu-id="7d9c7-115">Version</span><span class="sxs-lookup"><span data-stu-id="7d9c7-115">Version</span></span> | <span data-ttu-id="7d9c7-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="7d9c7-116">4.7.2</span></span>       |
| <span data-ttu-id="7d9c7-117">Type</span><span class="sxs-lookup"><span data-stu-id="7d9c7-117">Type</span></span>    | <span data-ttu-id="7d9c7-118">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="7d9c7-118">Retargeting</span></span> |
