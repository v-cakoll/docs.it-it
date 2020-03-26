---
title: Progettare con tipi riferimento nullable
description: Questa esercitazione avanzata fornisce un'introduzione ai tipi riferimento nullable. Si imparerà a esprimere le finalità della progettazione in merito a quando i valori di riferimento possono essere Null e a configurare il compilatore in modo che stabilisca quando non possono essere Null.
ms.date: 02/19/2019
ms.technology: csharp-null-safety
ms.custom: mvc
ms.openlocfilehash: 54cf9d812999cae837483b48cdedd89d9dc40fc9
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249129"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a>Esercitazione: Esprimere più chiaramente le finalità di progettazione con tipi riferimento nullable e non nullable

La versione 8.0 introduce tipi di [riferimento nullable,](../nullable-references.md)che completano i tipi di riferimento allo stesso modo in cui i tipi di valore nullable completano i tipi di valore. Per dichiarare una variabile come **tipo riferimento nullable** basta aggiungere un `?` alla fine del tipo. Ad esempio, `string?` rappresenta un tipo `string` nullable. È possibile usare questi nuovi tipi per esprimere più chiaramente le finalità della progettazione: alcune variabili *devono avere sempre un valore*, mentre in altre *un valore può mancare*.

In questa esercitazione si apprenderà come:

> [!div class="checklist"]
>
> - Incorporare tipi riferimento nullable e non nullable nelle progettazioni.
> - Abilitare i controlli dei tipi riferimento nullable in tutto il codice.
> - Scrivere codice in cui il compilatore impone tali decisioni di progettazione.
> - Usare la funzionalità dei riferimenti nullable nelle proprie progettazioni.

## <a name="prerequisites"></a>Prerequisiti

È necessario configurare il computer per l'esecuzione di .NET Core, incluso il compilatore c'è 8.0. Il compilatore di Cè 8.0 è disponibile con [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)o [.NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0).

Per questa esercitazione si presuppone che l'utente abbia familiarità con C# e .NET, inclusa l'interfaccia della riga di comando di .NET Core o Visual Studio.

## <a name="incorporate-nullable-reference-types-into-your-designs"></a>Incorporare tipi riferimento nullable nelle progettazioni

In questa esercitazione si compilerà una libreria che modella l'esecuzione di un sondaggio. Il codice usa tipi riferimento sia nullable che non nullable per rappresentare concetti reali. Le domande del sondaggio non possono mai essere Null. Un partecipante al sondaggio potrebbe preferire non rispondere a una domanda. Le risposte potrebbero `null` essere in questo caso.

Il codice scritto per questo esempio esprime questa intenzione e il compilatore la applica.

## <a name="create-the-application-and-enable-nullable-reference-types"></a>Creare l'applicazione e abilitare i tipi riferimento nullable

Creare una nuova applicazione console in Visual Studio oppure dalla riga di comando tramite `dotnet new console`. Assegnare all'applicazione il nome `NullableIntroduction`. Dopo aver creato l'applicazione, è necessario specificare che l'intero progetto viene compilato in un contesto di **annotazione nullable**abilitato. Aprire il file *con estensione csproj* e aggiungere un `Nullable` elemento all'elemento. `PropertyGroup` Impostare il relativo valore su `enable`. È necessario acconsentire esplicitamente alla funzionalità dei tipi di **riferimento nullable,** anche nei progetti 8.0 di C. Questo perché dopo che la funzionalità viene attivata, le dichiarazioni di variabili di riferimento esistenti diventano **tipi riferimento non nullable**. Sebbene tale decisione consenta di individuare i problemi in cui il codice esistente potrebbe non disporre di controlli null appropriati, potrebbe non riflettere in modo accurato l'intento di progettazione originale:While that decision will help find issues where existing code may not have proper null-checks, it may not precision reflect your original design intent:

```xml
<Nullable>enable</Nullable>
```

### <a name="design-the-types-for-the-application"></a>Progettare i tipi per l'applicazione

Per questa applicazione di sondaggio è necessario creare alcune classi:

- Una classe che modella l'elenco di domande.
- Una classe che modella un elenco di persone contattate per il sondaggio.
- Una classe che modella le risposte di una persona che ha partecipato al sondaggio.

Questi tipi useranno tipi riferimento sia nullable sia non nullable per indicare i membri obbligatori e quelli facoltativi. I tipi riferimento nullable comunicano chiaramente questa finalità della progettazione:

- Le domande che costituiscono il sondaggio non possono mai essere Null. Una domanda vuota non ha infatti alcun senso.
- I partecipanti al sondaggio non possono mai essere Null. Si vuole infatti tenere traccia delle persone che sono state contattate, anche quelle che non hanno accettato di partecipare.
- Una risposta a una domanda può essere Null. I partecipanti possono infatti rifiutarsi di rispondere ad alcune o a tutte le domande.

Se è stato programmato in C , si può essere `null` così abituati a i tipi di riferimento che consentono valori che potrebbero essere persi altre opportunità di dichiarare istanze non nullable:If you've programmed in C'è, you may be so accustomed to reference types that allow values that you may have missed other opportunities to declare non-nullable instances:

- La raccolta delle domande deve essere non nullable.
- La raccolta dei partecipanti deve essere non nullable.

Mentre si scrive il codice, si noterà che un tipo di riferimento non nullable come <xref:System.NullReferenceException>valore predefinito per i riferimenti evita errori comuni che potrebbero portare a s. Una lezione da questo tutorial è che hai preso `null`decisioni su quali variabili potrebbero o non potrebbero essere . Nelle versioni precedenti il linguaggio non forniva la sintassi necessaria per esprimere queste decisioni. Ora invece tutto questo è possibile.

L'app che verrà compilata esegue i passaggi seguenti:The app you'll build does the following steps:

1. Crea un sondaggio e vi aggiunge delle domande.
1. Crea un set pseudo-casuale di rispondenti per il sondaggio.
1. Contatta i rispondenti fino a quando la dimensione dell'indagine completata non raggiunge il numero di obiettivo.
1. Scrive statistiche importanti sulle risposte al sondaggio.

## <a name="build-the-survey-with-nullable-and-non-nullable-reference-types"></a>Compilare il sondaggio con tipi di riferimento nullable e non nullable

Il primo codice scritto crea il sondaggio. Occorre scrivere le classi necessarie per modellare una domanda del sondaggio e l'esecuzione del sondaggio. Il sondaggio ha tre tipi di domande, distinte dal formato della risposta: risposte Sì/No, risposte in forma di numero e risposte testuali. Creare `public SurveyQuestion` una classe:Create a class:

```csharp
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

Il compilatore interpreta ogni dichiarazione di variabile di tipo riferimento come un tipo di riferimento **non nullable** per il codice in un contesto di annotazione nullable abilitato. È possibile vedere il primo avviso aggiungendo le proprietà del testo della domanda e il tipo di domanda, come illustrato nel codice seguente:

```csharp
namespace NullableIntroduction
{
    public enum QuestionType
    {
        YesNo,
        Number,
        Text
    }

    public class SurveyQuestion
    {
        public string QuestionText { get; }
        public QuestionType TypeOfQuestion { get; }
    }
}
```

Poiché `QuestionText` non è stato inizializzato, il compilatore genera un avviso che informa che una proprietà non nullable non è stata inizializzata. Un requisito della progettazione è che il testo della domanda non sia Null, pertanto occorre aggiunge un costruttore per inizializzare questa proprietà e anche il valore `QuestionType`. La definizione finale della classe è simile al codice seguente:

[!code-csharp[DefineQuestion](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyQuestion.cs)]

Aggiungendo il costruttore, l'avviso viene rimosso. Anche l'argomento del costruttore è un tipo riferimento non nullable, quindi il compilatore non genera alcun avviso.

Creare quindi una classe `public` denominata `SurveyRun`. Questa classe contiene un elenco di metodi e oggetti `SurveyQuestion` per aggiungere domande al sondaggio, come illustrato nel codice seguente:

```csharp
using System.Collections.Generic;

namespace NullableIntroduction
{
    public class SurveyRun
    {
        private List<SurveyQuestion> surveyQuestions = new List<SurveyQuestion>();

        public void AddQuestion(QuestionType type, string question) =>
            AddQuestion(new SurveyQuestion(type, question));
        public void AddQuestion(SurveyQuestion surveyQuestion) => surveyQuestions.Add(surveyQuestion);
    }
}
```

Anche in questo caso occorre inizializzare l'oggetto elenco su un valore non Null per evitare che il compilatore generi un avviso. Nel secondo overload di `AddQuestion` non ci sono controlli dei valori Null in quanto non sono necessari: la variabile è stata infatti dichiarata come non nullable. Il suo valore non può essere `null`.

Passare a *Program.cs* nell'editor e `Main` sostituire il contenuto con le seguenti righe di codice:

[!code-csharp[AddQuestions](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

Poiché l'intero progetto si trova in un contesto di `null` annotazione nullable abilitato, si otterranno avvisi quando si passa a qualsiasi metodo che prevede un tipo di riferimento non nullable. Provare ad aggiungere la riga seguente a `Main`:

```csharp
surveyRun.AddQuestion(QuestionType.Text, default);
```

## <a name="create-respondents-and-get-answers-to-the-survey"></a>Creare i partecipanti e ottenere le risposte al sondaggio

A questo punto occorre scrivere il codice che genera le risposte al sondaggio. Questo processo include varie piccole attività:

1. Compilare un metodo che generi gli oggetti partecipante. Questi oggetti rappresentano le persone a cui è stato chiesto di completare il sondaggio.
1. Creare la logica per simulare la formulazione delle domande a un partecipante e la raccolta delle risposte oppure di nessun dato, se il partecipante non ha risposto.
1. Ripetere finché non ha risposto al sondaggio un numero sufficiente di partecipanti.

A questo punto occorre aggiungere una classe che rappresenti una risposta al sondaggio. Abilitare il supporto dei tipi riferimento nullable. Aggiungere una proprietà `Id` e un costruttore che la inizializza, come illustrato nel codice seguente:

```csharp
namespace NullableIntroduction
{
    public class SurveyResponse
    {
        public int Id { get; }

        public SurveyResponse(int id) => Id = id;
    }
}
```

Quindi aggiungere un metodo `static` per la creazione di nuovi partecipanti tramite la generazione di un ID casuale:

[!code-csharp[GenerateRespondents](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#Random)]

La responsabilità principale di questa classe è generare le risposte di un partecipante alle domande del sondaggio. A questo scopo è necessario eseguire i passaggi seguenti:

1. Chiedere di partecipare al sondaggio. Se la persona non acconsente, restituire una risposta mancante (o Null).
1. Porre ogni domanda e registrare la risposta. Ogni risposta può anche essere mancante (o Null).

Aggiungere il codice seguente alla classe `SurveyResponse`:

[!code-csharp[AnswerSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#AnswerSurvey)]

L'archivio per le risposte del sondaggio è un `Dictionary<int, string>?`, a indicare che può essere Null. Si sta usando la nuova funzionalità del linguaggio per dichiarare la finalità della progettazione, sia al compilatore che a chiunque legga il codice successivamente. Se si dereferenzierà `surveyResponses` senza prima controllare il `null` valore, si otterrà un avviso del compilatore. Non si riceve un avviso nel metodo `AnswerSurvey` perché il compilatore è in grado di determinare che la variabile `surveyResponses` è stata impostata su un valore non Null.

L'uso di `null` per le risposte mancanti evidenzia un aspetto essenziale per l'utilizzo dei tipi riferimento nullable, ovvero l'obiettivo non è rimuovere tutti i valori `null` dal programma. L'obiettivo è invece quello di assicurarsi che il codice scritto esprima lo scopo della progettazione. I valori mancanti sono un concetto necessario da esprimere nel codice. Il valore `null` rappresenta un modo chiaro per esprimere tali valori mancanti. Il tentativo di rimuovere tutti i valori `null` porta solo alla definizione di un altro modo per esprimere i valori mancanti senza `null`.

A questo punto occorre scrivere il metodo `PerformSurvey` nella classe `SurveyRun`. Aggiungere il codice seguente nella classe `SurveyRun`:

[!code-csharp[PerformSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

Anche in questo caso la scelta di un `List<SurveyResponse>?` nullable indica che la risposta può essere Null. Indica che il sondaggio non è ancora stato distribuito ad alcun partecipante. Si noti che i partecipanti continuano a essere aggiunti finché non acconsente un numero sufficiente.

L'ultimo passaggio dell'esecuzione del sondaggio consiste nell'aggiungere una chiamata per eseguire il sondaggio alla fine del metodo `Main`:

[!code-csharp[RunSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a>Esaminare le risposte al sondaggio

L'ultimo passaggio è la visualizzazione dei risultati del sondaggio. Occorre aggiungere codice a molte delle classi scritte. Questo codice dimostra il valore della distinzione fra i tipi riferimento nullable e non nullable. Per iniziare, aggiungere i due membri con corpo di espressione seguenti alla classe `SurveyResponse`:

[!code-csharp[ReportResponses](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

Poiché `surveyResponses` è un tipo di riferimento nullable, i controlli null sono necessari prima di dereferenziare esso. Il `Answer` metodo restituisce una stringa non nullable, pertanto è necessario coprire il caso di una risposta mancante utilizzando l'operatore di null-coalescing.

Aggiungere quindi questi tre membri con corpo di espressione alla classe `SurveyRun`:

[!code-csharp[ReportResults](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#RunReport)]

Il membro `AllParticipants` deve tenere conto del fatto che la variabile `respondents` potrebbe essere Null, ma il valore restituito non può essere Null. Se si modifica l'espressione rimuovendo `??` e la sequenza vuota che segue, il compilatore avvisa che il metodo potrebbe restituire `null` e la sua firma restituita restituisce un tipo non nullable.

Infine, aggiungere il ciclo seguente alla fine del metodo `Main`:

[!code-csharp[DisplaySurveyResults](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#WriteAnswers)]

Non è necessario eseguire alcun controllo dei valori `null` in questo codice perché le interfacce sottostanti sono state progettate in modo che restituiscano tutte tipi di riferimento non nullable.

## <a name="get-the-code"></a>Ottenere il codice

Il codice dell'esercitazione completata è disponibile nel repository [samples](https://github.com/dotnet/samples) nella cartella [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction).

È possibile fare delle prove cambiando le dichiarazioni di tipo fra tipi riferimento nullable e non nullable e osservare come vengono generati avvisi diversi per assicurare che non venga dereferenziato accidentalmente un valore `null`.

## <a name="next-steps"></a>Passaggi successivi

Ottenere altre informazioni eseguendo la migrazione di un'applicazione esistente per usare i tipi riferimento nullable:
> [!div class="nextstepaction"]
> [Aggiornare un'app per i tipi riferimento nullable](upgrade-to-nullable-references.md)
