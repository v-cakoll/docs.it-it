---
title: Istruzione Dim (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: b3384b771748a1f2c9e841407042f81ce6ebe76d
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2018
---
# <a name="dim-statement-visual-basic"></a>Istruzione Dim (Visual Basic)
Dichiara e alloca spazio di archiviazione per una o più variabili.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a>Parti  
  
-   `attributelist`  
  
     Facoltativo. Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `accessmodifier`  
  
     Facoltativo. Può essere uno dei seguenti:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [Protected Friend](../../language-reference/modifiers/protected-friend.md)
    
    - [Protetto privato](../../language-reference/modifiers/private-protected.md)

     Vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `Shared`  
  
     Facoltativo. Vedere [condiviso](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Facoltativo. Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Static`  
  
     Facoltativo. Vedere [statico](../../../visual-basic/language-reference/modifiers/static.md).  
  
-   `ReadOnly`  
  
     Facoltativo. Vedere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WithEvents`  
  
     Facoltativo. Specifica che si tratta di variabili oggetto che fanno riferimento a istanze di una classe che può generare eventi. Vedere [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).  
  
-   `variablelist`  
  
     Obbligatorio. Elenco di variabili dichiarate in questa istruzione.  
  
     `variable [ , variable ... ]`  
  
     Ogni `variable` presenta la sintassi e le parti seguenti:  
  
     `variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`  
  
    |Parte|Descrizione|  
    |---|---|  
    |`variablename`|Obbligatorio. Nome della variabile. Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
    |`boundslist`|Facoltativo. Elenco dei limiti di ciascuna dimensione della variabile di matrice.|  
    |`New`|Facoltativo. Crea una nuova istanza della classe quando il `Dim` istruzione viene eseguita.|  
    |`datatype`|Facoltativo. Tipo di dati della variabile.|  
    |`With`|Facoltativo. Introduce l'elenco di inizializzatori di oggetto.|  
    |`propertyname`|Facoltativo. Il nome di una proprietà nella classe crei un'istanza di.|  
    |`propinitializer`|Necessario dopo avere `propertyname` =. L'espressione viene valutata e assegnata al nome della proprietà.|  
    |`initializer`|Facoltativo se `New` non è specificato. Espressione che viene valutata e assegnata alla variabile quando viene creato.|  
  
## <a name="remarks"></a>Note  
 Il compilatore Visual Basic utilizza il `Dim` istruzione per determinare il tipo di dati della variabile e altre informazioni, ad esempio il codice che può accedere alla variabile. Nell'esempio seguente viene dichiarata una variabile per contenere un `Integer` valore.  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, struttura, classe o interfaccia.  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 Per un tipo riferimento, utilizzare il `New` (parola chiave) per creare una nuova istanza della classe o una struttura che viene specificato dal tipo di dati. Se si utilizza `New`, non si utilizza un'espressione dell'inizializzatore. Al contrario, specificare argomenti, se sono necessarie, per il costruttore della classe da cui si sta creando la variabile.  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 È possibile dichiarare una variabile in una stored procedure, blocco, classe, struttura o modulo. È possibile dichiarare una variabile in un file di origine, lo spazio dei nomi o interfaccia. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 È una variabile dichiarata a livello di modulo, all'esterno di qualsiasi routine, un *variabile membro* o *campo*. Le variabili membro sono nell'ambito in tutta la classe, struttura o modulo. Una variabile dichiarata a livello di routine è un *variabile locale*. Le variabili locali sono nell'ambito solo all'interno della routine o un blocco.  
  
 I seguenti modificatori di accesso vengono utilizzati per dichiarare le variabili all'esterno di una stored procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, e `Private`. Per ulteriori informazioni, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Il `Dim` parola chiave è facoltativa e in genere omesso se si specifica uno dei seguenti modificatori: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, o `WithEvents`.  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 Se `Option Explicit` è (impostazione predefinita), il compilatore richiede una dichiarazione per ciascuna variabile utilizzata. Per ulteriori informazioni, vedere [istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md).  
  
## <a name="specifying-an-initial-value"></a>Specificare un valore iniziale  
 Quando viene creato, è possibile assegnare un valore a una variabile. Per un tipo valore, utilizzare un *inizializzatore* per fornire un'espressione da assegnare alla variabile. L'espressione deve restituire una costante che può essere calcolata in fase di compilazione.  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 Se viene specificato un inizializzatore e non viene specificato un tipo di dati un `As` clausola *l'inferenza del tipo* viene utilizzato per dedurre il tipo di dati dall'inizializzatore. Nell'esempio seguente, entrambi `num1` e `num2` sono fortemente tipizzati come integer. Nella seconda dichiarazione, l'inferenza del tipo deduce il tipo dal valore 3.  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 L'inferenza del tipo si applica a livello di routine. Non è applicabile all'esterno di una routine in una classe, struttura, modulo o interfaccia. Per ulteriori informazioni sull'inferenza del tipo, vedere [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) e [locale l'inferenza del tipo](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 Per informazioni su ciò che accade quando un tipo di dati o l'inizializzatore non è specificato, vedere [valori e tipi di dati predefiniti](../../../visual-basic/language-reference/statements/dim-statement.md#default) più avanti in questo argomento.  
  
 È possibile utilizzare un *inizializzatore di oggetto* per dichiarare le istanze di tipi denominati e anonimi. Il codice seguente crea un'istanza di un `Student` classe e utilizza un inizializzatore di oggetto per inizializzare le proprietà.  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 Per ulteriori informazioni sugli inizializzatori di oggetti, vedere [procedura: dichiarare un oggetto utilizzando un inizializzatore di oggetto](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [gli inizializzatori di oggetto: tipi denominati e anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), e [tipi anonimi ](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="declaring-multiple-variables"></a>Dichiarazione di variabili di più  
 È possibile dichiarare più variabili in un'istruzione di dichiarazione, specificando il nome della variabile per ognuno di essi e dopo ogni nome di matrice con parentesi. Nel caso di più variabili, è possibile separarle mediante virgole.  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 Se si dichiarano più variabili con uno `As` clausola, non è possibile specificare un inizializzatore per tale gruppo di variabili.  
  
 È possibile specificare i tipi di dati diversi per variabili differenti utilizzando un oggetto separato `As` clausola per ogni variabile è dichiarata. Ogni variabile accetta il tipo di dati specificato nel primo `As` clausola rilevata dopo il relativo `variablename` parte.  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a>Matrici  
 È possibile dichiarare una variabile per contenere un *matrice*, che può contenere più valori. Per specificare che una variabile contiene una matrice, seguire la `variablename` immediatamente con parentesi. Per ulteriori informazioni sulle matrici, vedere [matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 È possibile specificare il limite inferiore e superiore di ciascuna dimensione della matrice. A tale scopo, includere un `boundslist` all'interno delle parentesi. Per ogni dimensione, il `boundslist` specifica il limite superiore e facoltativamente il limite inferiore. Il limite inferiore è sempre uguale a zero, se specifichi o meno. Ogni indice possono variare da zero tramite il relativo valore limite superiore.  
  
 Le due istruzioni seguenti sono equivalenti. Ogni istruzione dichiara una matrice di 21 `Integer` elementi. Quando si accede di matrice, l'indice può variare da 0 a 20.  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 L'istruzione seguente dichiara una matrice bidimensionale di tipo `Double`. La matrice è 4 righe (3 + 1) di 6 colonne (5 + 1) ogni. Si noti che il limite superiore rappresenta il valore più alto possibile per l'indice, non la lunghezza della dimensione. La lunghezza della dimensione è il limite superiore più uno.  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 Una matrice può avere da 1 a 32 dimensioni.  
  
 È possibile lasciare vuoto in una dichiarazione di matrice tutti i limiti. In questo caso, la matrice disponga del numero di dimensioni specificato, ma non viene inizializzata. Ha un valore `Nothing` fino a quando non si inizializzano alcuni dei relativi elementi. Il `Dim` istruzione deve specificare limiti per tutte le dimensioni o Nessuna dimensione.  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 Se la matrice contiene più di una dimensione, è necessario includere una virgola tra le parentesi per indicare il numero di dimensioni.  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 È possibile dichiarare un *matrice di lunghezza zero* dichiarando una delle dimensioni della matrice-1. Il valore di una variabile che contiene una matrice di lunghezza zero è `Nothing`. Matrici di lunghezza zero sono richiesti da alcune funzioni di common language runtime. Se si tenta di accedere a una matrice di questo tipo, si verifica un'eccezione di runtime. Per ulteriori informazioni, vedere [matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 È possibile inizializzare i valori di una matrice con un valore letterale della matrice. A tale scopo, racchiudere i valori di inizializzazione con parentesi graffe (`{}`).  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 Per le matrici multidimensionali, l'inizializzazione di ciascuna dimensione separata è racchiuso tra parentesi graffe all'interno della dimensione esterna. Gli elementi vengono specificati in ordine crescente di riga.  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 Per ulteriori informazioni sui valori letterali di matrice, vedere [matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
##  <a name="default"></a> Tipi di dati predefiniti e valori  
 Nella tabella seguente vengono descritti i risultati di varie combinazioni della specifica del tipo di dati e dell'inizializzatore in un'istruzione `Dim`.  
  
|Tipo di dati specificato?|Inizializzatore specificato?|Esempio|Risultato|  
|---|---|---|---|  
|No|No|`Dim qty`|Se [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) è off (impostazione predefinita), la variabile è impostata su `Nothing`.<br /><br /> Se `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|  
|No|Yes|`Dim qty = 5`|Se [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) è (impostazione predefinita), digitare la variabile accetta i dati dell'inizializzatore. Vedere [inferenza](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Se le istruzioni `Option Infer` e `Option Strict` sono disabilitate, il tipo di dati accettato dalla variabile è `Object`.<br /><br /> Se `Option Infer` è disabilitato e `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|  
|Sì|No|`Dim qty As Integer`|La variabile viene inizializzata sul valore predefinito per il tipo di dati. Vedere la tabella più avanti in questa sezione.|  
|Yes|Sì|`Dim qty  As Integer = 5`|Se il tipo di dati dell'inizializzatore non è convertibile nel tipo di dati specificato, si verifica un errore in fase di compilazione.|  
  
 Se si specifica un tipo di dati ma non si specifica un inizializzatore, Visual Basic Inizializza la variabile sul valore predefinito per il tipo di dati. Nella tabella seguente mostra il valore predefinito di valori di inizializzazione.  
  
|Tipo di dati|Valore predefinito|  
|---|---|  
|Tutti i tipi numerici (inclusi `Byte` e `SByte`)|0|  
|`Char`|Binario 0|  
|I tipi di riferimento (inclusi `Object`, `String`e tutte le matrici)|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|Mezzanotte del 1 ° gennaio dell'anno 1 (01/01/0001 12:00:00 AM)|  
  
 Ogni elemento di una struttura viene inizializzato come se fosse una variabile separata. Se si dichiara la lunghezza di una matrice, ma non si inizializza gli elementi, ogni elemento viene inizializzato come se fosse una variabile separata.  
  
## <a name="static-local-variable-lifetime"></a>Durata della variabile locale statica  
 Oggetto `Static` variabile locale ha una durata maggiore rispetto a quello della routine in cui viene dichiarato. I limiti di durata della variabile dipendono in cui la routine viene dichiarata e se è `Shared`.  
  
|Dichiarazione di routine|Variabile inizializzata|Variabile arresta esistente|  
|---|---|---|  
|In un modulo|La prima volta che viene chiamata la procedura|Arresto dell'esecuzione del programma|  
|In una classe o struttura, procedura è `Shared`|La prima volta la procedura viene chiamata su un'istanza specifica o nella classe o struttura stessa|Arresto dell'esecuzione del programma|  
|In una classe o struttura, non è stored procedure `Shared`|La prima volta che la routine viene chiamata su una specifica istanza|Quando l'istanza viene rilasciata per l'operazione di garbage collection (GC)|  
  
## <a name="attributes-and-modifiers"></a>Gli attributi e modificatori  
 È possibile applicare gli attributi solo per le variabili membro, non per le variabili locali. Un attributo fornisce informazioni per i metadati dell'assembly, che non è significativo per l'archiviazione temporanea, ad esempio le variabili locali.  
  
 A livello di modulo, è possibile utilizzare il `Static` modificatore per dichiarare le variabili membro. A livello di routine, non è possibile utilizzare `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, o i modificatori di accesso per dichiarare le variabili locali.  
  
 È possibile specificare il codice può accedere a una variabile fornendo un `accessmodifier`. Classe e modulo predefinito di variabili (all'esterno di qualsiasi routine) membro accesso privato e predefinito di variabili membro di struttura per l'accesso pubblico. È possibile regolare i livelli di accesso con i modificatori di accesso. È possibile utilizzare i modificatori di accesso con le variabili locali (all'interno di una routine).  
  
 È possibile specificare `WithEvents` solo a variabili membro, non le variabili locali all'interno di una stored procedure. Se si specifica `WithEvents`, il tipo di dati della variabile deve essere un tipo di classe specifico non `Object`. Non è possibile dichiarare una matrice con `WithEvents`. Per ulteriori informazioni sugli eventi, vedere [eventi](../../../visual-basic/programming-guide/language-features/events/index.md).  
  
> [!NOTE]
>  Codice esterno di una classe, struttura o un modulo necessario qualificare il nome di una variabile membro con il nome di tale classe, struttura o modulo. All'esterno di che una stored procedure o un blocco non può fare riferimento a variabili locali all'interno della routine o un blocco di codice.  
  
## <a name="releasing-managed-resources"></a>Rilasciare le risorse gestite  
 Il garbage collector di .NET Framework elimina le risorse gestite senza alcuna codifica aggiuntiva da parte dell'utente. Tuttavia, è possibile forzare l'eliminazione di una risorsa gestita anziché attendere che il garbage collector.  
  
 Se una classe contiene una risorsa particolarmente preziosa e rara (ad esempio, un handle di connessione o file di database), è possibile evitare di attendere la successiva operazione di garbage collection per pulire un'istanza di classe che non è più in uso. Una classe può implementare il <xref:System.IDisposable> interfaccia per fornire un modo per rilasciare le risorse prima di un'operazione di garbage collection. Una classe che implementa l'interfaccia espone un `Dispose` metodo che può essere chiamato per forzare il rilascio immediato delle risorse importanti.  
  
 Il `Using` istruzione automatizza il processo di acquisizione di una risorsa, l'esecuzione di un set di istruzioni e quindi l'eliminazione della risorsa. Tuttavia, è necessario implementare la risorsa di <xref:System.IDisposable> interfaccia. Per altre informazioni, vedere [Istruzione using](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente dichiara variabili utilizzando la `Dim` istruzione con varie opzioni.  
  
 [!code-vb[VbVbalrStatements#141](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono elencati i numeri primi compreso tra 1 e 30. L'ambito delle variabili locali è descritto nei commenti di codice.  
  
 [!code-vb[VbVbalrStatements#142](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, il `speedValue` variabile viene dichiarata a livello di classe. Il `Private` parola chiave viene utilizzata per dichiarare la variabile. La variabile è accessibile da qualsiasi routine di `Car` classe.  
  
 [!code-vb[VbVbalrStatements#144](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#145](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)  
 [Istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [Istruzione Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Pagina Compilazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [Dichiarazione di variabile](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Array](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Inizializzatori di oggetto: tipi denominati e tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Inizializzatori di oggetto: tipi denominati e tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Procedura: Dichiarare un oggetto usando un inizializzatore di oggetto](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)  
 [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
