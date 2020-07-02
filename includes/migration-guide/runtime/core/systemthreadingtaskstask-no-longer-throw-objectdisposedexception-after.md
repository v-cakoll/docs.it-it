---
ms.openlocfilehash: 3eab96149be1e40d528cfd552bbe05ca766cf4e8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620271"
---
### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a><span data-ttu-id="b30e2-101">System.Threading.Tasks.Task non genera più ObjectDisposedException dopo l'eliminazione dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="b30e2-101">System.Threading.Tasks.Task no longer throw ObjectDisposedException after object is disposed</span></span>

#### <a name="details"></a><span data-ttu-id="b30e2-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b30e2-102">Details</span></span>

<span data-ttu-id="b30e2-103">Ad eccezione di <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>, i metodi <xref:System.Threading.Tasks.Task?displayProperty=fullName> non generano più un'eccezione <xref:System.ObjectDisposedException?displayProperty=fullName> successivamente all'eliminazione dell'oggetto. Questa modifica supporta l'uso di attività memorizzate nella cache.</span><span class="sxs-lookup"><span data-stu-id="b30e2-103">Except for <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>, <xref:System.Threading.Tasks.Task?displayProperty=fullName> methods no longer throw an <xref:System.ObjectDisposedException?displayProperty=fullName> exception after the object is disposed.This change supports the use of cached tasks.</span></span> <span data-ttu-id="b30e2-104">Ad esempio, un metodo può restituire un'attività memorizzata nella cache per rappresentare un'operazione già completata anziché allocare una nuova attività.</span><span class="sxs-lookup"><span data-stu-id="b30e2-104">For example, a method can return a cached task to represent an already completed operation instead of allocating a new task.</span></span> <span data-ttu-id="b30e2-105">Ciò non è possibile nelle versioni precedenti di .NET Framework, perché qualsiasi utente dell'attività può rimuoverla e renderla così inutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="b30e2-105">This was impossible in previous .NET Framework versions, because any consumer of the task could dispose of it, which rendered it unusable.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b30e2-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b30e2-106">Suggestion</span></span>

<span data-ttu-id="b30e2-107">Tenere presente che i metodi Task potrebbero non generare più eccezioni <xref:System.ObjectDisposedException?displayProperty=fullName> nei casi in cui viene eliminato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="b30e2-107">Be aware that Task methods may no longer throw <xref:System.ObjectDisposedException?displayProperty=fullName> in cases when the object is disposed.</span></span> <span data-ttu-id="b30e2-108">Se un'app dipende da questa eccezione per venire a conoscenza dell'eliminazione di un'attività, è necessario aggiornarla in modo che controlli in modo esplicito lo stato dell'attività tramite <xref:System.Threading.Tasks.Task.Status>.</span><span class="sxs-lookup"><span data-stu-id="b30e2-108">If an app was depending on this exception to know that a task was disposed, it should be updated to explicitly check the task's status using <xref:System.Threading.Tasks.Task.Status>.</span></span>

| <span data-ttu-id="b30e2-109">Nome</span><span class="sxs-lookup"><span data-stu-id="b30e2-109">Name</span></span>    | <span data-ttu-id="b30e2-110">Valore</span><span class="sxs-lookup"><span data-stu-id="b30e2-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b30e2-111">Scope</span><span class="sxs-lookup"><span data-stu-id="b30e2-111">Scope</span></span>   |<span data-ttu-id="b30e2-112">Minorenne</span><span class="sxs-lookup"><span data-stu-id="b30e2-112">Minor</span></span>|
|<span data-ttu-id="b30e2-113">Version</span><span class="sxs-lookup"><span data-stu-id="b30e2-113">Version</span></span>|<span data-ttu-id="b30e2-114">4.5</span><span class="sxs-lookup"><span data-stu-id="b30e2-114">4.5</span></span>|
|<span data-ttu-id="b30e2-115">Type</span><span class="sxs-lookup"><span data-stu-id="b30e2-115">Type</span></span>|<span data-ttu-id="b30e2-116">Runtime</span><span class="sxs-lookup"><span data-stu-id="b30e2-116">Runtime</span></span>|
