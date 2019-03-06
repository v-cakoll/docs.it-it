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
ms.openlocfilehash: 7bee6bffcfe0660d1661cd2c8e2ddf0528e98620
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360264"
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
  
     Facoltativo. Visualizzare [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `accessmodifier`  
  
     Facoltativo. Può essere uno dei seguenti:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [Protected Friend](../../language-reference/modifiers/protected-friend.md)
    
    - [Private Protected](../../language-reference/modifiers/private-protected.md)

     Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `Shared`  
  
     Facoltativo. Visualizzare [condiviso](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Facoltativo. Visualizzare [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Static`  
  
     Facoltativo. Visualizzare [statici](../../../visual-basic/language-reference/modifiers/static.md).  
  
-   `ReadOnly`  
  
     Facoltativo. Visualizzare [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WithEvents`  
  
     Facoltativo. Specifica che si tratta di oggetti variabili che fanno riferimento alle istanze di una classe che può generare eventi. Visualizzare [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).  
  
-   `variablelist`  
  
     Obbligatorio. Elenco di variabili dichiarate in questa istruzione.  
  
     `variable [ , variable ... ]`  
  
     Ogni `variable` presenta la sintassi e le parti seguenti:  
  
     `variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`  
  
    |Parte|Descrizione|  
    |---|---|  
    |`variablename`|Obbligatorio. Nome della variabile. Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
    |`boundslist`|Facoltativo. Elenco dei limiti di ogni dimensione di una variabile di matrice.|  
    |`New`|Facoltativo. Crea una nuova istanza della classe quando il `Dim` istruzione viene eseguita.|  
    |`datatype`|Facoltativo. Tipo di dati della variabile.|  
    |`With`|Facoltativo. Introduce l'elenco di inizializzatori di oggetto.|  
    |`propertyname`|Facoltativo. Il nome di una proprietà nella classe si sta creando un'istanza di.|  
    |`propinitializer`|Dopo necessario `propertyname` =. L'espressione che viene valutata e assegnata al nome della proprietà.|  
    |`initializer`|Facoltativo se `New` non è specificato. Espressione che viene valutata e assegnato alla variabile quando viene creato.|  
  
## <a name="remarks"></a>Note  
 Il compilatore Visual Basic Usa la `Dim` istruzione per determinare il tipo di dati della variabile e altre informazioni, ad esempio il tipo di codice può accedere alla variabile. L'esempio seguente dichiara una variabile per contenere un `Integer` valore.  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, struttura, classe o interfaccia.  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 Per un tipo riferimento, si utilizza il `New` (parola chiave) per creare una nuova istanza della classe o una struttura che viene specificato dal tipo di dati. Se si usa `New`, non si utilizza un'espressione dell'inizializzatore. In alternativa, è fornire argomenti, se sono necessarie, per il costruttore della classe da cui si sta creando la variabile.  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 È possibile dichiarare una variabile in una routine, blocco, classe, struttura o modulo. È possibile dichiarare una variabile in un file di origine, lo spazio dei nomi o interfaccia. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Una variabile dichiarata a livello di modulo, all'esterno di qualsiasi routine è una *variabile membro* oppure *campo*. Le variabili membro rientrano nell'ambito in tutta la classe, struttura o modulo. Una variabile dichiarata a livello di routine è una *variabile locale*. Le variabili locali sono nell'ambito solo all'interno della routine o un blocco.  
  
 I seguenti modificatori di accesso vengono usati per dichiarare le variabili all'esterno di una routine: `Public`, `Protected`, `Friend`, `Protected Friend`, e `Private`. Per altre informazioni, vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Il `Dim` parola chiave è facoltativa e in genere omessi se si specifica uno dei modificatori seguenti: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, o `WithEvents`.  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 Se `Option Explicit` è abilitata (impostazione predefinita), il compilatore richiede una dichiarazione per tutte le variabili utilizzate. Per altre informazioni, vedere [istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md).  
  
## <a name="specifying-an-initial-value"></a>Se si specifica un valore iniziale  
 È possibile assegnare un valore a una variabile quando viene creato. Per un tipo di valore, Usa un' *inizializzatore* per fornire un'espressione da assegnare alla variabile. L'espressione deve restituire una costante che può essere calcolato in fase di compilazione.  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 Se viene specificato un inizializzatore e non viene specificato un tipo di dati un' `As` clausola *inferenza del tipo* viene usato per dedurre il tipo di dati dall'inizializzatore. Nell'esempio seguente, entrambe `num1` e `num2` sono fortemente tipizzati come numeri interi. Nella seconda dichiarazione, inferenza dei tipi deduce il tipo rispetto al valore 3.  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 L'inferenza del tipo si applica a livello di routine. Non è applicabile all'esterno di una routine in una classe, struttura, modulo o interfaccia. Per altre informazioni sull'inferenza del tipo, vedere [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) e [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 Per informazioni su cosa accade quando un tipo di dati o l'inizializzatore viene omesso, vedere [tipi di dati predefiniti e i valori](../../../visual-basic/language-reference/statements/dim-statement.md#default) più avanti in questo argomento.  
  
 È possibile usare un *inizializzatore di oggetto* per dichiarare le istanze di tipi denominati e anonimi. Il codice seguente crea un'istanza di un `Student` classe e Usa un inizializzatore di oggetto per inizializzare le proprietà.  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 Per altre informazioni sugli inizializzatori di oggetto, vedere [come: Dichiarare un oggetto usando un inizializzatore di oggetto](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [inizializzatori di oggetto: Tipi denominati e anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), e [tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="declaring-multiple-variables"></a>Dichiarare più variabili  
 È possibile dichiarare più variabili in un'istruzione di dichiarazione, specificando il nome della variabile per ognuno di essi e dopo ogni nome di matrice con parentesi. Nel caso di più variabili, è possibile separarle mediante virgole.  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 Se si dichiara più di una variabile con uno `As` clausola, non è possibile specificare un inizializzatore per il gruppo di variabili.  
  
 È possibile specificare tipi di dati diversi per diverse variabili utilizzando un oggetto separato `As` clausola per ogni variabile è dichiarata. Ogni variabile ha il tipo di dati specificato nel primo `As` clausola rilevata dopo il relativo `variablename` parte.  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a>Matrici  
 È possibile dichiarare una variabile per contenere un *matrice*, che può contenere più valori. Per specificare che una variabile contiene una matrice, seguire le `variablename` immediatamente con le parentesi. Per altre informazioni sulle matrici, vedere [Matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 È possibile specificare il limite inferiore e superiore di ogni dimensione della matrice. A tale scopo, includere un `boundslist` all'interno delle parentesi. Per ogni dimensione, il `boundslist` specifica il limite superiore e, facoltativamente, il limite inferiore. Il limite inferiore è sempre uguale a zero, se si specifichi o meno. Ogni indice può variare da zero tramite il relativo valore limite superiore.  
  
 Le due istruzioni seguenti sono equivalenti. Ogni istruzione dichiara una matrice di 21 `Integer` elementi. Quando si accede a matrice, l'indice può variare da 0 a 20.  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 L'istruzione seguente dichiara una matrice bidimensionale di tipo `Double`. La matrice ha 4 righe (3 + 1) di 6 (5 + 1) ogni colonna. Si noti che il limite superiore rappresenta il valore massimo possibile per l'indice, non la lunghezza della dimensione. La lunghezza della dimensione è il limite superiore più uno.  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 Una matrice può avere da 1 a 32 dimensioni.  
  
 È possibile lasciare vuoto in una dichiarazione di matrice tutti i limiti. In questo caso, la matrice disponga del numero di dimensioni specificato, ma è non inizializzato. Assume un valore di `Nothing` finché non viene inizializzata almeno alcuni dei relativi elementi. Il `Dim` istruzione deve specificare i limiti per tutte le dimensioni o per nessuna dimensione.  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 Se la matrice ha più di una dimensione, è necessario includere virgole tra parentesi per indicare il numero di dimensioni.  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 È possibile dichiarare un *matrice di lunghezza zero* dichiarando una delle dimensioni della matrice-1. Una variabile che contiene una matrice di lunghezza zero non ha il valore `Nothing`. Matrici di lunghezza zero sono richiesti da alcune funzioni di common language runtime. Se si tenta di accedere ad esempio una matrice, si verifica un'eccezione di runtime. Per altre informazioni, vedere [matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 È possibile inizializzare i valori di una matrice con un valore letterale di matrice. A tale scopo, racchiudere i valori di inizializzazione con parentesi graffe (`{}`).  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 Per le matrici multidimensionali, l'inizializzazione di ogni dimensione separata è racchiuso tra parentesi graffe nella dimensione esterna. Gli elementi vengono specificati in ordine di riga.  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 Per altre informazioni sui valori letterali di matrice, vedere [matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="default"></a> Tipi di dati predefiniti e i valori  
 Nella tabella seguente vengono descritti i risultati di varie combinazioni della specifica del tipo di dati e dell'inizializzatore in un'istruzione `Dim`.  
  
|Tipo di dati specificato?|Inizializzatore specificato?|Esempio|Risultato|  
|---|---|---|---|  
|No|No|`Dim qty`|Se [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) è disattivata (impostazione predefinita), la variabile è impostata su `Nothing`.<br /><br /> Se `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|  
|No|Sì|`Dim qty = 5`|Se [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) è abilitata (impostazione predefinita), la variabile accetta i dati di tipo dell'inizializzatore. Visualizzare [inferenza del tipo locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).<br /><br /> Se le istruzioni `Option Infer` e `Option Strict` sono disabilitate, il tipo di dati accettato dalla variabile è `Object`.<br /><br /> Se `Option Infer` è disabilitato e `Option Strict` è abilitato, si verifica un errore in fase di compilazione.|  
|Sì|No|`Dim qty As Integer`|La variabile viene inizializzata sul valore predefinito per il tipo di dati. Vedere la tabella più avanti in questa sezione.|  
|Sì|Sì|`Dim qty  As Integer = 5`|Se il tipo di dati dell'inizializzatore non è convertibile nel tipo di dati specificato, si verifica un errore in fase di compilazione.|  
  
 Se si specifica un tipo di dati ma non si specifica un inizializzatore, Visual Basic consente di inizializzare la variabile sul valore predefinito per il tipo di dati. La tabella seguente illustra l'impostazione predefinita i valori di inizializzazione.  
  
|Tipo di dati|Valore predefinito|  
|---|---|  
|Tutti i tipi numerici (incluso `Byte` e `SByte`)|0|  
|`Char`|Binario 0|  
|I tipi di riferimento (incluso `Object`, `String`e tutte le matrici)|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|Dalle 24.00 del 1 ° gennaio dell'anno 1 (01/01/0001 12:00:00 AM)|  
  
 Ogni elemento di struttura viene inizializzato come se fosse una variabile separata. Se si dichiara la lunghezza di una matrice, ma non si inizializzano gli elementi, ogni elemento viene inizializzato come se fosse una variabile separata.  
  
## <a name="static-local-variable-lifetime"></a>Durata delle variabili locale statica  
 Oggetto `Static` variabile locale ha una durata maggiore rispetto a quello della routine in cui è dichiarata. I limiti di durata della variabile dipendono in cui la routine è dichiarata e se è `Shared`.  
  
|Dichiarazione di routine|Variabile inizializzata|Variabile arresta esistente|  
|---|---|---|  
|In un modulo|La prima volta che viene chiamata la procedura|Quando il programma interrompe l'esecuzione|  
|In una classe o struttura, è procedura `Shared`|La prima volta la procedura viene chiamata su un'istanza specifica o nella classe o struttura stessa|Quando il programma interrompe l'esecuzione|  
|In una classe o struttura, non è procedure `Shared`|La prima volta la procedura viene chiamata su una specifica istanza|Quando l'istanza viene rilasciata per la garbage collection (GC)|  
  
## <a name="attributes-and-modifiers"></a>Attributi e i modificatori  
 È possibile applicare gli attributi solo per le variabili membro, non per le variabili locali. Un attributo fornisce informazioni per i metadati dell'assembly, che non è significativo per l'archiviazione temporanea, ad esempio le variabili locali.  
  
 A livello di modulo, non è possibile usare il `Static` modificatore per dichiarare le variabili membro. A livello di routine, non è possibile usare `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, o qualsiasi modificatori di accesso per dichiarare le variabili locali.  
  
 È possibile specificare il tipo di codice può accedere a una variabile, fornendo un `accessmodifier`. Classe e il modulo predefinito di variabili (all'esterno di qualsiasi routine) membri per accesso privato e predefinita di variabili di membro di struttura per l'accesso pubblico. È possibile modificare i livelli di accesso con i modificatori di accesso. È possibile usare i modificatori di accesso con le variabili locali (all'interno di una routine).  
  
 È possibile specificare `WithEvents` solo le variabili membro, non le variabili locali all'interno di una routine. Se si specifica `WithEvents`, il tipo di dati della variabile deve essere un tipo di classe specifica, non `Object`. Non è possibile dichiarare una matrice con `WithEvents`. Per altre informazioni sugli eventi, vedere [eventi](../../../visual-basic/programming-guide/language-features/events/index.md).  
  
> [!NOTE]
>  Codice esterno di una classe, struttura o un modulo necessario qualificare il nome della variabile di un membro con il nome di tale classe, struttura o modulo. All'esterno di che una routine o un blocco non può fare riferimento a variabili locali all'interno di tale routine o un blocco di codice.  
  
## <a name="releasing-managed-resources"></a>Rilasciare le risorse gestite  
 Il garbage collector di .NET Framework elimina le risorse gestite senza alcuna codifica aggiuntiva da parte dell'utente. Tuttavia, è possibile forzare l'eliminazione di una risorsa gestita anziché attendere che il garbage collector.  
  
 Se una classe mantiene una risorsa particolarmente preziosa e scarsa (ad esempio, un handle di connessione o file di database), è possibile evitare di attendere la successiva garbage collection per pulire un'istanza della classe che non è più in uso. Una classe può implementare il <xref:System.IDisposable> interfaccia per fornire un modo per rilasciare le risorse prima di un'operazione di garbage collection. Una classe che implementa l'interfaccia espone un `Dispose` metodo che può essere chiamato per forzare il rilascio immediato delle risorse preziose.  
  
 Il `Using` istruzione consente di automatizzare il processo di acquisizione di una risorsa, l'esecuzione di un set di istruzioni e successivamente eliminando la risorsa. Tuttavia, è necessario implementare la risorsa di <xref:System.IDisposable> interfaccia. Per altre informazioni, vedere [Istruzione using](../../../visual-basic/language-reference/statements/using-statement.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente dichiara le variabili usando i `Dim` istruzione con varie opzioni.  
  
 [!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente elenca i numeri primi compreso tra 1 e 30. L'ambito delle variabili locali è descritto nei commenti di codice.  
  
 [!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, il `speedValue` variabile viene dichiarata a livello di classe. Il `Private` parola chiave viene usata per dichiarare la variabile. La variabile è accessibile da qualsiasi routine di `Car` classe.  
  
 [!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]  
  
 [!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]  
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)
- [Istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Istruzione Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Istruzione Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Pagina Compilazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [Dichiarazione di variabile](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Matrici](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Inizializzatori di oggetto: Tipi denominati e anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Inizializzatori di oggetto: Tipi denominati e anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Procedura: Dichiarare un oggetto usando un inizializzatore di oggetto](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
