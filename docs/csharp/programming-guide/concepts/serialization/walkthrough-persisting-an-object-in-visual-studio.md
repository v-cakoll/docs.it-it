---
title: 'Procedura dettagliata: Persistenza di un oggetto tramite C#'
ms.date: 04/26/2018
ms.openlocfilehash: 85c5d1b711180eda5734d5860d996242c6bc89d1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167570"
---
# <a name="walkthrough-persisting-an-object-using-c"></a>Procedura dettagliata: Persistenza di un oggetto tramite C\#

È possibile usare la serializzazione per rendere persistenti i dati di un oggetto tra le istanze, consentendo di archiviare i valori e di recuperarli alla successiva creazione di un'istanza dell'oggetto.

In questa procedura verrà creato un oggetto `Loan` di base i cui dati verranno resi persistenti in un file. I dati verranno quindi recuperati dal file quando si ricrea l'oggetto.

> [!IMPORTANT]
> Questo esempio crea un nuovo file se il file non esiste già. Se un'applicazione deve creare un file, tale applicazione deve avere l'autorizzazione `Create` per la cartella. Le autorizzazioni vengono impostate usando gli elenchi di controllo di accesso. Se il file esiste già, per l'applicazione è necessaria solo l'autorizzazione `Write`, di livello inferiore. Se possibile, è più sicuro creare il file durante la distribuzione e concedere solo autorizzazioni `Read` per un singolo file, anziché autorizzazioni Create per una cartella. È anche più sicuro scrivere i dati nelle cartelle utente anziché nella cartella radice o nella cartella Programmi.

> [!IMPORTANT]
> In questo esempio i dati vengono archiviati in un file in formato binario. Non usare questi formati per i dati riservati, ad esempio password o informazioni sulla carta di credito.

## <a name="prerequisites"></a>Prerequisites

- Per consentire la compilazione e l'esecuzione, installare [.NET Core SDK](https://dotnet.microsoft.com/download).

- Installare l'editor del codice preferito, se non è già disponibile.

> [!TIP]
> È necessario installare un editor del codice? Provare [Visual Studio](https://visualstudio.com/downloads).

- L'esempio richiede C# 7.3. Vedere [Selezionare la versione del linguaggio C#](../../../language-reference/configure-language-version.md)

È possibile esaminare il codice di esempio online [nel repository GitHub degli esempi .NET](https://github.com/dotnet/samples/tree/master/csharp/serialization).

## <a name="creating-the-loan-object"></a>Creazione dell'oggetto Loan

Il primo passaggio consiste nel creare una classe `Loan` e un'applicazione console che usa la classe:

1. Creare una nuova applicazione. Digitare `dotnet new console -o serialization` per creare una nuova applicazione console in una sottodirectory denominata `serialization`.
1. Aprire l'applicazione nell'editor e aggiungere una nuova classe denominata `Loan.cs`.
1. Aggiungere il codice seguente alla classe `Loan`:

[!code-csharp[Loan class definition](../../../../../samples/snippets/csharp/serialization/Loan.cs#1)]

Sarà anche necessario creare un'applicazione che usi la classe `Loan`.

## <a name="serialize-the-loan-object"></a>Serializzare l'oggetto Loan

1. Aprire `Program.cs`. Aggiungere il codice seguente:

[!code-csharp[Create a loan object](../../../../../samples/snippets/csharp/serialization/Program.cs#1)]

Aggiungere un gestore per l'evento `PropertyChanged` e alcune righe per modificare l'oggetto `Loan` e visualizzare le modifiche. Le aggiunte sono presenti nel codice seguente:

[!code-csharp[Listening for the PropertyChanged event](../../../../../samples/snippets/csharp/serialization/Program.cs#2)]

A questo punto è possibile eseguire il codice e visualizzare l'output corrente:

```console
New customer value: Henry Clay
7.5
7.1
```

Se si esegue ripetutamente questa applicazione, vengono scritti sempre gli stessi valori. Un nuovo oggetto Loan viene creato ogni volta che si esegue il programma. Nel mondo reale i tassi di interesse variano periodicamente, ma non necessariamente ogni volta che l'applicazione viene eseguita. Il codice di serializzazione consente di mantenere il tasso di interesse più recente tra istanze diverse dell'applicazione. Nel passaggio successivo verrà eseguita questa operazione, aggiungendo la serializzazione alla classe Loan.

## <a name="using-serialization-to-persist-the-object"></a>Usare la serializzazione per la persistenza dell'oggetto

Per rendere persistenti i valori per la classe Loan, per prima cosa contrassegnare la classe con l'attributo `Serializable`. Aggiungere il codice riportato di seguito prima della dichiarazione della classe Loan:

[!code-csharp[Loan class definition](../../../../../samples/snippets/csharp/serialization/Loan.cs#2)]

<xref:System.SerializableAttribute> indica al compilatore che tutti gli elementi nella classe possono essere resi persistenti in un file. Poiché l'evento `PropertyChanged` non rappresenta una parte dell'oggetto grafico che deve essere archiviata, non deve essere serializzato. La serializzazione interesserebbe infatti tutti gli oggetti associati all'evento. È possibile aggiungere <xref:System.NonSerializedAttribute> alla dichiarazione di campo per il gestore dell'evento `PropertyChanged`.

[!code-csharp[Disable serialization for the event handler](../../../../../samples/snippets/csharp/serialization/Loan.cs#3)]

A partire da C# 7.3, è possibile collegare attributi al campo sottostante di una proprietà implementata automaticamente usando il valore di destinazione `field`. Il codice seguente aggiunge la proprietà `TimeLastLoaded` e la contrassegna come non serializzabile:

[!code-csharp[Disable serialization for an auto-implemented property](../../../../../samples/snippets/csharp/serialization/Loan.cs#4)]

Il passaggio successivo consiste nell'aggiungere il codice di serializzazione all'applicazione LoanApp. Per serializzare la classe e scriverla in un file, si usano gli spazi dei nomi <xref:System.IO> e <xref:System.Runtime.Serialization.Formatters.Binary>. Per evitare di digitare i nomi completi, è possibile aggiungere riferimenti agli spazi dei nomi necessari, come illustrato nel codice seguente:

[!code-csharp[Adding namespaces for serialization](../../../../../samples/snippets/csharp/serialization/Program.cs#3)]

Il passaggio successivo consiste nell'aggiungere codice per deserializzare l'oggetto dal file quando viene creato l'oggetto. Aggiungere una costante alla classe per il nome del file di dati serializzati, come illustrato nel codice seguente:

[!code-csharp[Define the name of the saved file](../../../../../samples/snippets/csharp/serialization/Program.cs#4)]

Aggiungere quindi il codice seguente dopo la riga che crea l'oggetto `TestLoan`:

[!code-csharp[Read from a file if it exists](../../../../../samples/snippets/csharp/serialization/Program.cs#5)]

È prima necessario verificare che il file esista. Se esiste, creare una classe <xref:System.IO.Stream> per leggere il file binario e una classe <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> per convertire il file. È anche necessario eseguire la conversione dal tipo di flusso al tipo di oggetto Loan.

È quindi necessario aggiungere codice per serializzare la classe in un file. Aggiungere il codice seguente dopo il codice esistente nel metodo `Main`:

[!code-csharp[Save the existing Loan object](../../../../../samples/snippets/csharp/serialization/Program.cs#6)]

A questo punto, è nuovamente possibile compilare ed eseguire l'applicazione. Si noti che, la prima volta che viene eseguita, il tasso di interesse inizia a 7,5 e quindi passa a 7,1. Chiudere l'applicazione ed eseguirla nuovamente. A questo punto, l'applicazione stampa un messaggio che comunica l'avvenuta lettura del file salvato e che il tasso di interesse corrisponde a 7,1 anche prima del codice che lo modifica.

## <a name="see-also"></a>Vedere anche

- [Serializzazione (C#)](index.md)
- [Guida per programmatori C#](../..//index.md)
