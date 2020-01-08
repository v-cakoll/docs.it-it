---
ms.openlocfilehash: 7c0930f6606aa96d2863dc740aef8e9cab724b37
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344861"
---
### <a name="change-in-default-value-of-useshellexecute"></a><span data-ttu-id="f99e7-101">Modificare il valore predefinito di UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="f99e7-101">Change in default value of UseShellExecute</span></span>

<span data-ttu-id="f99e7-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> ha un valore predefinito di `false` in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f99e7-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> has a default value of `false` on .NET Core.</span></span> <span data-ttu-id="f99e7-103">In .NET Framework, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="f99e7-103">On .NET Framework, its default value is `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f99e7-104">Descrizione delle modifiche</span><span class="sxs-lookup"><span data-stu-id="f99e7-104">Change description</span></span>

<span data-ttu-id="f99e7-105"><xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> consente di avviare direttamente un'applicazione, ad esempio con codice come `Process.Start("mspaint.exe")` che avvia Paint.</span><span class="sxs-lookup"><span data-stu-id="f99e7-105"><xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> lets you launch an application directly, for example, with code such as `Process.Start("mspaint.exe")` that launches Paint.</span></span> <span data-ttu-id="f99e7-106">Consente inoltre di avviare indirettamente un'applicazione associata se <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> è impostata su `true`.</span><span class="sxs-lookup"><span data-stu-id="f99e7-106">It also lets you indirectly launch an associated application if <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is set to `true`.</span></span> <span data-ttu-id="f99e7-107">In .NET Framework, il valore predefinito per <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> è `true`, vale a dire che il codice, ad esempio `Process.Start("mytextfile.txt")` avvierà il blocco note, se i file con *estensione txt* sono stati associati con tale editor.</span><span class="sxs-lookup"><span data-stu-id="f99e7-107">On .NET Framework, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `true`, meaning that code such as `Process.Start("mytextfile.txt")` would launch Notepad, if you've associated *.txt* files with that editor.</span></span> <span data-ttu-id="f99e7-108">Per impedire l'avvio indiretto di un'app in .NET Framework, è necessario impostare in modo esplicito <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> su `false`.</span><span class="sxs-lookup"><span data-stu-id="f99e7-108">To prevent indirectly launching an app on .NET Framework, you must explicitly set <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="f99e7-109">In .NET Core, il valore predefinito per <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> è `false`.</span><span class="sxs-lookup"><span data-stu-id="f99e7-109">On .NET Core, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `false`.</span></span> <span data-ttu-id="f99e7-110">Ciò significa che, per impostazione predefinita, le applicazioni associate non vengono avviate quando si chiama `Process.Start`.</span><span class="sxs-lookup"><span data-stu-id="f99e7-110">This means that, by default, associated applications are not launched when you call `Process.Start`.</span></span>

<span data-ttu-id="f99e7-111">Questa modifica è stata introdotta in .NET Core per motivi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f99e7-111">This change was introduced in .NET Core for performance reasons.</span></span> <span data-ttu-id="f99e7-112">In genere, <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> viene usato per avviare direttamente un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f99e7-112">Typically, <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> is used to launch an application directly.</span></span> <span data-ttu-id="f99e7-113">L'avvio diretto di un'app non deve coinvolgere la shell di Windows e sostenere il costo delle prestazioni associato.</span><span class="sxs-lookup"><span data-stu-id="f99e7-113">Launching an app directly does not need to involve the Windows shell and incur the associated performance cost.</span></span> <span data-ttu-id="f99e7-114">Per rendere più veloce questo caso predefinito, .NET Core modifica il valore predefinito di <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> in `false`.</span><span class="sxs-lookup"><span data-stu-id="f99e7-114">To make this default case faster, .NET Core changes the default value of <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="f99e7-115">Se necessario, è possibile acconsentire esplicitamente al percorso più lento.</span><span class="sxs-lookup"><span data-stu-id="f99e7-115">You can opt in to the slower path if you need it.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f99e7-116">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="f99e7-116">Version introduced</span></span>

<span data-ttu-id="f99e7-117">2.1</span><span class="sxs-lookup"><span data-stu-id="f99e7-117">2.1</span></span>

> [!NOTE]
> <span data-ttu-id="f99e7-118">Nelle versioni precedenti di .NET Core, `UseShellExecute` non è stato implementato per Windows.</span><span class="sxs-lookup"><span data-stu-id="f99e7-118">In earlier versions of .NET Core, `UseShellExecute` was not implemented for Windows.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f99e7-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="f99e7-119">Recommended action</span></span>

<span data-ttu-id="f99e7-120">Se l'app si basa sul comportamento precedente, chiamare <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> con <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> impostato su `true` sull'oggetto <xref:System.Diagnostics.ProcessStartInfo>.</span><span class="sxs-lookup"><span data-stu-id="f99e7-120">If your app relies on the old behavior, call <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> with <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> set to `true` on the <xref:System.Diagnostics.ProcessStartInfo> object.</span></span>

#### <a name="category"></a><span data-ttu-id="f99e7-121">Categoria</span><span class="sxs-lookup"><span data-stu-id="f99e7-121">Category</span></span>

<span data-ttu-id="f99e7-122">CoreFx</span><span class="sxs-lookup"><span data-stu-id="f99e7-122">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f99e7-123">API interessate</span><span class="sxs-lookup"><span data-stu-id="f99e7-123">Affected APIs</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
