---
title: Generazione di comandi SQL di modifica
ms.date: 03/30/2017
ms.assetid: 2188a39d-46ed-4a8b-906a-c9f15e6fefd1
ms.openlocfilehash: 8e0568e32094b6cc27137409f3d908928d82cebb
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615128"
---
# <a name="modification-sql-generation"></a><span data-ttu-id="8665d-102">Generazione di comandi SQL di modifica</span><span class="sxs-lookup"><span data-stu-id="8665d-102">Modification SQL Generation</span></span>
<span data-ttu-id="8665d-103">Questa sezione descrive come sviluppare un modulo di generazione SQL di modifica per il provider (database conforme a SQL:1999).</span><span class="sxs-lookup"><span data-stu-id="8665d-103">This section discusses how to develop a modification SQL generation module for your (SQL:1999-compliant database) provider.</span></span> <span data-ttu-id="8665d-104">Tale modulo è responsabile della conversione di un albero dei comandi di modifica nelle istruzioni SQL INSERT, UPDATE o DELETE appropriate.</span><span class="sxs-lookup"><span data-stu-id="8665d-104">This module is responsible for translating a modification command tree into the appropriate SQL INSERT, UPDATE or DELETE statements.</span></span>  
  
 <span data-ttu-id="8665d-105">Per informazioni sulla generazione SQL per le istruzioni select, vedere [generazione di comandi SQL](../../../../../docs/framework/data/adonet/ef/sql-generation.md).</span><span class="sxs-lookup"><span data-stu-id="8665d-105">For information about SQL generation for select statements, see [SQL Generation](../../../../../docs/framework/data/adonet/ef/sql-generation.md).</span></span>  
  
## <a name="overview-of-modification-command-trees"></a><span data-ttu-id="8665d-106">Panoramica degli alberi dei comandi di modifica</span><span class="sxs-lookup"><span data-stu-id="8665d-106">Overview of Modification Command Trees</span></span>  
 <span data-ttu-id="8665d-107">Il modulo di generazione SQL di modifica genera istruzioni SQL di modifica specifiche del database basate su un determinato DbModificationCommandTree di input.</span><span class="sxs-lookup"><span data-stu-id="8665d-107">The modification SQL generation module generates database-specific modification SQL statements based on a given input DbModificationCommandTree.</span></span>  
  
 <span data-ttu-id="8665d-108">Un oggetto DbModificationCommandTree è una rappresentazione del modello a oggetti di un'operazione DML di modifica (inserimento, aggiornamento o eliminazione), che eredita da DbCommandTree.</span><span class="sxs-lookup"><span data-stu-id="8665d-108">A DbModificationCommandTree is an object model representation of a modification DML operation (an insert, an update, or a delete operation), inheriting from DbCommandTree.</span></span> <span data-ttu-id="8665d-109">Esistono tre implementazioni di DbModificationCommandTree:</span><span class="sxs-lookup"><span data-stu-id="8665d-109">There are three implementations of DbModificationCommandTree:</span></span>  
  
-   <span data-ttu-id="8665d-110">DbInsertCommandTree</span><span class="sxs-lookup"><span data-stu-id="8665d-110">DbInsertCommandTree</span></span>  
  
-   <span data-ttu-id="8665d-111">DbUpdateCommandTree</span><span class="sxs-lookup"><span data-stu-id="8665d-111">DbUpdateCommandTree</span></span>  
  
-   <span data-ttu-id="8665d-112">DbDeleteCommandTree</span><span class="sxs-lookup"><span data-stu-id="8665d-112">DbDeleteCommandTree</span></span>  
  
 <span data-ttu-id="8665d-113">DbModificationCommandTree e le relative implementazioni prodotte dal [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] rappresentano sempre un'operazione singola riga.</span><span class="sxs-lookup"><span data-stu-id="8665d-113">DbModificationCommandTree and its implementations that are produced by the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] always represent a single row operation.</span></span> <span data-ttu-id="8665d-114">Questa sezione descrive questi tipi con i relativi vincoli in .NET Framework versione 3.5.</span><span class="sxs-lookup"><span data-stu-id="8665d-114">This section describes these types with their constraints in the .NET Framework version 3.5.</span></span>  
  
 <span data-ttu-id="8665d-115">![Diagram](../../../../../docs/framework/data/adonet/ef/media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")</span><span class="sxs-lookup"><span data-stu-id="8665d-115">![Diagram](../../../../../docs/framework/data/adonet/ef/media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")</span></span>  
  
 <span data-ttu-id="8665d-116">DbModificationCommandTree include una proprietà Target che rappresenta il set di destinazioni per l'operazione di modifica.</span><span class="sxs-lookup"><span data-stu-id="8665d-116">DbModificationCommandTree has a Target property that represents the target set for the modification operation.</span></span> <span data-ttu-id="8665d-117">La proprietà Expression di Target, che definisce il set di input, è sempre DbScanExpression.</span><span class="sxs-lookup"><span data-stu-id="8665d-117">The Target’s Expression property, which defines the input set is always DbScanExpression.</span></span>  <span data-ttu-id="8665d-118">Un oggetto DbScanExpression può rappresentare una tabella o una vista o un set di dati definito con una query se la proprietà di metadati "Definizione di Query" del relativo server di destinazione è diverso da null.</span><span class="sxs-lookup"><span data-stu-id="8665d-118">A DbScanExpression can either represent a table or a view, or a set of data defined with a query if the metadata property "Defining Query" of its Target is non-null.</span></span>  
  
 <span data-ttu-id="8665d-119">Un oggetto DbScanExpression che rappresenta una query può raggiungere un provider come destinazione della modifica solo se il set è stato definito tramite una query di definizione nel modello, ma non è stata specificata alcuna funzione per la corrispondente operazione di modifica.</span><span class="sxs-lookup"><span data-stu-id="8665d-119">A DbScanExpression that represents a query could only reach a provider as a target of modification if the set was defined by using a defining query in the model but no function was provided for the corresponding modification operation.</span></span> <span data-ttu-id="8665d-120">È possibile che alcuni provider non siano in grado di supportare tale scenario, ad esempio SqlClient.</span><span class="sxs-lookup"><span data-stu-id="8665d-120">Providers may not be able to support such a scenario (SqlClient, for example, does not).</span></span>  
  
 <span data-ttu-id="8665d-121">DbInsertCommandTree rappresenta un'operazione di inserimento di una singola riga espressa come albero dei comandi.</span><span class="sxs-lookup"><span data-stu-id="8665d-121">DbInsertCommandTree represents a single row insert operation expressed as a command tree.</span></span>  
  
```  
public sealed class DbInsertCommandTree : DbModificationCommandTree {  
   public IList<DbModificationClause> SetClauses { get }  
   public DbExpression Returning { get }  
}  
```  
  
 <span data-ttu-id="8665d-122">DbUpdateCommandTree rappresenta un'operazione di aggiornamento di una singola riga espressa come albero dei comandi.</span><span class="sxs-lookup"><span data-stu-id="8665d-122">DbUpdateCommandTree represents a single-row update operation expressed as a command tree.</span></span>  
  
 <span data-ttu-id="8665d-123">DbDeleteCommandTree rappresenta un'operazione di eliminazione di una singola riga espressa come albero dei comandi.</span><span class="sxs-lookup"><span data-stu-id="8665d-123">DbDeleteCommandTree represents a single row delete operation expressed as a command tree.</span></span>  
  
### <a name="restrictions-on-modification-command-tree-properties"></a><span data-ttu-id="8665d-124">Restrizioni sulle proprietà degli alberi dei comandi di modifica</span><span class="sxs-lookup"><span data-stu-id="8665d-124">Restrictions on Modification Command Tree Properties</span></span>  
 <span data-ttu-id="8665d-125">Le informazioni e le restrizioni seguenti si applicano alle proprietà degli alberi dei comandi di modifica.</span><span class="sxs-lookup"><span data-stu-id="8665d-125">The following information and restrictions apply to the modification command tree properties.</span></span>  
  
#### <a name="returning-in-dbinsertcommandtree-and-dbupdatecommandtree"></a><span data-ttu-id="8665d-126">Returning in DbInsertCommandTree e DbUpdateCommandTree</span><span class="sxs-lookup"><span data-stu-id="8665d-126">Returning in DbInsertCommandTree and DbUpdateCommandTree</span></span>  
 <span data-ttu-id="8665d-127">Quando è diversa da null, la proprietà Returning indica che il comando restituisce un lettore.</span><span class="sxs-lookup"><span data-stu-id="8665d-127">When non-null, Returning indicates that the command returns a reader.</span></span> <span data-ttu-id="8665d-128">In caso contrario, il comando deve restituire un valore scalare che indica il numero di righe interessate (inserite o aggiornate).</span><span class="sxs-lookup"><span data-stu-id="8665d-128">Otherwise, the command should return a scalar value indicating the number of rows affected (inserted or updated).</span></span>  
  
 <span data-ttu-id="8665d-129">Il valore Returning specifica una proiezione dei risultati da restituire in base alla riga inserita o aggiornata.</span><span class="sxs-lookup"><span data-stu-id="8665d-129">The Returning value specifies a projection of results to be returned based on the inserted or the updated row.</span></span> <span data-ttu-id="8665d-130">Può essere solo del tipo DbNewInstanceExpression che rappresenta una riga i cui argomenti sono oggetti DbPropertyExpression di un oggetto DbVariableReferenceExpression che rappresenta un riferimento alla proprietà Target dell'oggetto DbModificationCommandTree corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8665d-130">It can only be of type DbNewInstanceExpression representing a row, with each of its arguments being a DbPropertyExpression over a DbVariableReferenceExpression representing a reference to the Target of the corresponding DbModificationCommandTree.</span></span> <span data-ttu-id="8665d-131">Le proprietà rappresentate da DbPropertyExpressions e usate nella proprietà Returning sono sempre valori generati dall'archivio o calcolati.</span><span class="sxs-lookup"><span data-stu-id="8665d-131">The properties represented by the DbPropertyExpressions used in the property Returning are always store generated or computed values.</span></span> <span data-ttu-id="8665d-132">In DbInsertCommandTree la proprietà Returning non è null quando almeno una proprietà della tabella in cui viene inserita la riga viene specificata come generata dall'archivio o calcolata (contrassegnata come StoreGeneratedPattern.Identity o StoreGeneratedPattern.Computed in ssdl).</span><span class="sxs-lookup"><span data-stu-id="8665d-132">In DbInsertCommandTree, Returning is not null when at least one property of the table in which the row is being inserted is specified as store generated or computed (marked as StoreGeneratedPattern.Identity or StoreGeneratedPattern.Computed in the ssdl).</span></span> <span data-ttu-id="8665d-133">In DbUpdateCommandTrees la proprietà Returning non è null quando almeno una proprietà della tabella in cui viene aggiornata la riga viene specificata come generata dall'archivio o calcolata (contrassegnata come StoreGeneratedPattern.Identity o StoreGeneratedPattern.Computed in ssdl).</span><span class="sxs-lookup"><span data-stu-id="8665d-133">In DbUpdateCommandTrees, Returning is not null when at least one property of the table in which the row is being updated is specified as store computed (marked as StoreGeneratedPattern.Computed in the ssdl).</span></span>  
  
#### <a name="setclauses-in-dbinsertcommandtree-and-dbupdatecommandtree"></a><span data-ttu-id="8665d-134">SetClauses in DbInsertCommandTree e DbUpdateCommandTree</span><span class="sxs-lookup"><span data-stu-id="8665d-134">SetClauses in DbInsertCommandTree and DbUpdateCommandTree</span></span>  
 <span data-ttu-id="8665d-135">SetClauses specifica l'elenco di clausole SET di inserimento o di aggiornamento che definiscono l'operazione di inserimento o aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="8665d-135">SetClauses specifies the list of insert or update set clauses that define the insert or update operation.</span></span>  
  
```  
The elements of the list are specified as type DbModificationClause, which specifies a single clause in an insert or update modification operation. DbSetClause inherits from DbModificationClause and specifies the clause in a modification operation that sets the value of a property. Beginning in version 3.5 of the .NET Framework, all elements in SetClauses are of type SetClause.   
```  
  
 <span data-ttu-id="8665d-136">Property specifica la proprietà che deve essere aggiornata.</span><span class="sxs-lookup"><span data-stu-id="8665d-136">Property specifies the property that should be updated.</span></span> <span data-ttu-id="8665d-137">È sempre un oggetto DbPropertyExpression di un oggetto DbVariableReferenceExpression, che rappresenta un riferimento alla proprietà Target del corrispondente DbModificationCommandTree.</span><span class="sxs-lookup"><span data-stu-id="8665d-137">It is always a DbPropertyExpression over a DbVariableReferenceExpression, which represents a reference to the Target of the corresponding DbModificationCommandTree.</span></span>  
  
 <span data-ttu-id="8665d-138">Value specifica il nuovo valore con cui aggiornare la proprietà.</span><span class="sxs-lookup"><span data-stu-id="8665d-138">Value specifies the new value with which to update the property.</span></span> <span data-ttu-id="8665d-139">È di tipo DbConstantExpression o DbNullExpression.</span><span class="sxs-lookup"><span data-stu-id="8665d-139">It is either of type DbConstantExpression or DbNullExpression.</span></span>  
  
#### <a name="predicate-in-dbupdatecommandtree-and-dbdeletecommandtree"></a><span data-ttu-id="8665d-140">Predicate in DbUpdateCommandTree e DbDeleteCommandTree</span><span class="sxs-lookup"><span data-stu-id="8665d-140">Predicate in DbUpdateCommandTree and DbDeleteCommandTree</span></span>  
 <span data-ttu-id="8665d-141">Predicate specifica il predicato usato per determinare i membri della raccolta di destinazione da aggiornare o eliminare.</span><span class="sxs-lookup"><span data-stu-id="8665d-141">Predicate specifies the predicate used to determine which members of the target collection should be updated or deleted.</span></span> <span data-ttu-id="8665d-142">Si tratta di un albero delle espressioni costituito dal subset di DbExpression seguente:</span><span class="sxs-lookup"><span data-stu-id="8665d-142">It is an expression tree built of the following subset of DbExpressions:</span></span>  
  
-   <span data-ttu-id="8665d-143">DbComparisonExpression del tipo Equals, con l'elemento figlio di destra che corrisponde a un oggetto DbPropertyExpression secondo le restrizioni indicate di seguito e l'elemento figlio di sinistra che corrisponde a un oggetto DbConstantExpression.</span><span class="sxs-lookup"><span data-stu-id="8665d-143">DbComparisonExpression of kind Equals, with the right child being a DbPropertyExression as restricted below and the left child a DbConstantExpression.</span></span>  
  
-   <span data-ttu-id="8665d-144">DbConstantExpression</span><span class="sxs-lookup"><span data-stu-id="8665d-144">DbConstantExpression</span></span>  
  
-   <span data-ttu-id="8665d-145">DbIsNullExpression su un oggetto DbPropertyExpression secondo le restrizioni indicate di seguito</span><span class="sxs-lookup"><span data-stu-id="8665d-145">DbIsNullExpression over a DbPropertyExpresison as restricted below</span></span>  
  
-   <span data-ttu-id="8665d-146">DbPropertyExpression su un oggetto DbVariableReferenceExpression che rappresenta un riferimento alla proprietà Target del corrispondente DbModificationCommandTree.</span><span class="sxs-lookup"><span data-stu-id="8665d-146">DbPropertyExpression over a DbVariableReferenceExpression representing a reference to the Target of the corresponding DbModificationCommandTree.</span></span>  
  
-   <span data-ttu-id="8665d-147">DbAndExpression</span><span class="sxs-lookup"><span data-stu-id="8665d-147">DbAndExpression</span></span>  
  
-   <span data-ttu-id="8665d-148">DbNotExpression</span><span class="sxs-lookup"><span data-stu-id="8665d-148">DbNotExpression</span></span>  
  
-   <span data-ttu-id="8665d-149">DbOrExpression</span><span class="sxs-lookup"><span data-stu-id="8665d-149">DbOrExpression</span></span>  
  
## <a name="modification-sql-generation-in-the-sample-provider"></a><span data-ttu-id="8665d-150">Generazione di comandi SQL di modifica nel provider di esempio</span><span class="sxs-lookup"><span data-stu-id="8665d-150">Modification SQL Generation in the Sample Provider</span></span>  
 <span data-ttu-id="8665d-151">Il [Provider di esempio Entity Framework](https://go.microsoft.com/fwlink/?LinkId=180616) illustra i componenti dei provider di dati ADO.NET che supportano il [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8665d-151">The [Entity Framework Sample Provider](https://go.microsoft.com/fwlink/?LinkId=180616) demonstrates the components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="8665d-152">È destinato a un database SQL Server 2005 e viene implementato come wrapper basato sul provider di dati ADO.NET 2.0 System.Data.SqlClient.</span><span class="sxs-lookup"><span data-stu-id="8665d-152">It targets a SQL Server 2005 database and is implemented as a wrapper on top of System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="8665d-153">Il modulo di generazione SQL di modifica del provider di esempio (disponibile nel file SQL Generation\DmlSqlGenerator.cs) accetta un oggetto DbModificationCommandTree di input e produce una singola istruzione SQL di modifica, eventualmente seguita da un'istruzione Select per restituire un lettore se specificato da DbModificationCommandTree.</span><span class="sxs-lookup"><span data-stu-id="8665d-153">The modification SQL generation module of the sample provider (located in the file SQL Generation\DmlSqlGenerator.cs) takes an input DbModificationCommandTree and produces a single modification SQL statement possibly followed by a select statement to return a reader if specified by the DbModificationCommandTree.</span></span> <span data-ttu-id="8665d-154">Tenere presente che la forma dei comandi generati dipende dal database SQL Server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8665d-154">Note that the shape of the commands generated is affected by the target SQL Server database.</span></span>  
  
### <a name="helper-classes-expressiontranslator"></a><span data-ttu-id="8665d-155">Classi helper: ExpressionTranslator</span><span class="sxs-lookup"><span data-stu-id="8665d-155">Helper Classes: ExpressionTranslator</span></span>  
 <span data-ttu-id="8665d-156">ExpressionTranslator funge da comune convertitore con funzioni di base per tutte le proprietà dell'albero dei comandi di modifica di tipo DbExpression.</span><span class="sxs-lookup"><span data-stu-id="8665d-156">ExpressionTranslator serves as a common lightweight translator for all modification command tree properties of type DbExpression.</span></span> <span data-ttu-id="8665d-157">Supporta solo la conversione dei tipi di espressione ai quali sono vincolate le proprietà dell'albero dei comandi di modifica ed è stato creato tenendo conto di tali vincoli.</span><span class="sxs-lookup"><span data-stu-id="8665d-157">It supports translation of only the expression types to which the properties of the modification command tree are constrained and is built with the particular constraints in mind.</span></span>  
  
 <span data-ttu-id="8665d-158">Nelle informazioni seguenti viene descritta la visita di specifici tipi di espressione (i nodi con conversioni semplici vengono omessi).</span><span class="sxs-lookup"><span data-stu-id="8665d-158">The following information discusses visiting specific expression types (nodes with trivial translations are omitted).</span></span>  
  
### <a name="dbcomparisonexpression"></a><span data-ttu-id="8665d-159">DbComparisonExpression</span><span class="sxs-lookup"><span data-stu-id="8665d-159">DbComparisonExpression</span></span>  
 <span data-ttu-id="8665d-160">Quando ExpressionTranslator viene costruito con preserveMemberValues = true e quando la costante a destra è un oggetto DbConstantExpression (anziché DbNullExpression), associa l'operando di sinistra (un oggetto DbPropertyExpression) a tale DbConstantExpression.</span><span class="sxs-lookup"><span data-stu-id="8665d-160">When the ExpressionTranslator is constructed with preserveMemberValues = true, and when the constant to the right is a DbConstantExpression (instead of DbNullExpression), it associates the left operand (a DbPropertyExpressions) with that DbConstantExpression.</span></span> <span data-ttu-id="8665d-161">Quest'ultimo viene usato se è necessario generare un'istruzione Select di restituzione per identificare la riga interessata.</span><span class="sxs-lookup"><span data-stu-id="8665d-161">That is used if a return Select statement needs to be generated to identify the affected row.</span></span>  
  
### <a name="dbconstantexpression"></a><span data-ttu-id="8665d-162">DbConstantExpression</span><span class="sxs-lookup"><span data-stu-id="8665d-162">DbConstantExpression</span></span>  
 <span data-ttu-id="8665d-163">Per ogni costante visitata viene creato un parametro.</span><span class="sxs-lookup"><span data-stu-id="8665d-163">For each visited constant a parameter is created.</span></span>  
  
### <a name="dbpropertyexpression"></a><span data-ttu-id="8665d-164">DbPropertyExpression</span><span class="sxs-lookup"><span data-stu-id="8665d-164">DbPropertyExpression</span></span>  
 <span data-ttu-id="8665d-165">Poiché l'istanza di DbPropertyExpression rappresenta sempre la tabella di input, a meno che la generazione non abbia creato un alias (cosa che avviene solo negli scenari di aggiornamento quando viene usata una variabile di tabella), non è necessario specificare alcun alias per l'input. La conversione assume il nome di proprietà predefinito.</span><span class="sxs-lookup"><span data-stu-id="8665d-165">Given that the Instance of the DbPropertyExpression always represents the input table, unless the generation has created an alias (which only happens in update scenarios when a table variable is used), no alias needs to be specified for the input; the translation defaults to the property name.</span></span>  
  
## <a name="generating-an-insert-sql-command"></a><span data-ttu-id="8665d-166">Generazione di un comando SQL di inserimento</span><span class="sxs-lookup"><span data-stu-id="8665d-166">Generating an Insert SQL Command</span></span>  
 <span data-ttu-id="8665d-167">Per un determinato DbInsertCommandTree nel provider di esempio, il comando di inserimento generato si basa su uno dei due modelli di inserimento riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="8665d-167">For a given DbInsertCommandTree in the sample provider, the generated insert command follows one of the two insert templates below.</span></span>  
  
 <span data-ttu-id="8665d-168">Il primo modello presenta un comando per l'esecuzione dell'inserimento in base ai valori dell'elenco di SetClauses e un'istruzione SELECT per la restituzione delle proprietà specificate nella proprietà Returning della riga inserita se la proprietà Returning non è null.</span><span class="sxs-lookup"><span data-stu-id="8665d-168">The first template has a command to perform the insert given the values in the list of SetClauses, and a SELECT statement to return the properties specified in the Returning property for the inserted row if the Returning property was not null.</span></span> <span data-ttu-id="8665d-169">L'elemento predicato "\@ @ROWCOUNT > 0" è true se è stata inserita una riga.</span><span class="sxs-lookup"><span data-stu-id="8665d-169">The predicate element "\@@ROWCOUNT > 0" is true if a row was inserted.</span></span> <span data-ttu-id="8665d-170">L'elemento predicato "keyMemberI = keyValueI &#124; SCOPE_IDENTITY ()" assume la forma "keyMemberI = SCOPE_IDENTITY ()" solo se keyMemeberI è una chiave generato dall'archivio, in quanto SCOPE_IDENTITY () restituisce l'ultimo valore identity inserito in un'identità ( colonne generate dall'archivio).</span><span class="sxs-lookup"><span data-stu-id="8665d-170">The predicate element "keyMemberI =  keyValueI &#124; scope_identity()" takes the shape  "keyMemberI =  scope_identity()" only if keyMemeberI is a store-generated key, because scope_identity() returns the last identity value inserted into an identity (store-generated) column.</span></span>  
  
```  
-- first insert Template  
INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]    
VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES   
  
[SELECT <returning>   
 FROM <target>  
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]  
```  
  
 <span data-ttu-id="8665d-171">Il secondo modello è necessario se il comando Insert specifica l'inserimento di una riga in cui la chiave primaria è generata dall'archivio ma non è un tipo Integer e pertanto non può essere usata con scope_identity()).</span><span class="sxs-lookup"><span data-stu-id="8665d-171">The second template is needed if the insert specifies inserting a row where the primary key is store-generated but is not an integer type and therefore can't be used with scope_identity()).</span></span> <span data-ttu-id="8665d-172">Viene usato anche in presenza di una chiave composta generata dall'archivio.</span><span class="sxs-lookup"><span data-stu-id="8665d-172">It is also used if there is a compound store-generated key.</span></span>  
  
```  
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
  
 <span data-ttu-id="8665d-173">Nell'esempio riportato di seguito viene usato il modello incluso nel provider di esempio.</span><span class="sxs-lookup"><span data-stu-id="8665d-173">The following is an example that uses the model that is included with the sample provider.</span></span> <span data-ttu-id="8665d-174">Viene generato un comando di inserimento da un oggetto DbInsertCommandTree.</span><span class="sxs-lookup"><span data-stu-id="8665d-174">It generates an insert command from a DbInsertCommandTree.</span></span>  
  
 <span data-ttu-id="8665d-175">Nel codice seguente viene inserito un oggetto Category:</span><span class="sxs-lookup"><span data-stu-id="8665d-175">The following code inserts a Category:</span></span>  
  
```  
using (NorthwindEntities northwindContext = new NorthwindEntities()) {  
   Category c = new Category();  
   c.CategoryName = "Test Category";  
   c.Description = "A new category for testing";  
   northwindContext.AddObject("Categories", c);  
   northwindContext.SaveChanges();  
}  
```  
  
 <span data-ttu-id="8665d-176">In questo codice viene prodotto il seguente albero dei comandi passato al provider:</span><span class="sxs-lookup"><span data-stu-id="8665d-176">This code produces the following command tree, which is passed to the provider:</span></span>  
  
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
  
 <span data-ttu-id="8665d-177">Il comando di archiviazione prodotto dal provider di esempio è l'istruzione SQL seguente:</span><span class="sxs-lookup"><span data-stu-id="8665d-177">The store command that the sample provider produces is the following SQL statement:</span></span>  
  
```  
insert [dbo].[Categories]([CategoryName], [Description], [Picture])  
values (@p0, @p1, null)  
select [CategoryID]  
from [dbo].[Categories]  
where @@ROWCOUNT > 0 and [CategoryID] = scope_identity()  
```  
  
## <a name="generating-an-update-sql-command"></a><span data-ttu-id="8665d-178">Generazione di un comando SQL di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="8665d-178">Generating an Update SQL Command</span></span>  
 <span data-ttu-id="8665d-179">Per un determinato DbUpdateCommandTree, il comando di aggiornamento generato si basa sul modello seguente:</span><span class="sxs-lookup"><span data-stu-id="8665d-179">For a given DbUpdateCommandTree, the generated update command is based on the following template:</span></span>  
  
```  
-- UPDATE Template   
UPDATE <target>   
SET setClauseProprerty0 = setClauseValue0,  .. setClauseProprertyN = setClauseValueN  | @i = 0  
WHERE <predicate>  
  
[SELECT <returning>   
 FROM <target>  
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]  
```  
  
 <span data-ttu-id="8665d-180">La clausola set include la clausola set falsa ("@i = 0") solo se non sono specificate clausole alcun set.</span><span class="sxs-lookup"><span data-stu-id="8665d-180">The set clause has the fake set clause ("@i = 0") only if no set clauses are specified.</span></span> <span data-ttu-id="8665d-181">In questo modo si garantisce che le colonne calcolate dall'archivio vengano ricalcolate.</span><span class="sxs-lookup"><span data-stu-id="8665d-181">This is to ensure that any store-computed columns are recomputed.</span></span>  
  
 <span data-ttu-id="8665d-182">Solo se la proprietà Returning non è null, viene generata un'istruzione Select per restituire le proprietà specificate nella proprietà Returning.</span><span class="sxs-lookup"><span data-stu-id="8665d-182">Only if the Returning property is not null, a select statement is generated to return the properties specified in the Returning property.</span></span>  
  
 <span data-ttu-id="8665d-183">Nell'esempio riportato di seguito viene usato il modello incluso nel provider di esempio per generare un comando di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="8665d-183">The following example uses the model that is included with the sample provider to generate an update command.</span></span>  
  
 <span data-ttu-id="8665d-184">Nel codice utente seguente viene aggiornato un oggetto Category:</span><span class="sxs-lookup"><span data-stu-id="8665d-184">The following user code updates a Category:</span></span>  
  
```  
using (NorthwindEntities northwindContext = new NorthwindEntities()) {  
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "Test Category").First();  
   c.CategoryName = "New test name";  
   northwindContext.SaveChanges();  
}  
```  
  
 <span data-ttu-id="8665d-185">In questo codice utente viene prodotto il seguente albero dei comandi passato al provider:</span><span class="sxs-lookup"><span data-stu-id="8665d-185">This user code produces the following command tree, which is passed to the provider:</span></span>  
  
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
  
 <span data-ttu-id="8665d-186">Il provider di esempio produce il comando di archiviazione seguente:</span><span class="sxs-lookup"><span data-stu-id="8665d-186">The sample provider produces the following store command:</span></span>  
  
```  
update [dbo].[Categories]  
set [CategoryName] = @p0  
where ([CategoryID] = @p1)   
```  
  
### <a name="generating-a-delete-sql-command"></a><span data-ttu-id="8665d-187">Generazione di un comando SQL di eliminazione</span><span class="sxs-lookup"><span data-stu-id="8665d-187">Generating a Delete SQL Command</span></span>  
 <span data-ttu-id="8665d-188">Per un determinato DbDeleteCommandTree, il comando DELETE generato si basa sul modello seguente:</span><span class="sxs-lookup"><span data-stu-id="8665d-188">For a given DbDeleteCommandTree, the generated DELETE command is based on the following template:</span></span>  
  
```  
-- DELETE Template   
DELETE <target>   
WHERE <predicate>  
```  
  
 <span data-ttu-id="8665d-189">Nell'esempio riportato di seguito viene usato il modello incluso nel provider di esempio per generare un comando di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="8665d-189">The following example uses the model that is included with the sample provider to generate a delete command.</span></span>  
  
 <span data-ttu-id="8665d-190">Nel codice utente seguente viene eliminato un oggetto Category:</span><span class="sxs-lookup"><span data-stu-id="8665d-190">The following user code deletes a Category:</span></span>  
  
```  
using (NorthwindEntities northwindContext = new NorthwindEntities()) {  
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "New test name").First();  
   northwindContext.DeleteObject(c);  
   northwindContext.SaveChanges();  
}  
```  
  
 <span data-ttu-id="8665d-191">In questo codice utente viene prodotto il seguente albero dei comandi passato al provider:</span><span class="sxs-lookup"><span data-stu-id="8665d-191">This user code produces the following command tree, which is passed to the provider.</span></span>  
  
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
  
 <span data-ttu-id="8665d-192">Il provider di esempio produce il comando di archiviazione seguente:</span><span class="sxs-lookup"><span data-stu-id="8665d-192">The following store command is produced by the sample provider:</span></span>  
  
```  
delete [dbo].[Categories]  
where ([CategoryID] = @p0)  
```  
  
## <a name="see-also"></a><span data-ttu-id="8665d-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8665d-193">See Also</span></span>  
 [<span data-ttu-id="8665d-194">Scrittura di un provider di dati Entity Framework</span><span class="sxs-lookup"><span data-stu-id="8665d-194">Writing an Entity Framework Data Provider</span></span>](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
