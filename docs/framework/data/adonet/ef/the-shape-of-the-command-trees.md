---
title: Forma degli alberi dei comandi
ms.date: 03/30/2017
ms.assetid: 2215585e-ca47-45f8-98d4-8cb982f8c1d3
ms.openlocfilehash: 8368354049a77a56a5aa54ab500619576f41b0dc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854269"
---
# <a name="the-shape-of-the-command-trees"></a>Forma degli alberi dei comandi

Il modulo di generazione SQL è responsabile della generazione di una query SQL specifica di back-end basata su una determinata espressione dell'albero dei comandi della query di input. Questa sezione descrive le caratteristiche, le proprietà e la forma degli alberi dei comandi di query.

## <a name="query-command-trees-overview"></a>Panoramica degli alberi dei comandi di query

Un albero dei comandi di query è una rappresentazione del modello a oggetti di una query. Tali alberi dei comandi di query hanno due funzioni:

- Per esprimere una query di input specificata sulla Entity Framework.

- Esprimere una query di output specificata per un provider, che descrive una query sul back-end.

Gli alberi dei comandi di query supportano una semantica più completa rispetto alle query conformi a SQL:1999, che include il supporto per l'uso di raccolte annidate e l'esecuzione di operazioni sui tipi, ad esempio quelle per verificare se un'entità è di un determinato tipo o filtrare i set in base a un tipo.

La proprietà DBQueryCommandTree.Query è la radice dell'albero delle espressioni che descrive la logica della query. La proprietà DBQueryCommandTree.Parameters contiene un elenco di parametri usati nella query. L'albero delle espressioni è costituito da oggetti DbExpression.

Un oggetto DbExpression rappresenta un'attività di calcolo. I Entity Framework per la composizione di espressioni di query, tra cui costanti, variabili, funzioni, costruttori e operatori relazionali standard come Filter e join, sono disponibili diversi tipi di espressioni. Ogni oggetto DbExpression dispone di una proprietà ResultType che rappresenta il tipo del risultato prodotto da tale espressione. Questo tipo viene espresso come TypeUsage.

## <a name="shapes-of-the-output-query-command-tree"></a>Forme dell'albero dei comandi di query di output

Gli alberi dei comandi di query di output rappresentano in modo accurato query SQL relazionali e rispettano regole più rigorose rispetto a quelle applicate agli alberi dei comandi di query. Contengono in genere costrutti che vengono convertiti facilmente in SQL.

Gli alberi dei comandi di input vengono espresse in base al modello concettuale, che supporta proprietà di navigazione, associazioni tra entità ed ereditarietà. Gli alberi dei comandi di output vengono espresse in base al modello di archiviazione. Diversamente da questi ultimi, gli alberi dei comandi di input consentono di proiettare raccolte annidate.

Gli alberi dei comandi di query di output vengono compilati usando un subset degli oggetti DbExpression disponibili, che contiene alcune espressioni con un utilizzo limitato.

Le operazioni sui tipi, ad esempio quelle per verificare se una determinata espressione è di un tipo specifico o filtrare i set in base a un tipo, non sono presenti negli alberi dei comandi di output.

Negli alberi dei comandi di output solo le espressioni che restituiscono valori booleani vengono usate per le proiezioni e solo per i predicati nelle espressioni che richiedono un predicato, ad esempio un'istruzione Case o per il filtro.

La radice degli alberi dei comandi di query di output è un oggetto DbProjectExpression.

### <a name="expression-types-not-present-in-output-query-command-trees"></a>Tipi di espressione non inclusi negli alberi dei comandi di query di output

I tipi di espressione seguenti non sono validi in un albero dei comandi di query di output e non devono essere gestiti dai provider:

- DbDerefExpression

- DbEntityRefExpression

- DbRefKeyExpression

- DbIsOfExpression

- DbOfTypeExpression

- DbRefExpression

- DbRelationshipNavigationExpression

- DbTreatExpression

### <a name="expression-restrictions-and-notes"></a>Restrizioni e note relative alle espressioni

Molte espressioni possono essere usate solo in modo limitato negli alberi dei comandi di query di output:

#### <a name="dbfunctionexpression"></a>DbFunctionExpression

È possibile passare i tipi di funzione seguenti:

- Funzioni canoniche riconosciute dallo spazio dei nomi Edm.

- Funzioni di archivio predefinite riconosciute da BuiltInAttribute.

- Funzioni definite dall'utente.

Le funzioni canoniche (vedere [funzioni canoniche](./language-reference/canonical-functions.md) per ulteriori informazioni) vengono specificate come parte del Entity Framework e i provider devono fornire implementazioni per le funzioni canoniche basate su tali specifiche. Le funzioni di archivio si basano sulle specifiche contenute nel file manifesto del provider corrispondente. Le funzioni definite dall'utente si basano sulle specifiche di SSDL.

Inoltre, le funzioni che includono l'attributo NiladicFunction non dispongono di argomenti e devono essere convertite senza la parentesi finale,  Ovvero, per  *\<FunctionName*  *\<> anziché FunctionName > ()* .

#### <a name="dbnewinstanceexpression"></a>DbNewInstanceExpression

DbNewInstanceExpression può essere specificato solo nei due casi seguenti:

- Come proprietà Projection di DbProjectExpression.  In questo caso, vengono applicate le restrizioni seguenti:

  - Il risultato deve essere un tipo di riga.

  - I relativi argomenti devono essere espressioni che producono un risultato con un tipo primitivo. In genere, ogni argomento è un'espressione scalare, ad esempio un oggetto PropertyExpression su un oggetto DbVariableReferenceExpression, una chiamata a una funzione o un calcolo aritmetico di DbPropertyExpression su un oggetto DbVariableReferenceExpression o una chiamata a una funzione. È tuttavia possibile specificare un'espressione che rappresenta una subquery scalare anche nell'elenco di argomenti di un oggetto DbNewInstanceExpression. Un'espressione che rappresenta una sottoquery scalare è un albero delle espressioni che rappresenta una sottoquery che restituisce esattamente una riga e una colonna di un tipo primitivo con una radice dell'oggetto DbElementExpression

- Con un tipo restituito di raccolta, nel qual caso definisce una nuova raccolta delle espressioni specificate come argomenti.

#### <a name="dbvariablereferenceexpression"></a>DbVariableReferenceExpression

Un oggetto DbVariableReferenceExpression deve essere un elemento figlio del nodo DbPropertyExpression.

#### <a name="dbgroupbyexpression"></a>DbGroupByExpression

La proprietà Aggregates di un oggetto DbGroupByExpression può presentare solo elementi di tipo DbFunctionAggregate. Non esistono altri tipi di aggregazione.

#### <a name="dblimitexpression"></a>DbLimitExpression

La proprietà Limit può essere solo un oggetto DbConstantExpression o DbParameterReferenceExpression. Inoltre, la proprietà WithTies è sempre false in .NET Framework 3.5 e versioni precedenti.

#### <a name="dbscanexpression"></a>DbScanExpression

Quando viene usato negli alberi dei comandi di output, DbScanExpression rappresenta efficacemente un'analisi su una tabella, una vista o una query di archiviazione, rappresentata da EntitySetBase:: target.

Se la proprietà dei metadati "Defineing query" della destinazione è diversa da null, rappresenta una query, il testo della query per il quale viene fornito nella proprietà dei metadati nel linguaggio o nel dialetto specifico del provider, come specificato nella definizione dello schema dell'archivio.

In caso contrario, la destinazione rappresenta una tabella o una visualizzazione. Il prefisso dello schema si trova nella proprietà dei metadati "schema", se non è null; in caso contrario, è il nome del contenitore di entità.  Il nome della tabella o della vista è la proprietà dei metadati "Table", se non è null; in caso contrario, la proprietà Name della base del set di entità.

Tutte queste proprietà hanno origine dalla definizione dell'EntitySet corrispondente nel file SSDL (Store Schema Definition Language).

### <a name="using-primitive-types"></a>Utilizzo dei tipi primitivi

Quando si fa riferimento ai tipi primitivi negli alberi dei comandi di output, in genere il riferimento è contenuto nei tipi primitivi del modello concettuale. Per determinate espressioni, tuttavia, i, provider richiedono il tipo primitivo dell'archivio corrispondente. Esempi di tali espressioni includono DbCastExpression e in alcuni casi DbNullExpression, se il provider deve eseguire il cast del valore null al tipo corrispondente. In questi casi, i provider devono eseguire il mapping al tipo di provider in base al tipo primitivo e ai relativi facet.

## <a name="see-also"></a>Vedere anche

- [Generazione SQL](sql-generation.md)
