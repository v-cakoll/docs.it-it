---
ms.openlocfilehash: 0be59258df10aa13920551f011d68bc8efe20b93
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888124"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a><span data-ttu-id="f1c9f-101">API duplicate rimosse da Windows Form</span><span class="sxs-lookup"><span data-stu-id="f1c9f-101">Duplicated APIs removed from Windows Forms</span></span>

<span data-ttu-id="f1c9f-102">Un numero di API accidentalmente duplicate <xref:System.Windows.Forms?displayProperty=fullName> nello spazio dei nomi a partire da .NET Core 3.0 Preview 4 sono state rimosse in .NET Core 3.0 RC1.</span><span class="sxs-lookup"><span data-stu-id="f1c9f-102">A number of APIs accidentally duplicated in the <xref:System.Windows.Forms?displayProperty=fullName> namespace starting in .NET Core 3.0 Preview 4 have been removed in .NET Core 3.0 RC1.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f1c9f-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="f1c9f-103">Change description</span></span>

<span data-ttu-id="f1c9f-104">.NET Core 3.0 Preview 4 ha inavvertitamente <xref:System.Windows.Forms?displayProperty=fullName> duplicato un numero <xref:System.ComponentModel.Design?displayProperty=fullName> di tipi nello spazio dei nomi già esistenti nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f1c9f-104">.NET Core 3.0 Preview 4 inadvertently duplicated a number of types in the <xref:System.Windows.Forms?displayProperty=fullName> namespace that already existed in the <xref:System.ComponentModel.Design?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="f1c9f-105">A partire da .NET Core 3.0 RC1, questi tipi duplicati non sono più disponibili.</span><span class="sxs-lookup"><span data-stu-id="f1c9f-105">Starting with .NET Core 3.0 RC1, these duplicated types are no longer available.</span></span> <span data-ttu-id="f1c9f-106">Nella tabella seguente sono elencati il tipo originale e il tipo duplicato:</span><span class="sxs-lookup"><span data-stu-id="f1c9f-106">The following table shows lists the original type and its duplicated type:</span></span>

> [!div class="mx-tdCol2BreakAll"]
> |<span data-ttu-id="f1c9f-107">Tipo originale</span><span class="sxs-lookup"><span data-stu-id="f1c9f-107">Original type</span></span>|<span data-ttu-id="f1c9f-108">Tipo duplicato</span><span class="sxs-lookup"><span data-stu-id="f1c9f-108">Duplicated type</span></span>|
> |---|---|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
> |<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
> |<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a><span data-ttu-id="f1c9f-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="f1c9f-109">Version introduced</span></span>

<span data-ttu-id="f1c9f-110">3.0 RC1</span><span class="sxs-lookup"><span data-stu-id="f1c9f-110">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f1c9f-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="f1c9f-111">Recommended action</span></span>

<span data-ttu-id="f1c9f-112">Aggiornare il codice in modo che faccia riferimento al tipo originale, come illustrato nella colonna **Tipo originale** della tabella.</span><span class="sxs-lookup"><span data-stu-id="f1c9f-112">Update the code to reference the original type, as shown in the **Original type** column of the table.</span></span>

#### <a name="category"></a><span data-ttu-id="f1c9f-113">Category</span><span class="sxs-lookup"><span data-stu-id="f1c9f-113">Category</span></span>

<span data-ttu-id="f1c9f-114">Windows Form</span><span class="sxs-lookup"><span data-stu-id="f1c9f-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f1c9f-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="f1c9f-115">Affected APIs</span></span>

- <span data-ttu-id="f1c9f-116">No.</span><span class="sxs-lookup"><span data-stu-id="f1c9f-116">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis.

-->
