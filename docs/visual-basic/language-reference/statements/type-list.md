---
title: Elenco dei tipi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: 5fbb07154fce27feb257b431c1726446b42fbfe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605290"
---
# <a name="type-list-visual-basic"></a>Elenco dei tipi (Visual Basic)
Specifica il *parametri di tipo* per un *generico* elemento di programmazione. Più parametri sono separati da virgole. Di seguito è la sintassi per un parametro di tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`genericmodifier`|Facoltativo. Può essere utilizzato solo nelle interfacce e delegati generici. È possibile dichiarare un tipo covariante utilizzando il [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) parola chiave o controvarianti utilizzando il [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) (parola chiave). Vedere [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md).|  
|`typename`|Obbligatorio. Nome del parametro di tipo. Questo è un segnaposto, dovrà essere sostituito da un tipo definito specificato dall'argomento di tipo corrispondente.|  
|`constraintlist`|Facoltativo. Elenco di requisiti che vincolano il tipo di dati che può essere fornito per `typename`. Se si dispone di più vincoli, racchiuderli tra parentesi graffe (`{ }`) e separarle con virgole. È necessario introdurre l'elenco di vincoli con la [come](../../../visual-basic/language-reference/statements/as-clause.md) (parola chiave). Utilizzare `As` una sola volta, all'inizio dell'elenco.|  
  
## <a name="remarks"></a>Note  
 Ogni elemento di programmazione generico deve prendere almeno un parametro di tipo. Un parametro di tipo è un segnaposto per un tipo specifico (un *elemento costruito*) che il codice client specifica quando crea un'istanza del tipo generico. È possibile definire una classe generica, struttura, interfaccia, routine o delegato.  
  
 Per ulteriori informazioni sui casi in cui definire un tipo generico, vedere [tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md). Per ulteriori informazioni sui nomi dei parametri di tipo, vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Regole  
  
-   **Parentesi.** Se si fornisce un elenco di parametri di tipo, è necessario racchiuderlo tra parentesi ed è necessario introdurre l'elenco con il [di](../../../visual-basic/language-reference/statements/of-clause.md) (parola chiave). Utilizzare `Of` una sola volta, all'inizio dell'elenco.  
  
-   **Vincoli.** Un elenco di *vincoli* su un tipo di parametro può includere gli elementi seguenti in qualsiasi combinazione:  
  
    -   Numero qualsiasi di interfacce. Il tipo fornito deve implementare ogni interfaccia in questo elenco.  
  
    -   Al massimo una classe. Il tipo fornito deve ereditare da quella classe.  
  
    -   Parola chiave `New`. Il tipo fornito deve esporre un costruttore senza parametri accessibile il tipo generico. Ciò è utile se si vincola un parametro di tipo da uno o più interfacce. Un tipo che implementa le interfacce non necessariamente esporre un costruttore e a seconda del livello di accesso di un costruttore, il codice all'interno del tipo generico potrebbe non essere in grado di accedervi.  
  
    -   Entrambi i `Class` parola chiave o `Structure` (parola chiave). Il `Class` (parola chiave) Vincola un parametro di tipo generico per fare in modo che qualsiasi argomento di tipo passato è un tipo di riferimento, ad esempio una stringa, matrice o delegato, o un oggetto creato da una classe. Il `Structure` (parola chiave) Vincola un parametro di tipo generico per richiedere che qualsiasi argomento di tipo passato sia un tipo valore, ad esempio una struttura, enumerazione o tipo di dati di tipo. È possibile includere entrambi `Class` e `Structure` nello stesso `constraintlist`.  
  
     Il tipo specificato deve soddisfare tutti i requisiti inclusi in `constraintlist`.  
  
     I vincoli su ogni parametro di tipo sono indipendenti dai vincoli su altri parametri di tipo.  
  
## <a name="behavior"></a>Comportamento  
  
-   **Sostituzione della fase di compilazione.** Quando si crea un tipo costruito da un elemento di programmazione generico, si fornisce un tipo definito per ogni parametro di tipo. Il compilatore Visual Basic sostituisce il tipo specificato per tutte le occorrenze di `typename` all'interno dell'elemento generico.  
  
-   **Assenza di vincoli.** Se non si specifica alcun vincolo su un parametro di tipo, il codice è limitato alle operazioni e ai membri supportati dal [tipo di dati Object](../../../visual-basic/language-reference/data-types/object-data-type.md) per tale parametro di tipo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una struttura di definizione di una classe di dizionari generici, tra cui una funzione di base per aggiungere una nuova voce di dizionario.  
  
 [!code-vb[VbVbalrStatements#3](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_1.vb)]  
  
## <a name="example"></a>Esempio  
 Poiché `dictionary` è generico, il codice che lo utilizza può creare una varietà di oggetti da esso, ciascuno con le stesse funzionalità ma che agisce su un tipo di dati diversi. L'esempio seguente mostra una riga di codice che crea un `dictionary` con `String` voci e `Integer` chiavi.  
  
 [!code-vb[VbVbalrStatements#4](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_2.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene generata dall'esempio precedente la definizione di base equivalente.  
  
 [!code-vb[VbVbalrStatements#5](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_3.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
 [Operatore New](../../../visual-basic/language-reference/operators/new-operator.md)  
 [Livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Tipo di dati Object](../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Procedura: Usare una classe generica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
