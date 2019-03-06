---
title: Generazione di comandi SQL di modifica
ms.date: 03/30/2017
ms.assetid: 2188a39d-46ed-4a8b-906a-c9f15e6fefd1
ms.openlocfilehash: 13ed7186981e82d47f00b6a38a4328ed75f527f4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374752"
---
# <a name="modification-sql-generation"></a>Generazione di comandi SQL di modifica

Questa sezione descrive come sviluppare un modulo di generazione SQL di modifica per il provider (database conforme a SQL:1999). Tale modulo è responsabile della conversione di un albero dei comandi di modifica nelle istruzioni SQL INSERT, UPDATE o DELETE appropriate.

Per informazioni sulla generazione SQL per le istruzioni select, vedere [generazione di comandi SQL](../../../../../docs/framework/data/adonet/ef/sql-generation.md).

## <a name="overview-of-modification-command-trees"></a>Panoramica degli alberi dei comandi di modifica

Il modulo di generazione SQL di modifica genera istruzioni SQL di modifica specifiche del database basate su un determinato DbModificationCommandTree di input.

Un oggetto DbModificationCommandTree è una rappresentazione del modello a oggetti di un'operazione DML di modifica (inserimento, aggiornamento o eliminazione), che eredita da DbCommandTree. Esistono tre implementazioni di DbModificationCommandTree:

- DbInsertCommandTree

- DbUpdateCommandTree

- DbDeleteCommandTree

DbModificationCommandTree e le relative implementazioni prodotte dal [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] rappresentano sempre un'operazione singola riga. Questa sezione descrive questi tipi con i relativi vincoli in .NET Framework versione 3.5.

![Diagram](../../../../../docs/framework/data/adonet/ef/media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")

DbModificationCommandTree include una proprietà Target che rappresenta il set di destinazioni per l'operazione di modifica. La proprietà Expression di Target, che definisce il set di input, è sempre DbScanExpression.  Un oggetto DbScanExpression può rappresentare una tabella o una vista o un set di dati definito con una query se la proprietà di metadati "Definizione di Query" del relativo server di destinazione è diverso da null.

Un oggetto DbScanExpression che rappresenta una query può raggiungere un provider come destinazione della modifica solo se il set è stato definito tramite una query di definizione nel modello, ma non è stata specificata alcuna funzione per la corrispondente operazione di modifica. È possibile che alcuni provider non siano in grado di supportare tale scenario, ad esempio SqlClient.

DbInsertCommandTree rappresenta un'operazione di inserimento di una singola riga espressa come albero dei comandi.

```csharp
public sealed class DbInsertCommandTree : DbModificationCommandTree {
   public IList<DbModificationClause> SetClauses { get }
   public DbExpression Returning { get }
}
```

DbUpdateCommandTree rappresenta un'operazione di aggiornamento di una singola riga espressa come albero dei comandi.

DbDeleteCommandTree rappresenta un'operazione di eliminazione di una singola riga espressa come albero dei comandi.

### <a name="restrictions-on-modification-command-tree-properties"></a>Restrizioni sulle proprietà degli alberi dei comandi di modifica

Le informazioni e le restrizioni seguenti si applicano alle proprietà degli alberi dei comandi di modifica.

#### <a name="returning-in-dbinsertcommandtree-and-dbupdatecommandtree"></a>Returning in DbInsertCommandTree e DbUpdateCommandTree

Quando è diversa da null, la proprietà Returning indica che il comando restituisce un lettore. In caso contrario, il comando deve restituire un valore scalare che indica il numero di righe interessate (inserite o aggiornate).

Il valore Returning specifica una proiezione dei risultati da restituire in base alla riga inserita o aggiornata. Può essere solo del tipo DbNewInstanceExpression che rappresenta una riga i cui argomenti sono oggetti DbPropertyExpression di un oggetto DbVariableReferenceExpression che rappresenta un riferimento alla proprietà Target dell'oggetto DbModificationCommandTree corrispondente. Le proprietà rappresentate da DbPropertyExpressions e usate nella proprietà Returning sono sempre valori generati dall'archivio o calcolati. In DbInsertCommandTree la proprietà Returning non è null quando almeno una proprietà della tabella in cui viene inserita la riga viene specificata come generata dall'archivio o calcolata (contrassegnata come StoreGeneratedPattern.Identity o StoreGeneratedPattern.Computed in ssdl). In DbUpdateCommandTrees la proprietà Returning non è null quando almeno una proprietà della tabella in cui viene aggiornata la riga viene specificata come generata dall'archivio o calcolata (contrassegnata come StoreGeneratedPattern.Identity o StoreGeneratedPattern.Computed in ssdl).

#### <a name="setclauses-in-dbinsertcommandtree-and-dbupdatecommandtree"></a>SetClauses in DbInsertCommandTree e DbUpdateCommandTree

SetClauses specifica l'elenco di clausole SET di inserimento o di aggiornamento che definiscono l'operazione di inserimento o aggiornamento.

```
The elements of the list are specified as type DbModificationClause, which specifies a single clause in an insert or update modification operation. DbSetClause inherits from DbModificationClause and specifies the clause in a modification operation that sets the value of a property. Beginning in version 3.5 of the .NET Framework, all elements in SetClauses are of type SetClause.
```

Property specifica la proprietà che deve essere aggiornata. È sempre un oggetto DbPropertyExpression di un oggetto DbVariableReferenceExpression, che rappresenta un riferimento alla proprietà Target del corrispondente DbModificationCommandTree.

Value specifica il nuovo valore con cui aggiornare la proprietà. È di tipo DbConstantExpression o DbNullExpression.

#### <a name="predicate-in-dbupdatecommandtree-and-dbdeletecommandtree"></a>Predicate in DbUpdateCommandTree e DbDeleteCommandTree

Predicate specifica il predicato usato per determinare i membri della raccolta di destinazione da aggiornare o eliminare. Si tratta di un albero delle espressioni costituito dal subset di DbExpression seguente:

- DbComparisonExpression del tipo Equals, con l'elemento figlio di destra un oggetto DbPropertyExpression restrizioni indicate di seguito e il figlio sinistro di un oggetto DbConstantExpression.

- DbConstantExpression

- DbIsNullExpression su un oggetto DbPropertyExpression restrizioni indicate sotto

- DbPropertyExpression su un oggetto DbVariableReferenceExpression che rappresenta un riferimento alla proprietà Target del corrispondente DbModificationCommandTree.

- DbAndExpression

- DbNotExpression

- DbOrExpression

## <a name="modification-sql-generation-in-the-sample-provider"></a>Generazione di comandi SQL di modifica nel provider di esempio

Il [Provider di esempio Entity Framework](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) illustra i componenti dei provider di dati ADO.NET che supportano il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. È destinato a un database SQL Server 2005 e viene implementato come wrapper basato sul provider di dati ADO.NET 2.0 System.Data.SqlClient.

Il modulo di generazione SQL di modifica del provider di esempio (disponibile nel file SQL Generation\DmlSqlGenerator.cs) accetta un oggetto DbModificationCommandTree di input e produce una singola istruzione SQL di modifica, eventualmente seguita da un'istruzione Select per restituire un lettore se specificato da DbModificationCommandTree. Tenere presente che la forma dei comandi generati dipende dal database SQL Server di destinazione.

### <a name="helper-classes-expressiontranslator"></a>Classi helper: ExpressionTranslator

ExpressionTranslator funge da comune convertitore con funzioni di base per tutte le proprietà dell'albero dei comandi di modifica di tipo DbExpression. Supporta solo la conversione dei tipi di espressione ai quali sono vincolate le proprietà dell'albero dei comandi di modifica ed è stato creato tenendo conto di tali vincoli.

Nelle informazioni seguenti viene descritta la visita di specifici tipi di espressione (i nodi con conversioni semplici vengono omessi).

### <a name="dbcomparisonexpression"></a>DbComparisonExpression

Quando ExpressionTranslator viene costruito con preserveMemberValues = true e quando la costante a destra è un oggetto DbConstantExpression (anziché DbNullExpression), associa l'operando di sinistra (un oggetto DbPropertyExpression) a tale DbConstantExpression. Quest'ultimo viene usato se è necessario generare un'istruzione Select di restituzione per identificare la riga interessata.

### <a name="dbconstantexpression"></a>DbConstantExpression

Per ogni costante visitata viene creato un parametro.

### <a name="dbpropertyexpression"></a>DbPropertyExpression

Poiché l'istanza di DbPropertyExpression rappresenta sempre la tabella di input, a meno che la generazione non abbia creato un alias (cosa che avviene solo negli scenari di aggiornamento quando viene usata una variabile di tabella), non è necessario specificare alcun alias per l'input. La conversione assume il nome di proprietà predefinito.

## <a name="generating-an-insert-sql-command"></a>Generazione di un comando SQL di inserimento

Per un determinato DbInsertCommandTree nel provider di esempio, il comando di inserimento generato si basa su uno dei due modelli di inserimento riportati di seguito.

Il primo modello presenta un comando per l'esecuzione dell'inserimento in base ai valori dell'elenco di SetClauses e un'istruzione SELECT per la restituzione delle proprietà specificate nella proprietà Returning della riga inserita se la proprietà Returning non è null. L'elemento predicato "\@ @ROWCOUNT > 0" è true se è stata inserita una riga. L'elemento predicato "keyMemberI = keyValueI &#124; SCOPE_IDENTITY ()" assume la forma "keyMemberI = SCOPE_IDENTITY ()" solo se keyMemberI è una chiave generato dall'archivio, in quanto SCOPE_IDENTITY () restituisce l'ultimo valore identity inserito in un'identità ( colonne generate dall'archivio).

```sql
-- first insert Template
INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]
VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES

[SELECT <returning>
 FROM <target>
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]
```

Il secondo modello è necessario se il comando Insert specifica l'inserimento di una riga in cui la chiave primaria è generata dall'archivio ma non è un tipo Integer e pertanto non può essere usata con scope_identity()). Viene usato anche in presenza di una chiave composta generata dall'archivio.

```sql
-- second insert template
DECLARE @generated_keys TABLE [(keyMember0, … keyMemberN)

INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]
 OUTPUT inserted.KeyMember0, …, inserted.KeyMemberN INTO @generated_keys
 VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES

[SELECT <returning_over_t>
 FROM @generated_keys  AS g
JOIN <target> AS t ON g.KeyMember0 = t.KeyMember0 AND … g.KeyMemberN = t.KeyMemberN
 WHERE @@ROWCOUNT > 0
```

Nell'esempio riportato di seguito viene usato il modello incluso nel provider di esempio. Viene generato un comando di inserimento da un oggetto DbInsertCommandTree.

Nel codice seguente viene inserito un oggetto Category:

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = new Category();
   c.CategoryName = "Test Category";
   c.Description = "A new category for testing";
   northwindContext.AddObject("Categories", c);
   northwindContext.SaveChanges();
}
```

In questo codice viene prodotto il seguente albero dei comandi passato al provider:

```
DbInsertCommandTree
|_Parameters
|_Target : 'target'
| |_Scan : dbo.Categories
|_SetClauses
| |_DbSetClause
| | |_Property
| | | |_Var(target).CategoryName
| | |_Value
| |   |_'Test Category'
| |_DbSetClause
| | |_Property
| | | |_Var(target).Description
| | |_Value
| |   |_'A new category for testing'
| |_DbSetClause
|   |_Property
|   | |_Var(target).Picture
|   |_Value
|     |_null
|_Returning
  |_NewInstance : Record['CategoryID'=Edm.Int32]
    |_Column : 'CategoryID'
      |_Var(target).CategoryID
```

Il comando di archiviazione prodotto dal provider di esempio è l'istruzione SQL seguente:

```sql
insert [dbo].[Categories]([CategoryName], [Description], [Picture])
values (@p0, @p1, null)
select [CategoryID]
from [dbo].[Categories]
where @@ROWCOUNT > 0 and [CategoryID] = scope_identity()
```

## <a name="generating-an-update-sql-command"></a>Generazione di un comando SQL di aggiornamento

Per un determinato DbUpdateCommandTree, il comando di aggiornamento generato si basa sul modello seguente:

```sql
-- UPDATE Template
UPDATE <target>
SET setClauseProperty0 = setClauseValue0, .. setClausePropertyN = setClauseValueN  | @i = 0
WHERE <predicate>

[SELECT <returning>
 FROM <target>
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]
```

La clausola set include la clausola set falsa ("@i = 0") solo se non sono specificate clausole alcun set. In questo modo si garantisce che le colonne calcolate dall'archivio vengano ricalcolate.

Solo se la proprietà Returning non è null, viene generata un'istruzione Select per restituire le proprietà specificate nella proprietà Returning.

Nell'esempio riportato di seguito viene usato il modello incluso nel provider di esempio per generare un comando di aggiornamento.

Nel codice utente seguente viene aggiornato un oggetto Category:

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "Test Category").First();
   c.CategoryName = "New test name";
   northwindContext.SaveChanges();
}
```

In questo codice utente viene prodotto il seguente albero dei comandi passato al provider:

```
DbUpdateCommandTree
|_Parameters
|_Target : 'target'
| |_Scan : dbo.Categories
|_SetClauses
| |_DbSetClause
|   |_Property
|   | |_Var(target).CategoryName
|   |_Value
|     |_'New test name'
|_Predicate
| |_
|   |_Var(target).CategoryID
|   |_=
|   |_10
|_Returning
```

Il provider di esempio produce il comando di archiviazione seguente:

```sql
update [dbo].[Categories]
set [CategoryName] = @p0
where ([CategoryID] = @p1)
```

### <a name="generating-a-delete-sql-command"></a>Generazione di un comando SQL di eliminazione

Per un determinato DbDeleteCommandTree, il comando DELETE generato si basa sul modello seguente:

```sql
-- DELETE Template
DELETE <target>
WHERE <predicate>
```

Nell'esempio riportato di seguito viene usato il modello incluso nel provider di esempio per generare un comando di eliminazione.

Nel codice utente seguente viene eliminato un oggetto Category:

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "New test name").First();
   northwindContext.DeleteObject(c);
   northwindContext.SaveChanges();
}
```

In questo codice utente viene prodotto il seguente albero dei comandi passato al provider:

```
DbDeleteCommandTree
|_Parameters
|_Target : 'target'
| |_Scan : dbo.Categories
|_Predicate
  |_
    |_Var(target).CategoryID
    |_=
    |_10
```

Il provider di esempio produce il comando di archiviazione seguente:

```sql
delete [dbo].[Categories]
where ([CategoryID] = @p0)
```

## <a name="see-also"></a>Vedere anche

- [Scrittura di un provider di dati Entity Framework](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
