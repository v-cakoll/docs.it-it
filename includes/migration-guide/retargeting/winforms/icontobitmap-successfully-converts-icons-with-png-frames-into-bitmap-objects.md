---
ms.openlocfilehash: 811b1a91169eeebfa056d9ecdb07d342d3b32d85
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615715"
---
### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a><span data-ttu-id="3cb36-101">Icon.ToBitmap converte correttamente le icone con frame PNG in oggetti Bitmap</span><span class="sxs-lookup"><span data-stu-id="3cb36-101">Icon.ToBitmap successfully converts icons with PNG frames into Bitmap objects</span></span>

#### <a name="details"></a><span data-ttu-id="3cb36-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3cb36-102">Details</span></span>

<span data-ttu-id="3cb36-103">A partire dalle app destinate a .NET Framework 4.6, il metodo <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> converte correttamente le icone con frame PNG in oggetti Bitmap.</span><span class="sxs-lookup"><span data-stu-id="3cb36-103">Starting with the apps that target the .NET Framework 4.6, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method successfully converts icons with PNG frames into Bitmap objects.</span></span><p/><span data-ttu-id="3cb36-104">Nelle app destinate a .NET Framework 4.5.2 e alle versioni precedenti, il metodo <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> genera un'eccezione <xref:System.ArgumentOutOfRangeException> se l'oggetto Icon presenta frame PNG.</span><span class="sxs-lookup"><span data-stu-id="3cb36-104">In apps that target the .NET Framework 4.5.2 and earlier versions, the  <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method throws an <xref:System.ArgumentOutOfRangeException> exception if the Icon object has PNG frames.</span></span><p/><span data-ttu-id="3cb36-105">Questa modifica influisce sulle app che vengono ricompilate per essere destinate a .NET Framework 4.6 e che implementano una gestione speciale per l'eccezione <xref:System.ArgumentOutOfRangeException> generata quando un oggetto Icon presenta frame PNG.</span><span class="sxs-lookup"><span data-stu-id="3cb36-105">This change affects apps that are recompiled to target the .NET Framework 4.6 and that implement special handling for the <xref:System.ArgumentOutOfRangeException> that is thrown when an Icon object has PNG frames.</span></span> <span data-ttu-id="3cb36-106">Quando è in esecuzione su .NET Framework 4.6, la conversione viene completata correttamente, non viene più generata un'eccezione <xref:System.ArgumentOutOfRangeException> e quindi non viene più richiamato il gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="3cb36-106">When running under the .NET Framework 4.6, the conversion is successful, an <xref:System.ArgumentOutOfRangeException> is no longer thrown, and therefore the exception handler is no longer invoked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3cb36-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="3cb36-107">Suggestion</span></span>

<span data-ttu-id="3cb36-108">Se questo comportamento è indesiderato, è possibile conservare il comportamento precedente aggiungendo l'elemento seguente alla sezione `<runtime>` del file app.config:</span><span class="sxs-lookup"><span data-stu-id="3cb36-108">If this behavior is undesirable, you can retain the previous behavior by adding the following element to the `<runtime>` section of your app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre>

<span data-ttu-id="3cb36-109">Se il file app.config contiene già l'elemento `AppContextSwitchOverrides`, il nuovo valore deve essere unito con l'attributo value come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="3cb36-109">If the app.config file already contains the `AppContextSwitchOverrides` element, the new value should be merged with the value attribute like this:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="3cb36-110">Nome</span><span class="sxs-lookup"><span data-stu-id="3cb36-110">Name</span></span>    | <span data-ttu-id="3cb36-111">Valore</span><span class="sxs-lookup"><span data-stu-id="3cb36-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3cb36-112">Scope</span><span class="sxs-lookup"><span data-stu-id="3cb36-112">Scope</span></span>   | <span data-ttu-id="3cb36-113">Minorenne</span><span class="sxs-lookup"><span data-stu-id="3cb36-113">Minor</span></span>       |
| <span data-ttu-id="3cb36-114">Version</span><span class="sxs-lookup"><span data-stu-id="3cb36-114">Version</span></span> | <span data-ttu-id="3cb36-115">4.6</span><span class="sxs-lookup"><span data-stu-id="3cb36-115">4.6</span></span>         |
| <span data-ttu-id="3cb36-116">Type</span><span class="sxs-lookup"><span data-stu-id="3cb36-116">Type</span></span>    | <span data-ttu-id="3cb36-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="3cb36-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="3cb36-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="3cb36-118">Affected APIs</span></span>

- <xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType>
