---
ms.openlocfilehash: 92c03328414410d56a2ff5f445639757367b42c7
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420428"
---
### <a name="processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start"></a><span data-ttu-id="6a9b5-101">Process. StartInfo genera l'eccezione InvalidOperationException per i processi non avviati</span><span class="sxs-lookup"><span data-stu-id="6a9b5-101">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>

<span data-ttu-id="6a9b5-102">La lettura della <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> proprietà per i processi non avviati dal codice genera un'eccezione <xref:System.InvalidOperationException> .</span><span class="sxs-lookup"><span data-stu-id="6a9b5-102">Reading the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for processes that your code didn't start throws an <xref:System.InvalidOperationException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6a9b5-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="6a9b5-103">Change description</span></span>

<span data-ttu-id="6a9b5-104">In .NET Framework, l'accesso alla <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> proprietà per i processi non avviati dal codice restituisce un <xref:System.Diagnostics.ProcessStartInfo> oggetto fittizio.</span><span class="sxs-lookup"><span data-stu-id="6a9b5-104">In .NET Framework, accessing the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for processes that your code didn't start returns a dummy <xref:System.Diagnostics.ProcessStartInfo> object.</span></span> <span data-ttu-id="6a9b5-105">L'oggetto fittizio contiene i valori predefiniti per tutte le proprietà, ad eccezione di <xref:System.Diagnostics.ProcessStartInfo.EnvironmentVariables> .</span><span class="sxs-lookup"><span data-stu-id="6a9b5-105">The dummy object contains default values for all of its properties except <xref:System.Diagnostics.ProcessStartInfo.EnvironmentVariables>.</span></span>

<span data-ttu-id="6a9b5-106">A partire da .NET Core 1,0, se si legge la <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> proprietà per un processo che non è stato avviato (ovvero chiamando <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> ), <xref:System.InvalidOperationException> viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6a9b5-106">Starting in .NET Core 1.0, if you read the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for a process that you didn't start (that is, by calling <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>), an <xref:System.InvalidOperationException> is thrown.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6a9b5-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="6a9b5-107">Version introduced</span></span>

<span data-ttu-id="6a9b5-108">1.0</span><span class="sxs-lookup"><span data-stu-id="6a9b5-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6a9b5-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="6a9b5-109">Recommended action</span></span>

<span data-ttu-id="6a9b5-110">Non accedere alla <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> proprietà per i processi non avviati dal codice.</span><span class="sxs-lookup"><span data-stu-id="6a9b5-110">Do not access the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for processes that your code didn't start.</span></span> <span data-ttu-id="6a9b5-111">Ad esempio, non leggere questa proprietà per i processi restituiti da <xref:System.Diagnostics.Process.GetProcesses%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6a9b5-111">For example, don't read this property for processes returned by <xref:System.Diagnostics.Process.GetProcesses%2A?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="6a9b5-112">Category</span><span class="sxs-lookup"><span data-stu-id="6a9b5-112">Category</span></span>

<span data-ttu-id="6a9b5-113">Principali librerie .NET</span><span class="sxs-lookup"><span data-stu-id="6a9b5-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6a9b5-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="6a9b5-114">Affected APIs</span></span>

- <xref:System.Diagnostics.Process.StartInfo?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Process.StartInfo`

-->
