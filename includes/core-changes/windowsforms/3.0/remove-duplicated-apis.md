---
ms.openlocfilehash: e609b8006846cd202a6a7eeec2529cf1fbb09e7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937091"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a><span data-ttu-id="b2828-101">API duplicate rimosse da Windows Form</span><span class="sxs-lookup"><span data-stu-id="b2828-101">Duplicated APIs removed from Windows Forms</span></span>

<span data-ttu-id="b2828-102">Un numero di API accidentalmente duplicate <xref:System.Windows.Forms?displayProperty=fullName> nello spazio dei nomi a partire da .NET Core 3.0 Preview 4 sono state rimosse in .NET Core 3.0 RC1.</span><span class="sxs-lookup"><span data-stu-id="b2828-102">A number of APIs accidentally duplicated in the <xref:System.Windows.Forms?displayProperty=fullName> namespace starting in .NET Core 3.0 Preview 4 have been removed in .NET Core 3.0 RC1.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b2828-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="b2828-103">Change description</span></span>

<span data-ttu-id="b2828-104">.NET Core 3.0 Preview 4 ha inavvertitamente <xref:System.Windows.Forms?displayProperty=fullName> duplicato un numero <xref:System.ComponentModel.Design?displayProperty=fullName> di tipi nello spazio dei nomi già esistenti nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b2828-104">.NET Core 3.0 Preview 4 inadvertently duplicated a number of types in the <xref:System.Windows.Forms?displayProperty=fullName> namespace that already existed in the <xref:System.ComponentModel.Design?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="b2828-105">A partire da .NET Core 3.0 RC1, questi tipi duplicati non sono più disponibili.</span><span class="sxs-lookup"><span data-stu-id="b2828-105">Starting with .NET Core 3.0 RC1, these duplicated types are no longer available.</span></span> <span data-ttu-id="b2828-106">Nella tabella seguente sono elencati il tipo originale e il tipo duplicato:</span><span class="sxs-lookup"><span data-stu-id="b2828-106">The following table shows lists the original type and its duplicated type:</span></span>

> [!div class="mx-tdCol2BreakAll"]
> |<span data-ttu-id="b2828-107">Tipo originale</span><span class="sxs-lookup"><span data-stu-id="b2828-107">Original type</span></span>|<span data-ttu-id="b2828-108">Tipo duplicato</span><span class="sxs-lookup"><span data-stu-id="b2828-108">Duplicated type</span></span>|
> |---|---|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
> |<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
> |<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a><span data-ttu-id="b2828-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="b2828-109">Version introduced</span></span>

<span data-ttu-id="b2828-110">3.0 RC1</span><span class="sxs-lookup"><span data-stu-id="b2828-110">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b2828-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="b2828-111">Recommended action</span></span>

<span data-ttu-id="b2828-112">Aggiornare il codice in modo che faccia riferimento al tipo originale, come illustrato nella colonna **Tipo originale** della tabella.</span><span class="sxs-lookup"><span data-stu-id="b2828-112">Update the code to reference the original type, as shown in the **Original type** column of the table.</span></span>

#### <a name="category"></a><span data-ttu-id="b2828-113">Category</span><span class="sxs-lookup"><span data-stu-id="b2828-113">Category</span></span>

<span data-ttu-id="b2828-114">Windows Form</span><span class="sxs-lookup"><span data-stu-id="b2828-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b2828-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="b2828-115">Affected APIs</span></span>

- <span data-ttu-id="b2828-116">Non rilevabile tramite l'analisi API.</span><span class="sxs-lookup"><span data-stu-id="b2828-116">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis.

-->
