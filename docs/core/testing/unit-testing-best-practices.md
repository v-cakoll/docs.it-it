---
title: Procedure consigliate per la scrittura di unit test
description: Informazioni sulle procedure consigliate per la scrittura di unit test che migliorano la qualità del codice e la resilienza per i progetti .NET Core e .NET Standard.
author: jpreese
ms.author: wiwagn
ms.date: 07/28/2018
ms.openlocfilehash: 8a879c16e48dfde617f9cd20f58cab96039361f0
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324473"
---
# <a name="unit-testing-best-practices-with-net-core-and-net-standard"></a><span data-ttu-id="b09e8-103">Procedure consigliate di testing unità con .NET Core e .NET Standard</span><span class="sxs-lookup"><span data-stu-id="b09e8-103">Unit testing best practices with .NET Core and .NET Standard</span></span>

<span data-ttu-id="b09e8-104">La scrittura di unit test offre numerosi vantaggi: facilitano la regressione, rappresentano fonti di documentazione e semplificano la progettazione ottimale.</span><span class="sxs-lookup"><span data-stu-id="b09e8-104">There are numerous benefits to writing unit tests; they help with regression, provide documentation, and facilitate good design.</span></span> <span data-ttu-id="b09e8-105">Tuttavia, unit test deboli e di difficile lettura possono causare seri problemi nella base codice.</span><span class="sxs-lookup"><span data-stu-id="b09e8-105">However, hard to read and brittle unit tests can wreak havoc on your code base.</span></span> <span data-ttu-id="b09e8-106">Questo articolo descrive alcune procedure consigliate per la progettazione di unit test per i progetti .NET Core e .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="b09e8-106">This article describes some best practices regarding unit test design for your .NET Core and .NET Standard projects.</span></span>

<span data-ttu-id="b09e8-107">In questa guida verranno descritte alcune procedure consigliate per scrivere unit test flessibili e di facile comprensione.</span><span class="sxs-lookup"><span data-stu-id="b09e8-107">In this guide, you'll learn some best practices when writing unit tests to keep your tests resilient and easy to understand.</span></span>

<span data-ttu-id="b09e8-108">A cura di [John Reese](https://reese.dev) con ringraziamenti speciali a [Roy Osherove](https://osherove.com/)</span><span class="sxs-lookup"><span data-stu-id="b09e8-108">By [John Reese](https://reese.dev) with special thanks to [Roy Osherove](https://osherove.com/)</span></span>

## <a name="why-unit-test"></a><span data-ttu-id="b09e8-109">L'utilità degli unit test</span><span class="sxs-lookup"><span data-stu-id="b09e8-109">Why unit test?</span></span>

### <a name="less-time-performing-functional-tests"></a><span data-ttu-id="b09e8-110">Meno tempo da dedicare all'esecuzione dei test funzionali</span><span class="sxs-lookup"><span data-stu-id="b09e8-110">Less time performing functional tests</span></span>
<span data-ttu-id="b09e8-111">I test funzionali sono costosi.</span><span class="sxs-lookup"><span data-stu-id="b09e8-111">Functional tests are expensive.</span></span> <span data-ttu-id="b09e8-112">Comportano, in genere, l'apertura dell'applicazione e l'esecuzione di una serie di passaggi che l'utente, o chi per lui, deve eseguire per convalidare il comportamento previsto.</span><span class="sxs-lookup"><span data-stu-id="b09e8-112">They typically involve opening up the application and performing a series of steps that you (or someone else), must follow in order to validate the expected behavior.</span></span> <span data-ttu-id="b09e8-113">Questi passaggi potrebbero non essere sempre chiari per chi esegue il test, pertanto questi dovrà contattare qualcuno con maggiori conoscenze in materia per eseguire il test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-113">These steps may not always be known to the tester, which means they will have to reach out to someone more knowledgeable in the area in order to carry out the test.</span></span> <span data-ttu-id="b09e8-114">Il test di semplici modifiche può richiedere solo alcuni secondi, che possono diventare minuti per modifiche più significative.</span><span class="sxs-lookup"><span data-stu-id="b09e8-114">Testing itself could take seconds for trivial changes, or minutes for larger changes.</span></span> <span data-ttu-id="b09e8-115">Infine, questo processo deve essere ripetuto per ogni modifica apportata nel sistema.</span><span class="sxs-lookup"><span data-stu-id="b09e8-115">Lastly, this process must be repeated for every change that you make in the system.</span></span>

<span data-ttu-id="b09e8-116">Gli unit test, d'altra parte, accettano millisecondi, possono essere eseguiti alla pressione di un pulsante e non richiedono necessariamente alcuna conoscenza del sistema in grande.</span><span class="sxs-lookup"><span data-stu-id="b09e8-116">Unit tests, on the other hand, take milliseconds, can be run at the press of a button, and don't necessarily require any knowledge of the system at large.</span></span> <span data-ttu-id="b09e8-117">L'esito positivo o negativo del test è determinato dal test runner, non dai singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="b09e8-117">Whether or not the test passes or fails is up to the test runner, not the individual.</span></span>

### <a name="protection-against-regression"></a><span data-ttu-id="b09e8-118">Protezione contro la regressione</span><span class="sxs-lookup"><span data-stu-id="b09e8-118">Protection against regression</span></span>
<span data-ttu-id="b09e8-119">I difetti di regressione sono i difetti che vengono introdotti quando si apporta una modifica all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b09e8-119">Regression defects are defects that are introduced when a change is made to the application.</span></span> <span data-ttu-id="b09e8-120">È pratica comune per i tester testare non solo le nuove funzionalità, ma anche quelle già esistenti per verificare che le funzionalità implementate in precedenza continuino a funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="b09e8-120">It is common for testers to not only test their new feature but also features that existed beforehand in order to verify that previously implemented features still function as expected.</span></span>

<span data-ttu-id="b09e8-121">Con gli unit test, è possibile eseguire nuovamente l'intero gruppo di test dopo ogni compilazione o persino dopo la modifica di una sola riga di codice.</span><span class="sxs-lookup"><span data-stu-id="b09e8-121">With unit testing, it's possible to rerun your entire suite of tests after every build or even after you change a line of code.</span></span> <span data-ttu-id="b09e8-122">Questo, offrendo la certezza che il nuovo codice non interferisce con le funzionalità esistenti.</span><span class="sxs-lookup"><span data-stu-id="b09e8-122">Giving you confidence that your new code does not break existing functionality.</span></span>

### <a name="executable-documentation"></a><span data-ttu-id="b09e8-123">Documentazione eseguibile</span><span class="sxs-lookup"><span data-stu-id="b09e8-123">Executable documentation</span></span>
<span data-ttu-id="b09e8-124">Non è sempre facile sapere lo scopo di un particolare metodo o il suo comportamento con un dato input.</span><span class="sxs-lookup"><span data-stu-id="b09e8-124">It may not always be obvious what a particular method does or how it behaves given a certain input.</span></span> <span data-ttu-id="b09e8-125">Ci si potrebbe chiedere: che comportamento avrebbe questo metodo se fosse associato a una stringa vuota?</span><span class="sxs-lookup"><span data-stu-id="b09e8-125">You may ask yourself: How does this method behave if I pass it a blank string?</span></span> <span data-ttu-id="b09e8-126">Restituirebbe un valore null?</span><span class="sxs-lookup"><span data-stu-id="b09e8-126">Null?</span></span>

<span data-ttu-id="b09e8-127">Quando si dispone di un gruppo di unit test ben identificabili, per ogni test è possibile capire chiaramente l'output previsto per un dato input.</span><span class="sxs-lookup"><span data-stu-id="b09e8-127">When you have a suite of well-named unit tests, each test should be able to clearly explain the expected output for a given input.</span></span> <span data-ttu-id="b09e8-128">Inoltre, è possibile verificarne l'effettivo funzionamento.</span><span class="sxs-lookup"><span data-stu-id="b09e8-128">In addition, it should be able to verify that it actually works.</span></span>

### <a name="less-coupled-code"></a><span data-ttu-id="b09e8-129">Meno codice accoppiato</span><span class="sxs-lookup"><span data-stu-id="b09e8-129">Less coupled code</span></span>
<span data-ttu-id="b09e8-130">Quando il codice è strettamente accoppiato, può risultare difficile eseguire unit test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-130">When code is tightly coupled, it can be difficult to unit test.</span></span> <span data-ttu-id="b09e8-131">Senza la creazione di unit test per il codice che si sta scrivendo, l'accoppiamento potrebbe risultare meno evidente.</span><span class="sxs-lookup"><span data-stu-id="b09e8-131">Without creating unit tests for the code that you're writing, coupling may be less apparent.</span></span>

<span data-ttu-id="b09e8-132">La scrittura di test per il codice ha l'effetto di disaccoppiare naturalmente il codice perché le verifiche sarebbero, in caso contrario, più difficili.</span><span class="sxs-lookup"><span data-stu-id="b09e8-132">Writing tests for your code will naturally decouple your code, because it would be more difficult to test otherwise.</span></span>

## <a name="characteristics-of-a-good-unit-test"></a><span data-ttu-id="b09e8-133">Caratteristiche di un buon unit test</span><span class="sxs-lookup"><span data-stu-id="b09e8-133">Characteristics of a good unit test</span></span>

- <span data-ttu-id="b09e8-134">**Veloce**.</span><span class="sxs-lookup"><span data-stu-id="b09e8-134">**Fast**.</span></span> <span data-ttu-id="b09e8-135">Non è insolito per i progetti maturi comprendere migliaia di unit test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-135">It is not uncommon for mature projects to have thousands of unit tests.</span></span> <span data-ttu-id="b09e8-136">La durata dell'esecuzione degli unit test dovrebbe essere molto breve.</span><span class="sxs-lookup"><span data-stu-id="b09e8-136">Unit tests should take very little time to run.</span></span> <span data-ttu-id="b09e8-137">Millisecondi.</span><span class="sxs-lookup"><span data-stu-id="b09e8-137">Milliseconds.</span></span>
- <span data-ttu-id="b09e8-138">**Isolamento**.</span><span class="sxs-lookup"><span data-stu-id="b09e8-138">**Isolated**.</span></span> <span data-ttu-id="b09e8-139">Gli unit test sono autonomi, possono essere eseguiti in modo isolato e non hanno dipendenze verso fattori esterni, ad esempio file system o database.</span><span class="sxs-lookup"><span data-stu-id="b09e8-139">Unit tests are standalone, can be run in isolation, and have no dependencies on any outside factors such as a file system or database.</span></span>
- <span data-ttu-id="b09e8-140">**Ripetibile**.</span><span class="sxs-lookup"><span data-stu-id="b09e8-140">**Repeatable**.</span></span> <span data-ttu-id="b09e8-141">Uno unit test deve generare risultati costanti, vale a dire, deve restituire sempre lo stesso risultato se tra le esecuzioni non si modifica alcun elemento.</span><span class="sxs-lookup"><span data-stu-id="b09e8-141">Running a unit test should be consistent with its results, that is, it always returns the same result if you do not change anything in between runs.</span></span>
- <span data-ttu-id="b09e8-142">**Autonomo**.</span><span class="sxs-lookup"><span data-stu-id="b09e8-142">**Self-Checking**.</span></span> <span data-ttu-id="b09e8-143">Il test deve essere in grado di rilevare automaticamente se ha avuto esito positivo o meno senza alcun intervento.</span><span class="sxs-lookup"><span data-stu-id="b09e8-143">The test should be able to automatically detect if it passed or failed without any human interaction.</span></span>
- <span data-ttu-id="b09e8-144">**Rispetta i tempi previsti**.</span><span class="sxs-lookup"><span data-stu-id="b09e8-144">**Timely**.</span></span> <span data-ttu-id="b09e8-145">Il tempo richiesto per la scrittura di uno unit test deve essere proporzionale al tempo richiesto per la scrittura del codice sottoposto a test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-145">A unit test should not take a disproportionately long time to write compared to the code being tested.</span></span> <span data-ttu-id="b09e8-146">Se il test del codice richiede una quantità di tempo molto maggiore rispetto alla scrittura del codice, prendere in considerazione una struttura che risulti più testabile.</span><span class="sxs-lookup"><span data-stu-id="b09e8-146">If you find testing the code taking a large amount of time compared to writing the code, consider a design that is more testable.</span></span>

## <a name="code-coverage"></a><span data-ttu-id="b09e8-147">Code coverage</span><span class="sxs-lookup"><span data-stu-id="b09e8-147">Code coverage</span></span>

<span data-ttu-id="b09e8-148">Una percentuale di code coverage elevata è spesso associata a una maggiore qualità del codice.</span><span class="sxs-lookup"><span data-stu-id="b09e8-148">A high code coverage percentage is often associated with a higher quality of code.</span></span> <span data-ttu-id="b09e8-149">Tuttavia, la misurazione stessa *non è in grado* di determinare la qualità del codice.</span><span class="sxs-lookup"><span data-stu-id="b09e8-149">However, the measurement itself *cannot* determine the quality of code.</span></span> <span data-ttu-id="b09e8-150">L'impostazione di un obiettivo code coverage percentuale eccessivamente ambizioso può essere controproducente.</span><span class="sxs-lookup"><span data-stu-id="b09e8-150">Setting an overly ambitious code coverage percentage goal can be counterproductive.</span></span> <span data-ttu-id="b09e8-151">Immaginate un progetto complesso con migliaia di rami condizionali e immaginiamo di impostare un obiettivo del 95% code coverage.</span><span class="sxs-lookup"><span data-stu-id="b09e8-151">Imagine a complex project with thousands of conditional branches, and imagine that you set a goal of 95% code coverage.</span></span> <span data-ttu-id="b09e8-152">Attualmente il progetto mantiene il 90% code coverage.</span><span class="sxs-lookup"><span data-stu-id="b09e8-152">Currently the project maintains 90% code coverage.</span></span> <span data-ttu-id="b09e8-153">La quantità di tempo necessaria per tenere conto di tutti i casi perimetrali nel 5% rimanente potrebbe essere un'impresa massiccia e la proposta di valore diminuisce rapidamente.</span><span class="sxs-lookup"><span data-stu-id="b09e8-153">The amount of time it takes to account for all of the edge cases in the remaining 5% could be a massive undertaking, and the value proposition quickly diminishes.</span></span>

<span data-ttu-id="b09e8-154">Una percentuale di code coverage elevata non è un indicatore di esito positivo, né implica una elevata qualità del codice.</span><span class="sxs-lookup"><span data-stu-id="b09e8-154">A high code coverage percentage is not an indicator of success, nor does it imply high code quality.</span></span> <span data-ttu-id="b09e8-155">Rappresenta semplicemente la quantità di codice analizzata dagli unit test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-155">It just represents the amount of code that is covered by unit tests.</span></span> <span data-ttu-id="b09e8-156">Per ulteriori informazioni, vedere [unit testing code coverage](unit-testing-code-coverage.md).</span><span class="sxs-lookup"><span data-stu-id="b09e8-156">For more information, see [unit testing code coverage](unit-testing-code-coverage.md).</span></span>

## <a name="lets-speak-the-same-language"></a><span data-ttu-id="b09e8-157">Terminologia</span><span class="sxs-lookup"><span data-stu-id="b09e8-157">Let's speak the same language</span></span>
<span data-ttu-id="b09e8-158">Il termine *simulazione* è purtroppo spesso usato per discutere dei test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-158">The term *mock* is unfortunately often misused when talking about testing.</span></span> <span data-ttu-id="b09e8-159">I punti seguenti definiscono i tipi più comuni di *Fake* durante la scrittura di unit test:</span><span class="sxs-lookup"><span data-stu-id="b09e8-159">The following points define the most common types of *fakes* when writing unit tests:</span></span>

<span data-ttu-id="b09e8-160">*Fake* : un fake è un termine generico che può essere usato per descrivere uno stub o un oggetto fittizio.</span><span class="sxs-lookup"><span data-stu-id="b09e8-160">*Fake* - A fake is a generic term that can be used to describe either a stub or a mock object.</span></span> <span data-ttu-id="b09e8-161">Il fatto che sia uno stub o una simulazione dipende dal contesto in cui viene usato.</span><span class="sxs-lookup"><span data-stu-id="b09e8-161">Whether it's a stub or a mock depends on the context in which it's used.</span></span> <span data-ttu-id="b09e8-162">Quindi, in altre parole, un fake può essere uno stub o un mock.</span><span class="sxs-lookup"><span data-stu-id="b09e8-162">So in other words, a fake can be a stub or a mock.</span></span>

<span data-ttu-id="b09e8-163">*Mock*: un mock è un oggetto del sistema che decide se uno unit test ha avuto esito positivo o meno.</span><span class="sxs-lookup"><span data-stu-id="b09e8-163">*Mock* - A mock object is a fake object in the system that decides whether or not a unit test has passed or failed.</span></span> <span data-ttu-id="b09e8-164">Una simulazione inizia come un fake fino a quando non viene dichiarata in base a.</span><span class="sxs-lookup"><span data-stu-id="b09e8-164">A mock starts out as a Fake until it's asserted against.</span></span>

<span data-ttu-id="b09e8-165">*Stub*: è la sostituzione controllabile nel sistema di una dipendenza o di un collaboratore.</span><span class="sxs-lookup"><span data-stu-id="b09e8-165">*Stub* - A stub is a controllable replacement for an existing dependency (or collaborator) in the system.</span></span> <span data-ttu-id="b09e8-166">Utilizzando uno stub è possibile testare il codice senza prendere direttamente in considerazione la dipendenza.</span><span class="sxs-lookup"><span data-stu-id="b09e8-166">By using a stub, you can test your code without dealing with the dependency directly.</span></span> <span data-ttu-id="b09e8-167">Per impostazione predefinita, un fake è inizialmente uno stub.</span><span class="sxs-lookup"><span data-stu-id="b09e8-167">By default, a fake starts out as a stub.</span></span>

<span data-ttu-id="b09e8-168">Si consideri il frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="b09e8-168">Consider the following code snippet:</span></span>

```csharp
var mockOrder = new MockOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

<span data-ttu-id="b09e8-169">Quanto segue è un esempio di stub che verrebbe chiamato mock.</span><span class="sxs-lookup"><span data-stu-id="b09e8-169">This would be an example of stub being referred to as a mock.</span></span> <span data-ttu-id="b09e8-170">In questo caso, si tratta di stub.</span><span class="sxs-lookup"><span data-stu-id="b09e8-170">In this case, it is a stub.</span></span> <span data-ttu-id="b09e8-171">Si sta passando Order solo come mezzo per creare un'istanza di `Purchase` (il sistema sottoposto a test).</span><span class="sxs-lookup"><span data-stu-id="b09e8-171">You're just passing in the Order as a means to be able to instantiate `Purchase` (the system under test).</span></span> <span data-ttu-id="b09e8-172">Anche il nome `MockOrder` è fuorviante perché l'ordine non è una simulazione.</span><span class="sxs-lookup"><span data-stu-id="b09e8-172">The name `MockOrder` is also misleading because again, the order is not a mock.</span></span>

<span data-ttu-id="b09e8-173">Un approccio migliore sarebbe</span><span class="sxs-lookup"><span data-stu-id="b09e8-173">A better approach would be</span></span>

```csharp
var stubOrder = new FakeOrder();
var purchase = new Purchase(stubOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

<span data-ttu-id="b09e8-174">Rinominando la classe `FakeOrder` la si rende più generica e la si rende utilizzabile come mock o stub,</span><span class="sxs-lookup"><span data-stu-id="b09e8-174">By renaming the class to `FakeOrder`, you've made the class a lot more generic, the class can be used as a mock or a stub.</span></span> <span data-ttu-id="b09e8-175">a seconda del valore migliore per il tipo di test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-175">Whichever is better for the test case.</span></span> <span data-ttu-id="b09e8-176">Nell'esempio precedente, `FakeOrder` viene usato come stub.</span><span class="sxs-lookup"><span data-stu-id="b09e8-176">In the above example, `FakeOrder` is used as a stub.</span></span> <span data-ttu-id="b09e8-177">`FakeOrder` non viene usato in alcun modo durante l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="b09e8-177">You're not using the `FakeOrder` in any shape or form during the assert.</span></span> <span data-ttu-id="b09e8-178">`FakeOrder`è stato passato alla `Purchase` classe per soddisfare i requisiti del costruttore.</span><span class="sxs-lookup"><span data-stu-id="b09e8-178">`FakeOrder` was passed into the `Purchase` class to satisfy the requirements of the constructor.</span></span>

<span data-ttu-id="b09e8-179">Per usarlo come mock, si potrebbe procedere così</span><span class="sxs-lookup"><span data-stu-id="b09e8-179">To use it as a Mock, you could do something like this</span></span>

```csharp
var mockOrder = new FakeOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(mockOrder.Validated);
```

<span data-ttu-id="b09e8-180">In questo caso, si verifica una proprietà del fake, con un'asserzione su di essa, pertanto nel frammento di codice precedente, `mockOrder` è un mock.</span><span class="sxs-lookup"><span data-stu-id="b09e8-180">In this case, you are checking a property on the Fake (asserting against it), so in the above code snippet, the `mockOrder` is a Mock.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b09e8-181">È importante usare questa terminologia in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="b09e8-181">It's important to get this terminology correct.</span></span> <span data-ttu-id="b09e8-182">Se si chiamano gli stub "mock", altri sviluppatori faranno ipotesi errate sulle intenzioni espresse.</span><span class="sxs-lookup"><span data-stu-id="b09e8-182">If you call your stubs "mocks", other developers are going to make false assumptions about your intent.</span></span>

<span data-ttu-id="b09e8-183">La cosa principale da ricordare riguardo a mock e stub è che i mock sono analoghi agli stub, ma che si può rivolgere un'asserzione a un mock, ma non a uno stub.</span><span class="sxs-lookup"><span data-stu-id="b09e8-183">The main thing to remember about mocks versus stubs is that mocks are just like stubs, but you assert against the mock object, whereas you do not assert against a stub.</span></span>

## <a name="best-practices"></a><span data-ttu-id="b09e8-184">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="b09e8-184">Best practices</span></span>

### <a name="naming-your-tests"></a><span data-ttu-id="b09e8-185">Denominare i test</span><span class="sxs-lookup"><span data-stu-id="b09e8-185">Naming your tests</span></span>
<span data-ttu-id="b09e8-186">Il nome del test deve essere costituito da tre parti:</span><span class="sxs-lookup"><span data-stu-id="b09e8-186">The name of your test should consist of three parts:</span></span>

- <span data-ttu-id="b09e8-187">Nome del metodo testato.</span><span class="sxs-lookup"><span data-stu-id="b09e8-187">The name of the method being tested.</span></span>
- <span data-ttu-id="b09e8-188">Scenario in cui si sta testando.</span><span class="sxs-lookup"><span data-stu-id="b09e8-188">The scenario under which it's being tested.</span></span>
- <span data-ttu-id="b09e8-189">Comportamento previsto quando viene richiamato lo scenario.</span><span class="sxs-lookup"><span data-stu-id="b09e8-189">The expected behavior when the scenario is invoked.</span></span>

#### <a name="why"></a><span data-ttu-id="b09e8-190">Questo problema dipende</span><span class="sxs-lookup"><span data-stu-id="b09e8-190">Why?</span></span>

- <span data-ttu-id="b09e8-191">Gli standard di denominazione sono importanti perché esprimono in modo esplicito l'intento del test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-191">Naming standards are important because they explicitly express the intent of the test.</span></span>

<span data-ttu-id="b09e8-192">I test non si limitano a verificare che il codice funzioni, ma documentano anche il risultato.</span><span class="sxs-lookup"><span data-stu-id="b09e8-192">Tests are more than just making sure your code works, they also provide documentation.</span></span> <span data-ttu-id="b09e8-193">Osservando semplicemente il gruppo di unit test, sarà possibile dedurre il comportamento del codice senza neanche guardare il codice.</span><span class="sxs-lookup"><span data-stu-id="b09e8-193">Just by looking at the suite of unit tests, you should be able to infer the behavior of your code without even looking at the code itself.</span></span> <span data-ttu-id="b09e8-194">Inoltre, quando i test hanno esito negativo, è possibile vedere esattamente quali scenari non soddisfano le aspettative.</span><span class="sxs-lookup"><span data-stu-id="b09e8-194">Additionally, when tests fail, you can see exactly which scenarios do not meet your expectations.</span></span>

#### <a name="bad"></a><span data-ttu-id="b09e8-195">Scadente:</span><span class="sxs-lookup"><span data-stu-id="b09e8-195">Bad:</span></span>
[!code-csharp[BeforeNaming](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeNaming)]

#### <a name="better"></a><span data-ttu-id="b09e8-196">Migliore:</span><span class="sxs-lookup"><span data-stu-id="b09e8-196">Better:</span></span>
[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="arranging-your-tests"></a><span data-ttu-id="b09e8-197">Disposizione dei test</span><span class="sxs-lookup"><span data-stu-id="b09e8-197">Arranging your tests</span></span>
<span data-ttu-id="b09e8-198">**Disporre, agire, asserire** è uno schema comune per gli unit test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-198">**Arrange, Act, Assert** is a common pattern when unit testing.</span></span> <span data-ttu-id="b09e8-199">Come suggerisce il nome, è costituito da tre azioni principali:</span><span class="sxs-lookup"><span data-stu-id="b09e8-199">As the name implies, it consists of three main actions:</span></span>

- <span data-ttu-id="b09e8-200">*Disporre* gli oggetti, creandoli e configurandoli in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b09e8-200">*Arrange* your objects, creating and setting them up as necessary.</span></span>
- <span data-ttu-id="b09e8-201">*Agire* su un oggetto.</span><span class="sxs-lookup"><span data-stu-id="b09e8-201">*Act* on an object.</span></span>
- <span data-ttu-id="b09e8-202">*Asserire* che un dato comportamento è come previsto.</span><span class="sxs-lookup"><span data-stu-id="b09e8-202">*Assert* that something is as expected.</span></span>

#### <a name="why"></a><span data-ttu-id="b09e8-203">Questo problema dipende</span><span class="sxs-lookup"><span data-stu-id="b09e8-203">Why?</span></span>

- <span data-ttu-id="b09e8-204">Separare nettamente l'oggetto del test dai passaggi *disporre* e *asserire*.</span><span class="sxs-lookup"><span data-stu-id="b09e8-204">Clearly separates what is being tested from the *arrange* and *assert* steps.</span></span>
- <span data-ttu-id="b09e8-205">Il rischio di mescolare le asserzioni con il codice "agire" è minore.</span><span class="sxs-lookup"><span data-stu-id="b09e8-205">Less chance to intermix assertions with "Act" code.</span></span>

<span data-ttu-id="b09e8-206">La leggibilità è uno degli aspetti più importanti da considerare durante la scrittura di un test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-206">Readability is one of the most important aspects when writing a test.</span></span> <span data-ttu-id="b09e8-207">La separazione di ognuna di queste azioni all'interno del test evidenzia chiaramente le dipendenze necessarie per chiamare il codice, come viene chiamato il codice e ciò che si sta tentando di asserire.</span><span class="sxs-lookup"><span data-stu-id="b09e8-207">Separating each of these actions within the test clearly highlight the dependencies required to call your code, how your code is being called, and what you are trying to assert.</span></span> <span data-ttu-id="b09e8-208">Sebbene sia possibile combinare alcuni passaggi e ridurre le dimensioni del test, l'obiettivo principale rimane rendere il test più leggibile possibile.</span><span class="sxs-lookup"><span data-stu-id="b09e8-208">While it may be possible to combine some steps and reduce the size of your test, the primary goal is to make the test as readable as possible.</span></span>

#### <a name="bad"></a><span data-ttu-id="b09e8-209">Scadente:</span><span class="sxs-lookup"><span data-stu-id="b09e8-209">Bad:</span></span>
[!code-csharp[BeforeArranging](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeArranging)]

#### <a name="better"></a><span data-ttu-id="b09e8-210">Migliore:</span><span class="sxs-lookup"><span data-stu-id="b09e8-210">Better:</span></span>
[!code-csharp[AfterArranging](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterArranging)]

### <a name="write-minimally-passing-tests"></a><span data-ttu-id="b09e8-211">Scrivere test più semplici possibile</span><span class="sxs-lookup"><span data-stu-id="b09e8-211">Write minimally passing tests</span></span>
<span data-ttu-id="b09e8-212">L'input da usare in uno unit test deve essere il più semplice possibile per verificare il comportamento che si sta testando.</span><span class="sxs-lookup"><span data-stu-id="b09e8-212">The input to be used in a unit test should be the simplest possible in order to verify the behavior that you are currently testing.</span></span>

#### <a name="why"></a><span data-ttu-id="b09e8-213">Questo problema dipende</span><span class="sxs-lookup"><span data-stu-id="b09e8-213">Why?</span></span>

- <span data-ttu-id="b09e8-214">I test diventano più adattabili alle modifiche future nella base codice.</span><span class="sxs-lookup"><span data-stu-id="b09e8-214">Tests become more resilient to future changes in the codebase.</span></span>
- <span data-ttu-id="b09e8-215">I test hanno un comportamento più simile a quello dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="b09e8-215">Closer to testing behavior over implementation.</span></span>

<span data-ttu-id="b09e8-216">Test che includono più informazioni rispetto a quelle necessarie per la verifica hanno maggiori probabilità di contenere errori e il loro intento risulta meno chiaro.</span><span class="sxs-lookup"><span data-stu-id="b09e8-216">Tests that include more information than required to pass the test have a higher chance of introducing errors into the test and can make the intent of the test less clear.</span></span> <span data-ttu-id="b09e8-217">Quando si scrivono i test, si desidera concentrarsi sul comportamento.</span><span class="sxs-lookup"><span data-stu-id="b09e8-217">When writing tests, you want to focus on the behavior.</span></span> <span data-ttu-id="b09e8-218">L'impostazione di proprietà aggiuntive per i modelli o l'uso di valori diversi da zero quando non sono necessari distoglie l'attenzione da ciò che si sta tentando di provare.</span><span class="sxs-lookup"><span data-stu-id="b09e8-218">Setting extra properties on models or using non-zero values when not required, only detracts from what you are trying to prove.</span></span>

#### <a name="bad"></a><span data-ttu-id="b09e8-219">Scadente:</span><span class="sxs-lookup"><span data-stu-id="b09e8-219">Bad:</span></span>
[!code-csharp[BeforeMinimallyPassing](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeMinimallyPassing)]

#### <a name="better"></a><span data-ttu-id="b09e8-220">Migliore:</span><span class="sxs-lookup"><span data-stu-id="b09e8-220">Better:</span></span>
[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="avoid-magic-strings"></a><span data-ttu-id="b09e8-221">Evitare le "stringhe magiche"</span><span class="sxs-lookup"><span data-stu-id="b09e8-221">Avoid magic strings</span></span>
<span data-ttu-id="b09e8-222">La denominazione delle variabili negli unit test è importante quanto la denominazione delle variabili nel codice di produzione o anche di più.</span><span class="sxs-lookup"><span data-stu-id="b09e8-222">Naming variables in unit tests is as important, if not more important, than naming variables in production code.</span></span> <span data-ttu-id="b09e8-223">Gli unit test non devono contenere "stringhe magiche".</span><span class="sxs-lookup"><span data-stu-id="b09e8-223">Unit tests should not contain magic strings.</span></span>

#### <a name="why"></a><span data-ttu-id="b09e8-224">Questo problema dipende</span><span class="sxs-lookup"><span data-stu-id="b09e8-224">Why?</span></span>

- <span data-ttu-id="b09e8-225">Impediscono a chi legge il test di controllare il codice di produzione per scoprire ciò che rende il valore speciale.</span><span class="sxs-lookup"><span data-stu-id="b09e8-225">Prevents the need for the reader of the test to inspect the production code in order to figure out what makes the value special.</span></span>
- <span data-ttu-id="b09e8-226">Illustrano in modo esplicito ciò che si sta tentando di *dimostrare* anziché ciò che si tenta di *compiere*.</span><span class="sxs-lookup"><span data-stu-id="b09e8-226">Explicitly shows what you're trying to *prove* rather than trying to *accomplish*.</span></span>

<span data-ttu-id="b09e8-227">Le "stringhe magiche" possono causare confusione a chi legge il test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-227">Magic strings can cause confusion to the reader of your tests.</span></span> <span data-ttu-id="b09e8-228">Se una stringa appare insolita, ci si potrebbe domandare perché è stato scelto un determinato valore per un parametro o valore restituito.</span><span class="sxs-lookup"><span data-stu-id="b09e8-228">If a string looks out of the ordinary, they may wonder why a certain value was chosen for a parameter or return value.</span></span> <span data-ttu-id="b09e8-229">Ciò porterebbe a esaminare i dettagli di implementazione piuttosto che il test stesso.</span><span class="sxs-lookup"><span data-stu-id="b09e8-229">This may lead them to take a closer look at the implementation details, rather than focus on the test.</span></span>

> [!TIP]
> <span data-ttu-id="b09e8-230">Quando si scrivono i test, bisogna porsi l'obiettivo di esprimere nel modo più chiaro possibile le loro finalità.</span><span class="sxs-lookup"><span data-stu-id="b09e8-230">When writing tests, you should aim to express as much intent as possible.</span></span> <span data-ttu-id="b09e8-231">Nel caso delle "stringhe magiche", un buon espediente consiste nell'assegnare questi valori a costanti.</span><span class="sxs-lookup"><span data-stu-id="b09e8-231">In the case of magic strings, a good approach is to assign these values to constants.</span></span>

#### <a name="bad"></a><span data-ttu-id="b09e8-232">Scadente:</span><span class="sxs-lookup"><span data-stu-id="b09e8-232">Bad:</span></span>
[!code-csharp[BeforeMagicString](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeMagicString)]

#### <a name="better"></a><span data-ttu-id="b09e8-233">Migliore:</span><span class="sxs-lookup"><span data-stu-id="b09e8-233">Better:</span></span>
[!code-csharp[AfterMagicString](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterMagicString)]

### <a name="avoid-logic-in-tests"></a><span data-ttu-id="b09e8-234">Evitare la logica nei test</span><span class="sxs-lookup"><span data-stu-id="b09e8-234">Avoid logic in tests</span></span>
<span data-ttu-id="b09e8-235">Quando si scrivono gli unit test bisogna evitare la concatenazione manuale di stringhe e le condizioni logiche, ad esempio `if`, `while`, `for`, `switch` e così via.</span><span class="sxs-lookup"><span data-stu-id="b09e8-235">When writing your unit tests avoid manual string concatenation and logical conditions such as `if`, `while`, `for`, `switch`, etc.</span></span>

#### <a name="why"></a><span data-ttu-id="b09e8-236">Questo problema dipende</span><span class="sxs-lookup"><span data-stu-id="b09e8-236">Why?</span></span>

- <span data-ttu-id="b09e8-237">Minore possibilità di introdurre un bug nei test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-237">Less chance to introduce a bug inside of your tests.</span></span>
- <span data-ttu-id="b09e8-238">Per concentrarsi sul risultato finale anziché sui dettagli di implementazione.</span><span class="sxs-lookup"><span data-stu-id="b09e8-238">Focus on the end result, rather than implementation details.</span></span>

<span data-ttu-id="b09e8-239">Se si introduce la logica nel gruppo di test, la possibilità di introdurre un bug al suo interno aumenta notevolmente.</span><span class="sxs-lookup"><span data-stu-id="b09e8-239">When you introduce logic into your test suite, the chance of introducing a bug into it increases dramatically.</span></span> <span data-ttu-id="b09e8-240">L'ultimo posto in cui deve esserci un bug è il gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-240">The last place that you want to find a bug is within your test suite.</span></span> <span data-ttu-id="b09e8-241">Si deve avere un elevato livello di fiducia riguardo al funzionamento dei test altrimenti non sarà possibile considerarli attendibili.</span><span class="sxs-lookup"><span data-stu-id="b09e8-241">You should have a high level of confidence that your tests work, otherwise, you will not trust them.</span></span> <span data-ttu-id="b09e8-242">E dei test considerati non attendibili non hanno alcun valore.</span><span class="sxs-lookup"><span data-stu-id="b09e8-242">Tests that you do not trust, do not provide any value.</span></span> <span data-ttu-id="b09e8-243">Quando un test ha esito negativo, è necessario avere la percezione che ci sia un problema nel codice che non può essere ignorato.</span><span class="sxs-lookup"><span data-stu-id="b09e8-243">When a test fails, you want to have a sense that something is actually wrong with your code and that it cannot be ignored.</span></span>

> [!TIP]
> <span data-ttu-id="b09e8-244">Se risulta inevitabile inserire la logica nel test, è consigliabile suddividere il test in due o più test diversi.</span><span class="sxs-lookup"><span data-stu-id="b09e8-244">If logic in your test seems unavoidable, consider splitting the test up into two or more different tests.</span></span>

#### <a name="bad"></a><span data-ttu-id="b09e8-245">Scadente:</span><span class="sxs-lookup"><span data-stu-id="b09e8-245">Bad:</span></span>
[!code-csharp[LogicInTests](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#LogicInTests)]

#### <a name="better"></a><span data-ttu-id="b09e8-246">Migliore:</span><span class="sxs-lookup"><span data-stu-id="b09e8-246">Better:</span></span>
[!code-csharp[AfterTestLogic](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterTestLogic)]

### <a name="prefer-helper-methods-to-setup-and-teardown"></a><span data-ttu-id="b09e8-247">Prediligere i metodi helper agli attributi Setup e Teardown</span><span class="sxs-lookup"><span data-stu-id="b09e8-247">Prefer helper methods to setup and teardown</span></span>
<span data-ttu-id="b09e8-248">Se si richiede un oggetto o uno stato simile per i test, prediligere un metodo helper piuttosto che utilizzare gli attributi Setup e Teardown, se presenti.</span><span class="sxs-lookup"><span data-stu-id="b09e8-248">If you require a similar object or state for your tests, prefer a helper method than leveraging Setup and Teardown attributes if they exist.</span></span>

#### <a name="why"></a><span data-ttu-id="b09e8-249">Questo problema dipende</span><span class="sxs-lookup"><span data-stu-id="b09e8-249">Why?</span></span>

- <span data-ttu-id="b09e8-250">La lettura dei test è più agevole dal momento che la totalità del codice è visibile nel test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-250">Less confusion when reading the tests since all of the code is visible from within each test.</span></span>
- <span data-ttu-id="b09e8-251">Minore rischio di configurare troppo o troppo poco per il test specificato.</span><span class="sxs-lookup"><span data-stu-id="b09e8-251">Less chance of setting up too much or too little for the given test.</span></span>
- <span data-ttu-id="b09e8-252">Minor probabilità di condividere lo stato tra i test, creando dipendenze indesiderate tra di essi.</span><span class="sxs-lookup"><span data-stu-id="b09e8-252">Less chance of sharing state between tests, which creates unwanted dependencies between them.</span></span>

<span data-ttu-id="b09e8-253">Nel framework di testing unità, `Setup` viene chiamato prima di ogni unit test all'interno del gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-253">In unit testing frameworks, `Setup` is called before each and every unit test within your test suite.</span></span> <span data-ttu-id="b09e8-254">Mentre ad alcuni può apparire uno strumento utile, in realtà genera test troppo grandi e difficili da leggere.</span><span class="sxs-lookup"><span data-stu-id="b09e8-254">While some may see this as a useful tool, it generally ends up leading to bloated and hard to read tests.</span></span> <span data-ttu-id="b09e8-255">I requisiti per rendere ogni test operativo variano da test a test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-255">Each test will generally have different requirements in order to get the test up and running.</span></span> <span data-ttu-id="b09e8-256">Sfortunatamente, `Setup` obbliga a usare esattamente gli stessi requisiti per ogni test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-256">Unfortunately, `Setup` forces you to use the exact same requirements for each test.</span></span>

> [!NOTE]
> <span data-ttu-id="b09e8-257">SetUp e TearDown sono stati rimossi a partire dalla versione 2.x di xUnit</span><span class="sxs-lookup"><span data-stu-id="b09e8-257">xUnit has removed both SetUp and TearDown as of version 2.x</span></span>

#### <a name="bad"></a><span data-ttu-id="b09e8-258">Scadente:</span><span class="sxs-lookup"><span data-stu-id="b09e8-258">Bad:</span></span>
[!code-csharp[BeforeSetup](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeSetup)]

```csharp
// more tests...
```

[!code-csharp[BeforeHelperMethod](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeHelperMethod)]

#### <a name="better"></a><span data-ttu-id="b09e8-259">Migliore:</span><span class="sxs-lookup"><span data-stu-id="b09e8-259">Better:</span></span>
[!code-csharp[AfterHelperMethod](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterHelperMethod)]

```csharp
// more tests...
```

[!code-csharp[AfterSetup](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterSetup)]

### <a name="avoid-multiple-asserts"></a><span data-ttu-id="b09e8-260">Evitare le asserzioni multiple</span><span class="sxs-lookup"><span data-stu-id="b09e8-260">Avoid multiple asserts</span></span>
<span data-ttu-id="b09e8-261">Quando si scrivono i test, puntare a includere una sola asserzione per ogni test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-261">When writing your tests, try to only include one Assert per test.</span></span> <span data-ttu-id="b09e8-262">Le strategie comuni per usare una sola asserzione includono:</span><span class="sxs-lookup"><span data-stu-id="b09e8-262">Common approaches to using only one assert include:</span></span>

- <span data-ttu-id="b09e8-263">Creare un test separato per ogni asserzione.</span><span class="sxs-lookup"><span data-stu-id="b09e8-263">Create a separate test for each assert.</span></span>
- <span data-ttu-id="b09e8-264">Usare test con parametri.</span><span class="sxs-lookup"><span data-stu-id="b09e8-264">Use parameterized tests.</span></span>

#### <a name="why"></a><span data-ttu-id="b09e8-265">Questo problema dipende</span><span class="sxs-lookup"><span data-stu-id="b09e8-265">Why?</span></span>

- <span data-ttu-id="b09e8-266">Se un'asserzione ha esito negativo, le asserzioni successive non verranno valutate.</span><span class="sxs-lookup"><span data-stu-id="b09e8-266">If one Assert fails, the subsequent Asserts will not be evaluated.</span></span>
- <span data-ttu-id="b09e8-267">Garantisce che l'asserzione non venga applicata a più test case.</span><span class="sxs-lookup"><span data-stu-id="b09e8-267">Ensures you are not asserting multiple cases in your tests.</span></span>
- <span data-ttu-id="b09e8-268">Offre il quadro completo del motivo per cui i test non sono riusciti.</span><span class="sxs-lookup"><span data-stu-id="b09e8-268">Gives you the entire picture as to why your tests are failing.</span></span>

<span data-ttu-id="b09e8-269">Quando si introducono più asserzioni in un test case, non è sicuro che tutte le asserzioni verranno eseguite.</span><span class="sxs-lookup"><span data-stu-id="b09e8-269">When introducing multiple asserts into a test case, it is not guaranteed that all of the asserts will be executed.</span></span> <span data-ttu-id="b09e8-270">Nella maggior parte dei framework di testing unità, una volta che un'asserzione ha esito negativo in uno unit test, i test successivi sono automaticamente considerati come non riusciti.</span><span class="sxs-lookup"><span data-stu-id="b09e8-270">In most unit testing frameworks, once an assertion fails in a unit test, the proceeding tests are automatically considered to be failing.</span></span> <span data-ttu-id="b09e8-271">Ciò può generare confusione perché la funzionalità genererà un errore, anche se in realtà funziona.</span><span class="sxs-lookup"><span data-stu-id="b09e8-271">This can be confusing as functionality that is actually working, will be shown as failing.</span></span>

> [!NOTE]
> <span data-ttu-id="b09e8-272">Un'eccezione comune a questa regola riguarda l'asserzione per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="b09e8-272">A common exception to this rule is when asserting against an object.</span></span> <span data-ttu-id="b09e8-273">In questo caso, è in genere accettabile avere più asserzioni per ogni proprietà per assicurarsi che l'oggetto sia nello stato previsto.</span><span class="sxs-lookup"><span data-stu-id="b09e8-273">In this case, it is generally acceptable to have multiple asserts against each property to ensure the object is in the state that you expect it to be in.</span></span>

#### <a name="bad"></a><span data-ttu-id="b09e8-274">Scadente:</span><span class="sxs-lookup"><span data-stu-id="b09e8-274">Bad:</span></span>
[!code-csharp[BeforeMultipleAsserts](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeMultipleAsserts)]

#### <a name="better"></a><span data-ttu-id="b09e8-275">Migliore:</span><span class="sxs-lookup"><span data-stu-id="b09e8-275">Better:</span></span>
[!code-csharp[AfterMultipleAsserts](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterMultipleAsserts)]

### <a name="validate-private-methods-by-unit-testing-public-methods"></a><span data-ttu-id="b09e8-276">Convalidare i metodi privati tramite il testing unità dei metodi pubblici</span><span class="sxs-lookup"><span data-stu-id="b09e8-276">Validate private methods by unit testing public methods</span></span>
<span data-ttu-id="b09e8-277">Nella maggior parte dei casi, non è necessario testare un metodo privato.</span><span class="sxs-lookup"><span data-stu-id="b09e8-277">In most cases, there should not be a need to test a private method.</span></span> <span data-ttu-id="b09e8-278">I metodi privati sono un dettaglio di implementazione.</span><span class="sxs-lookup"><span data-stu-id="b09e8-278">Private methods are an implementation detail.</span></span> <span data-ttu-id="b09e8-279">Consideriamo la cosa da questo punto di vista: i metodi privati non esistono singolarmente.</span><span class="sxs-lookup"><span data-stu-id="b09e8-279">You can think of it this way: private methods never exist in isolation.</span></span> <span data-ttu-id="b09e8-280">A un certo punto, ci sarà un metodo pubblico che chiama il metodo privato come parte della sua implementazione.</span><span class="sxs-lookup"><span data-stu-id="b09e8-280">At some point, there is going to be a public facing method that calls the private method as part of its implementation.</span></span> <span data-ttu-id="b09e8-281">Quello che è opportuno prendere in considerazione è il risultato finale del metodo pubblico che chiama quello privato.</span><span class="sxs-lookup"><span data-stu-id="b09e8-281">What you should care about is the end result of the public method that calls into the private one.</span></span>

<span data-ttu-id="b09e8-282">Si consideri il caso seguente</span><span class="sxs-lookup"><span data-stu-id="b09e8-282">Consider the following case</span></span>

```csharp
public string ParseLogLine(string input)
{
    var sanitizedInput = TrimInput(input);
    return sanitizedInput;
}

private string TrimInput(string input)
{
    return input.Trim();
}
```

<span data-ttu-id="b09e8-283">La prima reazione dell'utente potrebbe essere iniziare a scrivere un test per `TrimInput` per verificare che il metodo funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="b09e8-283">Your first reaction may be to start writing a test for `TrimInput` because you want to make sure that the method is working as expected.</span></span> <span data-ttu-id="b09e8-284">Tuttavia, è probabile che `ParseLogLine` manipoli `sanitizedInput` in un modo imprevisto che rende il test di `TrimInput` inutile.</span><span class="sxs-lookup"><span data-stu-id="b09e8-284">However, it is entirely possible that `ParseLogLine` manipulates `sanitizedInput` in such a way that you do not expect, rendering a test against `TrimInput` useless.</span></span>

<span data-ttu-id="b09e8-285">Il test reale deve essere eseguito con il metodo pubblico `ParseLogLine` perché questo è ciò che è necessario considerare.</span><span class="sxs-lookup"><span data-stu-id="b09e8-285">The real test should be done against the public facing method `ParseLogLine` because that is what you should ultimately care about.</span></span>

```csharp
public void ParseLogLine_ByDefault_ReturnsTrimmedResult()
{
    var parser = new Parser();

    var result = parser.ParseLogLine(" a ");

    Assert.Equals("a", result);
}
```

<span data-ttu-id="b09e8-286">Tenendo presente questo aspetto, quando si vede un metodo privato, trovare il metodo pubblico e scrivere i test su tale metodo.</span><span class="sxs-lookup"><span data-stu-id="b09e8-286">With this viewpoint, if you see a private method, find the public method and write your tests against that method.</span></span> <span data-ttu-id="b09e8-287">Unicamente perché un metodo privato restituisce il risultato previsto non implica che il sistema che chiama il metodo privato usi il risultato in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="b09e8-287">Just because a private method returns the expected result, does not mean the system that eventually calls the private method uses the result correctly.</span></span>

### <a name="stub-static-references"></a><span data-ttu-id="b09e8-288">Riferimenti statici negli stub</span><span class="sxs-lookup"><span data-stu-id="b09e8-288">Stub static references</span></span>
<span data-ttu-id="b09e8-289">Uno dei principi a cui uno unit test si deve attenere è che deve avere controllo completo del sistema sottoposto a test.</span><span class="sxs-lookup"><span data-stu-id="b09e8-289">One of the principles of a unit test is that it must have full control of the system under test.</span></span> <span data-ttu-id="b09e8-290">Questa operazione può risultare problematica quando il codice di produzione include chiamate a riferimenti statici (ad esempio, `DateTime.Now` ).</span><span class="sxs-lookup"><span data-stu-id="b09e8-290">This can be problematic when production code includes calls to static references (for example, `DateTime.Now`).</span></span> <span data-ttu-id="b09e8-291">Si consideri il codice seguente</span><span class="sxs-lookup"><span data-stu-id="b09e8-291">Consider the following code</span></span>

```csharp
public int GetDiscountedPrice(int price)
{
    if(DateTime.Now.DayOfWeek == DayOfWeek.Tuesday)
    {
        return price / 2;
    }
    else
    {
        return price;
    }
}
```

<span data-ttu-id="b09e8-292">In che modo questo codice può essere sottoposta a testing unità?</span><span class="sxs-lookup"><span data-stu-id="b09e8-292">How can this code possibly be unit tested?</span></span> <span data-ttu-id="b09e8-293">Provare una strategia di questo tipo</span><span class="sxs-lookup"><span data-stu-id="b09e8-293">You may try an approach such as</span></span>

```csharp
public void GetDiscountedPrice_ByDefault_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(2, actual)
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(1, actual);
}
```

<span data-ttu-id="b09e8-294">Sfortunatamente, ci si renderà rapidamente conto che nel test ci sono un paio di problemi.</span><span class="sxs-lookup"><span data-stu-id="b09e8-294">Unfortunately, you will quickly realize that there are a couple problems with your tests.</span></span>

- <span data-ttu-id="b09e8-295">Se il gruppo di test viene eseguito di martedì, il secondo test avrà esito positivo, ma il primo test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b09e8-295">If the test suite is run on a Tuesday, the second test will pass, but the first test will fail.</span></span>
- <span data-ttu-id="b09e8-296">Se il gruppo di test viene eseguito un qualsiasi altro giorno, il primo test avrà esito positivo, ma il secondo test avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b09e8-296">If the test suite is run on any other day, the first test will pass, but the second test will fail.</span></span>

<span data-ttu-id="b09e8-297">Per risolvere questi problemi, sarà necessario introdurre un *seam* nel codice di produzione.</span><span class="sxs-lookup"><span data-stu-id="b09e8-297">To solve these problems, you'll need to introduce a *seam* into your production code.</span></span> <span data-ttu-id="b09e8-298">Una strategia consiste nell'inserire il codice da controllare in un'interfaccia e far dipendere il codice di produzione da tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b09e8-298">One approach is to wrap the code that you need to control in an interface and have the production code depend on that interface.</span></span>

```csharp
public interface IDateTimeProvider
{
    DayOfWeek DayOfWeek();
}

public int GetDiscountedPrice(int price, IDateTimeProvider dateTimeProvider)
{
    if(dateTimeProvider.DayOfWeek() == DayOfWeek.Tuesday)
    {
        return price / 2;
    }
    else
    {
        return price;
    }
}
```

<span data-ttu-id="b09e8-299">Il gruppo di test diventa</span><span class="sxs-lookup"><span data-stu-id="b09e8-299">Your test suite now becomes</span></span>

```csharp
public void GetDiscountedPrice_ByDefault_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Monday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(2, actual);
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Tuesday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(1, actual);
}
```

<span data-ttu-id="b09e8-300">Ora il gruppo di test ha pieno controllo su `DateTime.Now` ed è possibile sottoporre a stub qualsiasi valore durante la chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="b09e8-300">Now the test suite has full control over `DateTime.Now` and can stub any value when calling into the method.</span></span>
