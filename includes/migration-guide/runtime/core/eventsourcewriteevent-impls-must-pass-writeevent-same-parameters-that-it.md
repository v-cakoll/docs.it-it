---
ms.openlocfilehash: 47d0aa554d88726caca35fa6bebe4d863fdc0695
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235435"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="0983d-101">EventSource.WriteEvent impls deve passare a WriteEvent gli stessi parametri che ha ricevuto (oltre all'ID)</span><span class="sxs-lookup"><span data-stu-id="0983d-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0983d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0983d-102">Details</span></span>|<span data-ttu-id="0983d-103">Il runtime applica ora il contratto che specifica quanto segue: Una classe derivata da <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> che definisce un metodo di eventi ETW deve chiamare il metodo <code>EventSource.WriteEvent</code> della classe di base con l'ID evento seguito dagli stessi argomenti passati al metodo eventi ETW.</span><span class="sxs-lookup"><span data-stu-id="0983d-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>|
|<span data-ttu-id="0983d-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="0983d-104">Suggestion</span></span>|<span data-ttu-id="0983d-105">Viene generata un'eccezione <xref:System.IndexOutOfRangeException?displayProperty=name> se un <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> legge i dati <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> in-process per un'origine evento che viola questo contratto.</span><span class="sxs-lookup"><span data-stu-id="0983d-105">An <xref:System.IndexOutOfRangeException?displayProperty=name> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> data in process for an event source that violates this contract.</span></span>|
|<span data-ttu-id="0983d-106">Ambito</span><span class="sxs-lookup"><span data-stu-id="0983d-106">Scope</span></span>|<span data-ttu-id="0983d-107">Secondario</span><span class="sxs-lookup"><span data-stu-id="0983d-107">Minor</span></span>|
|<span data-ttu-id="0983d-108">Versione</span><span class="sxs-lookup"><span data-stu-id="0983d-108">Version</span></span>|<span data-ttu-id="0983d-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="0983d-109">4.5.1</span></span>|
|<span data-ttu-id="0983d-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="0983d-110">Type</span></span>|<span data-ttu-id="0983d-111">Runtime</span><span class="sxs-lookup"><span data-stu-id="0983d-111">Runtime</span></span>|
