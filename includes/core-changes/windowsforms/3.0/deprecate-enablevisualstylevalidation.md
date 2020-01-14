---
ms.openlocfilehash: 75baa4f23eae838defafd3ce9b3907a187982a18
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937087"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="da9e6-101">Opzione di compatibilità EnableVisualStyleValidation non supportata</span><span class="sxs-lookup"><span data-stu-id="da9e6-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="da9e6-102">L'opzione di compatibilità `Switch.System.Windows.Forms.EnableVisualStyleValidation` non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="da9e6-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="da9e6-103">Descrizione delle modifiche</span><span class="sxs-lookup"><span data-stu-id="da9e6-103">Change description</span></span>

<span data-ttu-id="da9e6-104">In .NET Framework, l'opzione di compatibilità `Switch.System.Windows.Forms.EnableVisualStyleValidation` consentiva a un'applicazione di rifiutare esplicitamente la convalida degli stili di visualizzazione forniti in un formato numerico.</span><span class="sxs-lookup"><span data-stu-id="da9e6-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="da9e6-105">In .NET Core, l'opzione `Switch.System.Windows.Forms.EnableVisualStyleValidation` non è supportata.</span><span class="sxs-lookup"><span data-stu-id="da9e6-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="da9e6-106">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="da9e6-106">Version introduced</span></span>

<span data-ttu-id="da9e6-107">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="da9e6-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="da9e6-108">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="da9e6-108">Recommended action</span></span>

<span data-ttu-id="da9e6-109">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="da9e6-109">Remove the switch.</span></span> <span data-ttu-id="da9e6-110">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="da9e6-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="da9e6-111">Categoria</span><span class="sxs-lookup"><span data-stu-id="da9e6-111">Category</span></span>

<span data-ttu-id="da9e6-112">Windows Form</span><span class="sxs-lookup"><span data-stu-id="da9e6-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="da9e6-113">API interessate</span><span class="sxs-lookup"><span data-stu-id="da9e6-113">Affected APIs</span></span>

- <span data-ttu-id="da9e6-114">nessuna</span><span class="sxs-lookup"><span data-stu-id="da9e6-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
