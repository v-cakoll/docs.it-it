---
ms.openlocfilehash: 53ded5ae6e5a025fc7992da099c3481587bb6f31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614901"
---
### <a name="privatefontcollectionaddfontfile-method-releases-font-resources"></a><span data-ttu-id="bfc1d-101">Rilascio di risorse tipo di carattere da parte del metodo PrivateFontCollection.AddFontFile</span><span class="sxs-lookup"><span data-stu-id="bfc1d-101">PrivateFontCollection.AddFontFile method releases Font resources</span></span>

#### <a name="details"></a><span data-ttu-id="bfc1d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bfc1d-102">Details</span></span>

<span data-ttu-id="bfc1d-103">In .NET Framework 4.7.1 e versioni precedenti, la classe <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> non rilascia le risorse tipo di carattere GDI+ dopo l'eliminazione di <xref:System.Drawing.Text.PrivateFontCollection> per gli oggetti <xref:System.Drawing.Font> che vengono aggiunti a questa raccolta tramite il metodo <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)>.</span><span class="sxs-lookup"><span data-stu-id="bfc1d-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> class does not release the GDI+ font resources after the <xref:System.Drawing.Text.PrivateFontCollection> is disposed for <xref:System.Drawing.Font> objects that are added to this collection using the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)> method.</span></span> <span data-ttu-id="bfc1d-104">In .NET Framework 4.7.2 e versioni successive, <xref:System.Drawing.Text.FontCollection.Dispose%2A> rilascia i tipi di carattere GDI+ aggiunti alla raccolta come file.</span><span class="sxs-lookup"><span data-stu-id="bfc1d-104">In the .NET Framework 4.7.2 and later <xref:System.Drawing.Text.FontCollection.Dispose%2A> releases the GDI+ fonts that were added to the collection as files.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bfc1d-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="bfc1d-105">Suggestion</span></span>

<span data-ttu-id="bfc1d-106">**Come acconsentire esplicitamente o escludere queste modifiche** Affinché un'applicazione tragga vantaggio da queste modifiche, è necessario che venga eseguita nel .NET Framework 4.7.2 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="bfc1d-106">**How to opt in or out of these changes** In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="bfc1d-107">L'applicazione può trarre vantaggio da queste modifiche in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bfc1d-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="bfc1d-108">Viene ricompilata in modo da essere destinata a .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="bfc1d-108">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="bfc1d-109">Questa modifica è abilitata per impostazione predefinita nelle applicazioni Windows Forms che usano .NET Framework 4.7.2 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="bfc1d-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="bfc1d-110">È destinata a .NET Framework 4.7.1 o versione precedente e rifiuta esplicitamente i comportamenti di accessibilità legacy aggiungendo l'[opzione AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) seguente alla sezione `<runtime>` del file app.config e impostandola su `false`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="bfc1d-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the `<runtime>` section of the app.config file and setting it to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Drawing.Text.DoNotRemoveGdiFontsResourcesFromFontCollection=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

<span data-ttu-id="bfc1d-111">Le applicazioni destinate a .NET Framework 4.7.2 o versione successiva che vogliono mantenere il comportamento legacy possono acconsentire esplicitamente a non rilasciare risorse tipo di carattere impostando in modo esplicito questa opzione AppContext su `true`.</span><span class="sxs-lookup"><span data-stu-id="bfc1d-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to not release font resources by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="bfc1d-112">Nome</span><span class="sxs-lookup"><span data-stu-id="bfc1d-112">Name</span></span>    | <span data-ttu-id="bfc1d-113">Valore</span><span class="sxs-lookup"><span data-stu-id="bfc1d-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bfc1d-114">Scope</span><span class="sxs-lookup"><span data-stu-id="bfc1d-114">Scope</span></span>   | <span data-ttu-id="bfc1d-115">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bfc1d-115">Edge</span></span>        |
| <span data-ttu-id="bfc1d-116">Version</span><span class="sxs-lookup"><span data-stu-id="bfc1d-116">Version</span></span> | <span data-ttu-id="bfc1d-117">4.7.2</span><span class="sxs-lookup"><span data-stu-id="bfc1d-117">4.7.2</span></span>       |
| <span data-ttu-id="bfc1d-118">Type</span><span class="sxs-lookup"><span data-stu-id="bfc1d-118">Type</span></span>    | <span data-ttu-id="bfc1d-119">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="bfc1d-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="bfc1d-120">API interessate</span><span class="sxs-lookup"><span data-stu-id="bfc1d-120">Affected APIs</span></span>

- <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>
- <xref:System.Drawing.Text.FontCollection.Dispose?displayProperty=nameWithType>
