---
ms.openlocfilehash: 9f6703c77e17ac9376aee944b891f4635dc7632e
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309149"
---
### <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="65854-101">I metodi WinForms ora generano ArgumentException</span><span class="sxs-lookup"><span data-stu-id="65854-101">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="65854-102">Alcuni Windows Forms metodi generano ora un oggetto <xref:System.ArgumentException> per gli argomenti non validi, in cui in precedenza non lo facevano.</span><span class="sxs-lookup"><span data-stu-id="65854-102">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="65854-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="65854-103">Change description</span></span>

<span data-ttu-id="65854-104">In precedenza, il passaggio di argomenti di tipo imprevisto o non corretto a determinati metodi di Windows Forms comporterebbe uno stato indeterminato.</span><span class="sxs-lookup"><span data-stu-id="65854-104">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="65854-105">A partire da .NET 5,0, questi metodi generano ora un oggetto <xref:System.ArgumentException> quando vengono passati argomenti non validi.</span><span class="sxs-lookup"><span data-stu-id="65854-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="65854-106">La generazione di un oggetto è <xref:System.ArgumentException> conforme al comportamento del runtime .NET.</span><span class="sxs-lookup"><span data-stu-id="65854-106">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="65854-107">Consente inoltre di migliorare l'esperienza di debug, comunicando chiaramente quale argomento non è valido.</span><span class="sxs-lookup"><span data-stu-id="65854-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="65854-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="65854-108">Version introduced</span></span>

<span data-ttu-id="65854-109">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="65854-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="65854-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="65854-110">Recommended action</span></span>

- <span data-ttu-id="65854-111">Aggiornare il codice per impedire il passaggio di argomenti non validi.</span><span class="sxs-lookup"><span data-stu-id="65854-111">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="65854-112">Se necessario, gestire un oggetto <xref:System.ArgumentException> quando si chiama il metodo.</span><span class="sxs-lookup"><span data-stu-id="65854-112">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

#### <a name="category"></a><span data-ttu-id="65854-113">Categoria</span><span class="sxs-lookup"><span data-stu-id="65854-113">Category</span></span>

<span data-ttu-id="65854-114">Windows Form</span><span class="sxs-lookup"><span data-stu-id="65854-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="65854-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="65854-115">Affected APIs</span></span>

<span data-ttu-id="65854-116">Nella tabella seguente sono elencati i metodi e i parametri interessati:</span><span class="sxs-lookup"><span data-stu-id="65854-116">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="65854-117">Metodo</span><span class="sxs-lookup"><span data-stu-id="65854-117">Method</span></span> | <span data-ttu-id="65854-118">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="65854-118">Parameter name</span></span> | <span data-ttu-id="65854-119">Condizione</span><span class="sxs-lookup"><span data-stu-id="65854-119">Condition</span></span> | <span data-ttu-id="65854-120">Versione aggiunta</span><span class="sxs-lookup"><span data-stu-id="65854-120">Version added</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="65854-121">L'argomento non è di tipo <xref:System.Windows.Forms.TabPage> .</span><span class="sxs-lookup"><span data-stu-id="65854-121">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="65854-122">Preview 1</span><span class="sxs-lookup"><span data-stu-id="65854-122">Preview 1</span></span> |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | <span data-ttu-id="65854-123">L'argomento è `null` , <xref:System.String.Empty?displayProperty=nameWithType> o uno spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="65854-123">Argument is `null`, <xref:System.String.Empty?displayProperty=nameWithType>, or white space.</span></span> | <span data-ttu-id="65854-124">Preview 5</span><span class="sxs-lookup"><span data-stu-id="65854-124">Preview 5</span></span> |
| <xref:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)> | `culture` | <span data-ttu-id="65854-125">Impossibile recuperare un oggetto `InputLanguage` per le impostazioni cultura specificate.</span><span class="sxs-lookup"><span data-stu-id="65854-125">Unable to retrieve an `InputLanguage` for the specified culture.</span></span> | <span data-ttu-id="65854-126">Anteprima 7</span><span class="sxs-lookup"><span data-stu-id="65854-126">Preview 7</span></span> |

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`
- `M:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)`

-->
