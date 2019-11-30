---
ms.openlocfilehash: 82835915efa0e113e81bb09bd5062ee3252f2a64
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568171"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a><span data-ttu-id="e986d-101">InvalidAsynchronousStateException spostato in un altro assembly</span><span class="sxs-lookup"><span data-stu-id="e986d-101">InvalidAsynchronousStateException moved to another assembly</span></span>

<span data-ttu-id="e986d-102">La classe <xref:System.ComponentModel.InvalidAsynchronousStateException> è stata spostata.</span><span class="sxs-lookup"><span data-stu-id="e986d-102">The <xref:System.ComponentModel.InvalidAsynchronousStateException> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e986d-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="e986d-103">Change description</span></span>

<span data-ttu-id="e986d-104">In .NET Core 2,2 e versioni precedenti, la classe <xref:System.ComponentModel.InvalidAsynchronousStateException> si trova nell'assembly *System. ComponentModel. TypeConverter* .</span><span class="sxs-lookup"><span data-stu-id="e986d-104">In .NET Core 2.2 and earlier versions, the <xref:System.ComponentModel.InvalidAsynchronousStateException> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="e986d-105">A partire da .NET Core 3,0, si trova nell'assembly *System. ComponentModel. Primitives* .</span><span class="sxs-lookup"><span data-stu-id="e986d-105">Starting with .NET Core 3.0, it is found in the *System.ComponentModel.Primitives* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e986d-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="e986d-106">Version introduced</span></span>

<span data-ttu-id="e986d-107">3.0</span><span class="sxs-lookup"><span data-stu-id="e986d-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e986d-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="e986d-108">Recommended action</span></span>

<span data-ttu-id="e986d-109">Questa modifica riguarda solo le applicazioni che usano la reflection per caricare il <xref:System.ComponentModel.InvalidAsynchronousStateException> chiamando un metodo come <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> o un overload di <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> che presuppone che il tipo sia in un assembly specifico.</span><span class="sxs-lookup"><span data-stu-id="e986d-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.InvalidAsynchronousStateException> by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="e986d-110">In tal caso, l'assembly a cui si fa riferimento nella chiamata al metodo deve essere aggiornato per riflettere il nuovo percorso dell'assembly del tipo.</span><span class="sxs-lookup"><span data-stu-id="e986d-110">If that is the case, the assembly the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="e986d-111">Category</span><span class="sxs-lookup"><span data-stu-id="e986d-111">Category</span></span>

<span data-ttu-id="e986d-112">CoreFx</span><span class="sxs-lookup"><span data-stu-id="e986d-112">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e986d-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="e986d-113">Affected APIs</span></span>

- <span data-ttu-id="e986d-114">nessuna</span><span class="sxs-lookup"><span data-stu-id="e986d-114">None</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
