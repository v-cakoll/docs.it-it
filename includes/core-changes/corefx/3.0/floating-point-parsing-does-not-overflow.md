---
ms.openlocfilehash: 30580b3fde5b8a99862896bb7d31c6c4024f97e8
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568204"
---
### <a name="floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception"></a><span data-ttu-id="a15b3-101">Le operazioni di analisi a virgola mobile non hanno più esito negativo o generano OverflowException</span><span class="sxs-lookup"><span data-stu-id="a15b3-101">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>

<span data-ttu-id="a15b3-102">I metodi di analisi a virgola mobile non generano più un <xref:System.OverflowException> o restituiscono `false` quando analizzano una stringa il cui valore numerico non è compreso nell'intervallo del <xref:System.Single> o <xref:System.Double> tipo a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="a15b3-102">The floating-point parsing methods no longer throw an <xref:System.OverflowException> or return `false` when they parse a string whose numeric value is outside the range of the <xref:System.Single> or <xref:System.Double> floating-point type.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a15b3-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="a15b3-103">Change description</span></span>

<span data-ttu-id="a15b3-104">In .NET Core 2,2 e versioni precedenti, i metodi <xref:System.Double.Parse%2A?displayProperty=nameWithType> e <xref:System.Single.Parse%2A?displayProperty=nameWithType> generano un'<xref:System.OverflowException> per i valori che non rientrano nell'intervallo del rispettivo tipo.</span><span class="sxs-lookup"><span data-stu-id="a15b3-104">In .NET Core 2.2 and earlier versions, the <xref:System.Double.Parse%2A?displayProperty=nameWithType> and <xref:System.Single.Parse%2A?displayProperty=nameWithType> methods throw an <xref:System.OverflowException> for values that outside the range of their respective type.</span></span> <span data-ttu-id="a15b3-105">I metodi <xref:System.Double.TryParse%2A?displayProperty=nameWithType> e <xref:System.Single.TryParse%2A?displayProperty=nameWithType> restituiscono `false` per le rappresentazioni di stringa di valori numerici fuori intervallo.</span><span class="sxs-lookup"><span data-stu-id="a15b3-105">The <xref:System.Double.TryParse%2A?displayProperty=nameWithType> and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> methods return `false` for the string representations of out-of-range numeric values.</span></span>

<span data-ttu-id="a15b3-106">A partire da .NET Core 3,0, i metodi <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType>e <xref:System.Single.TryParse%2A?displayProperty=nameWithType> non hanno più esito negativo durante l'analisi di stringhe numeriche non comprese nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="a15b3-106">Starting with .NET Core 3.0, the <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType>, and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> methods no longer fail when parsing out-of-range numeric strings.</span></span> <span data-ttu-id="a15b3-107">Al contrario, i metodi di analisi del <xref:System.Double> restituiscono <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> per i valori che superano <xref:System.Double.MaxValue?displayProperty=nameWithType>e restituiscono <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> per i valori minori di <xref:System.Double.MinValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a15b3-107">Instead, the <xref:System.Double> parsing methods return <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> for values that exceed <xref:System.Double.MaxValue?displayProperty=nameWithType>, and they return <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> for values that are less than <xref:System.Double.MinValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a15b3-108">Analogamente, i metodi di analisi <xref:System.Single> restituiscono <xref:System.Single.PositiveInfinity?displayProperty=nameWithType> per i valori che superano <xref:System.Single.MaxValue?displayProperty=nameWithType>e restituiscono <xref:System.Single.NegativeInfinity?displayProperty=nameWithType> per i valori minori di <xref:System.Single.MinValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a15b3-108">Similarly, the <xref:System.Single> parsing methods return <xref:System.Single.PositiveInfinity?displayProperty=nameWithType> for values that exceed <xref:System.Single.MaxValue?displayProperty=nameWithType>, and they return <xref:System.Single.NegativeInfinity?displayProperty=nameWithType> for values that are less than <xref:System.Single.MinValue?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="a15b3-109">Questa modifica è stata apportata per una conformità IEEE 754:2008 migliorata.</span><span class="sxs-lookup"><span data-stu-id="a15b3-109">This change was made for improved IEEE 754:2008 compliance.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a15b3-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="a15b3-110">Version introduced</span></span>

<span data-ttu-id="a15b3-111">3.0</span><span class="sxs-lookup"><span data-stu-id="a15b3-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a15b3-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="a15b3-112">Recommended action</span></span>

<span data-ttu-id="a15b3-113">Questa modifica può influire sul codice in uno dei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a15b3-113">This change can affect your code in either of two ways:</span></span>

- <span data-ttu-id="a15b3-114">Il codice dipende dal gestore per l'esecuzione del <xref:System.OverflowException> quando si verifica un overflow.</span><span class="sxs-lookup"><span data-stu-id="a15b3-114">Your code depends on the handler for the <xref:System.OverflowException> to execute when an overflow occurs.</span></span> <span data-ttu-id="a15b3-115">In tal caso, è necessario rimuovere l'istruzione `catch` e inserire qualsiasi codice necessario in un'istruzione `If` che verifica se <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> o <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> è `true`.</span><span class="sxs-lookup"><span data-stu-id="a15b3-115">In this case, you should remove the `catch` statement and place any necessary code in an `If` statement that tests whether <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> or <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> is `true`.</span></span>

- <span data-ttu-id="a15b3-116">Il codice presuppone che i valori a virgola mobile non siano `Infinity`.</span><span class="sxs-lookup"><span data-stu-id="a15b3-116">Your code assumes that floating-point values are not `Infinity`.</span></span> <span data-ttu-id="a15b3-117">In questo caso, è necessario aggiungere il codice necessario per verificare la presenza di valori a virgola mobile di `PositiveInfinity` e `NegativeInfinity`.</span><span class="sxs-lookup"><span data-stu-id="a15b3-117">In this case, you should add the necessary code to check for floating-point values of `PositiveInfinity` and `NegativeInfinity`.</span></span>

#### <a name="category"></a><span data-ttu-id="a15b3-118">Category</span><span class="sxs-lookup"><span data-stu-id="a15b3-118">Category</span></span>

<span data-ttu-id="a15b3-119">CoreFx</span><span class="sxs-lookup"><span data-stu-id="a15b3-119">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a15b3-120">API interessate</span><span class="sxs-lookup"><span data-stu-id="a15b3-120">Affected APIs</span></span>

- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
