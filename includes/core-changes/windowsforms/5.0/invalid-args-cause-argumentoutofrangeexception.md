---
ms.openlocfilehash: f42da00487735acdcc60f876c75e1dfd17103008
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702442"
---
### <a name="winforms-properties-now-throw-argumentoutofrangeexception"></a><span data-ttu-id="c22d6-101">Le proprietà di WinForms ora generano ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="c22d6-101">WinForms properties now throw ArgumentOutOfRangeException</span></span>

<span data-ttu-id="c22d6-102">Alcune proprietà di Windows Forms generano ora un oggetto <xref:System.ArgumentOutOfRangeException> per gli argomenti non validi, in cui in precedenza non lo facevano.</span><span class="sxs-lookup"><span data-stu-id="c22d6-102">Some Windows Forms properties now throw an <xref:System.ArgumentOutOfRangeException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c22d6-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="c22d6-103">Change description</span></span>

<span data-ttu-id="c22d6-104">In precedenza, queste proprietà generavano varie eccezioni, ad esempio <xref:System.NullReferenceException> , <xref:System.IndexOutOfRangeException> o <xref:System.ArgumentException> , quando venivano passati argomenti fuori intervallo.</span><span class="sxs-lookup"><span data-stu-id="c22d6-104">Previously, these properties threw various exceptions, such as <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>, or <xref:System.ArgumentException>, when passed out-of-range arguments.</span></span> <span data-ttu-id="c22d6-105">A partire da .NET 5,0, queste proprietà generano ora un oggetto <xref:System.ArgumentOutOfRangeException> quando vengono passati argomenti che non rientrano nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="c22d6-105">Starting in .NET 5.0, these properties now throw an <xref:System.ArgumentOutOfRangeException> when passed arguments that are out of range.</span></span>

<span data-ttu-id="c22d6-106">La generazione di un oggetto è <xref:System.ArgumentOutOfRangeException> conforme al comportamento del runtime .NET.</span><span class="sxs-lookup"><span data-stu-id="c22d6-106">Throwing an <xref:System.ArgumentOutOfRangeException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="c22d6-107">Consente inoltre di migliorare l'esperienza di debug, comunicando chiaramente quale argomento non è valido.</span><span class="sxs-lookup"><span data-stu-id="c22d6-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c22d6-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="c22d6-108">Version introduced</span></span>

<span data-ttu-id="c22d6-109">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="c22d6-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c22d6-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="c22d6-110">Recommended action</span></span>

- <span data-ttu-id="c22d6-111">Aggiornare il codice per impedire il passaggio di argomenti non validi.</span><span class="sxs-lookup"><span data-stu-id="c22d6-111">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="c22d6-112">Se necessario, gestire un oggetto <xref:System.ArgumentOutOfRangeException> quando si imposta la proprietà.</span><span class="sxs-lookup"><span data-stu-id="c22d6-112">If necessary, handle an <xref:System.ArgumentOutOfRangeException> when setting the property.</span></span>

#### <a name="category"></a><span data-ttu-id="c22d6-113">Category</span><span class="sxs-lookup"><span data-stu-id="c22d6-113">Category</span></span>

<span data-ttu-id="c22d6-114">Windows Form</span><span class="sxs-lookup"><span data-stu-id="c22d6-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c22d6-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="c22d6-115">Affected APIs</span></span>

<span data-ttu-id="c22d6-116">La tabella seguente elenca le proprietà e i parametri interessati:</span><span class="sxs-lookup"><span data-stu-id="c22d6-116">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="c22d6-117">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c22d6-117">Property</span></span> | <span data-ttu-id="c22d6-118">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="c22d6-118">Parameter name</span></span> | <span data-ttu-id="c22d6-119">Versione aggiunta</span><span class="sxs-lookup"><span data-stu-id="c22d6-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)?displayProperty=nameWithType> | `index` | <span data-ttu-id="c22d6-120">5,0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="c22d6-120">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.TreeNode.ImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="c22d6-121">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="c22d6-121">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.TreeNode.SelectedImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="c22d6-122">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="c22d6-122">5.0 Preview 6</span></span> |

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)`
- `P:System.Windows.Forms.TreeNode.ImageIndex`
- `P:System.Windows.Forms.TreeNode.SelectedImageIndex`

-->
