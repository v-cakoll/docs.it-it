---
ms.openlocfilehash: 5212c5d9513a8ef5f51693857d0ddb60db4e49b9
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158398"
---
### <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="b7e1e-101">I metodi WinForms ora generano ArgumentException</span><span class="sxs-lookup"><span data-stu-id="b7e1e-101">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="b7e1e-102">Alcuni Windows Forms metodi generano ora <xref:System.ArgumentException> un oggetto per gli argomenti non validi, in cui in precedenza non lo facevano.</span><span class="sxs-lookup"><span data-stu-id="b7e1e-102">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b7e1e-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="b7e1e-103">Change description</span></span>

<span data-ttu-id="b7e1e-104">In precedenza, il passaggio di argomenti di tipo imprevisto o non corretto a determinati metodi di Windows Forms comporterebbe uno stato indeterminato.</span><span class="sxs-lookup"><span data-stu-id="b7e1e-104">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="b7e1e-105">A partire da .NET 5,0, questi metodi generano <xref:System.ArgumentException> ora un oggetto quando vengono passati argomenti non validi.</span><span class="sxs-lookup"><span data-stu-id="b7e1e-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="b7e1e-106">La generazione <xref:System.ArgumentException> di un oggetto è conforme al comportamento del runtime .NET.</span><span class="sxs-lookup"><span data-stu-id="b7e1e-106">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="b7e1e-107">Consente inoltre di migliorare l'esperienza di debug, comunicando chiaramente quale argomento non è valido.</span><span class="sxs-lookup"><span data-stu-id="b7e1e-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

<span data-ttu-id="b7e1e-108">Nella tabella seguente sono elencati i metodi e i parametri interessati:</span><span class="sxs-lookup"><span data-stu-id="b7e1e-108">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="b7e1e-109">Metodo</span><span class="sxs-lookup"><span data-stu-id="b7e1e-109">Method</span></span> | <span data-ttu-id="b7e1e-110">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="b7e1e-110">Parameter name</span></span> | <span data-ttu-id="b7e1e-111">Condizione</span><span class="sxs-lookup"><span data-stu-id="b7e1e-111">Condition</span></span> | <span data-ttu-id="b7e1e-112">Versione aggiunta</span><span class="sxs-lookup"><span data-stu-id="b7e1e-112">Version added</span></span> |
|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="b7e1e-113">L'argomento non è di <xref:System.Windows.Forms.TabPage>tipo.</span><span class="sxs-lookup"><span data-stu-id="b7e1e-113">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="b7e1e-114">5,0 Anteprima 1</span><span class="sxs-lookup"><span data-stu-id="b7e1e-114">5.0 Preview 1</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="b7e1e-115">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="b7e1e-115">Version introduced</span></span>

<span data-ttu-id="b7e1e-116">.NET 5,0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="b7e1e-116">.NET 5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b7e1e-117">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="b7e1e-117">Recommended action</span></span>

- <span data-ttu-id="b7e1e-118">Aggiornare il codice per impedire il passaggio di argomenti non validi.</span><span class="sxs-lookup"><span data-stu-id="b7e1e-118">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="b7e1e-119">Se necessario, gestire un <xref:System.ArgumentException> oggetto quando si chiama il metodo.</span><span class="sxs-lookup"><span data-stu-id="b7e1e-119">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

#### <a name="category"></a><span data-ttu-id="b7e1e-120">Category</span><span class="sxs-lookup"><span data-stu-id="b7e1e-120">Category</span></span>

<span data-ttu-id="b7e1e-121">Windows Form</span><span class="sxs-lookup"><span data-stu-id="b7e1e-121">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b7e1e-122">API interessate</span><span class="sxs-lookup"><span data-stu-id="b7e1e-122">Affected APIs</span></span>

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`

-->
