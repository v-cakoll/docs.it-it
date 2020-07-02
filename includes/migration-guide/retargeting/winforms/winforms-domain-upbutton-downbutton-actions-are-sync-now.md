---
ms.openlocfilehash: f75a652f15be6b0d184db20dc5cd8aafd80539fe
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614910"
---
### <a name="winforms-domain-upbutton-and-downbutton-actions-are-in-sync-now"></a><span data-ttu-id="702b7-101">Azioni upbutton e downbutton del dominio di Windows Forms ora sincronizzate</span><span class="sxs-lookup"><span data-stu-id="702b7-101">WinForm's Domain upbutton and downbutton actions are in sync now</span></span>

#### <a name="details"></a><span data-ttu-id="702b7-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="702b7-102">Details</span></span>

<span data-ttu-id="702b7-103">In .NET Framework 4.7.1 e versioni precedenti, l'azione <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> del controllo <xref:System.Windows.Forms.DomainUpDown> viene ignorata se è presente testo del controllo e lo sviluppatore deve usare l'azione <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> sul controllo prima di usare l'azione <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="702b7-103">In the .NET Framework 4.7.1 and previous versions the <xref:System.Windows.Forms.DomainUpDown> control's <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action is ignored when control text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before using <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="702b7-104">A partire da .NET Framework 4.7.2 entrambe le azioni <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> e <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> funzionano in modo indipendente in questo scenario e rimangono sincronizzate.</span><span class="sxs-lookup"><span data-stu-id="702b7-104">Starting with the .NET Framework 4.7.2 both the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> actions work independently in this scenario and remain in sync.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="702b7-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="702b7-105">Suggestion</span></span>

<span data-ttu-id="702b7-106">Perché un'applicazione possa usufruire di queste modifiche, è necessario che sia eseguita in .NET Framework 4.7.2 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="702b7-106">In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="702b7-107">L'applicazione può trarre vantaggio da queste modifiche in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="702b7-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="702b7-108">Viene ricompilata in modo da essere destinata a .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="702b7-108">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="702b7-109">Questa modifica è abilitata per impostazione predefinita nelle applicazioni Windows Forms che usano .NET Framework 4.7.2 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="702b7-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="702b7-110">Rifiuta esplicitamente il comportamento di scorrimento legacy aggiungendo l'[opzione AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) seguente alla sezione `<runtime>` del file app.config e impostandola su `false`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="702b7-110">It opts out of the legacy scrolling behavior by adding the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the `<runtime>` section of the app config file and setting it to `false`, as the following example shows.</span></span>

<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="702b7-111">Nome</span><span class="sxs-lookup"><span data-stu-id="702b7-111">Name</span></span>    | <span data-ttu-id="702b7-112">Valore</span><span class="sxs-lookup"><span data-stu-id="702b7-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="702b7-113">Scope</span><span class="sxs-lookup"><span data-stu-id="702b7-113">Scope</span></span>   | <span data-ttu-id="702b7-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="702b7-114">Edge</span></span>        |
| <span data-ttu-id="702b7-115">Version</span><span class="sxs-lookup"><span data-stu-id="702b7-115">Version</span></span> | <span data-ttu-id="702b7-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="702b7-116">4.7.2</span></span>       |
| <span data-ttu-id="702b7-117">Type</span><span class="sxs-lookup"><span data-stu-id="702b7-117">Type</span></span>    | <span data-ttu-id="702b7-118">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="702b7-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="702b7-119">API interessate</span><span class="sxs-lookup"><span data-stu-id="702b7-119">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
