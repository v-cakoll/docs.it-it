---
title: Implementazione di una transazione implicita utilizzando l'ambito di transazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d1706a-1e0c-4c85-9704-75c908372eb9
ms.openlocfilehash: 33b51cf26a35bbdda70582d86db6ac39c22597da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174394"
---
# <a name="implementing-an-implicit-transaction-using-transaction-scope"></a>Implementazione di una transazione implicita utilizzando l'ambito di transazione
La classe <xref:System.Transactions.TransactionScope> consente di contrassegnare facilmente un blocco di codice come ambito partecipante a una transazione, senza che sia necessario interagire con la transazione stessa. Un ambito di transazione può selezionare e gestire automaticamente la transazione di ambiente. In quanto efficiente e di facile utilizzo, la classe <xref:System.Transactions.TransactionScope> rappresenta la scelta ideale per sviluppare un'applicazione transazionale.  
  
 Tale classe consente inoltre di eliminare la necessità di integrare esplicitamente le risorse nella transazione. Qualsiasi gestore di risorse dello spazio dei nomi <xref:System.Transactions> (ad esempio SQL Server 2005) è in grado di rilevare l'esistenza di una transazione di ambiente creata dall'ambito e quindi integrarsi automaticamente in tale transazione.  
  
## <a name="creating-a-transaction-scope"></a>Creazione di un ambito di transazione  
 Nell'esempio seguente viene illustrato un utilizzo semplificato della classe <xref:System.Transactions.TransactionScope>.  
  
 [!code-csharp[TransactionScope#1](../../../../samples/snippets/csharp/VS_Snippets_Remoting/TransactionScope/cs/ScopeWithSQL.cs#1)]
 [!code-vb[TransactionScope#1](../../../../samples/snippets/visualbasic/VS_Snippets_Remoting/TransactionScope/vb/ScopeWithSQL.vb#1)]  
  
 L'ambito di transazione viene avviato non appena si crea un nuovo oggetto <xref:System.Transactions.TransactionScope>.  Come illustrato nell'esempio di codice, è consigliabile `using` creare ambiti con un'istruzione. L'istruzione `using` è disponibile sia in C , e `try`in Visual Basic, e funziona come un ... `finally` per garantire che l'ambito venga eliminato correttamente.  
  
 Quando si crea un'istanza di <xref:System.Transactions.TransactionScope>, la gestione transazioni determina la transazione a cui partecipare. Una volta deciso, l'ambito partecipa sempre a quella transazione. La decisione si basa su due fattori: la presenza di una transazione di ambiente e il valore del parametro `TransactionScopeOption` del costruttore. La transazione di ambiente è la transazione in cui il codice viene eseguito. Per ottenere un riferimento a questa transazione è possibile chiamare la proprietà <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> statica della classe <xref:System.Transactions.Transaction>. Per altre informazioni sull'utilizzo di questo parametro, vedere la sezione Gestione del flusso di [transazioni tramite TransactionScopeOption](#ManageTxFlow) di questo argomento.  
  
## <a name="completing-a-transaction-scope"></a>Completamento di un ambito di transazione  
 Quando in una determinata applicazione vengono completate tutte le operazioni che si desidera eseguire in una transazione, è necessario chiamare una sola volta il metodo <xref:System.Transactions.TransactionScope.Complete%2A?displayProperty=nameWIthType> per informare la gestione transazioni che può essere eseguito il commit della transazione. È molto buona norma inserire <xref:System.Transactions.TransactionScope.Complete%2A> la chiamata a `using` come ultima istruzione nel blocco.  
  
 La mancata chiamata di questo metodo interrompe la transazione, perché il gestore delle transazioni interpreta questa operazione come un errore di sistema o equivalente a un'eccezione generata nell'ambito della transazione. Tuttavia, chiamare questo metodo non garantisce l'esecuzione del commit della transazione. Si tratta semplicemente di un modo per passare alla gestione transazioni le informazioni sullo stato. Dopo aver chiamato il metodo <xref:System.Transactions.TransactionScope.Complete%2A> non è più consentito utilizzare la proprietà <xref:System.Transactions.Transaction.Current%2A> per accedere alla transazione di ambiente. Se si ignora tale restrizione, il sistema genera un'eccezione.  
  
 Se <xref:System.Transactions.TransactionScope> l'oggetto ha creato inizialmente la transazione, il lavoro effettivo di commit della `using` transazione da parte del gestore delle transazioni si verifica dopo l'ultima riga di codice nel blocco. In caso contrario, il commit viene eseguito ogni volta che il metodo <xref:System.Transactions.CommittableTransaction.Commit%2A> viene chiamato dal proprietario dell'oggetto <xref:System.Transactions.CommittableTransaction>. A questo punto il gestore delle transazioni chiama i gestori delle <xref:System.Transactions.TransactionScope.Complete%2A> risorse e <xref:System.Transactions.TransactionScope> li informa di eseguire il commit o il rollback, a seconda che il metodo sia stato chiamato sull'oggetto.  
  
 L'istruzione `using` assicura <xref:System.Transactions.TransactionScope.Dispose%2A> che il <xref:System.Transactions.TransactionScope> metodo dell'oggetto venga chiamato anche se si verifica un'eccezione. Il metodo <xref:System.Transactions.TransactionScope.Dispose%2A> indica la fine dell'ambito della transazione. Le eccezioni che si verificano dopo la chiamata a questo metodo potrebbero non avere alcun effetto sulla transazione. Questo metodo consente inoltre di ripristinare lo stato precedente della transazione di ambiente.  
  
 Se l'ambito crea la transazione e quest'ultima viene interrotta, viene generata un'eccezione <xref:System.Transactions.TransactionAbortedException>. Se la gestione transazioni non è in grado di prendere una decisione in merito al commit, viene generata un'eccezione <xref:System.Transactions.TransactionInDoubtException>. Se viene eseguito il commit della transazione, non viene generata alcuna eccezione.  
  
## <a name="rolling-back-a-transaction"></a>Rollback di una transazione  
 Non è consigliabile chiamare il metodo <xref:System.Transactions.TransactionScope.Complete%2A> all'interno dell'ambito di una determinata transazione allo scopo di eseguirne il rollback. Ad esempio, è preferibile generare un'eccezione all'interno dell'ambito. In tal caso, verrà eseguito il rollback della transazione a cui tale ambito partecipa.  
  
## <a name="managing-transaction-flow-using-transactionscopeoption"></a><a name="ManageTxFlow"></a>Gestione del flusso delle transazioni tramite TransactionScopeOptionManaging transaction flow using TransactionScopeOption  
 Gli ambiti di transazione possono essere annidati chiamando un metodo che utilizza un oggetto <xref:System.Transactions.TransactionScope> dall'interno di un metodo dotato di un proprio ambito, come nel caso del metodo `RootMethod` illustrato nell'esempio seguente  
  
```csharp  
void RootMethod()
{
    using(TransactionScope scope = new TransactionScope())
    {
        /* Perform transactional work here */
        SomeMethod();
        scope.Complete();
    }
}

void SomeMethod()
{
    using(TransactionScope scope = new TransactionScope())
    {
        /* Perform transactional work here */
        scope.Complete();
    }
}
```  
  
 L'ambito di transazione superiore viene detto ambito radice.  
  
 La classe <xref:System.Transactions.TransactionScope> fornisce diversi overload di costruttori che accettano un'enumerazione di tipo <xref:System.Transactions.TransactionScopeOption> che definisce il comportamento transazionale dell'ambito.  
  
 Per gli oggetti <xref:System.Transactions.TransactionScope> sono disponibili tre opzioni:  
  
- Aggiungersi alla transazione di ambiente, se presente, oppure crearne una nuova.  
  
- Essere un nuovo ambito radice, ovvero avviare una nuova transazione e definire tale transazione come una nuova transazione di ambiente contenuta all'interno del proprio ambito.  
  
- Non partecipare ad alcuna transazione. In questo caso non viene creata alcuna transazione di ambiente.  
  
 Se l'ambito viene istanziato con l'opzione <xref:System.Transactions.TransactionScopeOption.Required> ed è presente una transazione di ambiente, l'ambito si aggiunge a tale transazione. Se invece non è presente alcuna transazione di ambiente, l'ambito crea una nuova transazione e diventa l'ambito radice. Si tratta del valore predefinito. Quando si utilizza l'opzione <xref:System.Transactions.TransactionScopeOption.Required>, l'ambito deve presentare lo stesso comportamento sia che rappresenti l'ambito radice sia che si aggiunga alla transazione di ambiente esistente.  
  
 Se l'ambito viene istanziato con l'opzione <xref:System.Transactions.TransactionScopeOption.RequiresNew>, tale ambito rappresenta sempre l'ambito radice. A tale scopo, avvia una nuova transazione che definisce come una nuova transazione di ambiente all'interno del proprio ambito.  
  
 Se l'ambito viene istanziato con l'opzione <xref:System.Transactions.TransactionScopeOption.Suppress>, tale ambito non partecipa ad alcuna transazione, indipendentemente dalla presenza di una transazione di ambito. Un ambito di cui è `null` stata creata un'istanza con questo valore sempre come transazione di ambiente.  
  
 La tabella seguente contiene un riepilogo delle opzioni appena elencate.  
  
|TransactionScopeOption|Transazione di ambiente|Transazione a cui partecipa l'ambito|  
|----------------------------|-------------------------|-----------------------------|  
|Obbligatoria|No|Nuova transazione (sarà la radice)|  
|RequiresNew|No|Nuova transazione (sarà la radice)|  
|Elimina|No|Nessuna transazione|  
|Obbligatoria|Sì|Transazione di ambiente|  
|RequiresNew|Sì|Nuova transazione (sarà la radice)|  
|Elimina|Sì|Nessuna transazione|  
  
 Quando un oggetto <xref:System.Transactions.TransactionScope> si aggiunge a una transazione di ambiente esistente, è possibile che l'eliminazione dell'ambito non comporti il termine della transazione, a meno che quest'ultima non venga interrotta dall'ambito. Se la transazione di ambiente è stata creata da un ambito radice, il metodo <xref:System.Transactions.CommittableTransaction.Commit%2A> viene chiamato sulla transazione solo quando l'ambito radice viene eliminato. Se la transazione è stata creata manualmente, la transazione termina quando il suo creatore la interrompe o ne esegue il commit.  
  
 Nell'esempio seguente viene mostrato un oggetto <xref:System.Transactions.TransactionScope> che crea tre oggetti ambito annidati, ognuno istanziato con un valore distinto dell'enumerazione <xref:System.Transactions.TransactionScopeOption>.  
  
```csharp  
using(TransactionScope scope1 = new TransactionScope())
//Default is Required
{
    using(TransactionScope scope2 = new TransactionScope(TransactionScopeOption.Required))
    {
        //...
    }

    using(TransactionScope scope3 = new TransactionScope(TransactionScopeOption.RequiresNew))
    {
        //...  
    }
  
    using(TransactionScope scope4 = new TransactionScope(TransactionScopeOption.Suppress))
    {
        //...  
    }
}
```  
  
 L'esempio mostra un blocco di codice in cui non esiste alcuna transazione di ambiente che crea un nuovo ambito (`scope1`) con l'opzione <xref:System.Transactions.TransactionScopeOption.Required>. L'ambito `scope1` è un ambito radice in quanto crea una nuova transazione (Transazione A) che definisce come transazione di ambiente. In `Scope1` quindi vengono creati tre nuovi oggetti, ciascuno con un valore diverso di <xref:System.Transactions.TransactionScopeOption>. Ad esempio, l'ambito `scope2` viene creato con l'opzione <xref:System.Transactions.TransactionScopeOption.Required> e, poiché esiste una transazione di ambiente, si aggiunge alla prima transazione creata dall'ambito `scope1`. Si noti che l'ambito `scope3` è l'ambito radice di una nuova transazione e che l'ambito `scope4` è privo di transazione di ambiente.  
  
 Benché il valore predefinito e più comunemente utilizzato dell'enumerazione <xref:System.Transactions.TransactionScopeOption> sia l'opzione <xref:System.Transactions.TransactionScopeOption.Required>, ognuno degli altri valori presenta uno scopo specifico.  

### <a name="non-transactional-code-inside-a-transaction-scope"></a>Codice non transazionale all'interno di un ambito di transazione

 L'opzione <xref:System.Transactions.TransactionScopeOption.Suppress> è utile quando si desidera preservare le operazioni eseguite dalla sezione di codice e non si desidera interrompere la transazione di ambiente se le operazioni hanno esito negativo. Ad esempio, questa opzione è utile quando si desidera eseguire operazioni di registrazione o di controllo, o quando si desidera pubblicare eventi agli iscritti, sia che la transazione di ambiente venga interrotta sia che ne venga eseguito il commit. Questo valore consente di includere una sezione di codice non transazionale in un ambito di transazione, come mostrato nell'esempio seguente.  
  
```csharp  
using(TransactionScope scope1 = new TransactionScope())
{
    try
    {
        //Start of non-transactional section
        using(TransactionScope scope2 = new
            TransactionScope(TransactionScopeOption.Suppress))  
        {  
            //Do non-transactional work here  
        }  
        //Restores ambient transaction here
   }
   catch {}  
   //Rest of scope1
}
```  
  
### <a name="voting-inside-a-nested-scope"></a>Votazione all'interno di un ambito annidato  
 Anche se un ambito annidato può aggiungersi alla transazione di ambiente dell'ambito radice, una chiamata al metodo <xref:System.Transactions.TransactionScope.Complete%2A> nell'ambito annidato non produce alcun effetto nell'ambito radice. Il commit della transazione viene eseguito soltanto se tutti gli ambiti dall'ambito radice, dal primo all'ultimo livello di annidamento, votano a favore del commit. La mancata chiamata a <xref:System.Transactions.TransactionScope.Complete%2A> in un ambito annidato influirà sull'ambito radice, in quanto la transazione di ambiente verrà interrotta immediatamente.  
  
## <a name="setting-the-transactionscope-timeout"></a>Impostazione del timeout di TransactionScope  
 Alcuni overload dei costruttori dell'ambito <xref:System.Transactions.TransactionScope> accettano un valore di tipo <xref:System.TimeSpan> utilizzato per controllare il timeout della transazione. Un timeout impostato su zero equivale a un timeout infinito. Un timeout infinito è particolarmente utile per l'esecuzione del debug, quando si desidera che il timeout della transazione di cui si sta eseguendo il debug non scada mentre si esegue il codice un'istruzione alla volta allo scopo di isolare un problema nella regola business. In tutti gli altri casi occorre prestare particolare attenzione quando si utilizza un timeout infinto, in quanto questo tipo timeout è in grado di aggirare tutti i meccanismi di protezione contro i deadlock delle transazioni.  
  
 In genere il timeout di un ambito <xref:System.Transactions.TransactionScope> viene impostato su un valore diverso da quello predefinito in due casi. Il primo è in fase di sviluppo, quando si desidera verificare il modo in cui le applicazioni gestiscono le transazioni interrotte. Se si imposta il timeout su un valore ridotto (ad esempio su un millisecondo) è possibile fare in modo che la transazione abbia esito negativo e quindi esaminare il codice di gestione degli errori. Il secondo caso in cui è utile impostare il timeout su un valore inferiore a quello predefinito è quando si sospetta che l'ambito sia coinvolto in un conflitto di risorse che genera deadlock. In tal caso lo scopo è interrompere la transazione il prima possibile senza attendere lo scadere del timeout predefinito.  
  
 Quando un ambito si aggiunge a una transazione specificando un timeout minore rispetto a quello impostato per la transazione di ambiente, il nuovo timeout ridotto viene applicato all'oggetto <xref:System.Transactions.TransactionScope> e l'ambito deve terminare entro il timeout annidato specificato; in caso contrario la transazione viene interrotta automaticamente. Se il timeout dell'ambito annidato è maggiore rispetto a quello della transazione di ambiente, tale timeout viene ignorato.  
  
## <a name="setting-the-transactionscope-isolation-level"></a>Impostazione del livello di isolamento di TransactionScope  
 Alcuni overload dei costruttori dell'ambito <xref:System.Transactions.TransactionScope> accettano una struttura di tipo <xref:System.Transactions.TransactionOptions> per specificare, oltre a un valore di timeout, anche un livello di isolamento. Per impostazione predefinita, la transazione viene eseguita con il livello di isolamento impostato su <xref:System.Transactions.IsolationLevel.Serializable>. I livelli di isolamento diversi da <xref:System.Transactions.IsolationLevel.Serializable> vengono in genere utilizzati nei sistemi caratterizzati da un numero elevato di operazioni di lettura. Per utilizzare questi livelli è necessario aver compreso in modo chiaro la teoria dell'elaborazione delle transazioni, la semantica delle transazioni stesse, le problematiche di concorrenza attinenti e le conseguenze sulla coerenza di sistema.  
  
 Inoltre, solo determinati gestori di risorse supportano tutti i livelli di isolamento ed è peraltro possibile che i gestori scelgano di partecipare alla transazione a un livello superiore rispetto a quello configurato.  
  
 Ad eccezione di <xref:System.Transactions.IsolationLevel.Serializable>, tutti i livelli di isolamento possono comportare problemi di coerenza dovuti alla possibilità che altre transazioni accedano alle stesse informazioni. La differenza tra i vari livelli di isolamento consiste nel modo in cui utilizzano i blocchi di lettura e di scrittura. Un blocco può essere tenuto attivo esclusivamente quando la transazione accede ai dati del gestore di risorse, oppure fino all'interruzione o all'esecuzione del commit della transazione. Il primo tipo di blocco consente di ottimizzare la velocità effettiva, mentre il secondo è ideale per garantire la coerenza. I due tipi di blocco e i due tipi di operazioni (lettura/scrittura) danno luogo a quattro livelli di isolamento di base. Per altre informazioni, vedere <xref:System.Transactions.IsolationLevel>.  
  
 Quando si utilizzano oggetti <xref:System.Transactions.TransactionScope> annidati, tutti gli ambiti annidati devono essere configurati in modo da utilizzare esattamente lo stesso livello di isolamento se intendono aggiungersi alla transazione di ambiente. Se un oggetto <xref:System.Transactions.TransactionScope> annidato tenta di aggiungersi alla transazione di ambiente specificando un livello di isolamento diverso, viene generata un'eccezione <xref:System.ArgumentException>.  
  
## <a name="interop-with-com"></a>Interoperabilità con COM+  
 Quando si crea una nuova istanza della classe <xref:System.Transactions.TransactionScope> è possibile utilizzare l'enumerazione <xref:System.Transactions.EnterpriseServicesInteropOption> in uno dei costruttori per specificare l'interoperabilità con COM+. Per ulteriori informazioni, vedere [Interoperabilità con Enterprise Services e transazioni COM.](interoperability-with-enterprise-services-and-com-transactions.md)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Transactions.Transaction.Clone%2A>
- <xref:System.Transactions.TransactionScope>
