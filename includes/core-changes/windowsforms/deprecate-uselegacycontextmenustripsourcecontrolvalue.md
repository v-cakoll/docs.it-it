---
ms.openlocfilehash: 5c1dc42a451d2c6a82e2c2429115db023c610334
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181827"
---
### <a name="switchsystemwindowsformsuselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a><span data-ttu-id="8a750-101">Opzione di compatibilità switch. System. Windows. Forms. UseLegacyContextMenuStripSourceControlValue non supportata</span><span class="sxs-lookup"><span data-stu-id="8a750-101">Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>

<span data-ttu-id="8a750-102">L' `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` opzione di compatibilità, introdotta in .NET Framework 4.7.2, non è supportata in Windows Forms in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="8a750-102">The `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch, which was introduced in .NET Framework 4.7.2, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8a750-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="8a750-103">Change description</span></span>

<span data-ttu-id="8a750-104">A partire da .NET Framework 4.7.2, l' `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` opzione di compatibilità consente allo sviluppatore di rifiutare esplicitamente il nuovo comportamento <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> della proprietà, che ora restituisce un riferimento al controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="8a750-104">Starting with the .NET Framework 4.7.2, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` compatibility switch allows the developer to opt out of the new behavior of the <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> property, which now returns a reference to the source control.</span></span> <span data-ttu-id="8a750-105">Il comportamento precedente della proprietà era restituire `null`.</span><span class="sxs-lookup"><span data-stu-id="8a750-105">The previous behavior of the property was to return `null`.</span></span> <span data-ttu-id="8a750-106">Per ulteriori informazioni, vedere [ \<AppContextSwitchOverrides > Element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span><span class="sxs-lookup"><span data-stu-id="8a750-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="8a750-107">In .NET Core l' `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` opzione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="8a750-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8a750-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="8a750-108">Version introduced</span></span>

<span data-ttu-id="8a750-109">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="8a750-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8a750-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="8a750-110">Recommended action</span></span>

<span data-ttu-id="8a750-111">Rimuovere l'opzione.</span><span class="sxs-lookup"><span data-stu-id="8a750-111">Remove the switch.</span></span> <span data-ttu-id="8a750-112">L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.</span><span class="sxs-lookup"><span data-stu-id="8a750-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="8a750-113">Category</span><span class="sxs-lookup"><span data-stu-id="8a750-113">Category</span></span>

<span data-ttu-id="8a750-114">Windows Form</span><span class="sxs-lookup"><span data-stu-id="8a750-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8a750-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="8a750-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
