---
ms.openlocfilehash: 9544b65f31772d0f4cee918528a73171fec4de99
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021821"
---
### <a name="change-in-default-value-of-useshellexecute"></a><span data-ttu-id="b5bb5-101">Modifica del valore predefinito di UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="b5bb5-101">Change in default value of UseShellExecute</span></span>

<span data-ttu-id="b5bb5-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType>ha un valore `false` predefinito di in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b5bb5-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> has a default value of `false` on .NET Core.</span></span> <span data-ttu-id="b5bb5-103">In .NET Framework il `true`valore predefinito è .</span><span class="sxs-lookup"><span data-stu-id="b5bb5-103">On .NET Framework, its default value is `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b5bb5-104">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="b5bb5-104">Change description</span></span>

<span data-ttu-id="b5bb5-105"><xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>consente di avviare direttamente un'applicazione, `Process.Start("mspaint.exe")` ad esempio, con codice come quello che avvia Paint.</span><span class="sxs-lookup"><span data-stu-id="b5bb5-105"><xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> lets you launch an application directly, for example, with code such as `Process.Start("mspaint.exe")` that launches Paint.</span></span> <span data-ttu-id="b5bb5-106">Consente inoltre di avviare indirettamente <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> un'applicazione associata se è impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="b5bb5-106">It also lets you indirectly launch an associated application if <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is set to `true`.</span></span> <span data-ttu-id="b5bb5-107">In .NET Framework, il <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> `true`valore predefinito per `Process.Start("mytextfile.txt")` è , ovvero il codice, ad esempio lancerebbe Il Blocco note, se sono stati associati file *con estensione txt* a tale editor.</span><span class="sxs-lookup"><span data-stu-id="b5bb5-107">On .NET Framework, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `true`, meaning that code such as `Process.Start("mytextfile.txt")` would launch Notepad, if you've associated *.txt* files with that editor.</span></span> <span data-ttu-id="b5bb5-108">Per impedire l'avvio indiretto di un'app `false`in .NET Framework, è necessario impostare in modo esplicito su <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="b5bb5-108">To prevent indirectly launching an app on .NET Framework, you must explicitly set <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="b5bb5-109">In .NET Core, il <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> `false`valore predefinito per è .</span><span class="sxs-lookup"><span data-stu-id="b5bb5-109">On .NET Core, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `false`.</span></span> <span data-ttu-id="b5bb5-110">Ciò significa che, per impostazione predefinita, `Process.Start`le applicazioni associate non vengono avviate quando si chiama .</span><span class="sxs-lookup"><span data-stu-id="b5bb5-110">This means that, by default, associated applications are not launched when you call `Process.Start`.</span></span>

<span data-ttu-id="b5bb5-111">Questa modifica è stata introdotta in .NET Core per motivi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b5bb5-111">This change was introduced in .NET Core for performance reasons.</span></span> <span data-ttu-id="b5bb5-112">In <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> genere, viene utilizzato per avviare direttamente un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b5bb5-112">Typically, <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> is used to launch an application directly.</span></span> <span data-ttu-id="b5bb5-113">L'avvio diretto di un'app non deve coinvolgere la shell di Windows e comporta il costo delle prestazioni associato.</span><span class="sxs-lookup"><span data-stu-id="b5bb5-113">Launching an app directly does not need to involve the Windows shell and incur the associated performance cost.</span></span> <span data-ttu-id="b5bb5-114">Per velocizzare questo caso predefinito, .NET <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> `false`Core modifica il valore predefinito di .</span><span class="sxs-lookup"><span data-stu-id="b5bb5-114">To make this default case faster, .NET Core changes the default value of <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="b5bb5-115">È possibile attivare il percorso più lento se necessario.</span><span class="sxs-lookup"><span data-stu-id="b5bb5-115">You can opt in to the slower path if you need it.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b5bb5-116">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="b5bb5-116">Version introduced</span></span>

<span data-ttu-id="b5bb5-117">2.1</span><span class="sxs-lookup"><span data-stu-id="b5bb5-117">2.1</span></span>

> [!NOTE]
> <span data-ttu-id="b5bb5-118">Nelle versioni precedenti di `UseShellExecute` .NET Core, non era implementato per Windows.</span><span class="sxs-lookup"><span data-stu-id="b5bb5-118">In earlier versions of .NET Core, `UseShellExecute` was not implemented for Windows.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b5bb5-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="b5bb5-119">Recommended action</span></span>

<span data-ttu-id="b5bb5-120">Se l'app si basa sul <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> comportamento `true` precedente, <xref:System.Diagnostics.ProcessStartInfo> chiama con impostato su sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="b5bb5-120">If your app relies on the old behavior, call <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> with <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> set to `true` on the <xref:System.Diagnostics.ProcessStartInfo> object.</span></span>

#### <a name="category"></a><span data-ttu-id="b5bb5-121">Category</span><span class="sxs-lookup"><span data-stu-id="b5bb5-121">Category</span></span>

<span data-ttu-id="b5bb5-122">Librerie .NET di base</span><span class="sxs-lookup"><span data-stu-id="b5bb5-122">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b5bb5-123">API interessate</span><span class="sxs-lookup"><span data-stu-id="b5bb5-123">Affected APIs</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
