---
ms.openlocfilehash: 97299ddb9bee89c792ddb3d2b9c37516180996f7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614882"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a><span data-ttu-id="82e3f-101">La proprietà ContextMenuStrip.SourceControl contiene un controllo valido in caso di ToolStripMenuItems annidati</span><span class="sxs-lookup"><span data-stu-id="82e3f-101">ContextMenuStrip.SourceControl property contains a valid control in the case of nested ToolStripMenuItems</span></span>

#### <a name="details"></a><span data-ttu-id="82e3f-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="82e3f-102">Details</span></span>

<span data-ttu-id="82e3f-103">In .NET Framework 4.7.1 e versioni precedenti, la proprietà <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> restituisce erroneamente Null quando l'utente apre il menu da controlli <xref:System.Windows.Forms.ToolStripMenuItem> annidati.</span><span class="sxs-lookup"><span data-stu-id="82e3f-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property incorrectly returns null when the user opens the menu from nested <xref:System.Windows.Forms.ToolStripMenuItem> controls.</span></span> <span data-ttu-id="82e3f-104">In .NET Framework 4.7.2 e versioni successive, la proprietà <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> è sempre impostata sul controllo del codice sorgente effettivo.</span><span class="sxs-lookup"><span data-stu-id="82e3f-104">In the .NET Framework 4.7.2 and later, <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> property is always set to the actual source control.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="82e3f-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="82e3f-105">Suggestion</span></span>

<span data-ttu-id="82e3f-106">**Come acconsentire esplicitamente o escludere queste modifiche** Affinché un'applicazione tragga vantaggio da queste modifiche, è necessario che venga eseguita nel .NET Framework 4.7.2 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="82e3f-106">**How to opt in or out of these changes** In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="82e3f-107">L'applicazione può trarre vantaggio da queste modifiche in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="82e3f-107">The application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="82e3f-108">È destinata a .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="82e3f-108">It targets the .NET Framework 4.7.2.</span></span> <span data-ttu-id="82e3f-109">Questa modifica è abilitata per impostazione predefinita nelle applicazioni Windows Forms che usano .NET Framework 4.7.2 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="82e3f-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span>
- <span data-ttu-id="82e3f-110">È destinata a .NET Framework 4.7.1 o versione precedente e rifiuta esplicitamente i comportamenti di accessibilità legacy aggiungendo l'[opzione AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) seguente alla sezione `<runtime>` del file app.config e impostandola su `false`, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="82e3f-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the `<runtime>` section of the app.config file and setting it to `false`, as the following example shows.</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false"/>
</runtime>
```

<span data-ttu-id="82e3f-111">Le applicazioni destinate a .NET Framework 4.7.2 o versione successiva e che vogliono mantenere il comportamento legacy possono acconsentire esplicitamente all'uso del valore del controllo del codice sorgente legacy impostando in modo esplicito questa opzione AppContext su `true`.</span><span class="sxs-lookup"><span data-stu-id="82e3f-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to the use of the legacy source control value by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="82e3f-112">Nome</span><span class="sxs-lookup"><span data-stu-id="82e3f-112">Name</span></span>    | <span data-ttu-id="82e3f-113">Valore</span><span class="sxs-lookup"><span data-stu-id="82e3f-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="82e3f-114">Scope</span><span class="sxs-lookup"><span data-stu-id="82e3f-114">Scope</span></span>   | <span data-ttu-id="82e3f-115">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="82e3f-115">Edge</span></span>        |
| <span data-ttu-id="82e3f-116">Version</span><span class="sxs-lookup"><span data-stu-id="82e3f-116">Version</span></span> | <span data-ttu-id="82e3f-117">4.7.2</span><span class="sxs-lookup"><span data-stu-id="82e3f-117">4.7.2</span></span>       |
| <span data-ttu-id="82e3f-118">Type</span><span class="sxs-lookup"><span data-stu-id="82e3f-118">Type</span></span>    | <span data-ttu-id="82e3f-119">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="82e3f-119">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="82e3f-120">API interessate</span><span class="sxs-lookup"><span data-stu-id="82e3f-120">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>
