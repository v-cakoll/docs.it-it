---
ms.openlocfilehash: 394f2daebad7b6af94bee4d7876796e87fe8ab19
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135626"
---
### <a name="handling-corrupted-state-exceptions-is-not-supported"></a><span data-ttu-id="48a67-101">La gestione delle eccezioni di stato danneggiato non è supportata</span><span class="sxs-lookup"><span data-stu-id="48a67-101">Handling corrupted state exceptions is not supported</span></span>

<span data-ttu-id="48a67-102">La gestione delle eccezioni di stato del processo danneggiato in .NET Core non è supportata.</span><span class="sxs-lookup"><span data-stu-id="48a67-102">Handling corrupted-process-state exceptions in .NET Core is not supported.</span></span>

#### <a name="change-description"></a><span data-ttu-id="48a67-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="48a67-103">Change description</span></span>

<span data-ttu-id="48a67-104">In precedenza, le eccezioni di stato del processo danneggiato potevano essere rilevate e gestite da gestori di eccezioni del codice gestito, ad esempio tramite un'istruzione [try-catch](../../../../docs/csharp/language-reference/keywords/try-catch.md) in C#.</span><span class="sxs-lookup"><span data-stu-id="48a67-104">Previously, corrupted-process-state exceptions could be caught and handled by managed code exception handlers, for example, by using a [try-catch](../../../../docs/csharp/language-reference/keywords/try-catch.md) statement in C#.</span></span>

<span data-ttu-id="48a67-105">A partire da .NET Core 1,0, le eccezioni di stato del processo danneggiate non possono essere gestite dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="48a67-105">Starting in .NET Core 1.0, corrupted-process-state exceptions cannot be handled by managed code.</span></span> <span data-ttu-id="48a67-106">Il Common Language Runtime non recapita eccezioni di stato del processo danneggiate al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="48a67-106">The common language runtime doesn't deliver corrupted-process-state exceptions to managed code.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="48a67-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="48a67-107">Version introduced</span></span>

<span data-ttu-id="48a67-108">1.0</span><span class="sxs-lookup"><span data-stu-id="48a67-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="48a67-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="48a67-109">Recommended action</span></span>

<span data-ttu-id="48a67-110">Evitare la necessità di gestire le eccezioni di stato del processo danneggiato risolvendo invece le situazioni che li portano.</span><span class="sxs-lookup"><span data-stu-id="48a67-110">Avoid the need to handle corrupted-process-state exceptions by addressing the situations that lead to them instead.</span></span> <span data-ttu-id="48a67-111">Se è assolutamente necessario gestire le eccezioni di stato del processo danneggiato, scrivere il gestore di eccezioni nel codice C o C++.</span><span class="sxs-lookup"><span data-stu-id="48a67-111">If it's absolutely necessary to handle corrupted-process-state exceptions, write the exception handler in C or C++ code.</span></span>

#### <a name="category"></a><span data-ttu-id="48a67-112">Category</span><span class="sxs-lookup"><span data-stu-id="48a67-112">Category</span></span>

<span data-ttu-id="48a67-113">Principali librerie .NET</span><span class="sxs-lookup"><span data-stu-id="48a67-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="48a67-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="48a67-114">Affected APIs</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName>
- [<span data-ttu-id="48a67-115">legacyCorruptedStateExceptionsPolicy (elemento)</span><span class="sxs-lookup"><span data-stu-id="48a67-115">legacyCorruptedStateExceptionsPolicy element</span></span>](~/docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)

<!--

#### Affected APIs

- `T:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute`

-->
