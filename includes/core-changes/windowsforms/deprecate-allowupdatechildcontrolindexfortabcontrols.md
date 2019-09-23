---
ms.openlocfilehash: 1d01de4b978309e05a6036953f2a6909628a2480
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "71181804"
---
### <a name="switchsystemwindowsformsallowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="aecd9-101">Opzione di compatibilità switch. System. Windows. Forms. AllowUpdateChildControlIndexForTabControls non supportata</span><span class="sxs-lookup"><span data-stu-id="aecd9-101">Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="aecd9-102">L' `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` opzione di compatibilità è supportata in Windows Forms in .NET Framework 4,6 e versioni successive, ma non è supportata in Windows Forms a partire da .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="aecd9-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported in Windows Forms starting with .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="aecd9-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="aecd9-103">Change description</span></span>

<span data-ttu-id="aecd9-104">In .NET Framework 4,6 e versioni successive, la selezione di una scheda riordina la raccolta di controlli.</span><span class="sxs-lookup"><span data-stu-id="aecd9-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="aecd9-105">L' `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` opzione di compatibilità consente a un'applicazione di ignorare questo riordino quando questo comportamento è indesiderato.</span><span class="sxs-lookup"><span data-stu-id="aecd9-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="aecd9-106">In .NET Core l' `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="aecd9-106">In .NET Core, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="aecd9-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="aecd9-107">Version introduced</span></span>

<span data-ttu-id="aecd9-108">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="aecd9-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="aecd9-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="aecd9-109">Recommended action</span></span>

<span data-ttu-id="aecd9-110">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="aecd9-110">Remove the switch.</span></span> <span data-ttu-id="aecd9-111">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="aecd9-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="aecd9-112">Category</span><span class="sxs-lookup"><span data-stu-id="aecd9-112">Category</span></span>

<span data-ttu-id="aecd9-113">Windows Form</span><span class="sxs-lookup"><span data-stu-id="aecd9-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="aecd9-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="aecd9-114">Affected APIs</span></span>

- <span data-ttu-id="aecd9-115">nessuno</span><span class="sxs-lookup"><span data-stu-id="aecd9-115">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
