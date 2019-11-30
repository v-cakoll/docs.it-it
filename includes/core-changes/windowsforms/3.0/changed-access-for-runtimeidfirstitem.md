---
ms.openlocfilehash: 5bbbf9075683b0f124e126b661b4ab85011e6c2e
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644047"
---
### <a name="change-of-access-for-accessibleobjectruntimeidfirstitem"></a><span data-ttu-id="0c616-101">Modifica dell'accesso per AccessibleObject. RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="0c616-101">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>

<span data-ttu-id="0c616-102">A partire da .NET Core 3,0 RC1, l'accessibilità di `AccessibleObject.RuntimeIDFirstItem` è cambiata da `protected` a `internal`.</span><span class="sxs-lookup"><span data-stu-id="0c616-102">Starting in .NET Core 3.0 RC1, the accessibility of `AccessibleObject.RuntimeIDFirstItem` has changed from `protected` to `internal`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0c616-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="0c616-103">Change description</span></span>

<span data-ttu-id="0c616-104">A partire da .NET Core 3,0 Preview 4, il campo `AccessibleObject.RuntimeIDFirstItem` è stato `protected`.</span><span class="sxs-lookup"><span data-stu-id="0c616-104">Starting with .NET Core 3.0 Preview 4, the `AccessibleObject.RuntimeIDFirstItem` field was `protected`.</span></span> <span data-ttu-id="0c616-105">A partire da .NET Core 3,0 RC1, è stato modificato da `protected` a `internal` per allinearsi con l'accessibilità del campo nella .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0c616-105">Starting with .NET Core 3.0 RC1, it has changed from `protected` to `internal` to align with the accessibility of the field in the .NET Framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0c616-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="0c616-106">Version introduced</span></span>

<span data-ttu-id="0c616-107">3,0 RC1</span><span class="sxs-lookup"><span data-stu-id="0c616-107">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0c616-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="0c616-108">Recommended action</span></span>

<span data-ttu-id="0c616-109">La modifica può interessare l'utente se è stata sviluppata un'app .NET Core con un tipo che deriva da <xref:System.Windows.Forms.AccessibleObject> e accede al campo `RuntimeIDFirstItem`.</span><span class="sxs-lookup"><span data-stu-id="0c616-109">The change can affect you if you've developed a .NET Core app with a type that derives from <xref:System.Windows.Forms.AccessibleObject> and accesses the `RuntimeIDFirstItem` field.</span></span> <span data-ttu-id="0c616-110">In tal caso, è possibile definire una costante locale come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0c616-110">If this is the case, you can define a local constant as follows:</span></span>

```csharp
const int RuntimeIDFirstItem = 0x2a;
```

#### <a name="category"></a><span data-ttu-id="0c616-111">Category</span><span class="sxs-lookup"><span data-stu-id="0c616-111">Category</span></span>

<span data-ttu-id="0c616-112">Windows Form</span><span class="sxs-lookup"><span data-stu-id="0c616-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0c616-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="0c616-113">Affected APIs</span></span>

- <span data-ttu-id="0c616-114">Non rilevabile tramite l'analisi dell'API.</span><span class="sxs-lookup"><span data-stu-id="0c616-114">Not detectable via API analysis.</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
