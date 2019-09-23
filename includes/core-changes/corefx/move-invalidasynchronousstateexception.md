---
ms.openlocfilehash: 4b41e5fcb6da638457ca8029a635f391b6a7b8ec
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182082"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a><span data-ttu-id="3454b-101">InvalidAsynchronousStateException spostato in un altro assembly</span><span class="sxs-lookup"><span data-stu-id="3454b-101">InvalidAsynchronousStateException moved to another assembly</span></span>

<span data-ttu-id="3454b-102">La <xref:System.ComponentModel.InvalidAsynchronousStateException> classe è stata spostata.</span><span class="sxs-lookup"><span data-stu-id="3454b-102">The <xref:System.ComponentModel.InvalidAsynchronousStateException> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3454b-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="3454b-103">Change description</span></span>

<span data-ttu-id="3454b-104">In .NET Core 2,2 e versioni precedenti, la <xref:System.ComponentModel.InvalidAsynchronousStateException> classe si trova nell'assembly *System. ComponentModel. TypeConverter* .</span><span class="sxs-lookup"><span data-stu-id="3454b-104">In .NET Core 2.2 and earlier versions, the <xref:System.ComponentModel.InvalidAsynchronousStateException> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="3454b-105">A partire da .NET Core 3,0, si trova nell'assembly *System. ComponentModel. Primitives* .</span><span class="sxs-lookup"><span data-stu-id="3454b-105">Starting with .NET Core 3.0, it is found in the *System.ComponentModel.Primitives* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3454b-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="3454b-106">Version introduced</span></span>

<span data-ttu-id="3454b-107">3.0</span><span class="sxs-lookup"><span data-stu-id="3454b-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3454b-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="3454b-108">Recommended action</span></span>

<span data-ttu-id="3454b-109">Questa modifica riguarda solo le applicazioni che usano la reflection per <xref:System.ComponentModel.InvalidAsynchronousStateException> caricare l'oggetto chiamando un metodo <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> come o un overload <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> di che presuppone che il tipo sia in un assembly specifico.</span><span class="sxs-lookup"><span data-stu-id="3454b-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.InvalidAsynchronousStateException> by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="3454b-110">In tal caso, l'assembly a cui si fa riferimento nella chiamata al metodo deve essere aggiornato per riflettere il nuovo percorso dell'assembly del tipo.</span><span class="sxs-lookup"><span data-stu-id="3454b-110">If that is the case, the assembly the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="3454b-111">Category</span><span class="sxs-lookup"><span data-stu-id="3454b-111">Category</span></span>

<span data-ttu-id="3454b-112">CoreFx</span><span class="sxs-lookup"><span data-stu-id="3454b-112">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3454b-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="3454b-113">Affected APIs</span></span>

- <span data-ttu-id="3454b-114">nessuno</span><span class="sxs-lookup"><span data-stu-id="3454b-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->