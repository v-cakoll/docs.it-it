---
title: Domande frequenti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 252ed666-0679-4eea-b71b-2f14117ef443
ms.openlocfilehash: 3cc879e97438138554f1d39cf588e01bfbba28a6
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634703"
---
# <a name="frequently-asked-questions"></a>Domande frequenti

Le sezioni seguenti rispondono ad alcuni problemi comuni che possono verificarsi quando si implementa LINQ.

Ulteriori problemi vengono risolti nella [risoluzione dei](troubleshooting.md)problemi.

## <a name="cannot-connect"></a>Connessione non possibile

D. Non è possibile connettersi al database.

Oggetto. Verificare che la stringa di connessione sia corretta e che l'istanza di SQL Server sia in esecuzione. Tenere inoltre presente che [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] richiede che sia abilitato il protocollo Named Pipes. Per ulteriori informazioni, vedere [learning by Walkthroughs](learning-by-walkthroughs.md).

## <a name="changes-to-database-lost"></a>Perdita delle modifiche al database

D. Quando si riesegue l'applicazione dopo avere apportato una modifica ai dati presenti nel database, la modifica va persa.

Oggetto. Accertarsi di chiamare <xref:System.Data.Linq.DataContext.SubmitChanges%2A> per salvare i risultati nel database.

## <a name="database-connection-open-how-long"></a>Durata di una connessione di database aperta

D. Per quanto tempo rimane aperta la connessione di database?

Oggetto. Una connessione rimane in genere aperta finché non si usano i risultati della query. Se si prevede di impiegare tempo per elaborare tutti i risultati ed è possibile memorizzare nella cache i risultati, applicare <xref:System.Linq.Enumerable.ToList%2A> alla query. Negli scenari comuni dove ogni oggetto viene elaborato solo una volta, il modello di flusso è superiore in `DataReader` e [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].

I dettagli esatti di utilizzo della connessione dipendono dagli elementi seguenti:

- Stato della connessione se <xref:System.Data.Linq.DataContext> viene costruito con un oggetto connessione.

- Impostazioni della stringa di connessione, ad esempio abilitando MARS (Multiple Active Result Sets). Per altre informazioni, vedere [MARS (Multiple Active Result Sets)](../multiple-active-result-sets-mars.md).

## <a name="updating-without-querying"></a>Aggiornamento senza query

D. È possibile aggiornare i dati della tabella senza prima eseguire una query sul database?

Oggetto. Sebbene [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non disponga di comandi di aggiornamento basati su set, è possibile usare le tecniche seguenti per aggiornare senza prima eseguire una query:

- Usare <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> per inviare il codice SQL.

- Creare una nuova istanza dell'oggetto e inizializzare tutti i valori (campi) correnti che influiscono sull'aggiornamento. Associare quindi l'oggetto a <xref:System.Data.Linq.DataContext> usando <xref:System.Data.Linq.Table%601.Attach%2A> e modificare il campo desiderato.

## <a name="unexpected-query-results"></a>Risultati imprevisti delle query

D. La query restituisce risultati imprevisti. Come è possibile controllare quello che si sta verificando?

Oggetto. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fornisce molti strumenti per controllare il codice SQL generato. Uno dei più importanti è <xref:System.Data.Linq.DataContext.Log%2A>. Per ulteriori informazioni, vedere [supporto](debugging-support.md)per il debug.

## <a name="unexpected-stored-procedure-results"></a>Risultati imprevisti delle stored procedure

D. Il valore restituito di una stored procedure viene calcolato da `MAX()`. Quando si trascina il stored procedure nell'area di progettazione O/R, il valore restituito non è corretto.

Oggetto. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fornisce due modalità per restituire i valori generati dal database tramite le stored procedure:

- Assegnando un nome al risultato di output.

- Specificando in modo esplicito un parametro di output.

Di seguito viene riportato un esempio di output non corretto. Poiché in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non è possibile eseguire il mapping dei risultati, viene restituito sempre 0:

```sql
create procedure proc2

as

begin

select max(i) from t where name like 'hello'

end
```

Di seguito viene riportato un esempio di output corretto usando un parametro di output:

```sql
create procedure proc2

@result int OUTPUT

as

select @result = MAX(i) from t where name like 'hello'

go
```

Di seguito viene riportato un esempio di output corretto assegnando un nome al risultato di output:

```sql
create procedure proc2

as

begin

select nax(i) AS MaxResult from t where name like 'hello'

end
```

Per ulteriori informazioni, vedere [personalizzazione di operazioni utilizzando stored procedure](customizing-operations-by-using-stored-procedures.md).

## <a name="serialization-errors"></a>Errori di inizializzazione

D. Quando si tenta di serializzare, viene ricevuto l'errore seguente: "tipo ' System. Data. Linq. ChangeTracker + StandardChangeTracker '... non è contrassegnato come serializzabile ".

Oggetto. La generazione del codice in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supporta la serializzazione <xref:System.Runtime.Serialization.DataContractSerializer>. Non supporta <xref:System.Xml.Serialization.XmlSerializer> o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>. Per altre informazioni, vedere [Serializzazione](serialization.md).

## <a name="multiple-dbml-files"></a>Più file DBML

D. Quando si dispone di più file DBML che condividono alcune tabelle, si verifica un errore del compilatore.

Oggetto. Impostare le proprietà dello **spazio dei** nomi del contesto e **dello spazio dei nomi dell'entità** dal Object Relational Designer a un valore distinto per ogni file dbml. Questo approccio elimina il conflitto di nome/spazio dei nomi.

## <a name="avoiding-explicit-setting-of-database-generated-values-on-insert-or-update"></a>Come evitare l'impostazione esplicita dei valori generati dal database nelle operazioni di inserimento o aggiornamento

D. Quando in una tabella di database con una colonna `DateCreated` la cui impostazione predefinita è SQL `Getdate()` si tenta di inserire un nuovo record usando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], il valore viene impostato su `NULL` anziché sul valore predefinito del database.

Oggetto. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] gestisce automaticamente questa situazione per le colonne Identity (incremento automatico) e rowguidcol (GUID generato dal database) e timestamp. In altri casi, è necessario impostare manualmente <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>=`true` e <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>=<xref:System.Data.Linq.Mapping.AutoSync.Always>/<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>/<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> proprietà.

## <a name="multiple-dataloadoptions"></a>Più valori DataLoadOptions

D. È possibile specificare opzioni di caricamento aggiuntive senza sovrascrivere la prima?

Oggetto. Sì. La prima opzione non viene sovrascritta, come illustrato nell'esempio seguente:

```vb
Dim dlo As New DataLoadOptions()
dlo.LoadWith(Of Order)(Function(o As Order) o.Customer)
dlo.LoadWith(Of Order)(Function(o As Order) o.OrderDetails)
```

```csharp
DataLoadOptions dlo = new DataLoadOptions();
dlo.LoadWith<Order>(o => o.Customer);
dlo.LoadWith<Order>(o => o.OrderDetails);
```

## <a name="errors-using-sql-compact-35"></a>Errori durante l'uso di SQL Compact 3.5

D. Si verifica un errore quando si trascinano le tabelle da un database SQL Server Compact 3,5.

Oggetto. Il Object Relational Designer non supporta SQL Server Compact 3,5, sebbene il runtime di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. In questa situazione, è necessario creare classi dell'entità personalizzate e aggiungere gli attributi adatti.

## <a name="errors-in-inheritance-relationships"></a>Errori nelle relazioni di ereditarietà

D. Nella Object Relational Designer è stata utilizzata la forma di ereditarietà della casella degli strumenti per connettere due entità, ma si verificano errori.

Oggetto. Non è sufficiente creare la relazione. È necessario fornire informazioni quali la colonna del discriminatore, il valore del discriminatore della classe base e il valore del discriminatore della classe derivata.

## <a name="provider-model"></a>Modello provider

D. È disponibile un modello provider pubblico?

Oggetto. Non è disponibile alcun un modello provider pubblico. A questo punto, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supporta solo SQL Server e SQL Server Compact 3,5.

## <a name="sql-injection-attacks"></a>Attacchi SQL injection

D. Come viene protetto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dagli attacchi SQL injection?

Oggetto. L'intrusione nel codice SQL ha rappresentato un pericolo significativo per le query SQL tradizionali formate concatenando l'input dell'utente. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] evita tale intrusione usando <xref:System.Data.SqlClient.SqlParameter> nelle query. L'input dell'utente viene convertito in valori di parametro. Questo approccio impedisce l'uso di comandi dannosi dall'input del cliente.

## <a name="changing-read-only-flag-in-dbml-files"></a>Modifica del flag di sola lettura nei file DBML

D. Come è possibile eliminare i metodi di impostazione da alcune proprietà quando si crea un modello a oggetti da un file DBML?

Oggetto. Attenersi alla procedura riportata di seguito per questo scenario avanzato:

1. Nel file con estensione dbml modificare la proprietà impostando il flag <xref:System.Data.Linq.ITable.IsReadOnly%2A> su `True`.

2. Aggiungere una classe parziale. Creare un costruttore con i parametri per i membri di sola lettura.

3. Esaminare il valore <xref:System.Data.Linq.Mapping.UpdateCheck> predefinito (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>) per determinare se questo valore è corretto per l'applicazione.

    > [!CAUTION]
    > Se si usa il Object Relational Designer in Visual Studio, le modifiche potrebbero essere sovrascritte.

## <a name="aptca"></a>APTCA

D. System.Data.Linq è contrassegnato per l'uso da codice parzialmente attendibile?

Oggetto. Sì, l'assembly System. Data. Linq. dll è tra gli assembly .NET Framework contrassegnati con l'attributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute>. Senza questo contrassegno, gli assembly nel .NET Framework devono essere usati solo da codice completamente attendibile.

Lo scenario principale in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per consentire chiamanti parzialmente attendibili è quello di consentire l'accesso all'assembly [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] da applicazioni Web, in cui la configurazione del *trust* è media.

## <a name="mapping-data-from-multiple-tables"></a>Esecuzione del mapping dei dati da più tabelle

D. I dati dell'entità derivano da più tabelle. Come è possibile eseguirne il mapping?

Oggetto. È possibile creare una visualizzazione in un database ed eseguire il mapping dell'entità alla visualizzazione. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera lo stesso codice SQL per le visualizzazioni come per le tabelle.

> [!NOTE]
> L'utilizzo di visualizzazioni in questo scenario presenta delle limitazioni. Questo approccio funziona in modo più sicuro quando le operazioni eseguite su <xref:System.Data.Linq.Table%601> vengono supportate dalla visualizzazione sottostante. Solo l'utente conosce le operazioni desiderate da eseguire. Ad esempio, la maggior parte delle applicazioni è di sola lettura e un altro numero notevole esegue `Create`/`Update`/operazioni di `Delete` solo utilizzando le stored procedure sulle viste.

## <a name="connection-pooling"></a>Pool di connessioni

D. È disponibile un costrutto che possa facilitare il pool <xref:System.Data.Linq.DataContext>?

Oggetto. Non tentare di riutilizzare le istanze di <xref:System.Data.Linq.DataContext>. Ogni oggetto <xref:System.Data.Linq.DataContext> conserva lo stato (inclusa una cache delle identità) per una determinata sessione di modifica/query. Per ottenere nuove istanze basate sullo stato corrente del database, usare un nuovo oggetto <xref:System.Data.Linq.DataContext>.

È comunque possibile usare il pool di connessioni ADO.NET sottostanti. Per altre informazioni, vedere [Pool di connessioni SQL Server (ADO.NET)](../../sql-server-connection-pooling.md).

## <a name="second-datacontext-is-not-updated"></a>Il secondo oggetto DataContext non viene aggiornato

D. Un'istanza di <xref:System.Data.Linq.DataContext> è stata usata per archiviare i valori nel database. Tuttavia, un secondo oggetto <xref:System.Data.Linq.DataContext> nello stesso database non riflette i valori aggiornati. La seconda istanza <xref:System.Data.Linq.DataContext> sembra restituire i valori memorizzati nella cache.

Oggetto. Questo comportamento è previsto dalla progettazione. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] continua a restituire gli stessi valori o le stesse istanze specificate nella prima istanza. Quando si effettuano gli aggiornamenti, usare la concorrenza ottimistica. I dati originali vengono usati per controllare lo stato corrente del database in modo da asserire che risulta ancora invariato. Se è stato modificato, si verifica un conflitto e l'applicazione deve risolverlo. Un'opzione dell'applicazione è reimpostare lo stato originale allo stato corrente del database e provare nuovamente l'aggiornamento. Per altre informazioni, vedere [procedura: gestire i conflitti di modifica](how-to-manage-change-conflicts.md).

È anche possibile impostare <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> su false, in modo da disattivare la memorizzazione nella cache e la ricerca delle modifiche. È quindi possibile recuperare gli ultimi valori ogni volta che si esegue una query.

## <a name="cannot-call-submitchanges-in-read-only-mode"></a>Impossibile chiamare SubmitChanges in modalità di sola lettura

D. Quando si tenta di chiamare <xref:System.Data.Linq.DataContext.SubmitChanges%2A> in modalità di sola lettura, si verifica un errore.

Oggetto. La modalità di sola lettura non consente al contesto di tenere traccia delle modifiche.

## <a name="see-also"></a>Vedere anche

- [Reference](reference.md)
- [Risoluzione dei problemi](troubleshooting.md)
- [Sicurezza in LINQ to SQL](security-in-linq-to-sql.md)
