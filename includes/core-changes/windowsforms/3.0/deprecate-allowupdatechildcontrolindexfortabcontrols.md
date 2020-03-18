---
ms.openlocfilehash: 7e76c32ddeb50eaf1ee93d7cf3cac7469187cc41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937054"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="50827-101">Opzione di compatibilità AllowUpdateChildControlIndexForTabControls non supportata</span><span class="sxs-lookup"><span data-stu-id="50827-101">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="50827-102">L'opzione `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` di compatibilità è supportata in Windows Form in .NET Framework 4.6 e versioni successive, ma non in Windows Form a partire da .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="50827-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported in Windows Forms starting with .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="50827-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="50827-103">Change description</span></span>

<span data-ttu-id="50827-104">In .NET Framework 4.6 e versioni successive, la selezione di una scheda riordina la raccolta di controlli.</span><span class="sxs-lookup"><span data-stu-id="50827-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="50827-105">L'opzione `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` di compatibilità consente a un'applicazione di ignorare questo riordinamento quando questo comportamento non è auspicabile.</span><span class="sxs-lookup"><span data-stu-id="50827-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="50827-106">In .NET Core `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` l'opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="50827-106">In .NET Core, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="50827-107">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="50827-107">Version introduced</span></span>

<span data-ttu-id="50827-108">3.0 Anteprima 9</span><span class="sxs-lookup"><span data-stu-id="50827-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="50827-109">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="50827-109">Recommended action</span></span>

<span data-ttu-id="50827-110">Rimuovere l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="50827-110">Remove the switch.</span></span> <span data-ttu-id="50827-111">L'opzione non è supportata e non sono disponibili funzionalità alternative.</span><span class="sxs-lookup"><span data-stu-id="50827-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="50827-112">Category</span><span class="sxs-lookup"><span data-stu-id="50827-112">Category</span></span>

<span data-ttu-id="50827-113">Windows Form</span><span class="sxs-lookup"><span data-stu-id="50827-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="50827-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="50827-114">Affected APIs</span></span>

- <span data-ttu-id="50827-115">nessuno</span><span class="sxs-lookup"><span data-stu-id="50827-115">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
