---
ms.openlocfilehash: e6bb1d53cbe1883b8faef75bd22942bd4f65a5e6
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "71181739"
---
### <a name="switchsystemwindowsformsenablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="109b6-101">Opzione di compatibilità switch. System. Windows. Forms. EnableVisualStyleValidation non supportata</span><span class="sxs-lookup"><span data-stu-id="109b6-101">Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="109b6-102">L' `Switch.System.Windows.Forms.EnableVisualStyleValidation` opzione di compatibilità non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="109b6-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="109b6-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="109b6-103">Change description</span></span>

<span data-ttu-id="109b6-104">In .NET Framework, l' `Switch.System.Windows.Forms.EnableVisualStyleValidation` opzione di compatibilità consentiva a un'applicazione di rifiutare esplicitamente la convalida degli stili di visualizzazione forniti in un formato numerico.</span><span class="sxs-lookup"><span data-stu-id="109b6-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span> 

<span data-ttu-id="109b6-105">In .NET Core l' `Switch.System.Windows.Forms.EnableVisualStyleValidation` opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="109b6-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="109b6-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="109b6-106">Version introduced</span></span>

<span data-ttu-id="109b6-107">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="109b6-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="109b6-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="109b6-108">Recommended action</span></span>

<span data-ttu-id="109b6-109">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="109b6-109">Remove the switch.</span></span> <span data-ttu-id="109b6-110">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="109b6-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="109b6-111">Category</span><span class="sxs-lookup"><span data-stu-id="109b6-111">Category</span></span>

<span data-ttu-id="109b6-112">Windows Form</span><span class="sxs-lookup"><span data-stu-id="109b6-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="109b6-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="109b6-113">Affected APIs</span></span>

- <span data-ttu-id="109b6-114">nessuno</span><span class="sxs-lookup"><span data-stu-id="109b6-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
