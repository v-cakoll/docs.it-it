---
ms.openlocfilehash: a1db9916c69c5974191eb6108fb54a0d9ff060d2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622037"
---
### <a name="sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a><span data-ttu-id="05602-101">SqlConnection.Open non riesce in Windows 7 se sono presenti un provider LSP o BSP Winsock non IFS</span><span class="sxs-lookup"><span data-stu-id="05602-101">SqlConnection.Open fails on Windows 7 with non-IFS Winsock BSP or LSP present</span></span>

#### <a name="details"></a><span data-ttu-id="05602-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="05602-102">Details</span></span>

<span data-ttu-id="05602-103"><xref:System.Data.SqlClient.SqlConnection.Open> e <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)> hanno esito negativo in .NET Framework 4.5 se in esecuzione in un computer Windows 7 in cui sono presenti un provider LSP o BSP Winsock non IFS. Per determinare se è installato un provider LSP o BSP Winsock non IFS, usare il comando <code>netsh WinSock Show Catalog</code> ed esaminare ogni elemento <code>Winsock Catalog Provider Entry</code> restituito.</span><span class="sxs-lookup"><span data-stu-id="05602-103"><xref:System.Data.SqlClient.SqlConnection.Open> and <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)> fail in the .NET Framework 4.5 if running on a Windows 7 machine with a non-IFS Winsock BSP or LSP are present on the computer.To determine whether a non-IFS BSP or LSP is installed, use the <code>netsh WinSock Show Catalog</code> command, and examine every <code>Winsock Catalog Provider Entry</code> item that is returned.</span></span> <span data-ttu-id="05602-104">Se per il valore Service Flags è impostato il bit <code>0x20000</code>, il provider usa handle IFS e funzionerà correttamente.</span><span class="sxs-lookup"><span data-stu-id="05602-104">If the Service Flags value has the <code>0x20000</code> bit set, the provider uses IFS handles and will work correctly.</span></span> <span data-ttu-id="05602-105">Se il bit <code>0x20000</code> non è impostato, si tratta di un LSP o BSP non-IFS.</span><span class="sxs-lookup"><span data-stu-id="05602-105">If the <code>0x20000</code> bit is clear (not set), it is a non-IFS BSP or LSP.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="05602-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="05602-106">Suggestion</span></span>

<span data-ttu-id="05602-107">Questo bug è stato risolto in .NET Framework 4.5.2, pertanto può essere evitato eseguendo l'aggiornamento di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05602-107">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="05602-108">In alternativa, è possibile evitarlo rimuovendo qualsiasi provider LSP Winsock non-IFS installato.</span><span class="sxs-lookup"><span data-stu-id="05602-108">Alternatively, it can be avoided by removing any installed non-IFS Winsock LSPs.</span></span>

| <span data-ttu-id="05602-109">Nome</span><span class="sxs-lookup"><span data-stu-id="05602-109">Name</span></span>    | <span data-ttu-id="05602-110">Valore</span><span class="sxs-lookup"><span data-stu-id="05602-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="05602-111">Scope</span><span class="sxs-lookup"><span data-stu-id="05602-111">Scope</span></span>   |<span data-ttu-id="05602-112">Minorenne</span><span class="sxs-lookup"><span data-stu-id="05602-112">Minor</span></span>|
|<span data-ttu-id="05602-113">Version</span><span class="sxs-lookup"><span data-stu-id="05602-113">Version</span></span>|<span data-ttu-id="05602-114">4.5</span><span class="sxs-lookup"><span data-stu-id="05602-114">4.5</span></span>|
|<span data-ttu-id="05602-115">Type</span><span class="sxs-lookup"><span data-stu-id="05602-115">Type</span></span>|<span data-ttu-id="05602-116">Runtime</span><span class="sxs-lookup"><span data-stu-id="05602-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="05602-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="05602-117">Affected APIs</span></span>

-<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)?displayProperty=nameWithType></li></ul>|
