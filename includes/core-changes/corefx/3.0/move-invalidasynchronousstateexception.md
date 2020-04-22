---
ms.openlocfilehash: ace0a4a60ad4d3f3a13cf4bdb2431e61d04ad8e7
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021647"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a><span data-ttu-id="eca56-101">InvalidAsynchronousStateException spostato in un altro assembly</span><span class="sxs-lookup"><span data-stu-id="eca56-101">InvalidAsynchronousStateException moved to another assembly</span></span>

<span data-ttu-id="eca56-102">La <xref:System.ComponentModel.InvalidAsynchronousStateException> classe è stata spostata.</span><span class="sxs-lookup"><span data-stu-id="eca56-102">The <xref:System.ComponentModel.InvalidAsynchronousStateException> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="eca56-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="eca56-103">Change description</span></span>

<span data-ttu-id="eca56-104">In .NET Core 2.2 e <xref:System.ComponentModel.InvalidAsynchronousStateException> versioni precedenti, la classe si trova nell'assembly *System.ComponentModel.TypeConverter.*</span><span class="sxs-lookup"><span data-stu-id="eca56-104">In .NET Core 2.2 and earlier versions, the <xref:System.ComponentModel.InvalidAsynchronousStateException> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="eca56-105">A partire da .NET Core 3.0, si trova nell'assembly *System.ComponentModel.Primitives.*</span><span class="sxs-lookup"><span data-stu-id="eca56-105">Starting with .NET Core 3.0, it is found in the *System.ComponentModel.Primitives* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="eca56-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="eca56-106">Version introduced</span></span>

<span data-ttu-id="eca56-107">3.0</span><span class="sxs-lookup"><span data-stu-id="eca56-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="eca56-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="eca56-108">Recommended action</span></span>

<span data-ttu-id="eca56-109">Questa modifica ha effetto solo sulle <xref:System.ComponentModel.InvalidAsynchronousStateException> applicazioni che utilizzano la reflection per caricare l'oggetto chiamando un metodo, ad <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> esempio o un overload che <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> presuppone che il tipo si trova in un determinato assembly.</span><span class="sxs-lookup"><span data-stu-id="eca56-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.InvalidAsynchronousStateException> by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="eca56-110">In questo caso, l'assembly a cui si fa riferimento nella chiamata al metodo deve essere aggiornato per riflettere il nuovo percorso dell'assembly del tipo.</span><span class="sxs-lookup"><span data-stu-id="eca56-110">If that is the case, the assembly the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="eca56-111">Category</span><span class="sxs-lookup"><span data-stu-id="eca56-111">Category</span></span>

<span data-ttu-id="eca56-112">Librerie .NET di base</span><span class="sxs-lookup"><span data-stu-id="eca56-112">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="eca56-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="eca56-113">Affected APIs</span></span>

<span data-ttu-id="eca56-114">No.</span><span class="sxs-lookup"><span data-stu-id="eca56-114">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
