---
title: Progettare con tipi riferimento nullable
description: Questa esercitazione avanzata fornisce un'introduzione ai tipi riferimento nullable. Si imparerà a esprimere le finalità della progettazione in merito a quando i valori di riferimento possono essere Null e a configurare il compilatore in modo che stabilisca quando non possono essere Null.
ms.date: 12/03/2018
ms.custom: mvc
ms.openlocfilehash: 535efcdc303c17a55f6a4054ea3f5e5ed87e5f28
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2019
ms.locfileid: "56092202"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a>Esercitazione: Esprimere più chiaramente le finalità di progettazione con tipi riferimento nullable e non nullable

In C# 8 sono ora disponibili i **tipi riferimento nullable**, che completano i tipi riferimento allo stesso modo in cui i tipi valore nullable completano i tipi valore. Per dichiarare una variabile come **tipo riferimento nullable** basta aggiungere un `?` alla fine del tipo. Ad esempio, `string?` rappresenta un tipo `string` nullable. È possibile usare questi nuovi tipi per esprimere più chiaramente le finalità della progettazione: alcune variabili *devono avere sempre un valore*, mentre in altre *un valore può mancare*.

In questa esercitazione si imparerà a:

> [!div class="checklist"]
> * Incorporare tipi riferimento nullable e non nullable nelle progettazioni.
> * Abilitare i controlli dei tipi riferimento nullable in tutto il codice.
> * Scrivere codice in cui il compilatore impone tali decisioni di progettazione.
> * Usare la funzionalità dei riferimenti nullable nelle proprie progettazioni.

## <a name="prerequisites"></a>Prerequisiti

È necessario configurare il computer per l'esecuzione di .NET Core, incluso il compilatore della versione beta di C# 8.0. Il compilatore della versione beta di C# 8 è disponibile con [Visual Studio 2019 Preview 1](https://visualstudio.microsoft.com/vs/preview/) o [.NET Core 3.0 Preview 1](https://dotnet.microsoft.com/download/dotnet-core/3.0).

Per questa esercitazione si presuppone che l'utente abbia familiarità con C# e .NET, inclusa l'interfaccia della riga di comando di .NET Core o Visual Studio.

## <a name="incorporate-nullable-reference-types-into-your-designs"></a>Incorporare tipi riferimento nullable nelle progettazioni

In questa esercitazione si compilerà una libreria che modella l'esecuzione di un sondaggio. Il codice usa tipi riferimento sia nullable che non nullable per rappresentare concetti reali. Le domande del sondaggio non possono mai essere Null. Un partecipante al sondaggio potrebbe preferire non rispondere a una domanda. In questo caso le risposte potrebbero essere Null.

Il codice scritto per questo esempio esprime questa intenzione e il compilatore la applica.

## <a name="create-the-application-and-enable-nullable-reference-types"></a>Creare l'applicazione e abilitare i tipi riferimento nullable

Creare una nuova applicazione console in Visual Studio oppure dalla riga di comando tramite `dotnet new console`. Assegnare all'applicazione il nome `NullableIntroduction`. Dopo aver creato l'applicazione, sarà necessario abilitare le funzionalità della versione beta di C# 8. Aprire il file `csproj` e aggiungere un elemento `LangVersion` all'elemento `PropertyGroup`:

```xml
<LangVersion>8.0</LangVersion>
```

In alternativa, è possibile usare le proprietà del progetto di Visual Studio per abilitare C# 8. In Esplora soluzioni fare clic con il pulsante destro del mouse sul nodo del progetto e scegliere **Proprietà**. Selezionare quindi la scheda **Compilazione** e fare clic su **Avanzate**. Nell'elenco a discesa relativo alla versione del linguaggio selezionare **C# 8.0 (beta)**.

È necessario acconsentire esplicitamente alle funzionalità dei **tipi riferimento nullable**, anche nei progetti C# 8. Questo perché dopo che la funzionalità viene attivata, le dichiarazioni di variabili di riferimento esistenti diventano **tipi riferimento non nullable**. Sebbene questa decisione contribuisca a individuare problemi laddove il codice esistente non disponga di adeguati controlli dei valori Null, potrebbe non rispecchiare esattamente le finalità originali della progettazione. La funzionalità viene attivata con una nuova direttiva pragma:

```csharp
#nullable enable
```

È possibile aggiungere questa direttiva pragma in un punto qualsiasi di un file di origine per attivare la funzionalità dei tipi riferimento nullable a partire da quel punto. La direttiva pragma supporta anche l'argomento `disable` per disattivare la funzionalità.

È anche possibile attivare i **tipi riferimento nullable** per un intero progetto aggiungendo l'elemento seguente al file con estensione csproj, ad esempio, immediatamente dopo l'elemento `LangVersion` che ha abilitato C# 8.0:

```xml
<NullableContextOptions>enable</NullableContextOptions>
```

### <a name="design-the-types-for-the-application"></a>Progettare i tipi per l'applicazione

Per questa applicazione di sondaggio è necessario creare alcune classi:

- Una classe che modella l'elenco di domande.
- Una classe che modella un elenco di persone contattate per il sondaggio.
- Una classe che modella le risposte di una persona che ha partecipato al sondaggio.

Questi tipi useranno tipi riferimento sia nullable sia non nullable per indicare i membri obbligatori e quelli facoltativi. I tipi riferimento nullable comunicano chiaramente questa finalità della progettazione:

- Le domande che fanno parte del sondaggio non possono mai essere Null: non ha senso porre una domanda vuota.
- I partecipanti al sondaggio non possono mai essere Null. Si vuole infatti tenere traccia delle persone che sono state contattate, anche quelle che non hanno accettato di partecipare.
- Una risposta a una domanda può essere Null. I partecipanti possono infatti rifiutarsi di rispondere ad alcune o a tutte le domande.

Se si ha esperienza di programmazione in C#, si potrebbe essere abituati a fare riferimento a tipi che ammettono valori Null al punto da non aver mai provato altre opportunità di dichiarare istanze non nullable:

- La raccolta delle domande deve essere non nullable.
- La raccolta dei partecipanti deve essere non nullable.

Durante la scrittura del codice, si noterà che l'uso di un tipo riferimento non nullable come impostazione predefinita per i riferimenti consente di evitare errori comuni che potrebbero generare eccezioni dovute a riferimenti Null. In questa esercitazione sono state prese decisioni in merito a quali variabili possono o non possono essere Null. Nelle versioni precedenti il linguaggio non forniva la sintassi necessaria per esprimere queste decisioni. Ora invece tutto questo è possibile.

L'app che si intende compilare eseguirà i passaggi seguenti:

1. Creare un sondaggio e aggiungervi domande.
1. Creare un insieme pseudo-casuale di partecipanti al sondaggio.
1. Contattare i partecipanti finché le dimensioni del sondaggio completato non raggiungono il numero prefissato.
1. Scrivere le statistiche importanti sulle risposte al sondaggio.

## <a name="build-the-survey-with-nullable-and-non-nullable-types"></a>Compilare il sondaggio con tipi nullable e non nullable

Il primo codice scritto crea il sondaggio. Occorre scrivere le classi necessarie per modellare una domanda del sondaggio e l'esecuzione del sondaggio. Il sondaggio include tre tipi di domande, distinti in base al formato della risposta: risposte Sì/No, risposte numeriche e risposte di testo. Creare una classe `public` `SurveyQuestion`. Includere la direttiva pragma `#nullable enable` subito dopo le istruzioni `using`:

```csharp
#nullable enable
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

L'aggiunta della direttiva pragma `#nullable enable` indica al compilatore di interpretare ogni dichiarazione di variabile del tipo riferimento come tipo riferimento **non-nullable**. È possibile vedere il primo avviso aggiungendo le proprietà del testo della domanda e il tipo di domanda, come illustrato nel codice seguente:

```csharp
#nullable enable
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

[!code-csharp[DefineQuestion](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyQuestion.cs)]

Aggiungendo il costruttore, l'avviso viene rimosso. Anche l'argomento del costruttore è un tipo riferimento non nullable, quindi il compilatore non genera alcun avviso.

Creare quindi una classe `public` denominata `SurveyRun`. Includere la direttiva `#nullable enable` dopo le istruzioni `using`. Questa classe contiene un elenco di metodi e oggetti `SurveyQuestion` per aggiungere domande al sondaggio, come illustrato nel codice seguente:

```csharp
using System.Collections.Generic;

#nullable enable
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

Passare a `Program.cs` nell'editor preferito e sostituire il contenuto di `Main` con le righe di codice seguenti:

[!code-csharp[AddQuestions](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

Senza la direttiva pragma `#nullable enable` all'inizio del file, il compilatore non genera un avviso quando si passa `null` come testo dell'argomento `AddQuestion`. Correggere il problema aggiungendo `#nullable enable` dopo l'istruzione `using`. Provare ad aggiungere la riga seguente a `Main`:

```csharp
surveyRun.AddQuestion(QuestionType.Text, default);
```

## <a name="create-respondents-and-get-answers-to-the-survey"></a>Creare i partecipanti e ottenere le risposte al sondaggio

A questo punto occorre scrivere il codice che genera le risposte al sondaggio. A tale scopo è necessario eseguire alcune piccole attività:

1. Compilare un metodo che generi gli oggetti partecipante. Questi oggetti rappresentano le persone a cui è stato chiesto di completare il sondaggio.
1. Creare la logica per simulare la formulazione delle domande a un partecipante e la raccolta delle risposte oppure di nessun dato, se il partecipante non ha risposto.
1. Ripetere finché non ha risposto al sondaggio un numero sufficiente di partecipanti.

A questo punto occorre aggiungere una classe che rappresenti una risposta al sondaggio. Abilitare il supporto dei tipi riferimento nullable. Aggiungere una proprietà `Id` e un costruttore che la inizializza, come illustrato nel codice seguente:

```csharp
#nullable enable
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

[!code-csharp[GenerateRespondents](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#Random)]

La responsabilità principale di questa classe è generare le risposte di un partecipante alle domande del sondaggio. A questo scopo è necessario eseguire i passaggi seguenti:

1. Chiedere di partecipare al sondaggio. Se la persona non acconsente, restituire una risposta mancante (o Null).
1. Porre ogni domanda e registrare la risposta. Ogni risposta può anche essere mancante (o Null).

Aggiungere il codice seguente alla classe `SurveyResponse`:

[!code-csharp[AnswerSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#AnswerSurvey)]

L'archivio per le risposte del sondaggio è un `Dictionary<int, string>?`, a indicare che può essere Null. Si sta usando la nuova funzionalità del linguaggio per dichiarare la finalità della progettazione, sia al compilatore che a chiunque legga il codice successivamente. Se si dereferenzia `surveyResponses` senza prima verificare la presenza del valore Null, si riceve un avviso del compilatore. Non si riceve un avviso nel metodo `AnswerSurvey` perché il compilatore è in grado di determinare che la variabile `surveyResponses` è stata impostata su un valore non Null.

A questo punto occorre scrivere il metodo `PerformSurvey` nella classe `SurveyRun`. Aggiungere il codice seguente nella classe `SurveyRun`:

[!code-csharp[PerformSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

Anche in questo caso la scelta di un `List<SurveyResponse>?` nullable indica che la risposta può essere Null. Indica che il sondaggio non è ancora stato distribuito ad alcun partecipante. Si noti che i partecipanti continuano a essere aggiunti finché non acconsente un numero sufficiente.

L'ultimo passaggio dell'esecuzione del sondaggio consiste nell'aggiungere una chiamata per eseguire il sondaggio alla fine del metodo `Main`:

[!code-csharp[RunSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a>Esaminare le risposte al sondaggio

L'ultimo passaggio è la visualizzazione dei risultati del sondaggio. Occorre aggiungere codice a molte delle classi scritte. Questo codice dimostra il valore della distinzione fra i tipi riferimento nullable e non nullable. Per iniziare, aggiungere i due membri con corpo di espressione seguenti alla classe `SurveyResponse`:

[!code-csharp[ReportResponses](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

Poiché `surveyResponses` è un tipo riferimento non nullable, non è necessario eseguire alcun controllo del tipo prima di dereferenziarlo. Il metodo `Answer` restituisce una stringa non nullable, quindi scegliere l'overload di `GetValueOrDefault` che accetta un secondo argomento come valore predefinito.

Aggiungere quindi questi tre membri con corpo di espressione alla classe `SurveyRun`:

[!code-csharp[ReportResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#RunReport)]

Il membro `AllParticipants` deve tenere conto del fatto che la variabile `respondents` potrebbe essere Null, ma il valore restituito non può essere Null. Se si modifica l'espressione rimuovendo `??` e la sequenza vuota che segue, il compilatore avvisa che il metodo potrebbe restituire `null` e la sua firma restituita restituisce un tipo non nullable.

Infine, aggiungere il ciclo seguente alla fine del metodo `Main`:

[!code-csharp[DisplaySurveyResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#WriteAnswers)]

Non è necessario eseguire alcun controllo dei valori `null` in questo codice perché le interfacce sottostanti sono state progettate in modo che restituiscano tutte tipi di riferimento non nullable.

## <a name="get-the-code"></a>Ottenere il codice

Il codice dell'esercitazione completata è disponibile nel repository [samples](https://github.com/dotnet/samples) nella cartella [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction).

È possibile fare delle prove cambiando le dichiarazioni di tipo fra tipi riferimento nullable e non nullable e osservare come vengono generati avvisi diversi per assicurare che non venga dereferenziato accidentalmente un valore `null`.

## <a name="next-steps"></a>Passaggi successivi

Per altre informazioni, leggere una panoramica dei tipi riferimento nullable.
> [!div class="nextstepaction"]
> [Panoramica dei riferimenti nullable](../nullable-references.md)
