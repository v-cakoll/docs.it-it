---
title: Istruzione Const (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: 089c2dca99373f379e1eff319cf8c41242e5f135
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835310"
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
 Facoltativo. Elenco di attributi che si applicano a tutte le costanti dichiarato nella presente informativa. Visualizzare [elenco di attributi](../../../visual-basic/language-reference/statements/attribute-list.md) parentesi angolari ("`<`"e"`>`").  
  
 `accessmodifier`  
 Facoltativo. Questa scheda consente di specificare il tipo di codice può accedere a queste costanti. Può essere [pubbliche](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [privata](../../../visual-basic/language-reference/modifiers/private.md), o [Private Protected](../../language-reference/modifiers/private-protected.md).
  
 `Shadows`  
 Facoltativo. Consente di dichiarare nuovamente e nascondere un elemento di programmazione in una classe base. Visualizzare [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `constantlist`  
 Obbligatorio. Elenco di costanti che vengono dichiarate in questa istruzione.  
  
 `constant` `[ ,` `constant` `... ]`  
  
 Ogni `constant` presenta la sintassi e le parti seguenti:  
  
 `constantname` `[ As` `datatype` `] =` `initializer`  
  
|Parte|Descrizione|  
|----------|-----------------|  
|`constantname`|Obbligatorio. Nome della costante. Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`datatype`|Obbligatorio se `Option Strict` è `On`. Tipo di dati della costante.|  
|`initializer`|Obbligatorio. Espressione che viene valutata in fase di compilazione e assegnato alla costante.|  
  
## <a name="remarks"></a>Note  
 Se si dispone di un valore che non cambia mai nell'applicazione, è possibile definire una costante denominata e usarlo al posto di un valore letterale. È più facile da ricordare al valore di un nome. È possibile definire la costante a una sola volta e usarla in molte posizioni nel codice. Se in una versione successiva è necessario ridefinire il valore di `Const` istruzione è l'unica piattaforma è necessario apportare una modifica.  
  
 È possibile usare `Const` solo a livello di modulo o routine. Ciò significa che il *contesto della dichiarazione* per una variabile deve essere una classe, struttura, modulo, procedura o blocco e non può essere un file di origine, lo spazio dei nomi o interfaccia. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Predefinito di costante locale (all'interno di una routine) per l'accesso pubblico e si non è possibile usare modificatori di accesso su di essi. Classe e il modulo predefinito di costanti (all'esterno di qualsiasi routine) membri per accesso privato e predefinito di costanti di membro di struttura per l'accesso pubblico. È possibile modificare i livelli di accesso con i modificatori di accesso.  
  
## <a name="rules"></a>Regole  
  
-   **Contesto della dichiarazione.** Una costante dichiarata a livello di modulo, all'esterno di qualsiasi routine è una *costante membro*; è un membro della classe, struttura, o modulo che lo dichiara.  
  
     Una costante dichiarata a livello di routine è una *costante locale*; è locale per la routine o un blocco che lo dichiara.  
  
-   **Attributi.** È possibile applicare gli attributi solo per le costanti di membro, non per le costanti locali. Un attributo fornisce informazioni per i metadati dell'assembly, che non è significativo per l'archiviazione temporanea, ad esempio le costanti locali.  
  
-   **Modificatori.** Per impostazione predefinita, tutte le costanti vengono `Shared`, `Static`, e `ReadOnly`. È possibile utilizzare queste parole chiave quando si dichiara una costante.  
  
     A livello di routine, non è possibile usare `Shadows` o qualsiasi modificatori di accesso per dichiarare le costanti locali.  
  
-   **Più costanti.** È possibile dichiarare le costanti diversi nella stessa istruzione di dichiarazione, specificando il `constantname` parte per ognuno di essi. Più costanti sono separate da virgole.  
  
## <a name="data-type-rules"></a>Regole di tipo di dati  
  
-   **Tipi di dati.** Il `Const` istruzione può dichiarare il tipo di dati di una variabile. È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione.  
  
-   **Tipo predefinito.** Se non si specifica `datatype`, la costante accetta il tipo di dati di `initializer`. Se si specificano entrambe `datatype` e `initializer`, il tipo di dati `initializer` deve essere convertibile in `datatype`. Se nessuno di essi `datatype` né `initializer` è presente, il valore predefinito è di tipo di dati `Object`.  
  
-   **Tipi diversi.** È possibile specificare tipi di dati diversi per le costanti diversi utilizzando un oggetto separato `As` clausola per ogni variabile è dichiarata. Tuttavia, non è possibile dichiarare più costanti dello stesso tipo tramite un comune `As` clausola.  
  
-   **Inizializzazione.** È necessario inizializzare il valore di ogni costante in `constantlist`. Si utilizza `initializer` per fornire un'espressione da assegnare alla costante. L'espressione può essere qualsiasi combinazione di valori letterali, altre costanti che sono già definite e membri di enumerazione che sono già definiti. È possibile utilizzare gli operatori logici e aritmetici per combinare tali elementi.  
  
     È possibile usare le variabili o funzioni in `initializer`. Tuttavia, è possibile utilizzare parole chiave di conversione, ad esempio `CByte` e `CShort`. È anche possibile usare `AscW` se viene chiamata con una costante `String` o `Char` argomento, dal momento che possono essere valutati in fase di compilazione.  
  
## <a name="behavior"></a>Comportamento  
  
-   **Ambito.** Costanti locali sono accessibili solo dall'interno della routine o un blocco. Costanti di membro sono accessibili da qualsiasi punto all'interno di loro classe, struttura o modulo.  
  
-   **Qualification.** Codice esterno di una classe, struttura o un modulo necessario qualificare il nome di una costante membro con il nome di tale classe, struttura o modulo. All'esterno di che una routine o un blocco non può fare riferimento a costanti locali all'interno di tale routine o un blocco di codice.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Const` istruzione per dichiarare le costanti per l'uso al posto dei valori letterali.  
  
 [!code-vb[VbVbalrStatements#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#13)]  
  
## <a name="example"></a>Esempio  
 Se si definisce una costante con tipo di dati `Object`, il compilatore Visual Basic restituisce il tipo della `initializer`, invece di `Object`. Nell'esempio seguente, la costante `naturalLogBase` ha il tipo di runtime `Decimal`.  
  
 [!code-vb[VbVbalrStatements#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#87)]  
  
 L'esempio precedente Usa la <xref:System.Type.ToString%2A> metodo sul <xref:System.Type> oggetto restituito dal [operatore GetType](../../../visual-basic/language-reference/operators/gettype-operator.md), in quanto <xref:System.Type> non può essere convertito in `String` usando `CStr`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md)
- [Direttiva #Const](../../../visual-basic/language-reference/directives/const-directive.md)
- [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Istruzione ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Costanti ed enumerazioni](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [Costanti ed enumerazioni](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
