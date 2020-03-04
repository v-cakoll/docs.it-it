---
title: Progettare con tipi riferimento nullable
description: Questa esercitazione avanzata fornisce un'introduzione ai tipi riferimento nullable. Si imparerà a esprimere le finalità della progettazione in merito a quando i valori di riferimento possono essere Null e a configurare il compilatore in modo che stabilisca quando non possono essere Null.
ms.date: 02/19/2019
ms.technology: csharp-null-safety
ms.custom: mvc
ms.openlocfilehash: b00050c1d151b95e330f94eb9393a4031e47d5a8
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78240067"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a>Esercitazione: Esprimere più chiaramente le finalità di progettazione con tipi riferimento nullable e non nullable

C#8,0 introduce [tipi di riferimento Nullable](../nullable-references.md), che completano i tipi di riferimento in modo analogo ai tipi di valore Nullable. Per dichiarare una variabile come **tipo riferimento nullable** basta aggiungere un `?` alla fine del tipo. Ad esempio, `string?` rappresenta un tipo `string` nullable. È possibile usare questi nuovi tipi per esprimere più chiaramente le finalità della progettazione: alcune variabili *devono avere sempre un valore*, mentre in altre *un valore può mancare*.

In questa esercitazione si apprenderà come:

> [!div class="checklist"]
>
> - Incorporare tipi riferimento nullable e non nullable nelle progettazioni.
> - Abilitare i controlli dei tipi riferimento nullable in tutto il codice.
> - Scrivere codice in cui il compilatore impone tali decisioni di progettazione.
> - Usare la funzionalità dei riferimenti nullable nelle proprie progettazioni.

## <a name="prerequisites"></a>Prerequisites

È necessario configurare il computer per l'esecuzione di .NET Core, incluso il C# compilatore 8,0. Il C# compilatore 8,0 è disponibile con [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)o [.NET Core 3,0](https://dotnet.microsoft.com/download/dotnet-core/3.0).

Per questa esercitazione si presuppone che l'utente abbia familiarità con C# e .NET, inclusa l'interfaccia della riga di comando di .NET Core o Visual Studio.

## <a name="incorporate-nullable-reference-types-into-your-designs"></a>Incorporare tipi riferimento nullable nelle progettazioni

In questa esercitazione si compilerà una libreria che modella l'esecuzione di un sondaggio. Il codice usa tipi riferimento sia nullable che non nullable per rappresentare concetti reali. Le domande del sondaggio non possono mai essere Null. Un partecipante al sondaggio potrebbe preferire non rispondere a una domanda. In questo caso, le risposte potrebbero essere `null`.

Il codice scritto per questo esempio esprime questa intenzione e il compilatore la applica.

## <a name="create-the-application-and-enable-nullable-reference-types"></a>Creare l'applicazione e abilitare i tipi riferimento nullable

Creare una nuova applicazione console in Visual Studio oppure dalla riga di comando tramite `dotnet new console`. Assegnare all'applicazione il nome `NullableIntroduction`. Dopo aver creato l'applicazione, è necessario specificare che l'intero progetto venga compilato in un **contesto di annotazione Nullable**abilitato. Aprire il file con *estensione csproj* e aggiungere un elemento `Nullable` all'elemento `PropertyGroup`. Impostare il relativo valore su `enable`. È necessario optare per la funzionalità dei **tipi di riferimento Nullable** , anche nei C# progetti 8,0. Questo perché dopo che la funzionalità viene attivata, le dichiarazioni di variabili di riferimento esistenti diventano **tipi riferimento non nullable**. Sebbene questa decisione consenta di individuare i problemi per cui il codice esistente potrebbe non avere controlli null appropriati, potrebbe non riflettere accuratamente la finalità di progettazione originale:

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

Se è stata eseguita la C#programmazione in, è possibile che si sia abituati a fare riferimento ai tipi che consentono di `null` valori che potrebbero aver perso altre opportunità per dichiarare istanze non nullable:

- La raccolta delle domande deve essere non nullable.
- La raccolta dei partecipanti deve essere non nullable.

Quando si scrive il codice, si noterà che un tipo di riferimento non nullable come il valore predefinito per i riferimenti evita errori comuni che potrebbero causare <xref:System.NullReferenceException>s. Una lezione di questa esercitazione consiste nel prendere decisioni sulle variabili che possono o non essere `null`. Nelle versioni precedenti il linguaggio non forniva la sintassi necessaria per esprimere queste decisioni. Ora invece tutto questo è possibile.

L'app da compilare esegue i passaggi seguenti:

1. Consente di creare un sondaggio e di aggiungere domande.
1. Crea un set pseudo-casuale di intervistati per il sondaggio.
1. Contatta gli intervistati fino a quando la dimensione del sondaggio completata raggiunge il numero obiettivo.
1. Scrive statistiche importanti sulle risposte del sondaggio.

## <a name="build-the-survey-with-nullable-and-non-nullable-types"></a>Compilare il sondaggio con tipi nullable e non nullable

Il primo codice scritto crea il sondaggio. Occorre scrivere le classi necessarie per modellare una domanda del sondaggio e l'esecuzione del sondaggio. Il sondaggio ha tre tipi di domande, distinte dal formato della risposta: risposte Sì/No, risposte in forma di numero e risposte testuali. Creare una classe `public SurveyQuestion`:

```csharp
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

Il compilatore interpreta ogni dichiarazione di variabile di tipo riferimento come tipo di riferimento **non nullable** per il codice in un contesto di annotazione Nullable abilitato. È possibile vedere il primo avviso aggiungendo le proprietà del testo della domanda e il tipo di domanda, come illustrato nel codice seguente:

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

Passare a *Program.cs* nell'editor e sostituire il contenuto di `Main` con le righe di codice seguenti:

[!code-csharp[AddQuestions](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

Poiché l'intero progetto si trova in un contesto di annotazione Nullable abilitato, si riceveranno avvisi quando si passa `null` a qualsiasi metodo che prevede un tipo di riferimento non nullable. Provare ad aggiungere la riga seguente a `Main`:

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

L'archivio per le risposte del sondaggio è un `Dictionary<int, string>?`, a indicare che può essere Null. Si sta usando la nuova funzionalità del linguaggio per dichiarare la finalità della progettazione, sia al compilatore che a chiunque legga il codice successivamente. Se si dereferenziano `surveyResponses` senza prima verificare il valore di `null`, verrà visualizzato un avviso del compilatore. Non si riceve un avviso nel metodo `AnswerSurvey` perché il compilatore è in grado di determinare che la variabile `surveyResponses` è stata impostata su un valore non Null.

L'uso di `null` per le risposte mancanti evidenzia un aspetto essenziale per l'utilizzo dei tipi riferimento nullable, ovvero l'obiettivo non è rimuovere tutti i valori `null` dal programma. L'obiettivo è invece quello di assicurarsi che il codice scritto esprima lo scopo della progettazione. I valori mancanti sono un concetto necessario da esprimere nel codice. Il valore `null` rappresenta un modo chiaro per esprimere tali valori mancanti. Il tentativo di rimuovere tutti i valori `null` porta solo alla definizione di un altro modo per esprimere i valori mancanti senza `null`.

A questo punto occorre scrivere il metodo `PerformSurvey` nella classe `SurveyRun`. Aggiungere il codice seguente nella classe `SurveyRun`:

[!code-csharp[PerformSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

Anche in questo caso la scelta di un `List<SurveyResponse>?` nullable indica che la risposta può essere Null. Indica che il sondaggio non è ancora stato distribuito ad alcun partecipante. Si noti che i partecipanti continuano a essere aggiunti finché non acconsente un numero sufficiente.

L'ultimo passaggio dell'esecuzione del sondaggio consiste nell'aggiungere una chiamata per eseguire il sondaggio alla fine del metodo `Main`:

[!code-csharp[RunSurvey](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a>Esaminare le risposte al sondaggio

L'ultimo passaggio è la visualizzazione dei risultati del sondaggio. Occorre aggiungere codice a molte delle classi scritte. Questo codice dimostra il valore della distinzione fra i tipi riferimento nullable e non nullable. Per iniziare, aggiungere i due membri con corpo di espressione seguenti alla classe `SurveyResponse`:

[!code-csharp[ReportResponses](~/samples/snippets/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

Poiché `surveyResponses` è un tipo di riferimento Nullable, i controlli null sono necessari prima di dereferenziarli. Il metodo `Answer` restituisce una stringa che non ammette i valori null, pertanto è necessario coprire il caso di una risposta mancante utilizzando l'operatore di Unione null.

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
