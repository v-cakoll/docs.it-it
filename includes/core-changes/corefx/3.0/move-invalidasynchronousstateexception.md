---
ms.openlocfilehash: 78678b4b352bb063d1521e9aee3492c0cee059b8
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721581"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a><span data-ttu-id="0d155-101">InvalidAsynchronousStateException spostato in un altro assembly</span><span class="sxs-lookup"><span data-stu-id="0d155-101">InvalidAsynchronousStateException moved to another assembly</span></span>

<span data-ttu-id="0d155-102">La <xref:System.ComponentModel.InvalidAsynchronousStateException> classe è stata spostata.</span><span class="sxs-lookup"><span data-stu-id="0d155-102">The <xref:System.ComponentModel.InvalidAsynchronousStateException> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0d155-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="0d155-103">Change description</span></span>

<span data-ttu-id="0d155-104">In .NET Core 2,2 e versioni precedenti, la <xref:System.ComponentModel.InvalidAsynchronousStateException> classe si trova nell'assembly *System. ComponentModel. TypeConverter* .</span><span class="sxs-lookup"><span data-stu-id="0d155-104">In .NET Core 2.2 and earlier versions, the <xref:System.ComponentModel.InvalidAsynchronousStateException> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="0d155-105">A partire da .NET Core 3,0, si trova nell'assembly *System. ComponentModel. Primitives* .</span><span class="sxs-lookup"><span data-stu-id="0d155-105">Starting with .NET Core 3.0, it is found in the *System.ComponentModel.Primitives* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0d155-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="0d155-106">Version introduced</span></span>

<span data-ttu-id="0d155-107">3.0</span><span class="sxs-lookup"><span data-stu-id="0d155-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0d155-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="0d155-108">Recommended action</span></span>

<span data-ttu-id="0d155-109">Questa modifica riguarda solo le applicazioni che usano la reflection per caricare l'oggetto chiamando <xref:System.ComponentModel.InvalidAsynchronousStateException> un metodo come <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> o un overload di <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> che presuppone che il tipo sia in un assembly specifico.</span><span class="sxs-lookup"><span data-stu-id="0d155-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.InvalidAsynchronousStateException> by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="0d155-110">In tal caso, aggiornare l'assembly a cui viene fatto riferimento nella chiamata al metodo per riflettere il nuovo percorso dell'assembly del tipo.</span><span class="sxs-lookup"><span data-stu-id="0d155-110">If that is the case, update the assembly referenced in the method call to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="0d155-111">Category</span><span class="sxs-lookup"><span data-stu-id="0d155-111">Category</span></span>

<span data-ttu-id="0d155-112">Principali librerie .NET</span><span class="sxs-lookup"><span data-stu-id="0d155-112">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0d155-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="0d155-113">Affected APIs</span></span>

<span data-ttu-id="0d155-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="0d155-114">None.</span></span>

<!--

#### Affected APIs

- Not detectable via API analysis

-->
