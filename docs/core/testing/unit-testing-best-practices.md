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
# <a name="unit-testing-best-practices-with-net-core-and-net-standard"></a>Procedure consigliate di testing unità con .NET Core e .NET Standard

La scrittura di unit test offre numerosi vantaggi: facilitano la regressione, rappresentano fonti di documentazione e semplificano la progettazione ottimale. Tuttavia, unit test deboli e di difficile lettura possono causare seri problemi nella base codice. Questo articolo descrive alcune procedure consigliate per la progettazione di unit test per i progetti .NET Core e .NET Standard.

In questa guida verranno descritte alcune procedure consigliate per scrivere unit test flessibili e di facile comprensione.

A cura di [John Reese](https://reese.dev) con ringraziamenti speciali a [Roy Osherove](https://osherove.com/)

## <a name="why-unit-test"></a>L'utilità degli unit test

### <a name="less-time-performing-functional-tests"></a>Meno tempo da dedicare all'esecuzione dei test funzionali
I test funzionali sono costosi. Comportano, in genere, l'apertura dell'applicazione e l'esecuzione di una serie di passaggi che l'utente, o chi per lui, deve eseguire per convalidare il comportamento previsto. Questi passaggi potrebbero non essere sempre chiari per chi esegue il test, pertanto questi dovrà contattare qualcuno con maggiori conoscenze in materia per eseguire il test. Il test di semplici modifiche può richiedere solo alcuni secondi, che possono diventare minuti per modifiche più significative. Infine, questo processo deve essere ripetuto per ogni modifica apportata nel sistema.

Gli unit test, d'altra parte, accettano millisecondi, possono essere eseguiti alla pressione di un pulsante e non richiedono necessariamente alcuna conoscenza del sistema in grande. L'esito positivo o negativo del test è determinato dal test runner, non dai singoli utenti.

### <a name="protection-against-regression"></a>Protezione contro la regressione
I difetti di regressione sono i difetti che vengono introdotti quando si apporta una modifica all'applicazione. È pratica comune per i tester testare non solo le nuove funzionalità, ma anche quelle già esistenti per verificare che le funzionalità implementate in precedenza continuino a funzionare come previsto.

Con gli unit test, è possibile eseguire nuovamente l'intero gruppo di test dopo ogni compilazione o persino dopo la modifica di una sola riga di codice. Questo, offrendo la certezza che il nuovo codice non interferisce con le funzionalità esistenti.

### <a name="executable-documentation"></a>Documentazione eseguibile
Non è sempre facile sapere lo scopo di un particolare metodo o il suo comportamento con un dato input. Ci si potrebbe chiedere: che comportamento avrebbe questo metodo se fosse associato a una stringa vuota? Restituirebbe un valore null?

Quando si dispone di un gruppo di unit test ben identificabili, per ogni test è possibile capire chiaramente l'output previsto per un dato input. Inoltre, è possibile verificarne l'effettivo funzionamento.

### <a name="less-coupled-code"></a>Meno codice accoppiato
Quando il codice è strettamente accoppiato, può risultare difficile eseguire unit test. Senza la creazione di unit test per il codice che si sta scrivendo, l'accoppiamento potrebbe risultare meno evidente.

La scrittura di test per il codice ha l'effetto di disaccoppiare naturalmente il codice perché le verifiche sarebbero, in caso contrario, più difficili.

## <a name="characteristics-of-a-good-unit-test"></a>Caratteristiche di un buon unit test

- **Veloce**. Non è insolito per i progetti maturi comprendere migliaia di unit test. La durata dell'esecuzione degli unit test dovrebbe essere molto breve. Millisecondi.
- **Isolamento**. Gli unit test sono autonomi, possono essere eseguiti in modo isolato e non hanno dipendenze verso fattori esterni, ad esempio file system o database.
- **Ripetibile**. Uno unit test deve generare risultati costanti, vale a dire, deve restituire sempre lo stesso risultato se tra le esecuzioni non si modifica alcun elemento.
- **Autonomo**. Il test deve essere in grado di rilevare automaticamente se ha avuto esito positivo o meno senza alcun intervento.
- **Rispetta i tempi previsti**. Il tempo richiesto per la scrittura di uno unit test deve essere proporzionale al tempo richiesto per la scrittura del codice sottoposto a test. Se il test del codice richiede una quantità di tempo molto maggiore rispetto alla scrittura del codice, prendere in considerazione una struttura che risulti più testabile.

## <a name="code-coverage"></a>Code coverage

Una percentuale di code coverage elevata è spesso associata a una maggiore qualità del codice. Tuttavia, la misurazione stessa *non è in grado* di determinare la qualità del codice. L'impostazione di un obiettivo code coverage percentuale eccessivamente ambizioso può essere controproducente. Immaginate un progetto complesso con migliaia di rami condizionali e immaginiamo di impostare un obiettivo del 95% code coverage. Attualmente il progetto mantiene il 90% code coverage. La quantità di tempo necessaria per tenere conto di tutti i casi perimetrali nel 5% rimanente potrebbe essere un'impresa massiccia e la proposta di valore diminuisce rapidamente.

Una percentuale di code coverage elevata non è un indicatore di esito positivo, né implica una elevata qualità del codice. Rappresenta semplicemente la quantità di codice analizzata dagli unit test. Per ulteriori informazioni, vedere [unit testing code coverage](unit-testing-code-coverage.md).

## <a name="lets-speak-the-same-language"></a>Terminologia
Il termine *simulazione* è purtroppo spesso usato per discutere dei test. I punti seguenti definiscono i tipi più comuni di *Fake* durante la scrittura di unit test:

*Fake* : un fake è un termine generico che può essere usato per descrivere uno stub o un oggetto fittizio. Il fatto che sia uno stub o una simulazione dipende dal contesto in cui viene usato. Quindi, in altre parole, un fake può essere uno stub o un mock.

*Mock*: un mock è un oggetto del sistema che decide se uno unit test ha avuto esito positivo o meno. Una simulazione inizia come un fake fino a quando non viene dichiarata in base a.

*Stub*: è la sostituzione controllabile nel sistema di una dipendenza o di un collaboratore. Utilizzando uno stub è possibile testare il codice senza prendere direttamente in considerazione la dipendenza. Per impostazione predefinita, un fake è inizialmente uno stub.

Si consideri il frammento di codice seguente:

```csharp
var mockOrder = new MockOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

Quanto segue è un esempio di stub che verrebbe chiamato mock. In questo caso, si tratta di stub. Si sta passando Order solo come mezzo per creare un'istanza di `Purchase` (il sistema sottoposto a test). Anche il nome `MockOrder` è fuorviante perché l'ordine non è una simulazione.

Un approccio migliore sarebbe

```csharp
var stubOrder = new FakeOrder();
var purchase = new Purchase(stubOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

Rinominando la classe `FakeOrder` la si rende più generica e la si rende utilizzabile come mock o stub, a seconda del valore migliore per il tipo di test. Nell'esempio precedente, `FakeOrder` viene usato come stub. `FakeOrder` non viene usato in alcun modo durante l'asserzione. `FakeOrder`è stato passato alla `Purchase` classe per soddisfare i requisiti del costruttore.

Per usarlo come mock, si potrebbe procedere così

```csharp
var mockOrder = new FakeOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(mockOrder.Validated);
```

In questo caso, si verifica una proprietà del fake, con un'asserzione su di essa, pertanto nel frammento di codice precedente, `mockOrder` è un mock.

> [!IMPORTANT]
> È importante usare questa terminologia in modo corretto. Se si chiamano gli stub "mock", altri sviluppatori faranno ipotesi errate sulle intenzioni espresse.

La cosa principale da ricordare riguardo a mock e stub è che i mock sono analoghi agli stub, ma che si può rivolgere un'asserzione a un mock, ma non a uno stub.

## <a name="best-practices"></a>Procedure consigliate

### <a name="naming-your-tests"></a>Denominare i test
Il nome del test deve essere costituito da tre parti:

- Nome del metodo testato.
- Scenario in cui si sta testando.
- Comportamento previsto quando viene richiamato lo scenario.

#### <a name="why"></a>Questo problema dipende

- Gli standard di denominazione sono importanti perché esprimono in modo esplicito l'intento del test.

I test non si limitano a verificare che il codice funzioni, ma documentano anche il risultato. Osservando semplicemente il gruppo di unit test, sarà possibile dedurre il comportamento del codice senza neanche guardare il codice. Inoltre, quando i test hanno esito negativo, è possibile vedere esattamente quali scenari non soddisfano le aspettative.

#### <a name="bad"></a>Scadente:
[!code-csharp[BeforeNaming](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeNaming)]

#### <a name="better"></a>Migliore:
[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="arranging-your-tests"></a>Disposizione dei test
**Disporre, agire, asserire** è uno schema comune per gli unit test. Come suggerisce il nome, è costituito da tre azioni principali:

- *Disporre* gli oggetti, creandoli e configurandoli in base alle esigenze.
- *Agire* su un oggetto.
- *Asserire* che un dato comportamento è come previsto.

#### <a name="why"></a>Questo problema dipende

- Separare nettamente l'oggetto del test dai passaggi *disporre* e *asserire*.
- Il rischio di mescolare le asserzioni con il codice "agire" è minore.

La leggibilità è uno degli aspetti più importanti da considerare durante la scrittura di un test. La separazione di ognuna di queste azioni all'interno del test evidenzia chiaramente le dipendenze necessarie per chiamare il codice, come viene chiamato il codice e ciò che si sta tentando di asserire. Sebbene sia possibile combinare alcuni passaggi e ridurre le dimensioni del test, l'obiettivo principale rimane rendere il test più leggibile possibile.

#### <a name="bad"></a>Scadente:
[!code-csharp[BeforeArranging](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeArranging)]

#### <a name="better"></a>Migliore:
[!code-csharp[AfterArranging](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterArranging)]

### <a name="write-minimally-passing-tests"></a>Scrivere test più semplici possibile
L'input da usare in uno unit test deve essere il più semplice possibile per verificare il comportamento che si sta testando.

#### <a name="why"></a>Questo problema dipende

- I test diventano più adattabili alle modifiche future nella base codice.
- I test hanno un comportamento più simile a quello dell'implementazione.

Test che includono più informazioni rispetto a quelle necessarie per la verifica hanno maggiori probabilità di contenere errori e il loro intento risulta meno chiaro. Quando si scrivono i test, si desidera concentrarsi sul comportamento. L'impostazione di proprietà aggiuntive per i modelli o l'uso di valori diversi da zero quando non sono necessari distoglie l'attenzione da ciò che si sta tentando di provare.

#### <a name="bad"></a>Scadente:
[!code-csharp[BeforeMinimallyPassing](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeMinimallyPassing)]

#### <a name="better"></a>Migliore:
[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="avoid-magic-strings"></a>Evitare le "stringhe magiche"
La denominazione delle variabili negli unit test è importante quanto la denominazione delle variabili nel codice di produzione o anche di più. Gli unit test non devono contenere "stringhe magiche".

#### <a name="why"></a>Questo problema dipende

- Impediscono a chi legge il test di controllare il codice di produzione per scoprire ciò che rende il valore speciale.
- Illustrano in modo esplicito ciò che si sta tentando di *dimostrare* anziché ciò che si tenta di *compiere*.

Le "stringhe magiche" possono causare confusione a chi legge il test. Se una stringa appare insolita, ci si potrebbe domandare perché è stato scelto un determinato valore per un parametro o valore restituito. Ciò porterebbe a esaminare i dettagli di implementazione piuttosto che il test stesso.

> [!TIP]
> Quando si scrivono i test, bisogna porsi l'obiettivo di esprimere nel modo più chiaro possibile le loro finalità. Nel caso delle "stringhe magiche", un buon espediente consiste nell'assegnare questi valori a costanti.

#### <a name="bad"></a>Scadente:
[!code-csharp[BeforeMagicString](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeMagicString)]

#### <a name="better"></a>Migliore:
[!code-csharp[AfterMagicString](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterMagicString)]

### <a name="avoid-logic-in-tests"></a>Evitare la logica nei test
Quando si scrivono gli unit test bisogna evitare la concatenazione manuale di stringhe e le condizioni logiche, ad esempio `if`, `while`, `for`, `switch` e così via.

#### <a name="why"></a>Questo problema dipende

- Minore possibilità di introdurre un bug nei test.
- Per concentrarsi sul risultato finale anziché sui dettagli di implementazione.

Se si introduce la logica nel gruppo di test, la possibilità di introdurre un bug al suo interno aumenta notevolmente. L'ultimo posto in cui deve esserci un bug è il gruppo di test. Si deve avere un elevato livello di fiducia riguardo al funzionamento dei test altrimenti non sarà possibile considerarli attendibili. E dei test considerati non attendibili non hanno alcun valore. Quando un test ha esito negativo, è necessario avere la percezione che ci sia un problema nel codice che non può essere ignorato.

> [!TIP]
> Se risulta inevitabile inserire la logica nel test, è consigliabile suddividere il test in due o più test diversi.

#### <a name="bad"></a>Scadente:
[!code-csharp[LogicInTests](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#LogicInTests)]

#### <a name="better"></a>Migliore:
[!code-csharp[AfterTestLogic](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterTestLogic)]

### <a name="prefer-helper-methods-to-setup-and-teardown"></a>Prediligere i metodi helper agli attributi Setup e Teardown
Se si richiede un oggetto o uno stato simile per i test, prediligere un metodo helper piuttosto che utilizzare gli attributi Setup e Teardown, se presenti.

#### <a name="why"></a>Questo problema dipende

- La lettura dei test è più agevole dal momento che la totalità del codice è visibile nel test.
- Minore rischio di configurare troppo o troppo poco per il test specificato.
- Minor probabilità di condividere lo stato tra i test, creando dipendenze indesiderate tra di essi.

Nel framework di testing unità, `Setup` viene chiamato prima di ogni unit test all'interno del gruppo di test. Mentre ad alcuni può apparire uno strumento utile, in realtà genera test troppo grandi e difficili da leggere. I requisiti per rendere ogni test operativo variano da test a test. Sfortunatamente, `Setup` obbliga a usare esattamente gli stessi requisiti per ogni test.

> [!NOTE]
> SetUp e TearDown sono stati rimossi a partire dalla versione 2.x di xUnit

#### <a name="bad"></a>Scadente:
[!code-csharp[BeforeSetup](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeSetup)]

```csharp
// more tests...
```

[!code-csharp[BeforeHelperMethod](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeHelperMethod)]

#### <a name="better"></a>Migliore:
[!code-csharp[AfterHelperMethod](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterHelperMethod)]

```csharp
// more tests...
```

[!code-csharp[AfterSetup](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterSetup)]

### <a name="avoid-multiple-asserts"></a>Evitare le asserzioni multiple
Quando si scrivono i test, puntare a includere una sola asserzione per ogni test. Le strategie comuni per usare una sola asserzione includono:

- Creare un test separato per ogni asserzione.
- Usare test con parametri.

#### <a name="why"></a>Questo problema dipende

- Se un'asserzione ha esito negativo, le asserzioni successive non verranno valutate.
- Garantisce che l'asserzione non venga applicata a più test case.
- Offre il quadro completo del motivo per cui i test non sono riusciti.

Quando si introducono più asserzioni in un test case, non è sicuro che tutte le asserzioni verranno eseguite. Nella maggior parte dei framework di testing unità, una volta che un'asserzione ha esito negativo in uno unit test, i test successivi sono automaticamente considerati come non riusciti. Ciò può generare confusione perché la funzionalità genererà un errore, anche se in realtà funziona.

> [!NOTE]
> Un'eccezione comune a questa regola riguarda l'asserzione per un oggetto. In questo caso, è in genere accettabile avere più asserzioni per ogni proprietà per assicurarsi che l'oggetto sia nello stato previsto.

#### <a name="bad"></a>Scadente:
[!code-csharp[BeforeMultipleAsserts](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeMultipleAsserts)]

#### <a name="better"></a>Migliore:
[!code-csharp[AfterMultipleAsserts](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterMultipleAsserts)]

### <a name="validate-private-methods-by-unit-testing-public-methods"></a>Convalidare i metodi privati tramite il testing unità dei metodi pubblici
Nella maggior parte dei casi, non è necessario testare un metodo privato. I metodi privati sono un dettaglio di implementazione. Consideriamo la cosa da questo punto di vista: i metodi privati non esistono singolarmente. A un certo punto, ci sarà un metodo pubblico che chiama il metodo privato come parte della sua implementazione. Quello che è opportuno prendere in considerazione è il risultato finale del metodo pubblico che chiama quello privato.

Si consideri il caso seguente

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

La prima reazione dell'utente potrebbe essere iniziare a scrivere un test per `TrimInput` per verificare che il metodo funzioni come previsto. Tuttavia, è probabile che `ParseLogLine` manipoli `sanitizedInput` in un modo imprevisto che rende il test di `TrimInput` inutile.

Il test reale deve essere eseguito con il metodo pubblico `ParseLogLine` perché questo è ciò che è necessario considerare.

```csharp
public void ParseLogLine_ByDefault_ReturnsTrimmedResult()
{
    var parser = new Parser();

    var result = parser.ParseLogLine(" a ");

    Assert.Equals("a", result);
}
```

Tenendo presente questo aspetto, quando si vede un metodo privato, trovare il metodo pubblico e scrivere i test su tale metodo. Unicamente perché un metodo privato restituisce il risultato previsto non implica che il sistema che chiama il metodo privato usi il risultato in modo corretto.

### <a name="stub-static-references"></a>Riferimenti statici negli stub
Uno dei principi a cui uno unit test si deve attenere è che deve avere controllo completo del sistema sottoposto a test. Questa operazione può risultare problematica quando il codice di produzione include chiamate a riferimenti statici (ad esempio, `DateTime.Now` ). Si consideri il codice seguente

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

In che modo questo codice può essere sottoposta a testing unità? Provare una strategia di questo tipo

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

Sfortunatamente, ci si renderà rapidamente conto che nel test ci sono un paio di problemi.

- Se il gruppo di test viene eseguito di martedì, il secondo test avrà esito positivo, ma il primo test avrà esito negativo.
- Se il gruppo di test viene eseguito un qualsiasi altro giorno, il primo test avrà esito positivo, ma il secondo test avrà esito negativo.

Per risolvere questi problemi, sarà necessario introdurre un *seam* nel codice di produzione. Una strategia consiste nell'inserire il codice da controllare in un'interfaccia e far dipendere il codice di produzione da tale interfaccia.

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

Il gruppo di test diventa

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

Ora il gruppo di test ha pieno controllo su `DateTime.Now` ed è possibile sottoporre a stub qualsiasi valore durante la chiamata al metodo.
