---
ms.openlocfilehash: aab7d8538c875e35c832acc2a6c64beb84d4fb47
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702441"
---
### <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="5fb8c-101">I metodi WinForms ora generano ArgumentException</span><span class="sxs-lookup"><span data-stu-id="5fb8c-101">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="5fb8c-102">Alcuni Windows Forms metodi generano ora un oggetto <xref:System.ArgumentException> per gli argomenti non validi, in cui in precedenza non lo facevano.</span><span class="sxs-lookup"><span data-stu-id="5fb8c-102">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5fb8c-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="5fb8c-103">Change description</span></span>

<span data-ttu-id="5fb8c-104">In precedenza, il passaggio di argomenti di tipo imprevisto o non corretto a determinati metodi di Windows Forms comporterebbe uno stato indeterminato.</span><span class="sxs-lookup"><span data-stu-id="5fb8c-104">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="5fb8c-105">A partire da .NET 5,0, questi metodi generano ora un oggetto <xref:System.ArgumentException> quando vengono passati argomenti non validi.</span><span class="sxs-lookup"><span data-stu-id="5fb8c-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="5fb8c-106">La generazione di un oggetto è <xref:System.ArgumentException> conforme al comportamento del runtime .NET.</span><span class="sxs-lookup"><span data-stu-id="5fb8c-106">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="5fb8c-107">Consente inoltre di migliorare l'esperienza di debug, comunicando chiaramente quale argomento non è valido.</span><span class="sxs-lookup"><span data-stu-id="5fb8c-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

<span data-ttu-id="5fb8c-108">Nella tabella seguente sono elencati i metodi e i parametri interessati:</span><span class="sxs-lookup"><span data-stu-id="5fb8c-108">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="5fb8c-109">Metodo</span><span class="sxs-lookup"><span data-stu-id="5fb8c-109">Method</span></span> | <span data-ttu-id="5fb8c-110">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="5fb8c-110">Parameter name</span></span> | <span data-ttu-id="5fb8c-111">Condizione</span><span class="sxs-lookup"><span data-stu-id="5fb8c-111">Condition</span></span> | <span data-ttu-id="5fb8c-112">Versione aggiunta</span><span class="sxs-lookup"><span data-stu-id="5fb8c-112">Version added</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="5fb8c-113">L'argomento non è di tipo <xref:System.Windows.Forms.TabPage> .</span><span class="sxs-lookup"><span data-stu-id="5fb8c-113">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="5fb8c-114">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="5fb8c-114">5.0 Preview 1</span></span> |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | <span data-ttu-id="5fb8c-115">L'argomento è `null` , <xref:System.String.Empty?displayProperty=nameWithType> o uno spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="5fb8c-115">Argument is `null`, <xref:System.String.Empty?displayProperty=nameWithType>, or white space.</span></span> | <span data-ttu-id="5fb8c-116">5,0 Preview 5</span><span class="sxs-lookup"><span data-stu-id="5fb8c-116">5.0 Preview 5</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="5fb8c-117">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="5fb8c-117">Version introduced</span></span>

<span data-ttu-id="5fb8c-118">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="5fb8c-118">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5fb8c-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="5fb8c-119">Recommended action</span></span>

- <span data-ttu-id="5fb8c-120">Aggiornare il codice per impedire il passaggio di argomenti non validi.</span><span class="sxs-lookup"><span data-stu-id="5fb8c-120">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="5fb8c-121">Se necessario, gestire un oggetto <xref:System.ArgumentException> quando si chiama il metodo.</span><span class="sxs-lookup"><span data-stu-id="5fb8c-121">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

#### <a name="category"></a><span data-ttu-id="5fb8c-122">Category</span><span class="sxs-lookup"><span data-stu-id="5fb8c-122">Category</span></span>

<span data-ttu-id="5fb8c-123">Windows Form</span><span class="sxs-lookup"><span data-stu-id="5fb8c-123">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5fb8c-124">API interessate</span><span class="sxs-lookup"><span data-stu-id="5fb8c-124">Affected APIs</span></span>

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>
- <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`

-->
