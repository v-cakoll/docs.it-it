---
ms.openlocfilehash: 1ea2d70a7cfe04cc4c4b9b58ea6bb6fa0226b245
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721604"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a><span data-ttu-id="f30f1-101">Modifica dell'accesso per AccessibleObject. RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="f30f1-101">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>

<span data-ttu-id="f30f1-102">A partire da .NET Core 3,0 RC1, l'accessibilità di `AccessibleObject.RuntimeIDFirstItem` è cambiata da `protected` a `internal` .</span><span class="sxs-lookup"><span data-stu-id="f30f1-102">Starting in .NET Core 3.0 RC1, the accessibility of `AccessibleObject.RuntimeIDFirstItem` has changed from `protected` to `internal`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f30f1-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="f30f1-103">Change description</span></span>

<span data-ttu-id="f30f1-104">A partire da .NET Core 3,0 Preview 4, il `AccessibleObject.RuntimeIDFirstItem` campo era `protected` .</span><span class="sxs-lookup"><span data-stu-id="f30f1-104">Starting with .NET Core 3.0 Preview 4, the `AccessibleObject.RuntimeIDFirstItem` field was `protected`.</span></span> <span data-ttu-id="f30f1-105">A partire da .NET Core 3,0 RC1, è stato modificato da `protected` a `internal` per allinearsi all'accessibilità del campo nell'.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f30f1-105">Starting with .NET Core 3.0 RC1, it has changed from `protected` to `internal` to align with the accessibility of the field in the .NET Framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f30f1-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="f30f1-106">Version introduced</span></span>

<span data-ttu-id="f30f1-107">3,0 RC1</span><span class="sxs-lookup"><span data-stu-id="f30f1-107">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f30f1-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="f30f1-108">Recommended action</span></span>

<span data-ttu-id="f30f1-109">La modifica può interessare l'utente se è stata sviluppata un'app .NET Core con un tipo che deriva da <xref:System.Windows.Forms.AccessibleObject> e accede al `RuntimeIDFirstItem` campo.</span><span class="sxs-lookup"><span data-stu-id="f30f1-109">The change can affect you if you've developed a .NET Core app with a type that derives from <xref:System.Windows.Forms.AccessibleObject> and accesses the `RuntimeIDFirstItem` field.</span></span> <span data-ttu-id="f30f1-110">In tal caso, è possibile definire una costante locale come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f30f1-110">If this is the case, you can define a local constant as follows:</span></span>

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a><span data-ttu-id="f30f1-111">Category</span><span class="sxs-lookup"><span data-stu-id="f30f1-111">Category</span></span>

<span data-ttu-id="f30f1-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f30f1-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f30f1-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="f30f1-113">Affected APIs</span></span>

- <span data-ttu-id="f30f1-114">Non rilevabile tramite l'analisi dell'API.</span><span class="sxs-lookup"><span data-stu-id="f30f1-114">Not detectable via API analysis.</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis.

-->
