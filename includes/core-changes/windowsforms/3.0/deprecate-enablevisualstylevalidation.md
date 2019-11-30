---
ms.openlocfilehash: 84b6bfc32f5a73597b227098e5aee1e3450cf85b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644012"
---
### <a name="switchsystemwindowsformsenablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="8ab8a-101">Opzione di compatibilità switch. System. Windows. Forms. EnableVisualStyleValidation non supportata</span><span class="sxs-lookup"><span data-stu-id="8ab8a-101">Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="8ab8a-102">L'opzione di compatibilità `Switch.System.Windows.Forms.EnableVisualStyleValidation` non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="8ab8a-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8ab8a-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="8ab8a-103">Change description</span></span>

<span data-ttu-id="8ab8a-104">In .NET Framework, l'opzione di compatibilità `Switch.System.Windows.Forms.EnableVisualStyleValidation` consentiva a un'applicazione di rifiutare esplicitamente la convalida degli stili di visualizzazione forniti in un formato numerico.</span><span class="sxs-lookup"><span data-stu-id="8ab8a-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="8ab8a-105">In .NET Core, l'opzione `Switch.System.Windows.Forms.EnableVisualStyleValidation` non è supportata.</span><span class="sxs-lookup"><span data-stu-id="8ab8a-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8ab8a-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="8ab8a-106">Version introduced</span></span>

<span data-ttu-id="8ab8a-107">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="8ab8a-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8ab8a-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="8ab8a-108">Recommended action</span></span>

<span data-ttu-id="8ab8a-109">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="8ab8a-109">Remove the switch.</span></span> <span data-ttu-id="8ab8a-110">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="8ab8a-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="8ab8a-111">Category</span><span class="sxs-lookup"><span data-stu-id="8ab8a-111">Category</span></span>

<span data-ttu-id="8ab8a-112">Windows Form</span><span class="sxs-lookup"><span data-stu-id="8ab8a-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8ab8a-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="8ab8a-113">Affected APIs</span></span>

- <span data-ttu-id="8ab8a-114">nessuna</span><span class="sxs-lookup"><span data-stu-id="8ab8a-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
