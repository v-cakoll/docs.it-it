---
title: Architettura e progettazione
ms.date: 03/30/2017
ms.assetid: bd738d39-00e2-4bab-b387-90aac1a014bd
ms.openlocfilehash: 5a0d8aac401a3485bc5f158bcda893ad9ab424e8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530470"
---
# <a name="architecture-and-design"></a><span data-ttu-id="bbb40-102">Architettura e progettazione</span><span class="sxs-lookup"><span data-stu-id="bbb40-102">Architecture and Design</span></span>
<span data-ttu-id="bbb40-103">Il modulo di generazione SQL nel [Provider di esempio](https://go.microsoft.com/fwlink/?LinkId=180616) viene implementato come un visitatore dell'albero delle espressioni che rappresenta l'albero dei comandi.</span><span class="sxs-lookup"><span data-stu-id="bbb40-103">The SQL generation module in the [Sample Provider](https://go.microsoft.com/fwlink/?LinkId=180616) is implemented as a visitor on the expression tree that represents the command tree.</span></span> <span data-ttu-id="bbb40-104">La generazione viene eseguita in un unico passaggio sull'albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="bbb40-104">The generation is done in a single pass over the expression tree.</span></span>  
  
 <span data-ttu-id="bbb40-105">I nodi dell'albero vengono elaborati dal basso verso l'alto.</span><span class="sxs-lookup"><span data-stu-id="bbb40-105">The nodes of the tree are processed from the bottom up.</span></span> <span data-ttu-id="bbb40-106">Prima viene prodotta una struttura intermedia: SqlSelectStatement o SqlBuilder. Entrambe implementano ISqlFragment.</span><span class="sxs-lookup"><span data-stu-id="bbb40-106">First, an intermediate structure is produced: SqlSelectStatement or SqlBuilder, both implementing ISqlFragment.</span></span> <span data-ttu-id="bbb40-107">Successivamente da tale struttura viene prodotta l'istruzione SQL della stringa.</span><span class="sxs-lookup"><span data-stu-id="bbb40-107">Next, the string SQL statement is produced from that structure.</span></span> <span data-ttu-id="bbb40-108">Esistono due motivi per cui viene prodotta la struttura intermedia:</span><span class="sxs-lookup"><span data-stu-id="bbb40-108">There are two reasons for the intermediate structure:</span></span>  
  
-   <span data-ttu-id="bbb40-109">Un'istruzione SQL SELECT viene popolata in modo non corretto da un punto di vista logico.</span><span class="sxs-lookup"><span data-stu-id="bbb40-109">Logically, a SQL SELECT statement is populated out of order.</span></span> <span data-ttu-id="bbb40-110">I nodi che partecipano alla clausola FROM vengono visitati prima di quelli che partecipano alla clausola WHERE, GROUP BY e ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="bbb40-110">The nodes that participate in the FROM clause are visited before the nodes that participate in the WHERE, GROUP BY, and the ORDER BY clause.</span></span>  
  
-   <span data-ttu-id="bbb40-111">Per evitare conflitti durante la ridenominazione degli alias, è necessario identificare tutti gli alias usati.</span><span class="sxs-lookup"><span data-stu-id="bbb40-111">To rename aliases, you must identify all used aliases to avoid collisions during renaming.</span></span> <span data-ttu-id="bbb40-112">È possibile rinviare le scelte di ridenominazione in SqlBuilder, usando gli oggetti Symbol per rappresentare le colonne candidate per la ridenominazione.</span><span class="sxs-lookup"><span data-stu-id="bbb40-112">To defer the renaming choices in SqlBuilder, use Symbol objects to represent the columns that are candidates for renaming.</span></span>  
  
 <span data-ttu-id="bbb40-113">![Diagramma](../../../../../docs/framework/data/adonet/ef/media/de1ca705-4f7c-4d2d-ace5-afefc6d3cefa.gif "de1ca705-4f7c-4d2d-ace5-afefc6d3cefa")</span><span class="sxs-lookup"><span data-stu-id="bbb40-113">![Diagram](../../../../../docs/framework/data/adonet/ef/media/de1ca705-4f7c-4d2d-ace5-afefc6d3cefa.gif "de1ca705-4f7c-4d2d-ace5-afefc6d3cefa")</span></span>  
  
 <span data-ttu-id="bbb40-114">Nella prima fase, durante la visita dell'albero delle espressioni, le espressioni vengono raggruppate in oggetti SqlSelectStatements e i join e gli alias di join vengono resi bidimensionali.</span><span class="sxs-lookup"><span data-stu-id="bbb40-114">In the first phase, while visiting the expression tree, expressions are grouped into SqlSelectStatements, joins are flattened, and join aliases are flattened.</span></span> <span data-ttu-id="bbb40-115">Durante questo passaggio, gli oggetti Symbol rappresentano colonne o alias di input che possono essere rinominati.</span><span class="sxs-lookup"><span data-stu-id="bbb40-115">During this pass, Symbol objects represent columns or input aliases that may be renamed.</span></span>  
  
 <span data-ttu-id="bbb40-116">Nella seconda fase, durante la produzione della stringa effettiva, gli alias vengono rinominati.</span><span class="sxs-lookup"><span data-stu-id="bbb40-116">In the second phase, while producing the actual string, aliases are renamed.</span></span>  
  
## <a name="data-structures"></a><span data-ttu-id="bbb40-117">Strutture di dati</span><span class="sxs-lookup"><span data-stu-id="bbb40-117">Data Structures</span></span>  
 <span data-ttu-id="bbb40-118">In questa sezione illustra i tipi usati nel [Provider di esempio](https://go.microsoft.com/fwlink/?LinkId=180616) consente di compilare un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="bbb40-118">This section discusses the types used in the [Sample Provider](https://go.microsoft.com/fwlink/?LinkId=180616) that you use to build a SQL statement.</span></span>  
  
### <a name="isqlfragment"></a><span data-ttu-id="bbb40-119">ISqlFragment</span><span class="sxs-lookup"><span data-stu-id="bbb40-119">ISqlFragment</span></span>  
 <span data-ttu-id="bbb40-120">Questa sezione analizza le classi che implementano l'interfaccia ISqlFragment che ha una duplice funzione:</span><span class="sxs-lookup"><span data-stu-id="bbb40-120">This section covers the classes that implement the ISqlFragment interface, which serves two purposes:</span></span>  
  
-   <span data-ttu-id="bbb40-121">Un tipo restituito comune per tutti i metodi del visitatore.</span><span class="sxs-lookup"><span data-stu-id="bbb40-121">A common return type for all the visitor methods.</span></span>  
  
-   <span data-ttu-id="bbb40-122">Fornisce un metodo per scrivere la stringa SQL finale.</span><span class="sxs-lookup"><span data-stu-id="bbb40-122">Gives a method to write the final SQL string.</span></span>  
  
```  
internal interface ISqlFragment {  
   void WriteSql(SqlWriter writer, SqlGenerator sqlGenerator);  
}  
```  
  
#### <a name="sqlbuilder"></a><span data-ttu-id="bbb40-123">SqlBuilder</span><span class="sxs-lookup"><span data-stu-id="bbb40-123">SqlBuilder</span></span>  
 <span data-ttu-id="bbb40-124">SqlBuilder è un dispositivo di raccolta per la stringa SQL finale, simile a StringBuilder.</span><span class="sxs-lookup"><span data-stu-id="bbb40-124">SqlBuilder is a gathering device for the final SQL string, similar to StringBuilder.</span></span> <span data-ttu-id="bbb40-125">È formato dalle stringhe che costituiscono l'SQL finale, insieme all'oggetto ISqlFragments che può essere convertito in stringhe.</span><span class="sxs-lookup"><span data-stu-id="bbb40-125">It consists of the strings that make up the final SQL, along with ISqlFragments that can be converted into strings.</span></span>  
  
```  
internal sealed class SqlBuilder : ISqlFragment {  
   public void Append(object s)  
   public void AppendLine()  
   public bool IsEmpty  
}  
```  
  
#### <a name="sqlselectstatement"></a><span data-ttu-id="bbb40-126">SqlSelectStatement</span><span class="sxs-lookup"><span data-stu-id="bbb40-126">SqlSelectStatement</span></span>  
 <span data-ttu-id="bbb40-127">SqlSelectStatement rappresenta un'istruzione SQL SELECT canonica della forma "SELECT...</span><span class="sxs-lookup"><span data-stu-id="bbb40-127">SqlSelectStatement represents a canonical SQL SELECT statement of the shape "SELECT …</span></span> <span data-ttu-id="bbb40-128">DA..</span><span class="sxs-lookup"><span data-stu-id="bbb40-128">FROM  ..</span></span> <span data-ttu-id="bbb40-129">POSIZIONE IN CUI...</span><span class="sxs-lookup"><span data-stu-id="bbb40-129">WHERE …</span></span> <span data-ttu-id="bbb40-130">RAGGRUPPA PER...</span><span class="sxs-lookup"><span data-stu-id="bbb40-130">GROUP BY …</span></span> <span data-ttu-id="bbb40-131">ORDER BY".</span><span class="sxs-lookup"><span data-stu-id="bbb40-131">ORDER BY".</span></span>  
  
 <span data-ttu-id="bbb40-132">Ognuna delle clausole SQL viene rappresentata da un oggetto StringBuilder</span><span class="sxs-lookup"><span data-stu-id="bbb40-132">Each of the SQL clauses is represented by a StringBuilder.</span></span> <span data-ttu-id="bbb40-133">e inoltre rileva se è stato specificato Distinct e se l'istruzione è al livello più alto.</span><span class="sxs-lookup"><span data-stu-id="bbb40-133">In addition, it tracks whether Distinct has been specified and whether the statement is topmost.</span></span> <span data-ttu-id="bbb40-134">Se l'istruzione non è al livello più alto, la clausola ORDER BY viene omessa, a meno che nell'istruzione non sia inclusa anche una clausola TOP.</span><span class="sxs-lookup"><span data-stu-id="bbb40-134">If the statement is not topmost, the ORDER BY clause is omitted unless the statement also has a TOP clause.</span></span>  
  
 <span data-ttu-id="bbb40-135">FromExtents contiene l'elenco di input per l'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="bbb40-135">FromExtents contains the list of inputs for the SELECT statement.</span></span> <span data-ttu-id="bbb40-136">Generalmente è presente un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="bbb40-136">There is usually just one element in this.</span></span> <span data-ttu-id="bbb40-137">È possibile che le istruzioni SELECT per i join contengano temporaneamente più di un elemento.</span><span class="sxs-lookup"><span data-stu-id="bbb40-137">SELECT statements for joins may temporarily have more than one element.</span></span>  
  
 <span data-ttu-id="bbb40-138">Se l'istruzione SELECT viene creata da un nodo di join, SqlSelectStatement gestisce un elenco di tutti gli extent che sono stati resi bidimensionali nel join in AllJoinExtents.</span><span class="sxs-lookup"><span data-stu-id="bbb40-138">If the SELECT statement is created by a Join node, SqlSelectStatement maintains a list of all the extents that have been flattened in the join in AllJoinExtents.</span></span> <span data-ttu-id="bbb40-139">OuterExtents rappresenta i riferimenti esterni di SqlSelectStatement e viene usato per la ridenominazione degli alias di input.</span><span class="sxs-lookup"><span data-stu-id="bbb40-139">OuterExtents represents outer references of the SqlSelectStatement and is used for input alias renaming.</span></span>  
  
```  
internal sealed class SqlSelectStatement : ISqlFragment {  
   internal bool IsDistinct { get, set };  
   internal bool IsTopMost  
  
   internal List<Symbol> AllJoinExtents { get, set };  
   internal List<Symbol> FromExtents { get};  
   internal Dictionary<Symbol, bool> OuterExtents { get};  
  
   internal TopClause Top { get, set };  
  
   internal SqlBuilder Select {get};  
   internal SqlBuilder From  
   internal SqlBuilder Where  
   internal SqlBuilder GroupBy  
   public SqlBuilder OrderBy  
}  
```  
  
#### <a name="topclause"></a><span data-ttu-id="bbb40-140">TopClause</span><span class="sxs-lookup"><span data-stu-id="bbb40-140">TopClause</span></span>  
 <span data-ttu-id="bbb40-141">TopClause rappresenta l'espressione TOP in un oggetto SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="bbb40-141">TopClause represents the TOP expression in a SqlSelectStatement.</span></span> <span data-ttu-id="bbb40-142">La proprietà TopCount indica il numero di righe TOP che devono essere selezionate.</span><span class="sxs-lookup"><span data-stu-id="bbb40-142">The TopCount property indicates how many TOP rows should be selected.</span></span>  <span data-ttu-id="bbb40-143">Se WithTies è true, TopClause è stato compilato da un oggetto DbLimitExpession.</span><span class="sxs-lookup"><span data-stu-id="bbb40-143">When WithTies is true, the TopClause was built from a DbLimitExpession.</span></span>  
  
```  
class TopClause : ISqlFragment {  
   internal bool WithTies {get}  
   internal ISqlFragment TopCount {get}  
   internal TopClause(ISqlFragment topCount, bool withTies)  
   internal TopClause(int topCount, bool withTies)  
}  
```  
  
### <a name="symbols"></a><span data-ttu-id="bbb40-144">Symbols</span><span class="sxs-lookup"><span data-stu-id="bbb40-144">Symbols</span></span>  
 <span data-ttu-id="bbb40-145">Le classi correlate ai simboli e la tabella dei simboli eseguono la ridenominazione degli alias di input, la bidimensionalità degli alias di join e la ridenominazione degli alias di colonna.</span><span class="sxs-lookup"><span data-stu-id="bbb40-145">The Symbol-related classes and the symbol table perform input alias renaming, join alias flattening, and column alias renaming.</span></span>  
  
 <span data-ttu-id="bbb40-146">La classe Symbol rappresenta un extent, un'istruzione SELECT annidata o una colonna.</span><span class="sxs-lookup"><span data-stu-id="bbb40-146">The Symbol class represents an extent, a nested SELECT statement, or a column.</span></span> <span data-ttu-id="bbb40-147">Viene usata in sostituzione di un alias effettivo per consentire che venga rinominato dopo essere stato usato e contiene inoltre informazioni aggiuntive relative all'elemento che rappresenta (come il tipo).</span><span class="sxs-lookup"><span data-stu-id="bbb40-147">It is used instead of an actual alias to allow for renaming after it has been used and it also carries additional information for the artifact it represents (like the type).</span></span>  
  
```  
class Symbol : ISqlFragment {  
   internal Dictionary<string, Symbol> Columns {get}  
   internal bool NeedsRenaming {get, set}  
   internal bool IsUnnest {get, set}   //not used  
  
   public string Name{get}  
   public string NewName {get,set}  
   internal TypeUsage Type {get, set}  
  
   public Symbol(string name, TypeUsage type)  
}  
```  
  
 <span data-ttu-id="bbb40-148">Name archivia l'alias originale per l'extent rappresentato, l'istruzione SELECT annidata o una colonna.</span><span class="sxs-lookup"><span data-stu-id="bbb40-148">Name stores the original alias for the represented extent, nested SELECT statement, or a column.</span></span>  
  
 <span data-ttu-id="bbb40-149">NewName archivia l'alias che verrà usato nell'istruzione SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="bbb40-149">NewName stores the alias that will be used in the SQL SELECT statement.</span></span> <span data-ttu-id="bbb40-150">Viene originariamente impostato su Name e rinominato solo se necessario quando viene generata la query della stringa finale.</span><span class="sxs-lookup"><span data-stu-id="bbb40-150">It is originally set to Name, and only renamed if needed when generating the final string query.</span></span>  
  
 <span data-ttu-id="bbb40-151">Type è utile solo per i simboli che rappresentano extent e istruzioni SELECT annidate.</span><span class="sxs-lookup"><span data-stu-id="bbb40-151">Type is only useful for symbols representing extents and nested SELECT statements.</span></span>  
  
#### <a name="symbolpair"></a><span data-ttu-id="bbb40-152">SymbolPair</span><span class="sxs-lookup"><span data-stu-id="bbb40-152">SymbolPair</span></span>  
 <span data-ttu-id="bbb40-153">La classe SymbolPair viene usata per rendere bidimensionali i record.</span><span class="sxs-lookup"><span data-stu-id="bbb40-153">The SymbolPair class addresses record flattening.</span></span>  
  
 <span data-ttu-id="bbb40-154">Si consideri un'espressione di proprietà D (v, "j3.j2.j1.a.x") in cui v è un VarRef v, j1, j2 j3 sono join, a è un extent e x è una colonna.</span><span class="sxs-lookup"><span data-stu-id="bbb40-154">Consider a property expression D(v, "j3.j2.j1.a.x") where v is a VarRef, j1, j2, j3 are joins, a is an extent, and x is a columns.</span></span>  
  
 <span data-ttu-id="bbb40-155">Tale espressione dovrà essere convertita in {j'}.{x'}.</span><span class="sxs-lookup"><span data-stu-id="bbb40-155">This has to be translated eventually into {j'}.{x'}.</span></span> <span data-ttu-id="bbb40-156">Il campo di origine rappresenta l'oggetto SqlStatement più esterno che rappresenta un'espressione di join, ad esempio j2. Si tratta sempre di un simbolo Join.</span><span class="sxs-lookup"><span data-stu-id="bbb40-156">The source field represents the outermost SqlStatement, representing a join expression (say j2); this is always a Join symbol.</span></span> <span data-ttu-id="bbb40-157">Il campo di colonna si sposta da un simbolo di join al successivo, fino ad arrestarsi in corrispondenza di un simbolo non di join.</span><span class="sxs-lookup"><span data-stu-id="bbb40-157">The column field moves from one join symbol to the next until it stops at a non-join symbol.</span></span> <span data-ttu-id="bbb40-158">Tale simbolo viene restituito quando viene visitato un oggetto DbPropertyExpression ma non viene mai aggiunto a un oggetto SqlBuilder.</span><span class="sxs-lookup"><span data-stu-id="bbb40-158">This is returned when visiting a DbPropertyExpression but is never added to a SqlBuilder.</span></span>  
  
```  
class SymbolPair : ISqlFragment {  
   public Symbol Source;  
   public Symbol Column;  
   public SymbolPair(Symbol source, Symbol column)  
}  
```  
  
#### <a name="joinsymbol"></a><span data-ttu-id="bbb40-159">JoinSymbol</span><span class="sxs-lookup"><span data-stu-id="bbb40-159">JoinSymbol</span></span>  
 <span data-ttu-id="bbb40-160">Un simbolo Join è un simbolo che rappresenta un'istruzione SELECT annidata con un join o un input di join.</span><span class="sxs-lookup"><span data-stu-id="bbb40-160">A Join symbol is a Symbol that represents a nested SELECT statement with a join or a join input.</span></span>  
  
```  
internal sealed class JoinSymbol : Symbol {  
   internal List<Symbol> ColumnList {get, set}  
   internal List<Symbol> ExtentList {get}  
   internal List<Symbol> FlattenedExtentList {get, set}  
   internal Dictionary<string, Symbol> NameToExtent {get}  
   internal bool IsNestedJoin {get, set}  
  
   public JoinSymbol(string name, TypeUsage type, List<Symbol> extents)  
}  
```  
  
 <span data-ttu-id="bbb40-161">ColumnList rappresenta l'elenco di colonne della clausola SELECT quando questo simbolo rappresenta un'istruzione SQL SELECT.</span><span class="sxs-lookup"><span data-stu-id="bbb40-161">ColumnList represents the list of columns in the SELECT clause if this symbol represents a SQL SELECT statement.</span></span> <span data-ttu-id="bbb40-162">ExtentList è l'elenco degli extent inclusi nella clausola SELECT.</span><span class="sxs-lookup"><span data-stu-id="bbb40-162">ExtentList is the list of extents in the SELECT clause.</span></span> <span data-ttu-id="bbb40-163">Se il join presenta più extent resi bidimensionali al livello superiore, FlattenedExtentList rileva gli extent per assicurarsi che i rispettivi alias vengano rinominati correttamente.</span><span class="sxs-lookup"><span data-stu-id="bbb40-163">If the join has multiple extents flattened at the top level, FlattenedExtentList tracks the extents to ensure that extent aliases are renamed correctly.</span></span>  
  
 <span data-ttu-id="bbb40-164">NameToExtent include in ExtentList tutti gli extent di un dizionario.</span><span class="sxs-lookup"><span data-stu-id="bbb40-164">NameToExtent has all the extents in ExtentList as a dictionary.</span></span> <span data-ttu-id="bbb40-165">IsNestedJoin viene usato per determinare se un oggetto JoinSymbol è un normale simbolo di join oppure un simbolo con un oggetto SqlSelectStatement corrispondente.</span><span class="sxs-lookup"><span data-stu-id="bbb40-165">IsNestedJoin is used to determine whether a JoinSymbol is an ordinary join symbol or one that has a corresponding SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="bbb40-166">Tutti gli elenchi vengono impostati esattamente una volta e quindi usati per ricerche o enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bbb40-166">All the lists are set exactly once and then used for lookups or enumeration.</span></span>  
  
#### <a name="symboltable"></a><span data-ttu-id="bbb40-167">SymbolTable</span><span class="sxs-lookup"><span data-stu-id="bbb40-167">SymbolTable</span></span>  
 <span data-ttu-id="bbb40-168">SymbolTable viene usato per risolvere i nomi di variabile in simboli.</span><span class="sxs-lookup"><span data-stu-id="bbb40-168">SymbolTable is used to resolve variable names to Symbols.</span></span> <span data-ttu-id="bbb40-169">SymbolTable viene implementato come stack con una nuova voce per ogni ambito.</span><span class="sxs-lookup"><span data-stu-id="bbb40-169">SymbolTable is implemented as a stack with a new entry for each scope.</span></span> <span data-ttu-id="bbb40-170">Le ricerche vengono eseguite dalla parte superiore alla parte inferiore dello stack, fino a che non viene trovata una voce.</span><span class="sxs-lookup"><span data-stu-id="bbb40-170">Lookups search from the top of the stack to the bottom until an entry is found.</span></span>  
  
```  
internal sealed class SymbolTable {  
   internal void EnterScope()  
   internal void ExitScope()  
   internal void Add(string name, Symbol value)  
   internal Symbol Lookup(string name)  
}  
```  
  
 <span data-ttu-id="bbb40-171">Esiste un solo oggetto SymbolTable per un'istanza del modulo di generazione SQL.</span><span class="sxs-lookup"><span data-stu-id="bbb40-171">There is only one SymbolTable per one instance of the Sql Generation module.</span></span> <span data-ttu-id="bbb40-172">Per ogni nodo relazionale vengono immessi e terminati ambiti.</span><span class="sxs-lookup"><span data-stu-id="bbb40-172">Scopes are entered and exited for each relational node.</span></span> <span data-ttu-id="bbb40-173">Tutti i simboli inclusi nei primi ambiti sono visibili agli ambiti successivi, a meno che non siano nascosti dagli altri simboli con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="bbb40-173">All symbols in earlier scopes are visible to later scopes unless hidden by other symbols with the same name.</span></span>  
  
### <a name="global-state-for-the-visitor"></a><span data-ttu-id="bbb40-174">Stato globale per il visitatore</span><span class="sxs-lookup"><span data-stu-id="bbb40-174">Global State for the Visitor</span></span>  
 <span data-ttu-id="bbb40-175">Come supporto nelle operazioni di ridenominazione di alias e colonne, è utile tenere un elenco di tutti i nomi di colonna (AllColumnNames) e degli alias degli extent (AllExtentNames) usati nel primo passaggio sull'albero della query.</span><span class="sxs-lookup"><span data-stu-id="bbb40-175">To assist in renaming of aliases and columns, maintain a list of all the column names (AllColumnNames) and extent aliases (AllExtentNames) that have been used in the first pass over the query tree.</span></span>  <span data-ttu-id="bbb40-176">La tabella dei simboli consente di risolvere i nomi di variabile in simboli.</span><span class="sxs-lookup"><span data-stu-id="bbb40-176">The symbol table resolves variable names to Symbols.</span></span> <span data-ttu-id="bbb40-177">IsVarRefSingle viene usato solo a scopo di verifica e non è strettamente necessario.</span><span class="sxs-lookup"><span data-stu-id="bbb40-177">IsVarRefSingle is only used for verification purposes, it is not strictly necessary.</span></span>  
  
 <span data-ttu-id="bbb40-178">I due stack usati tramite CurrentSelectStatement e IsParentAJoin vengono usati per passare i "parametri" dai nodi padre ai nodi figlio, dal momento che il modello di visitatore non consente di passare i parametri.</span><span class="sxs-lookup"><span data-stu-id="bbb40-178">The two stacks used via CurrentSelectStatement and IsParentAJoin are used to pass "parameters" from parent to child nodes, since the visitor pattern does not allow us to pass parameters.</span></span>  
  
```  
internal Dictionary<string, int> AllExtentNames {get}  
internal Dictionary<string, int> AllColumnNames {get}  
SymbolTable symbolTable = new SymbolTable();  
bool isVarRefSingle = false;  
  
Stack<SqlSelectStatement> selectStatementStack;  
private SqlSelectStatement CurrentSelectStatement{get}  
  
Stack<bool> isParentAJoinStack;  
private bool IsParentAJoin{get}  
```  
  
## <a name="common-scenarios"></a><span data-ttu-id="bbb40-179">Scenari comuni</span><span class="sxs-lookup"><span data-stu-id="bbb40-179">Common Scenarios</span></span>  
 <span data-ttu-id="bbb40-180">Questa sezione illustra gli scenari comuni del provider.</span><span class="sxs-lookup"><span data-stu-id="bbb40-180">This section discusses common provider scenarios.</span></span>  
  
### <a name="grouping-expression-nodes-into-sql-statements"></a><span data-ttu-id="bbb40-181">Raggruppamento di nodi di espressione in Istruzioni SQL</span><span class="sxs-lookup"><span data-stu-id="bbb40-181">Grouping Expression Nodes into SQL Statements</span></span>  
 <span data-ttu-id="bbb40-182">Quando si incontra il primo nodo relazionale (in genere un extent DbScanExpression) durante la visita dell'albero dal basso verso l'alto, viene creato un oggetto SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="bbb40-182">A SqlSelectStatement is created when the first relational node is encountered (typically a DbScanExpression extent) when visiting the tree from the bottom up.</span></span> <span data-ttu-id="bbb40-183">Per produrre un'istruzione SQL SELECT con il minor numero possibile di query annidate, aggregare in tale oggetto SqlSelectStatement il maggior numero possibile di nodi padre.</span><span class="sxs-lookup"><span data-stu-id="bbb40-183">To produce a SQL SELECT statement with as few nested queries as possible, aggregate as many of its parent nodes as possible in that SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="bbb40-184">La decisione relativa alla possibilità di aggiungere un nodo specificato (relazionale) all'oggetto SqlSelectStatement corrente (quello restituito durante la visita dell'input) o alla necessità di avviare una nuova istruzione viene elaborata dal metodo IsCompatible e dipende dagli elementi già inclusi in SqlSelectStatement, ovvero dai nodi che si trovano al di sotto del nodo specificato.</span><span class="sxs-lookup"><span data-stu-id="bbb40-184">The decision of whether a given (relational) node can be added to the current SqlSelectStatement (the one returned when visiting the input) or if a new statement needs to be started is computed by the method IsCompatible and depends on what is already in the SqlSelectStatement, which depends on what nodes were below the given node.</span></span>  
  
 <span data-ttu-id="bbb40-185">In genere, se le clausole dell'istruzione SQL vengono valutate dopo le clausole in cui i nodi considerati per l'unione non sono vuoti, non è possibile aggiungere il nodo all'istruzione corrente.</span><span class="sxs-lookup"><span data-stu-id="bbb40-185">Typically, if SQL statement clauses are evaluated after clauses where the nodes being considered for merging are not empty, the node cannot be added to the current statement.</span></span> <span data-ttu-id="bbb40-186">Se ad esempio il nodo successivo è un filtro, tale nodo può essere incorporato nell'oggetto SqlSelectStatement corrente solo se si verificano le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbb40-186">For example, if the next node is a Filter, that node can be incorporated into the current SqlSelectStatement only if the following is true:</span></span>  
  
-   <span data-ttu-id="bbb40-187">L'elenco SELECT è vuoto.</span><span class="sxs-lookup"><span data-stu-id="bbb40-187">The SELECT list is empty.</span></span> <span data-ttu-id="bbb40-188">Se l'elenco SELECT non è vuoto, l'elenco di selezione è stato prodotto da un nodo che precede il filtro e il predicato può fare riferimento alle colonne prodotte dall'elenco SELECT.</span><span class="sxs-lookup"><span data-stu-id="bbb40-188">If the SELECT list is not empty, the select list was produced by a node preceding the filter and the predicate may refer to columns produced by that SELECT list.</span></span>  
  
-   <span data-ttu-id="bbb40-189">La classe GROUPBY è vuota.</span><span class="sxs-lookup"><span data-stu-id="bbb40-189">The GROUPBY is empty.</span></span> <span data-ttu-id="bbb40-190">Se GROUPBY non è vuota, l'aggiunta del filtro comporterebbe l'applicazione di filtri prima del raggruppamento e tale procedura non è corretta.</span><span class="sxs-lookup"><span data-stu-id="bbb40-190">If the GROUPBY is not empty, adding the filter would mean filtering before grouping, which is not correct.</span></span>  
  
-   <span data-ttu-id="bbb40-191">La clausola TOP è vuota.</span><span class="sxs-lookup"><span data-stu-id="bbb40-191">The TOP clause is empty.</span></span> <span data-ttu-id="bbb40-192">Se la clausola TOP non è vuota, l'aggiunta del filtro comporterebbe l'applicazione di filtri prima dell'esecuzione di TOP e tale procedura non è corretta.</span><span class="sxs-lookup"><span data-stu-id="bbb40-192">If the TOP clause is not empty, adding the filter would mean filtering before doing TOP, which is not correct.</span></span>  
  
 <span data-ttu-id="bbb40-193">Queste indicazioni non valgono per i nodi non relazionali come DbConstantExpression o le espressioni aritmetiche, poiché questi sono sempre inclusi come parte di un oggetto SqlSelectStatement esistente.</span><span class="sxs-lookup"><span data-stu-id="bbb40-193">This does not apply to non-relational nodes like DbConstantExpression or arithmetic expressions, because these are always included as part of an existing SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="bbb40-194">Quando inoltre si incontra la radice dell'albero dei join (un nodo join privo di join padre), viene avviato un nuovo oggetto SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="bbb40-194">Also, when encountering the root of join tree (a join node that does not have a join parent), a new SqlSelectStatement is started.</span></span> <span data-ttu-id="bbb40-195">Tutti i rispettivi join figlio del lato sinistro vengono aggregati nell'oggetto SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="bbb40-195">All of its left spine join children are aggregated into that SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="bbb40-196">Ogni qualvolta viene avviato un nuovo oggetto SqlSelectStatement e quello corrente viene aggiunto all'input, può essere necessario completare l'oggetto SqlSelectStatement corrente aggiungendo colonne di proiezione (una clausola SELECT), se non ne esiste già una.</span><span class="sxs-lookup"><span data-stu-id="bbb40-196">Whenever a new SqlSelectStatement is started, and the current one is added to the input, the current SqlSelectStatement may need to be completed by adding projection columns (a SELECT clause) if one does not exist.</span></span> <span data-ttu-id="bbb40-197">È possibile eseguire questa operazione con il metodo AddDefaultColumns che analizza FromExtents di SqlSelectStatement e aggiunge all'elenco delle colonne previste tutte le colonne che rientrano nell'ambito dell'elenco di extent rappresentato da FromExtents.</span><span class="sxs-lookup"><span data-stu-id="bbb40-197">This is done with the method AddDefaultColumns, which looks at the FromExtents of the SqlSelectStatement and adds all the columns that the list of extents represented by FromExtents brings in scope to the list of projected columns.</span></span> <span data-ttu-id="bbb40-198">Ciò accade in quanto a questo punto non è noto a quali colonne fanno riferimento gli altri nodi.</span><span class="sxs-lookup"><span data-stu-id="bbb40-198">This is done, because at that point, it is unknown which columns are referenced by the other nodes.</span></span> <span data-ttu-id="bbb40-199">È possibile ottimizzare la procedura includendo nella proiezione le sole colonne che possono essere usate in un momento successivo.</span><span class="sxs-lookup"><span data-stu-id="bbb40-199">This can be optimized to only project the columns that can later be used.</span></span>  
  
### <a name="join-flattening"></a><span data-ttu-id="bbb40-200">Bidimensionalità del join</span><span class="sxs-lookup"><span data-stu-id="bbb40-200">Join Flattening</span></span>  
 <span data-ttu-id="bbb40-201">La proprietà IsParentAJoin consente di stabilire se è possibile rendere bidimensionale un join specificato.</span><span class="sxs-lookup"><span data-stu-id="bbb40-201">The IsParentAJoin property helps determine whether a given join can be flattened.</span></span> <span data-ttu-id="bbb40-202">In particolare, IsParentAJoin restituisce `true` solo per il figlio sinistro di un join e per ogni oggetto DbScanExpression che costituisce un input immediato per un join. In questo caso, il nodo figlio riusa lo stesso oggetto SqlSelectStatement che verrà successivamente usato dal padre.</span><span class="sxs-lookup"><span data-stu-id="bbb40-202">In particular, IsParentAJoin returns `true` only for the left child of a join and for each DbScanExpression that is an immediate input to a join, in which case that child node reuses the same SqlSelectStatement that the parent would later use.</span></span> <span data-ttu-id="bbb40-203">Per altre informazioni, vedere "Unione di espressioni".</span><span class="sxs-lookup"><span data-stu-id="bbb40-203">For more information, see "Join Expressions".</span></span>  
  
### <a name="input-alias-redirecting"></a><span data-ttu-id="bbb40-204">Reindirizzamento degli alias di input</span><span class="sxs-lookup"><span data-stu-id="bbb40-204">Input Alias Redirecting</span></span>  
 <span data-ttu-id="bbb40-205">È possibile ottenere il reindirizzamento degli alias di input usando la tabella dei simboli.</span><span class="sxs-lookup"><span data-stu-id="bbb40-205">Input alias redirecting is accomplished with the symbol table.</span></span>  
  
 <span data-ttu-id="bbb40-206">Per illustrare il reindirizzamento di alias di input, fare riferimento al primo esempio nella [generazione di SQL dagli alberi dei comandi - procedure consigliate](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="bbb40-206">To explain input alias redirecting, refer to the first example in [Generating SQL from Command Trees - Best Practices](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md).</span></span>  <span data-ttu-id="bbb40-207">In questo esempio "a" deve essere reindirizzato in "b" nella proiezione.</span><span class="sxs-lookup"><span data-stu-id="bbb40-207">There "a" needed to be redirected to "b" in the projection.</span></span>  
  
 <span data-ttu-id="bbb40-208">Quando viene creato un oggetto SqlSelectStatement, l'extent che costituisce l'input per il nodo viene inserito nella proprietà From dell'oggetto SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="bbb40-208">When a SqlSelectStatement object is created, the extent that is the input to the node is put in the From property of the SqlSelectStatement.</span></span> <span data-ttu-id="bbb40-209">Per rappresentare tale extent, viene creato un oggetto Symbol (<simbolo_b>) in base al nome dell'associazione di input ("b") e "AS " +  <simbolo_b> viene aggiunto alla clausola FROM.</span><span class="sxs-lookup"><span data-stu-id="bbb40-209">A Symbol (<symbol_b>) is created based on the input binding name ("b") to represent that extent and "AS  " +  <symbol_b> is appended to the From Clause.</span></span>  <span data-ttu-id="bbb40-210">Il simbolo viene inoltre aggiunto alla proprietà FromExtents.</span><span class="sxs-lookup"><span data-stu-id="bbb40-210">The symbol is also added to the FromExtents property.</span></span>  
  
 <span data-ttu-id="bbb40-211">Il simbolo viene aggiunto anche alla tabella dei simboli per consentire il collegamento al nome dell'associazione di input ("b", <symbol_b>).</span><span class="sxs-lookup"><span data-stu-id="bbb40-211">The symbol is also added to the symbol table to link the input binding name to it ("b", <symbol_b>).</span></span>  
  
 <span data-ttu-id="bbb40-212">Se un nodo successivo riusa lo stesso oggetto SqlSelectStatement, viene aggiunta una voce alla tabella dei simboli per collegare il rispettivo nome dell'associazione di input al simbolo.</span><span class="sxs-lookup"><span data-stu-id="bbb40-212">If a subsequent node reuses that SqlSelectStatement, it adds an entry to the symbol table to link its input binding name to that symbol.</span></span> <span data-ttu-id="bbb40-213">In questo esempio, DbProjectExpression con il nome dell'associazione di input di "a" riutilizzerebbe SqlSelectStatement e aggiungere ("a", \< symbol_b >) alla tabella.</span><span class="sxs-lookup"><span data-stu-id="bbb40-213">In our example, the DbProjectExpression with the input binding name of "a" would reuse the SqlSelectStatement and add ("a", \< symbol_b>) to the table.</span></span>  
  
 <span data-ttu-id="bbb40-214">Quando le espressioni fanno riferimento al nome dell'associazione di input del nodo che sta riusando l'oggetto SqlSelectStatement, tale riferimento viene risolto usando la tabella dei simboli nel simbolo reindirizzato corretto.</span><span class="sxs-lookup"><span data-stu-id="bbb40-214">When expressions reference the input binding name of the node that is reusing the SqlSelectStatement, that reference is resolved using the symbol table to the correct redirected symbol.</span></span> <span data-ttu-id="bbb40-215">Quando "a" da "a.x" viene risolto durante la visita dell'oggetto DbVariableReferenceExpression che rappresenta "a", verrà risolto nell'oggetto Symbol <symbol_b>.</span><span class="sxs-lookup"><span data-stu-id="bbb40-215">When "a" from "a.x" is resolved while visiting the DbVariableReferenceExpression representing "a" it will resolve to the Symbol <symbol_b>.</span></span>  
  
### <a name="join-alias-flattening"></a><span data-ttu-id="bbb40-216">Bidimensionalità degli alias di join</span><span class="sxs-lookup"><span data-stu-id="bbb40-216">Join Alias Flattening</span></span>  
 <span data-ttu-id="bbb40-217">Il bidimensionalità degli alias di join viene realizzata durante la visita di un oggetto DbPropertyExpression, come descritto nella sezione intitolata DbPropertyExpression.</span><span class="sxs-lookup"><span data-stu-id="bbb40-217">Join alias flattening is achieved when visiting a DbPropertyExpression as described in the section titled DbPropertyExpression.</span></span>  
  
### <a name="column-name-and-extent-alias-renaming"></a><span data-ttu-id="bbb40-218">Ridenominazione dei nomi di colonna e degli alias degli extent</span><span class="sxs-lookup"><span data-stu-id="bbb40-218">Column Name and Extent Alias Renaming</span></span>  
 <span data-ttu-id="bbb40-219">È possibile risolvere il problema della ridenominazione dei nomi di colonna e degli alias degli extent mediante l'uso di simboli che vengono semplicemente sostituiti dagli alias nella seconda fase della generazione, descritta nella sezione intitolata Seconda fase della generazione SQL: generazione della stringa di comando.</span><span class="sxs-lookup"><span data-stu-id="bbb40-219">The issue of column name and extent alias renaming is addressed by using symbols that only get substituted with aliases in the second phase of the generation described in the section titled Second Phase of SQL Generation: Generating the String Command.</span></span>  
  
## <a name="first-phase-of-the-sql-generation-visiting-the-expression-tree"></a><span data-ttu-id="bbb40-220">Prima fase della generazione SQL: visita dell'albero delle espressioni</span><span class="sxs-lookup"><span data-stu-id="bbb40-220">First Phase of the SQL Generation: Visiting the Expression Tree</span></span>  
 <span data-ttu-id="bbb40-221">Questa sezione descrive la prima fase di generazione SQL, quando viene visitata l'espressione che rappresenta la query e viene prodotta una struttura intermedia, ovvero un oggetto SqlSelectStatement o un oggetto SqlBuilder.</span><span class="sxs-lookup"><span data-stu-id="bbb40-221">This section describes the first phase of SQL generation, when the expression representing the query is visited and an intermediate structure is produced, either a SqlSelectStatement or a SqlBuilder.</span></span>  
  
 <span data-ttu-id="bbb40-222">Questa sezione descrive i principi su cui si basa la visita di diverse categorie del nodo di espressione e vengono forniti dettagli relativi alla visita di tipi di espressione specifici.</span><span class="sxs-lookup"><span data-stu-id="bbb40-222">This section describes the principles of visiting different expression node categories, and details of visiting specific expression types.</span></span>  
  
### <a name="relational-non-join-nodes"></a><span data-ttu-id="bbb40-223">Nodi relazionali (non join)</span><span class="sxs-lookup"><span data-stu-id="bbb40-223">Relational (Non-Join) Nodes</span></span>  
 <span data-ttu-id="bbb40-224">Di seguito vengono indicati i tipi di espressione che supportano nodi non join:</span><span class="sxs-lookup"><span data-stu-id="bbb40-224">The following expression types support non-join nodes:</span></span>  
  
-   <span data-ttu-id="bbb40-225">DbDistinctExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-225">DbDistinctExpression</span></span>  
  
-   <span data-ttu-id="bbb40-226">DbFilterExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-226">DbFilterExpression</span></span>  
  
-   <span data-ttu-id="bbb40-227">DbGroupByExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-227">DbGroupByExpression</span></span>  
  
-   <span data-ttu-id="bbb40-228">DbLimitExpession</span><span class="sxs-lookup"><span data-stu-id="bbb40-228">DbLimitExpession</span></span>  
  
-   <span data-ttu-id="bbb40-229">DbProjectExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-229">DbProjectExpression</span></span>  
  
-   <span data-ttu-id="bbb40-230">DbSkipExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-230">DbSkipExpression</span></span>  
  
-   <span data-ttu-id="bbb40-231">DbSortExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-231">DbSortExpression</span></span>  
  
 <span data-ttu-id="bbb40-232">Il modello che viene seguito per la visita di questi nodi è il seguente:</span><span class="sxs-lookup"><span data-stu-id="bbb40-232">Visiting these nodes follows the following pattern:</span></span>  
  
1.  <span data-ttu-id="bbb40-233">Visitare l'input relazionale e ottenere l'oggetto SqlSelectStatement risultante.</span><span class="sxs-lookup"><span data-stu-id="bbb40-233">Visit the relational input and get the resulting SqlSelectStatement.</span></span> <span data-ttu-id="bbb40-234">L'input in un nodo relazionale potrebbe essere uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbb40-234">The input to a relational node could be one of the following:</span></span>  
  
    -   <span data-ttu-id="bbb40-235">Un nodo relazionale che include un extent, ad esempio un oggetto DbScanExpression.</span><span class="sxs-lookup"><span data-stu-id="bbb40-235">A relational node, including an extent (a DbScanExpression, for example).</span></span> <span data-ttu-id="bbb40-236">Quando si visita un nodo di questo tipo, viene restituito un oggetto SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="bbb40-236">Visiting such a node returns a SqlSelectStatement.</span></span>  
  
    -   <span data-ttu-id="bbb40-237">Un'espressione dell'operazione di impostazione, ad esempio UNION ALL.</span><span class="sxs-lookup"><span data-stu-id="bbb40-237">A set operation expression (UNION ALL, for example).</span></span> <span data-ttu-id="bbb40-238">Il risultato deve essere racchiuso tra parentesi e inserito nella clausola FROM di un nuovo oggetto SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="bbb40-238">The result has to be wrapped in brackets and put in the FROM clause of a new SqlSelectStatement.</span></span>  
  
2.  <span data-ttu-id="bbb40-239">Controllare se il nodo corrente può essere aggiunto all'oggetto SqlSelectStatement prodotto dall'input.</span><span class="sxs-lookup"><span data-stu-id="bbb40-239">Check whether the current node can be added to the SqlSelectStatement produced by the input.</span></span> <span data-ttu-id="bbb40-240">Questa procedura viene descritta nella sezione intitolata Raggruppamento di espressioni nelle istruzioni SQL.</span><span class="sxs-lookup"><span data-stu-id="bbb40-240">The section titled Grouping Expressions into SQL Statements describes this.</span></span> <span data-ttu-id="bbb40-241">Se non può essere aggiunto,</span><span class="sxs-lookup"><span data-stu-id="bbb40-241">If not,</span></span>  
  
    -   <span data-ttu-id="bbb40-242">Visualizzare l'oggetto SqlSelectStatement corrente.</span><span class="sxs-lookup"><span data-stu-id="bbb40-242">Pop the current SqlSelectStatement object.</span></span>  
  
    -   <span data-ttu-id="bbb40-243">Creare un nuovo oggetto SqlSelectStatement e aggiungere l'oggetto SqlSelectStatement visualizzato come FROM del nuovo oggetto SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="bbb40-243">Create a new SqlSelectStatement object and add the popped SqlSelectStatement as the FROM of the new SqlSelectStatement object.</span></span>  
  
    -   <span data-ttu-id="bbb40-244">Inserire il nuovo oggetto in cima allo stack.</span><span class="sxs-lookup"><span data-stu-id="bbb40-244">Put the new object on top of the stack.</span></span>  
  
3.  <span data-ttu-id="bbb40-245">Reindirizzare l'associazione di espressioni di input nel simbolo corretto dall'input.</span><span class="sxs-lookup"><span data-stu-id="bbb40-245">Redirect the input expression binding to the correct symbol from the input.</span></span> <span data-ttu-id="bbb40-246">Queste informazioni si trovano nell'oggetto SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="bbb40-246">This information is maintained in the SqlSelectStatement object.</span></span>  
  
4.  <span data-ttu-id="bbb40-247">Aggiungere un nuovo ambito SymbolTable.</span><span class="sxs-lookup"><span data-stu-id="bbb40-247">Add a new SymbolTable scope.</span></span>  
  
5.  <span data-ttu-id="bbb40-248">Visitare la parte non di input dell'espressione, ad esempio Projection e Predicate.</span><span class="sxs-lookup"><span data-stu-id="bbb40-248">Visit the non-input part of the expression (for example, Projection and Predicate).</span></span>  
  
6.  <span data-ttu-id="bbb40-249">Visualizzare tutti gli oggetti aggiunti agli stack globali.</span><span class="sxs-lookup"><span data-stu-id="bbb40-249">Pop all the objects added to the global stacks.</span></span>  
  
 <span data-ttu-id="bbb40-250">Non esiste un diretto equivalente di DbSkipExpression in SQL.</span><span class="sxs-lookup"><span data-stu-id="bbb40-250">DbSkipExpression not have a direct equivalent in SQL.</span></span> <span data-ttu-id="bbb40-251">Logicamente viene convertito in:</span><span class="sxs-lookup"><span data-stu-id="bbb40-251">Logically, it is translated into:</span></span>  
  
```  
SELECT Y.x1, Y.x2, ..., Y.xn  
FROM (  
   SELECT X.x1, X.x2, ..., X.xn, row_number() OVER (ORDER BY sk1, sk2, ...) AS [row_number]   
   FROM input as X   
   ) as Y  
WHERE Y.[row_number] > count   
ORDER BY sk1, sk2, ...  
```  
  
### <a name="join-expressions"></a><span data-ttu-id="bbb40-252">Espressioni di join</span><span class="sxs-lookup"><span data-stu-id="bbb40-252">Join Expressions</span></span>  
 <span data-ttu-id="bbb40-253">Gli elementi seguenti sono considerati espressioni di join e vengono elaborati come di consueto, ovvero mediante il metodo VisitJoinExpression:</span><span class="sxs-lookup"><span data-stu-id="bbb40-253">The following are considered join expressions and they are processed in a common way, by the VisitJoinExpression method:</span></span>  
  
-   <span data-ttu-id="bbb40-254">DbApplyExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-254">DbApplyExpression</span></span>  
  
-   <span data-ttu-id="bbb40-255">DbJoinExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-255">DbJoinExpression</span></span>  
  
-   <span data-ttu-id="bbb40-256">DbCrossJoinExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-256">DbCrossJoinExpression</span></span>  
  
 <span data-ttu-id="bbb40-257">I passaggi della visita sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbb40-257">The following are the visit steps:</span></span>  
  
 <span data-ttu-id="bbb40-258">Prima di visitare i figli, viene chiamato il metodo IsParentAJoin per controllare se il nodo di join è un figlio di un join su un lato sinistro.</span><span class="sxs-lookup"><span data-stu-id="bbb40-258">First, before visiting the children, IsParentAJoin is invoked to check whether the join node is a child of a join along a left spine.</span></span> <span data-ttu-id="bbb40-259">Se viene restituito False, viene avviato un nuovo oggetto SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="bbb40-259">If it returns false, a new SqlSelectStatement is started.</span></span> <span data-ttu-id="bbb40-260">In questo caso, i join vengono visitati in modo diverso dal resto dei nodi, in quanto il padre (il nodo di join) crea l'oggetto SqlSelectStatement per consentirne l'uso da parte dei figli.</span><span class="sxs-lookup"><span data-stu-id="bbb40-260">In that sense, joins are visited differently from the rest of the nodes, as the parent (the join node) creates the SqlSelectStatement for the children to possibly use.</span></span>  
  
 <span data-ttu-id="bbb40-261">Elaborare quindi gli input uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="bbb40-261">Second, process the inputs one at a time.</span></span> <span data-ttu-id="bbb40-262">Per ogni input:</span><span class="sxs-lookup"><span data-stu-id="bbb40-262">For each input:</span></span>  
  
1.  <span data-ttu-id="bbb40-263">Visitare l'input.</span><span class="sxs-lookup"><span data-stu-id="bbb40-263">Visit the input.</span></span>  
  
2.  <span data-ttu-id="bbb40-264">Completare l'elaborazione del risultato della visita dell'input chiamando il metodo ProcessJoinInputResult, responsabile della gestione della tabella dei simboli, dopo aver visitato un figlio di un'espressione di join e possibilmente aver completato l'oggetto SqlSelectStatement prodotto dal figlio.</span><span class="sxs-lookup"><span data-stu-id="bbb40-264">Post process the result of visiting the input by invoking ProcessJoinInputResult, which is responsible for maintaining the symbol table after visiting a child of a join expression and possibly finishing the SqlSelectStatement produced by the child.</span></span> <span data-ttu-id="bbb40-265">Il risultato del figlio potrebbe essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbb40-265">The child's result could be one of the following:</span></span>  
  
    -   <span data-ttu-id="bbb40-266">Un oggetto SqlSelectStatement diverso da quello al quale verrà aggiunto il padre.</span><span class="sxs-lookup"><span data-stu-id="bbb40-266">A SqlSelectStatement different from the one to which the parent will be added.</span></span> <span data-ttu-id="bbb40-267">In questo caso, può essere necessario completarlo aggiungendo colonne predefinite.</span><span class="sxs-lookup"><span data-stu-id="bbb40-267">In such case, it may need to be completed by adding default columns.</span></span> <span data-ttu-id="bbb40-268">Se l'input è un join, è necessario creare un nuovo simbolo di join.</span><span class="sxs-lookup"><span data-stu-id="bbb40-268">If the input was a Join, you need to create a new join symbol.</span></span> <span data-ttu-id="bbb40-269">In caso contrario, creare un simbolo normale.</span><span class="sxs-lookup"><span data-stu-id="bbb40-269">Otherwise, create a normal symbol.</span></span>  
  
    -   <span data-ttu-id="bbb40-270">Un extent, ad esempio un oggetto DbScanExpression, nel qual caso viene semplicemente aggiunto all'elenco di input dell'oggetto SqlSelectStatement del padre.</span><span class="sxs-lookup"><span data-stu-id="bbb40-270">An extent (a DbScanExpression, for example), in which case it is simply added to the list of inputs of the parent’s SqlSelectStatement.</span></span>  
  
    -   <span data-ttu-id="bbb40-271">Un oggetto diverso da SqlSelectStatement, nel qual caso viene racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="bbb40-271">Not a SqlSelectStatement, in which case it is wrapped with brackets.</span></span>  
  
    -   <span data-ttu-id="bbb40-272">Lo stesso oggetto SqlSelectStatement al quale viene aggiunto il padre.</span><span class="sxs-lookup"><span data-stu-id="bbb40-272">The same SqlSelectStatement to which the parent is added.</span></span> <span data-ttu-id="bbb40-273">In questo caso, i simboli dell'elenco FromExtents devono essere sostituiti da un unico nuovo oggetto JoinSymbol che li rappresenta tutti.</span><span class="sxs-lookup"><span data-stu-id="bbb40-273">In such case, the symbols in the FromExtents list need to be replaced with a single new JoinSymbol representing them all.</span></span>  
  
    -   <span data-ttu-id="bbb40-274">Per i primi tre casi viene chiamato il metodo AddFromSymbol per aggiungere la clausola AS e aggiornare la tabella dei simboli.</span><span class="sxs-lookup"><span data-stu-id="bbb40-274">For the first three cases, AddFromSymbol is called to add the AS clause, and update the symbol table.</span></span>  
  
 <span data-ttu-id="bbb40-275">Il terzo passaggio è costituito dalla visita della condizione di join (se presente).</span><span class="sxs-lookup"><span data-stu-id="bbb40-275">Third, the join condition (if any) is visited.</span></span>  
  
### <a name="set-operations"></a><span data-ttu-id="bbb40-276">Operazioni sui set</span><span class="sxs-lookup"><span data-stu-id="bbb40-276">Set Operations</span></span>  
 <span data-ttu-id="bbb40-277">Le operazioni di impostazione DbUnionAllExpression, DbExceptExpression e DbIntersectExpression vengono elaborate dal metodo VisitSetOpExpression.</span><span class="sxs-lookup"><span data-stu-id="bbb40-277">The set operations DbUnionAllExpression, DbExceptExpression, and DbIntersectExpression are processed by the method VisitSetOpExpression.</span></span> <span data-ttu-id="bbb40-278">Tale metodo crea un SqlBuilder della forma</span><span class="sxs-lookup"><span data-stu-id="bbb40-278">It creates a SqlBuilder of the shape</span></span>  
  
```xml  
<leftSqlSelectStatement> <setOp> <rightSqlSelectStatement>  
```  
  
 <span data-ttu-id="bbb40-279">In cui \<leftSqlSelectStatement > e \<rightSqlSelectStatement > sono oggetti SqlSelectStatements ottenuti mediante la visita di ognuno degli input, e \<setOp > è l'operazione corrispondente (ad esempio UNION ALL).</span><span class="sxs-lookup"><span data-stu-id="bbb40-279">Where \<leftSqlSelectStatement> and \<rightSqlSelectStatement> are SqlSelectStatements obtained by visiting each of the inputs, and \<setOp> is the corresponding operation (UNION ALL for example).</span></span>  
  
### <a name="dbscanexpression"></a><span data-ttu-id="bbb40-280">DbScanExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-280">DbScanExpression</span></span>  
 <span data-ttu-id="bbb40-281">Se viene visitato in un contesto di join (come un input in un join che è un figlio del lato sinistro di un altro join), DbScanExpression restituisce un SqlBuilder con l'SQL di destinazione per la destinazione corrispondente, ovvero una visualizzazione, una tabella o una query di definizione.</span><span class="sxs-lookup"><span data-stu-id="bbb40-281">If visited in a join context (as an input to a join that is a left child of another join), DbScanExpression returns a SqlBuilder with the target SQL for the corresponding target, which is either a defining query, table, or a view.</span></span> <span data-ttu-id="bbb40-282">In caso contrario, viene creato un nuovo SqlSelectStatement con il campo FROM impostato in modo da corrispondere alla destinazione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="bbb40-282">Otherwise, a new SqlSelectStatement is created with the FROM field set to correspond to the corresponding target.</span></span>  
  
### <a name="dbvariablereferenceexpression"></a><span data-ttu-id="bbb40-283">DbVariableReferenceExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-283">DbVariableReferenceExpression</span></span>  
 <span data-ttu-id="bbb40-284">La visita di un oggetto DbVariableReferenceExpression restituisce l'oggetto Symbol che corrisponde all'espressione di riferimento della variabile in base a una ricerca nella tabella dei simboli.</span><span class="sxs-lookup"><span data-stu-id="bbb40-284">The visit of a DbVariableReferenceExpression returns the Symbol corresponding to that variable reference expression based on a look up in the symbol table.</span></span>  
  
### <a name="dbpropertyexpression"></a><span data-ttu-id="bbb40-285">DbPropertyExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-285">DbPropertyExpression</span></span>  
 <span data-ttu-id="bbb40-286">La bidimensionalità degli alias di join viene identificata ed elaborata durante la visita di un oggetto DbPropertyExpression.</span><span class="sxs-lookup"><span data-stu-id="bbb40-286">Join alias flattening is identified and processed when visiting a DbPropertyExpression.</span></span>  
  
 <span data-ttu-id="bbb40-287">Viene prima visitata la proprietà Instance e il risultato è un oggetto Symbol, JoinSymbol o SymbolPair.</span><span class="sxs-lookup"><span data-stu-id="bbb40-287">The Instance property is first visited and the result is a Symbol, a JoinSymbol, or a SymbolPair.</span></span> <span data-ttu-id="bbb40-288">I tre casi vengono gestiti nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="bbb40-288">Here is how these three cases are handled:</span></span>  
  
-   <span data-ttu-id="bbb40-289">Se viene restituito un oggetto JoinSymbol, la rispettiva proprietà NameToExtent contiene un simbolo per la proprietà necessaria.</span><span class="sxs-lookup"><span data-stu-id="bbb40-289">If a JoinSymbol is returned, than its NameToExtent property contains a symbol for the needed property.</span></span> <span data-ttu-id="bbb40-290">Se il simbolo di join rappresenta un join annidato, viene restituita una nuova coppia di simboli con il simbolo di join per rilevare il simbolo che verrebbe usato come alias dell'istanza e il simbolo che rappresenta la proprietà effettiva per l'altre risoluzione.</span><span class="sxs-lookup"><span data-stu-id="bbb40-290">If the join symbol represents a nested join, a new Symbol pair is returned with the join symbol to track the symbol that would be used as the instance alias, and the symbol representing the actual property for further resolving.</span></span>  
  
-   <span data-ttu-id="bbb40-291">Se viene restituito un oggetto SymbolPair e la parte della colonna è un simbolo di join, viene restituito nuovamente un simbolo di join, ma in questo caso la proprietà della colonna viene aggiornata in modo da puntare alla proprietà rappresentata dall'espressione della proprietà corrente.</span><span class="sxs-lookup"><span data-stu-id="bbb40-291">If a SymbolPair is returned and the Column part is a join symbol, a join symbol is again returned, but now the column property is updated to point to the property represented by the current property expression.</span></span> <span data-ttu-id="bbb40-292">In caso contrario, viene restituito un SqlBuilder con l'origine SymbolPair come alias e il simbolo per la proprietà corrente come colonna.</span><span class="sxs-lookup"><span data-stu-id="bbb40-292">Otherwise a SqlBuilder is returned with the SymbolPair source as the alias, and the symbol for the current property as the column.</span></span>  
  
-   <span data-ttu-id="bbb40-293">Se viene restituito un oggetto Symbol, il metodo Visit restituisce un metodo SqlBuilder con l'istanza specifica come alias e il nome di proprietà come nome di colonna.</span><span class="sxs-lookup"><span data-stu-id="bbb40-293">If a Symbol is returned, the Visit method returns a SqlBuilder method with that instance as the alias, and the property name as column name.</span></span>  
  
### <a name="dbnewinstanceexpression"></a><span data-ttu-id="bbb40-294">DbNewInstanceExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-294">DbNewInstanceExpression</span></span>  
 <span data-ttu-id="bbb40-295">Se viene usato come proprietà Projection di DbProjectExpression, DbNewInstanceExpression produce un elenco delimitato da virgole degli argomenti per rappresentare le colonne previste.</span><span class="sxs-lookup"><span data-stu-id="bbb40-295">When used as the Projection property of DbProjectExpression, DbNewInstanceExpression produces a comma-separated list of the arguments to represent the projected columns.</span></span>  
  
 <span data-ttu-id="bbb40-296">Quando DbNewInstanceExpression presenta un tipo restituito di raccolta e definisce una nuova raccolta delle espressioni fornite come argomenti, i tre casi seguenti vengono gestiti separatamente:</span><span class="sxs-lookup"><span data-stu-id="bbb40-296">When DbNewInstanceExpression has a collection return type, and defines a new collection of the expressions provided as arguments, the following three cases are handled separately:</span></span>  
  
-   <span data-ttu-id="bbb40-297">Se l'unico argomento di DbNewInstanceExpression è DbElementExpression, viene convertito come segue:</span><span class="sxs-lookup"><span data-stu-id="bbb40-297">If DbNewInstanceExpression has DbElementExpression as the only argument, it is translated as follows:</span></span>  
  
    ```  
    NewInstance(Element(X)) =>  SELECT TOP 1 …FROM X  
    ```  
  
 <span data-ttu-id="bbb40-298">Se in DbNewInstanceExpression non sono presenti argomenti (rappresenta una tabella vuota), DbNewInstanceExpression viene convertito in:</span><span class="sxs-lookup"><span data-stu-id="bbb40-298">If DbNewInstanceExpression has no arguments (represents an empty table), DbNewInstanceExpression is translated into:</span></span>  
  
```  
SELECT CAST(NULL AS <primitiveType>) as X  
FROM (SELECT 1) AS Y WHERE 1=0  
```  
  
 <span data-ttu-id="bbb40-299">In caso contrario, DbNewInstanceExpression compila una scala union all degli argomenti:</span><span class="sxs-lookup"><span data-stu-id="bbb40-299">Otherwise DbNewInstanceExpression builds a union-all ladder of the arguments:</span></span>  
  
```  
SELECT <visit-result-arg1> as X  
UNION ALL SELECT <visit-result-arg2> as X  
UNION ALL …  
UNION ALL SELECT <visit-result-argN> as X  
```  
  
### <a name="dbfunctionexpression"></a><span data-ttu-id="bbb40-300">DbFunctionExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-300">DbFunctionExpression</span></span>  
 <span data-ttu-id="bbb40-301">Le funzioni canoniche e quelle predefinite vengono elaborate allo stesso modo: se è necessaria una gestione speciale, ad esempio TRIM(string) in LTRIM(RTRIM(string), viene richiamato il gestore appropriato.</span><span class="sxs-lookup"><span data-stu-id="bbb40-301">Canonical and built-in functions are processed the same way: if they need special handling (TRIM(string) to  LTRIM(RTRIM(string), for example), the appropriate handler is invoked.</span></span> <span data-ttu-id="bbb40-302">In caso contrario vengono convertite in FunctionName(arg1, arg2, ..., argn).</span><span class="sxs-lookup"><span data-stu-id="bbb40-302">Otherwise they are translated to FunctionName(arg1, arg2, ..., argn).</span></span>  
  
 <span data-ttu-id="bbb40-303">Vengono usati i dizionari per tenere traccia delle funzioni per cui è necessaria una gestione speciale e dei rispettivi gestori appropriati.</span><span class="sxs-lookup"><span data-stu-id="bbb40-303">Dictionaries are used to keep track of which functions need special handling and their appropriate handlers.</span></span>  
  
 <span data-ttu-id="bbb40-304">Le funzioni definite dall'utente vengono convertite in NamespaceName.FunctionName(arg1, arg2, ..., argn).</span><span class="sxs-lookup"><span data-stu-id="bbb40-304">User-defined functions are tanslated to NamespaceName.FunctionName(arg1, arg2, ..., argn).</span></span>  
  
### <a name="dbelementexpression"></a><span data-ttu-id="bbb40-305">DbElementExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-305">DbElementExpression</span></span>  
 <span data-ttu-id="bbb40-306">Il metodo che visita DbElementExpression viene richiamato solo per visitare un oggetto DbElementExpression quando viene usato per rappresentare una sottoquery scalare.</span><span class="sxs-lookup"><span data-stu-id="bbb40-306">The method that visits DbElementExpression is only invoked for visiting a DbElementExpression when used to represent a scalar subquery.</span></span> <span data-ttu-id="bbb40-307">Pertanto, DbElementExpression viene convertito in un oggetto SqlSelectStatement completo e viene racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="bbb40-307">Therefore, DbElementExpression translates into a complete SqlSelectStatement and adds brackets around it.</span></span>  
  
### <a name="dbquantifierexpression"></a><span data-ttu-id="bbb40-308">DbQuantifierExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-308">DbQuantifierExpression</span></span>  
 <span data-ttu-id="bbb40-309">A seconda del tipo di espressione (Any o All), DbQuantifierExpression viene convertito come:</span><span class="sxs-lookup"><span data-stu-id="bbb40-309">Depending on the expression type (Any or All), DbQuantifierExpression is translated it as:</span></span>  
  
```  
Any(input, x) => Exists(Filter(input,x))  
All(input, x) => Not Exists(Filter(input, not(x))  
```  
  
### <a name="dbnotexpression"></a><span data-ttu-id="bbb40-310">DbNotExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-310">DbNotExpression</span></span>  
 <span data-ttu-id="bbb40-311">In alcuni casi è possibile comprimere la conversione di DbNotExpression con la rispettiva espressione di input.</span><span class="sxs-lookup"><span data-stu-id="bbb40-311">In some cases it is possible to collapse the translation of DbNotExpression with its input expression.</span></span> <span data-ttu-id="bbb40-312">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bbb40-312">For example:</span></span>  
  
```  
Not(IsNull(a)) =>  "a IS NOT NULL"  
Not(All(input, x) => Not (Not Exists(Filter(input, not(x))) => Exists(Filter(input, not(x))  
```  
  
 <span data-ttu-id="bbb40-313">Il motivo per cui viene eseguita la seconda compressione è che sono state introdotte inefficienze dal provider durante la conversione dell'oggetto DbQuantifierExpression di tipo All.</span><span class="sxs-lookup"><span data-stu-id="bbb40-313">The reason the second collapse is performed is because inefficiencies were introduced by the provider when translating DbQuantifierExpression of type All.</span></span> <span data-ttu-id="bbb40-314">Ciò non ha consentito a Entity Framework di eseguire la semplificazione.</span><span class="sxs-lookup"><span data-stu-id="bbb40-314">Thus the Entity Framework could not have done the simplification.</span></span>  
  
### <a name="dbisemptyexpression"></a><span data-ttu-id="bbb40-315">DbIsEmptyExpression</span><span class="sxs-lookup"><span data-stu-id="bbb40-315">DbIsEmptyExpression</span></span>  
 <span data-ttu-id="bbb40-316">DbIsEmptyExpression viene convertito come:</span><span class="sxs-lookup"><span data-stu-id="bbb40-316">DbIsEmptyExpression is translated as:</span></span>  
  
```  
IsEmpty(inut) = Not Exists(input)  
```  
  
## <a name="second-phase-of-sql-generation-generating-the-string-command"></a><span data-ttu-id="bbb40-317">Seconda fase della generazione SQL: generazione della stringa di comando</span><span class="sxs-lookup"><span data-stu-id="bbb40-317">Second Phase of SQL Generation: Generating the String Command</span></span>  
 <span data-ttu-id="bbb40-318">In caso di generazione di una stringa di comando SQL, SqlSelectStatement produce alias effettivi per i simboli che risolvono il problema della ridenominazione dei nomi di colonna e degli alias degli extent.</span><span class="sxs-lookup"><span data-stu-id="bbb40-318">When generating a string SQL command, the SqlSelectStatement produces actual aliases for the symbols, which addresses the issue of column name and extent alias renaming.</span></span>  
  
 <span data-ttu-id="bbb40-319">La ridenominazione degli alias degli extent si verifica durante la scrittura dell'oggetto SqlSelectStatement in una stringa.</span><span class="sxs-lookup"><span data-stu-id="bbb40-319">Extent alias renaming occurs while writing the SqlSelectStatement object into a string.</span></span> <span data-ttu-id="bbb40-320">Prima si crea un elenco di tutti gli alias usati dagli extent esterni.</span><span class="sxs-lookup"><span data-stu-id="bbb40-320">First create a list of all the aliases used by the outer extents.</span></span> <span data-ttu-id="bbb40-321">Ogni simbolo incluso in FromExtents (o AllJoinExtents se è non Null), viene rinominato se collide con alcuni degli extent esterni.</span><span class="sxs-lookup"><span data-stu-id="bbb40-321">Each symbol in the FromExtents (or AllJoinExtents if it is non-null), gets renamed if it collides with any of the outer extents.</span></span> <span data-ttu-id="bbb40-322">Se la ridenominazione è necessaria, non creerà conflitti con nessun extent raccolto in AllExtentNames.</span><span class="sxs-lookup"><span data-stu-id="bbb40-322">If renaming is needed, it will not conflict with any of the extents collected in AllExtentNames.</span></span>  
  
 <span data-ttu-id="bbb40-323">La ridenominazione delle colonne si verifica durante la scrittura di un oggetto Symbol in una stringa.</span><span class="sxs-lookup"><span data-stu-id="bbb40-323">Column renaming occurs while writing a Symbol object to a string.</span></span> <span data-ttu-id="bbb40-324">AddDefaultColumns nella prima fase ha determinato se è necessario rinominare un simbolo specifico di una colonna.</span><span class="sxs-lookup"><span data-stu-id="bbb40-324">AddDefaultColumns in the first phase has determined if a certain column symbol has to be renamed.</span></span> <span data-ttu-id="bbb40-325">Nella seconda fase viene eseguita solo la ridenominazione con la verifica che il nome prodotto non crei conflitti con uno dei nomi usati in AllColumnNames</span><span class="sxs-lookup"><span data-stu-id="bbb40-325">In the second phase only the rename occurs making sure that the name produced does not conflict with any name used in AllColumnNames</span></span>  
  
 <span data-ttu-id="bbb40-326">Per produrre nomi univoci sia per gli alias degli extent che per le colonne, usare <existing_name>_n, in cui n è l'alias più piccolo che non è stato ancora usato.</span><span class="sxs-lookup"><span data-stu-id="bbb40-326">To produce unique names both for extent aliases and for columns, use <existing_name>_n where n is the smallest alias that has not been used yet.</span></span> <span data-ttu-id="bbb40-327">L'elenco globale di tutti gli alias aumenta la necessità di eseguire ridenominazioni a catena.</span><span class="sxs-lookup"><span data-stu-id="bbb40-327">The global list of all aliases increases the need for cascading renames.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb40-328">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbb40-328">See Also</span></span>  
 [<span data-ttu-id="bbb40-329">Generazione di comandi SQL nel provider di esempio</span><span class="sxs-lookup"><span data-stu-id="bbb40-329">SQL Generation in the Sample Provider</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)
