---
ms.openlocfilehash: a007022bf32ffe76861f6f9016a7edace17b0f61
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620354"
---
### <a name="data-written-to-printsystemjobinfojobstream-must-be-in-xps-format"></a><span data-ttu-id="6c45d-101">I dati scritti in PrintSystemJobInfo.JobStream devono essere in formato XPS</span><span class="sxs-lookup"><span data-stu-id="6c45d-101">Data written to PrintSystemJobInfo.JobStream must be in XPS format</span></span>

#### <a name="details"></a><span data-ttu-id="6c45d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6c45d-102">Details</span></span>

<span data-ttu-id="6c45d-103">La proprietà <xref:System.Printing.PrintSystemJobInfo.JobStream> espone il flusso di un processo di stampa.</span><span class="sxs-lookup"><span data-stu-id="6c45d-103">The <xref:System.Printing.PrintSystemJobInfo.JobStream> property exposes the stream of a print job.</span></span> <span data-ttu-id="6c45d-104">L'utente può inviare dati non elaborati ai componenti di stampa del sistema operativo sottostanti scrivendo in questo flusso. A partire da .NET Framework 4.5 in Windows 8 e nelle versioni successive del sistema operativo Windows i dati scritti in questo flusso devono essere salvati come flusso del pacchetto in formato XPS.</span><span class="sxs-lookup"><span data-stu-id="6c45d-104">The user can send raw data to the underlying operating system printing components by writing to this stream.Starting with the .NET Framework 4.5 on Windows 8 and later versions of the Windows operating system, data written to this stream must be in XPS format as a package stream.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6c45d-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="6c45d-105">Suggestion</span></span>

<span data-ttu-id="6c45d-106">Per ottenere l'output del contenuto di stampa, è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c45d-106">To output print content, you can do either of the following:</span></span><ul><li><span data-ttu-id="6c45d-107">Usare la classe <xref:System.Windows.Xps.XpsDocumentWriter> per ottenere l'output del contenuto di stampa.</span><span class="sxs-lookup"><span data-stu-id="6c45d-107">Use the <xref:System.Windows.Xps.XpsDocumentWriter> class to output print content.</span></span> <span data-ttu-id="6c45d-108">Questa è l'alternativa consigliata.</span><span class="sxs-lookup"><span data-stu-id="6c45d-108">This is the recommended alternative.</span></span></li><li><span data-ttu-id="6c45d-109">Verificare che i dati inviati al flusso restituito dalla proprietà <xref:System.Printing.PrintSystemJobInfo.JobStream> siano salvati in un flusso del pacchetto in formato XPS.</span><span class="sxs-lookup"><span data-stu-id="6c45d-109">Ensure that the data sent to the stream returned by the <xref:System.Printing.PrintSystemJobInfo.JobStream> property is in XPS format as a package stream.</span></span></li></ul>

| <span data-ttu-id="6c45d-110">Nome</span><span class="sxs-lookup"><span data-stu-id="6c45d-110">Name</span></span>    | <span data-ttu-id="6c45d-111">Valore</span><span class="sxs-lookup"><span data-stu-id="6c45d-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6c45d-112">Scope</span><span class="sxs-lookup"><span data-stu-id="6c45d-112">Scope</span></span>   |<span data-ttu-id="6c45d-113">Minorenne</span><span class="sxs-lookup"><span data-stu-id="6c45d-113">Minor</span></span>|
|<span data-ttu-id="6c45d-114">Version</span><span class="sxs-lookup"><span data-stu-id="6c45d-114">Version</span></span>|<span data-ttu-id="6c45d-115">4.5</span><span class="sxs-lookup"><span data-stu-id="6c45d-115">4.5</span></span>|
|<span data-ttu-id="6c45d-116">Type</span><span class="sxs-lookup"><span data-stu-id="6c45d-116">Type</span></span>|<span data-ttu-id="6c45d-117">Runtime</span><span class="sxs-lookup"><span data-stu-id="6c45d-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6c45d-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="6c45d-118">Affected APIs</span></span>

-<xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType></li></ul>|
