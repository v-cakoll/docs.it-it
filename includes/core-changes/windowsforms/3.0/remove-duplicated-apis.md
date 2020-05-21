---
ms.openlocfilehash: 3dfacadb5127319d4ce27f367803637cfb1ed00f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721027"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a><span data-ttu-id="48512-101">API duplicate rimosse da Windows Forms</span><span class="sxs-lookup"><span data-stu-id="48512-101">Duplicated APIs removed from Windows Forms</span></span>

<span data-ttu-id="48512-102">Una serie di API duplicate accidentalmente nello <xref:System.Windows.Forms?displayProperty=fullName> spazio dei nomi a partire da .net core 3,0 Preview 4 sono state rimosse in .net core 3,0 RC1.</span><span class="sxs-lookup"><span data-stu-id="48512-102">A number of APIs accidentally duplicated in the <xref:System.Windows.Forms?displayProperty=fullName> namespace starting in .NET Core 3.0 Preview 4 have been removed in .NET Core 3.0 RC1.</span></span>

#### <a name="change-description"></a><span data-ttu-id="48512-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="48512-103">Change description</span></span>

<span data-ttu-id="48512-104">.NET Core 3,0 Preview 4 ha inavvertitamente duplicato un numero di tipi nello <xref:System.Windows.Forms?displayProperty=fullName> spazio dei nomi già esistente nello <xref:System.ComponentModel.Design?displayProperty=fullName> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="48512-104">.NET Core 3.0 Preview 4 inadvertently duplicated a number of types in the <xref:System.Windows.Forms?displayProperty=fullName> namespace that already existed in the <xref:System.ComponentModel.Design?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="48512-105">A partire da .NET Core 3,0 RC1, questi tipi duplicati non sono più disponibili.</span><span class="sxs-lookup"><span data-stu-id="48512-105">Starting with .NET Core 3.0 RC1, these duplicated types are no longer available.</span></span> <span data-ttu-id="48512-106">Nella tabella seguente vengono elencati il tipo originale e il tipo duplicato:</span><span class="sxs-lookup"><span data-stu-id="48512-106">The following table shows lists the original type and its duplicated type:</span></span>

> [!div class="mx-tdCol2BreakAll"]
> |<span data-ttu-id="48512-107">Tipo originale</span><span class="sxs-lookup"><span data-stu-id="48512-107">Original type</span></span>|<span data-ttu-id="48512-108">Tipo duplicato</span><span class="sxs-lookup"><span data-stu-id="48512-108">Duplicated type</span></span>|
> |---|---|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
> |<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
> |<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a><span data-ttu-id="48512-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="48512-109">Version introduced</span></span>

<span data-ttu-id="48512-110">3,0 RC1</span><span class="sxs-lookup"><span data-stu-id="48512-110">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="48512-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="48512-111">Recommended action</span></span>

<span data-ttu-id="48512-112">Aggiornare il codice in modo che faccia riferimento al tipo originale, come illustrato nella colonna di **tipo originale** della tabella.</span><span class="sxs-lookup"><span data-stu-id="48512-112">Update the code to reference the original type, as shown in the **Original type** column of the table.</span></span>

#### <a name="category"></a><span data-ttu-id="48512-113">Category</span><span class="sxs-lookup"><span data-stu-id="48512-113">Category</span></span>

<span data-ttu-id="48512-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="48512-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="48512-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="48512-115">Affected APIs</span></span>

- <span data-ttu-id="48512-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="48512-116">None.</span></span>

<!--

#### Affected APIs

- Not detectable via API analysis.

-->
