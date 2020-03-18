---
ms.openlocfilehash: 75baa4f23eae838defafd3ce9b3907a187982a18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937087"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="f3ed3-101">EnableVisualStyleValidation opzione di compatibilità non supportata</span><span class="sxs-lookup"><span data-stu-id="f3ed3-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="f3ed3-102">L'opzione `Switch.System.Windows.Forms.EnableVisualStyleValidation` di compatibilità non è supportata in Windows Form in .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f3ed3-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f3ed3-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="f3ed3-103">Change description</span></span>

<span data-ttu-id="f3ed3-104">In .NET Framework `Switch.System.Windows.Forms.EnableVisualStyleValidation` l'opzione di compatibilità consente a un'applicazione di rifiutare esplicitamente la convalida degli stili di visualizzazione forniti in formato numerico.</span><span class="sxs-lookup"><span data-stu-id="f3ed3-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="f3ed3-105">In .NET Core `Switch.System.Windows.Forms.EnableVisualStyleValidation` l'opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="f3ed3-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f3ed3-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="f3ed3-106">Version introduced</span></span>

<span data-ttu-id="f3ed3-107">3.0 Anteprima 9</span><span class="sxs-lookup"><span data-stu-id="f3ed3-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f3ed3-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="f3ed3-108">Recommended action</span></span>

<span data-ttu-id="f3ed3-109">Rimuovere l'interruttore.</span><span class="sxs-lookup"><span data-stu-id="f3ed3-109">Remove the switch.</span></span> <span data-ttu-id="f3ed3-110">L'opzione non è supportata e non sono disponibili funzionalità alternative.</span><span class="sxs-lookup"><span data-stu-id="f3ed3-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="f3ed3-111">Category</span><span class="sxs-lookup"><span data-stu-id="f3ed3-111">Category</span></span>

<span data-ttu-id="f3ed3-112">Windows Form</span><span class="sxs-lookup"><span data-stu-id="f3ed3-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f3ed3-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="f3ed3-113">Affected APIs</span></span>

- <span data-ttu-id="f3ed3-114">nessuno</span><span class="sxs-lookup"><span data-stu-id="f3ed3-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
