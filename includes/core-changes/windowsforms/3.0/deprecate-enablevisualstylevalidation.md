---
ms.openlocfilehash: 97e38685777c7c418c0ccd91f4c433501ecf3aaa
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721484"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="0bb03-101">Opzione di compatibilità EnableVisualStyleValidation non supportata</span><span class="sxs-lookup"><span data-stu-id="0bb03-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="0bb03-102">L' `Switch.System.Windows.Forms.EnableVisualStyleValidation` opzione di compatibilità non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="0bb03-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0bb03-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="0bb03-103">Change description</span></span>

<span data-ttu-id="0bb03-104">In .NET Framework, l' `Switch.System.Windows.Forms.EnableVisualStyleValidation` opzione di compatibilità consentiva a un'applicazione di rifiutare esplicitamente la convalida degli stili di visualizzazione forniti in un formato numerico.</span><span class="sxs-lookup"><span data-stu-id="0bb03-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="0bb03-105">In .NET Core l' `Switch.System.Windows.Forms.EnableVisualStyleValidation` opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="0bb03-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0bb03-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="0bb03-106">Version introduced</span></span>

<span data-ttu-id="0bb03-107">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="0bb03-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0bb03-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="0bb03-108">Recommended action</span></span>

<span data-ttu-id="0bb03-109">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="0bb03-109">Remove the switch.</span></span> <span data-ttu-id="0bb03-110">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="0bb03-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="0bb03-111">Category</span><span class="sxs-lookup"><span data-stu-id="0bb03-111">Category</span></span>

<span data-ttu-id="0bb03-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0bb03-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0bb03-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="0bb03-113">Affected APIs</span></span>

- <span data-ttu-id="0bb03-114">Nessuno</span><span class="sxs-lookup"><span data-stu-id="0bb03-114">None</span></span>

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
