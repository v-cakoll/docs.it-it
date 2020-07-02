---
ms.openlocfilehash: 662c140f019add66ff6605d47ad1f32c3f50d711
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620241"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="1be0c-101">EventSource.WriteEvent impls deve passare a WriteEvent gli stessi parametri che ha ricevuto (oltre all'ID)</span><span class="sxs-lookup"><span data-stu-id="1be0c-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

#### <a name="details"></a><span data-ttu-id="1be0c-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1be0c-102">Details</span></span>

<span data-ttu-id="1be0c-103">Il runtime applica ora il contratto che specifica quanto segue: Una classe derivata da <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> che definisce un metodo di eventi ETW deve chiamare il metodo <code>EventSource.WriteEvent</code> della classe di base con l'ID evento seguito dagli stessi argomenti passati al metodo eventi ETW.</span><span class="sxs-lookup"><span data-stu-id="1be0c-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1be0c-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="1be0c-104">Suggestion</span></span>

<span data-ttu-id="1be0c-105">Viene generata un'eccezione <xref:System.IndexOutOfRangeException?displayProperty=fullName> se un <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> legge i dati <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> in-process per un'origine evento che viola questo contratto.</span><span class="sxs-lookup"><span data-stu-id="1be0c-105">An <xref:System.IndexOutOfRangeException?displayProperty=fullName> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process for an event source that violates this contract.</span></span>

| <span data-ttu-id="1be0c-106">Nome</span><span class="sxs-lookup"><span data-stu-id="1be0c-106">Name</span></span>    | <span data-ttu-id="1be0c-107">Valore</span><span class="sxs-lookup"><span data-stu-id="1be0c-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1be0c-108">Scope</span><span class="sxs-lookup"><span data-stu-id="1be0c-108">Scope</span></span>   |<span data-ttu-id="1be0c-109">Minorenne</span><span class="sxs-lookup"><span data-stu-id="1be0c-109">Minor</span></span>|
|<span data-ttu-id="1be0c-110">Version</span><span class="sxs-lookup"><span data-stu-id="1be0c-110">Version</span></span>|<span data-ttu-id="1be0c-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="1be0c-111">4.5.1</span></span>|
|<span data-ttu-id="1be0c-112">Type</span><span class="sxs-lookup"><span data-stu-id="1be0c-112">Type</span></span>|<span data-ttu-id="1be0c-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="1be0c-113">Runtime</span></span>|
