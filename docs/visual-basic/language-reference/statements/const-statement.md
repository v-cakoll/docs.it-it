---
title: Istruzione Const (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: bb4c524fa5c29efbcbe485fb5e86c8cf0fa432e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="const-statement-visual-basic"></a>Istruzione Const (Visual Basic)
Dichiara e definisce una o più costanti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## <a name="parts"></a>Parti  
 `attributelist`  
 Facoltativo. Elenco di attributi che si applicano a tutte le costanti dichiarate in questa istruzione. Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md) tra parentesi quadre ("`<`"e"`>`").  
  
 `accessmodifier`  
 Facoltativo. Consente di specificare il codice può accedere a queste costanti. Può essere [pubblica](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, o [privata](../../../visual-basic/language-reference/modifiers/private.md).  
  
 `Shadows`  
 Facoltativo. Consente di dichiarare nuovamente e nascondere un elemento di programmazione in una classe base. Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `constantlist`  
 Obbligatorio. Elenco di costanti che vengono dichiarate in questa istruzione.  
  
 `constant` `[ ,` `constant` `... ]`  
  
 Ogni `constant` presenta la sintassi e le parti seguenti:  
  
 `constantname` `[ As` `datatype` `] =` `initializer`  
  
|Parte|Descrizione|  
|----------|-----------------|  
|`constantname`|Obbligatorio. Nome della costante. Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`datatype`|Obbligatorio se `Option Strict` è `On`. Tipo di dati della costante.|  
|`initializer`|Obbligatorio. Espressione che viene valutata in fase di compilazione e assegnato alla costante.|  
  
## <a name="remarks"></a>Note  
 Se si dispone di un valore che non viene mai modificata nell'applicazione, è possibile definire una costante denominata e utilizzarlo al posto di un valore letterale. È facile da ricordare rispetto a un valore di un nome. È possibile definire la costante a una sola volta e usarla in numerose posizioni nel codice. Se in una versione successiva è necessario ridefinire il valore, il `Const` istruzione è l'unico punto è necessario apportare una modifica.  
  
 È possibile utilizzare `Const` solo a livello di modulo o routine. Ciò significa che il *contesto della dichiarazione* per una variabile deve essere una classe, struttura, modulo, routine o blocco e non può essere un file di origine, lo spazio dei nomi o interfaccia. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Impostazione predefinita le costanti locali (all'interno di una routine) per l'accesso pubblico ed è possibile utilizzare modificatori di accesso su di essi. Classe e modulo predefinito di costanti (all'esterno di qualsiasi routine) membro accesso privato e predefinito di costanti di membro di struttura per l'accesso pubblico. È possibile regolare i livelli di accesso con i modificatori di accesso.  
  
## <a name="rules"></a>Regole  
  
-   **Contesto della dichiarazione.** Una costante dichiarata a livello di modulo, all'esterno di qualsiasi routine, un *costante membro*; è un membro della classe, struttura o modulo che lo dichiara.  
  
     Una costante dichiarata a livello di routine è un *costante locale*; è locale per la routine o un blocco che lo dichiara.  
  
-   **Attributi.** È possibile applicare gli attributi solo per le costanti di membro, non per le costanti locali. Un attributo fornisce informazioni per i metadati dell'assembly, che non è significativo per l'archiviazione temporanea, ad esempio le costanti locali.  
  
-   **Modificatori.** Per impostazione predefinita, tutte le costanti sono `Shared`, `Static`, e `ReadOnly`. Non è possibile utilizzare uno qualsiasi di queste parole chiave per dichiarare una costante.  
  
     A livello di routine, non è possibile utilizzare `Shadows` o i modificatori di accesso per dichiarare le costanti locali.  
  
-   **Più costanti.** È possibile dichiarare più costanti nella stessa istruzione di dichiarazione, specificando il `constantname` parte per ognuno di essi. Più costanti sono separate da virgole.  
  
## <a name="data-type-rules"></a>Regole di tipo di dati  
  
-   **Tipi di dati.** Il `Const` istruzione può dichiarare il tipo di dati di una variabile. È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione.  
  
-   **Tipo predefinito.** Se non si specifica `datatype`, la costante accetta il tipo di dati `initializer`. Se si specificano entrambi `datatype` e `initializer`, il tipo di dati `initializer` deve essere convertibile in `datatype`. Se non si specifica `datatype` né `initializer` è presente, il tipo di dati predefinite per `Object`.  
  
-   **Tipi diversi.** È possibile specificare i tipi di dati diversi per costanti diverse utilizzando un oggetto separato `As` clausola per ogni variabile è dichiarata. Tuttavia, non è possibile dichiarare più costanti dello stesso tipo utilizzando un comune `As` clausola.  
  
-   **inizializzazione.** È necessario inizializzare il valore di ogni costante in `constantlist`. Utilizzare `initializer` per fornire un'espressione da assegnare alla costante. L'espressione può essere qualsiasi combinazione di valori letterali, sono già definite altre costanti e membri di enumerazione che sono già definiti. È possibile utilizzare gli operatori aritmetici e logici per combinare tali elementi.  
  
     Non è possibile utilizzare variabili o funzioni `initializer`. Tuttavia, è possibile utilizzare parole chiave di conversione, ad esempio `CByte` e `CShort`. È inoltre possibile utilizzare `AscW` se viene chiamata con una costante `String` o `Char` argomento, dal momento che può essere valutato in fase di compilazione.  
  
## <a name="behavior"></a>Comportamento  
  
-   **Ambito.** Le costanti locali sono accessibili solo dall'interno della routine o un blocco. Costanti di membro sono accessibili da qualsiasi punto all'interno di loro classe, struttura o modulo.  
  
-   **Qualifica.** Codice esterno di una classe, struttura o un modulo necessario qualificare il nome di una costante membro con il nome di tale classe, struttura o modulo. All'esterno di che una stored procedure o un blocco non può fare riferimento a costanti locali all'interno della routine o un blocco di codice.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Const` istruzione per dichiarare le costanti da utilizzare in sostituzione di valori letterali.  
  
 [!code-vb[VbVbalrStatements#13](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_1.vb)]  
  
## <a name="example"></a>Esempio  
 Se si definisce una costante con tipo di dati `Object`, il compilatore Visual Basic fornisce il tipo di `initializer`, invece di `Object`. Nell'esempio seguente, la costante `naturalLogBase` è di tipo in fase di esecuzione `Decimal`.  
  
 [!code-vb[VbVbalrStatements#87](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_2.vb)]  
  
 Nell'esempio precedente viene utilizzato il <xref:System.Type.ToString%2A> metodo il <xref:System.Type> oggetto restituito dal [operatore GetType](../../../visual-basic/language-reference/operators/gettype-operator.md)perché <xref:System.Type> non può essere convertito in `String` utilizzando `CStr`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 [Istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Direttiva #Const](../../../visual-basic/language-reference/directives/const-directive.md)  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Costanti ed enumerazioni](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 [Costanti ed enumerazioni](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
