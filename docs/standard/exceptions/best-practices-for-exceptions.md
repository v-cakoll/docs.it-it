---
title: Procedure consigliate per le eccezioni - .NET
ms.date: 12/05/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
ms.openlocfilehash: 1de231b01e3fa97e78a87ae6b0595a9b5536374e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160170"
---
# <a name="best-practices-for-exceptions"></a>Procedure consigliate per le eccezioni

Un'applicazione progettata correttamente gestisce eccezioni ed errori per impedire arresti anomali dell'applicazione. Questa sezione descrive le procedure consigliate per la gestione e la creazione di eccezioni.

## <a name="use-trycatchfinally-blocks-to-recover-from-errors-or-release-resources"></a>Usare blocchi try/catch/finally per correggere errori o rilasciare risorse

Usare i blocchi `try`/`catch` intorno al codice che può potenzialmente generare un'eccezione ***and*** che il codice non può correggere. Nei blocchi `catch` ordinare sempre le eccezioni dalla più derivata alla meno derivata. Tutte le eccezioni derivano da <xref:System.Exception>. Le eccezioni più derivate non vengono gestite da una clausola catch preceduta da una clausola catch per una classe di eccezione di base. Quando il codice non corregge un'eccezione, non recuperare l'eccezione. Abilitare i metodi nella parte superiore dello stack di chiamata per eseguire il ripristino, se possibile.

Pulire le risorse allocate con istruzioni `using` o blocchi `finally`. Preferire le istruzioni `using` per pulire automaticamente le risorse quando vengono generate eccezioni. Usare i blocchi `finally` per pulire le risorse che non implementano <xref:System.IDisposable>. Il codice in una clausola `finally` viene quasi sempre eseguito anche se vengono generate eccezioni.

## <a name="handle-common-conditions-without-throwing-exceptions"></a>Gestire le condizioni comuni senza generare eccezioni

È consigliabile gestire le condizioni che potrebbero verificarsi ma potrebbero generare un'eccezione in modo da evitare l'eccezione. Ad esempio, se si tenta di chiudere una connessione già chiusa, si otterrà `InvalidOperationException`. Per impedire che ciò accada, usare un'istruzione `if` per verificare lo stato della connessione prima di tentare di chiuderla.

[!code-cpp[Conceptual.Exception.Handling#2](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]

Se prima della chiusura non viene verificato lo stato della connessione, è possibile rilevare l'eccezione `InvalidOperationException`.

[!code-cpp[Conceptual.Exception.Handling#3](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]

Nella scelta del metodo è necessario considerare la frequenza con cui si prevede che l'evento possa verificarsi.

- Usare la gestione delle eccezioni se l'evento non si verifica molto spesso, ovvero, se l'evento è davvero eccezionale e indica un errore quale la fine imprevista di un file. Quando si utilizza la gestione delle eccezioni, una minore quantità di codice viene eseguita in condizioni normali.

- Ricercare le condizioni di errore nel codice se l'evento si verifica ripetutamente e può essere considerato parte dell'esecuzione normale. Quando si ricercano le condizioni di errore comuni, viene eseguita una minore quantità di codice poiché vengono evitate le eccezioni.

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a>Progettare le classi in modo da evitare le eccezioni

Una classe può offrire metodi o proprietà che consentono di evitare di effettuare una chiamata che potrebbe generare un'eccezione. Con la classe <xref:System.IO.FileStream>, ad esempio, sono disponibili metodi che consentono di determinare se è stata raggiunta la fine del file. I metodi possono essere usati per evitare l'eccezione che verrebbe generata se si continua la lettura oltre la fine del file. L'esempio seguente illustra come continuare la lettura fino alla fine di un file senza generare un'eccezione.

[!code-cpp[Conceptual.Exception.Handling#5](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]

Un altro modo per evitare le eccezioni consiste nel restituire Null (o default) per i casi di errore estremamente comuni, invece di generare un'eccezione. Un caso di errore estremamente comune può essere considerato come un normale flusso di controllo. Restituendo Null (o default) in questi casi, si riduce al minimo l'impatto sulle prestazioni di un'app.

Per i tipi di valore, la scelta tra `Nullable<T>` o default come indicatore di errore è un aspetto da considerare in relazione all'app specifica. Usando `Nullable<Guid>`, `default` diventa `null` invece di `Guid.Empty`. Talvolta, l'aggiunta di `Nullable<T>` può indicare più chiaramente quando un valore è presente o assente. Altre volte, l'aggiunta di `Nullable<T>` può creare casi aggiuntivi da controllare che non sono necessari e serve solo per creare potenziali fonti di errore.

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a>Generare eccezioni anziché restituire un codice di errore

Le eccezioni garantiscono il rilevamento degli errori quando il codice chiamante non rileva un codice restituito.

## <a name="use-the-predefined-net-exception-types"></a>Usare i tipi di eccezione .NET predefiniti

Introdurre una nuova classe di eccezioni solo quando non è possibile applicare una classe predefinita. Ad esempio:

- Generare un'eccezione <xref:System.InvalidOperationException> se un set di proprietà o una chiamata al metodo non è adatta allo stato corrente dell'oggetto.

- Generare un'eccezione <xref:System.ArgumentException> una delle classi predefinite che derivano da <xref:System.ArgumentException> se vengono passati parametri non validi.

## <a name="end-exception-class-names-with-the-word-exception"></a>Terminare i nomi delle classi di eccezioni con la parola `Exception`

Quando è necessaria un'eccezione personalizzata, assegnare un nome appropriato all'eccezione e derivarla dalla classe <xref:System.Exception>. Ad esempio:

[!code-cpp[Conceptual.Exception.Handling#4](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]

## <a name="include-three-constructors-in-custom-exception-classes"></a>Inserire tre costruttori nelle classi di eccezioni personalizzate

Usare almeno i tre costruttori comuni quando si creano classi di eccezione personalizzate: il costruttore senza parametri, un costruttore che accetta un messaggio stringa e un costruttore che accetta un messaggio stringa e un'eccezione interna.

- <xref:System.Exception.%23ctor>, che usa valori predefiniti.

- <xref:System.Exception.%23ctor%28System.String%29>, che accetta un messaggio stringa.

- <xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, che accetta un messaggio stringa e un'eccezione interna.

Per un esempio, vedere [Procedura: Creare eccezioni definite dall'utente](how-to-create-user-defined-exceptions.md).

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a>Garantire la disponibilità dei dati dell'eccezione per il codice eseguito in modalità remota

Quando si creano eccezioni definite dall'utente, garantire che i metadati relativi alle eccezioni siano disponibili per il codice eseguito in modalità remota.

Ad esempio, nelle implementazioni .NET che supportano domini app, è possibile che si verifichino eccezioni nei domini app. Si supponga che il dominio app A crei il dominio app B che esegue codice che genera un'eccezione. Per rilevare e gestire correttamente l'eccezione è necessario che il dominio app A sia in grado di individuare l'assembly contenente l'eccezione generata dal dominio app B. Se il dominio app B genera un'eccezione contenuta in un assembly nella relativa base dell'applicazione ma non nella base dell'applicazione del dominio app A, il dominio app A non sarà in grado di individuare l'eccezione e Common Language Runtime genererà un'eccezione <xref:System.IO.FileNotFoundException>. Per evitare che questo si verifichi è possibile distribuire l'assembly contenente le informazioni sull'eccezione in due modi:

- Inserendo l'assembly in una base applicativa comune condivisa da entrambi i domini applicazione

    \- - oppure -

- Se i domini non condividono alcuna base applicativa comune, firmando l'assembly contenente le informazioni sull'eccezione con un nome sicuro e distribuendo tale assembly nella Global Assembly Cache.

## <a name="use-grammatically-correct-error-messages"></a>Usare messaggi di errore grammaticalmente corretti

Scrivere frasi chiare e includere la punteggiatura finale. Ogni frase della stringa assegnata alla proprietà <xref:System.Exception.Message?displayProperty=nameWithType> deve terminare con un punto. Ad esempio, "Overflow della tabella del log." è una stringa del messaggio corretta.

## <a name="include-a-localized-string-message-in-every-exception"></a>Includere in ogni eccezione un messaggio stringa localizzato

Il messaggio di errore visualizzato all'utente è derivato dalla proprietà <xref:System.Exception.Message?displayProperty=nameWithType> dell'eccezione generata e non dal nome della classe di eccezione. In genere, si assegna un valore alla proprietà <xref:System.Exception.Message?displayProperty=nameWithType> passando la stringa del messaggio all'argomento `message` di un [costruttore di eccezione](xref:System.Exception.%23ctor%2A).

Per le applicazioni localizzate, è necessario specificare una stringa di messaggio localizzata per ogni eccezione che può essere generata dall'applicazione. Usare i file di risorse per specificare i messaggi di errore localizzati. Per informazioni sulla localizzazione di applicazioni e il recupero di stringhe localizzate, vedere gli articoli seguenti:For information on localizing applications and retrieving localized strings, see the following articles:

- [Procedura: Creare eccezioni definite dall'utente con messaggi di eccezione localizzati](how-to-create-localized-exception-messages.md)
- [Risorse nelle applicazioni desktop](../../framework/resources/index.md)
- <xref:System.Resources.ResourceManager?displayProperty=nameWithType>

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a>Nelle eccezioni personalizzate specificare le proprietà aggiuntive necessarie

Specificare le proprietà aggiuntive di un'eccezione (oltre alla stringa del messaggio personalizzata) solo in un contesto di codice in cui è utile avere a disposizione altre informazioni. Ad esempio, <xref:System.IO.FileNotFoundException> fornisce la proprietà <xref:System.IO.FileNotFoundException.FileName>.

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a>Inserire istruzioni throw in modo che l'analisi dello stack risulti utile

La traccia dello stack inizia in corrispondenza dell'istruzione in cui l'eccezione viene generata e termina in corrispondenza dell'istruzione `catch` che intercetta l'eccezione.

## <a name="use-exception-builder-methods"></a>Usare metodi per la creazione di eccezioni

Una classe genera spesso la stessa eccezione da punti diversi dell'implementazione. Per evitare codice di dimensioni eccessive, utilizzare metodi di supporto che creano l'eccezione e la restituiscono. Ad esempio:

[!code-cpp[Conceptual.Exception.Handling#6](~/samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]

In alcuni casi è preferibile usare il costruttore dell'eccezione per compilare l'eccezione. Un esempio è una classe di eccezioni globali, ad esempio <xref:System.ArgumentException>.

## <a name="restore-state-when-methods-dont-complete-due-to-exceptions"></a>Ripristinare lo stato quando i metodi non sono completi a causa di eccezioni

I chiamanti dovrebbero avere la garanzia che non si verifichino effetti secondari quando un'eccezione viene generata da un metodo. Ad esempio, se è presente un codice che trasferisce denaro prelevandolo da un conto e depositandolo in un altro conto e viene generata un'eccezione durante l'esecuzione del deposito, non si desidera che il prelievo rimanga attivo.

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect.
    to.Deposit(amount);
}
```

```vb
Public Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    from.Withdrawal(amount)
    ' If the deposit fails, the withdrawal shouldn't remain in effect.
    [to].Deposit(amount)
End Sub
```

Il metodo riportato sopra non genera direttamente eccezioni, ma deve essere scritto a scopo difensivo in modo tale che se l'operazione di deposito non riesce, il prelievo venga respinto.

Un modo per gestire questa situazione consiste nel rilevare eventuali eccezioni generate dalla transazione di deposito e annullare il prelievo.

```csharp
private static void TransferFunds(Account from, Account to, decimal amount)
{
    string withdrawalTrxID = from.Withdrawal(amount);
    try
    {
        to.Deposit(amount);
    }
    catch
    {
        from.RollbackTransaction(withdrawalTrxID);
        throw;
    }
}
```

```vb
Private Shared Sub TransferFunds(from As Account, [to] As Account, amount As Decimal)
    Dim withdrawalTrxID As String = from.Withdrawal(amount)
    Try
        [to].Deposit(amount)
    Catch
        from.RollbackTransaction(withdrawalTrxID)
        Throw
    End Try
End Sub
```

Questo esempio illustra l'uso di `throw` per generare nuovamente l'eccezione originale rendendo in questo modo più semplice per i chiamanti visualizzare la causa effettiva del problema senza dover esaminare la proprietà <xref:System.Exception.InnerException>. In alternativa è possibile generare una nuova eccezione e includere l'eccezione originale come eccezione interna:

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new TransferFundsException("Withdrawal failed.", innerException: ex)
    {
        From = from,
        To = to,
        Amount = amount
    };
}
```

```vb
Catch ex As Exception
    from.RollbackTransaction(withdrawalTrxID)
    Throw New TransferFundsException("Withdrawal failed.", innerException:=ex) With
    {
        .From = from,
        .[To] = [to],
        .Amount = amount
    }
End Try
```

## <a name="see-also"></a>Vedere anche

- [Eccezioni](index.md)
