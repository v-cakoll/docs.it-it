---
title: Istruzione Class (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Class
helpviewer_keywords:
- class modules
- Class statement [Visual Basic]
- classes [Visual Basic], fields
- fields [Visual Basic], of classes
- class types [Visual Basic], class statements
- classes [Visual Basic], creating
- classes [Visual Basic], data members
- data members [Visual Basic], of classes
ms.assetid: f2664f38-eb5a-4d4b-a374-1d041521fb6c
ms.openlocfilehash: 7bc2d6a6b3e01cd7efa00763d3b9bf3a0026be6f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975875"
---
# <a name="class-statement-visual-basic"></a>Istruzione Class (Visual Basic)
Dichiara il nome di una classe e introduce la definizione delle variabili, proprietà, eventi e le procedure che comprende la classe.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] [ Partial ] _  
Class name [ ( Of typelist ) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ statements ]  
End Class  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`attributelist`|Facoltativo. Visualizzare [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Facoltativo. Può essere uno dei seguenti:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protetto](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br />- [Private Protected](../../language-reference/modifiers/private-protected.md)<br/><br/> Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Facoltativo. Visualizzare [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Facoltativo. Visualizzare [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Facoltativo. Visualizzare [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`Partial`|Facoltativo. Indica una definizione parziale della classe. Visualizzare [parziale](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Obbligatorio. Nome di questa classe. Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Facoltativo. Specifica che si tratta di una classe generica.|  
|`typelist`|Obbligatorio se si usa la [di](../../../visual-basic/language-reference/statements/of-clause.md) (parola chiave). Elenco di parametri di tipo per questa classe. Visualizzare [elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Facoltativo. Indica che questa classe eredita i membri di un'altra classe. Visualizzare [istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Obbligatorio se si usa il `Inherits` istruzione. Il nome della classe da cui deriva questa classe.|  
|`Implements`|Facoltativo. Indica che questa classe implementa i membri di una o più interfacce. Visualizzare [implementa istruzione](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Obbligatorio se si usa il `Implements` istruzione. I nomi delle interfacce di che questa classe implementa.|  
|`statements`|Facoltativo. Istruzioni che definiscono i membri di questa classe.|  
|`End Class`|Obbligatorio. Termina il `Class` definizione.|  
  
## <a name="remarks"></a>Note  
 Oggetto `Class` istruzione definisce un nuovo tipo di dati. Oggetto *classe* è un blocco predefinito fondamentale della programmazione orientata agli oggetti (OOP). Per altre informazioni, vedere [oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
 È possibile usare `Class` solo a livello di spazio dei nomi o modulo. Ciò significa che il *contesto della dichiarazione* per una classe deve essere un file di origine, lo spazio dei nomi, classe, struttura, modulo o dell'interfaccia e non può essere una routine o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Ogni istanza di una classe ha una durata indipendente da tutte le altre istanze. Questa durata ha inizio quando viene creato da un [nuovo operatore](../../../visual-basic/language-reference/operators/new-operator.md) clausola o da una funzione, ad esempio <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>. Termina quando tutte le variabili che puntano all'istanza sono state impostate su [Nothing](../../../visual-basic/language-reference/nothing.md) o per istanze di altre classi.  
  
 Le classi per impostazione predefinita a [Friend](../../../visual-basic/language-reference/modifiers/friend.md) accesso. È possibile modificare i livelli di accesso con i modificatori di accesso. Per altre informazioni, vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regole  
  
-   **Annidamento.** È possibile definire una classe all'interno di altra. Classe esterna viene chiamata il *contenente classi*, e la classe interna viene chiamata una *classi annidate*.  
  
-   **Ereditarietà.** Se la classe Usa il [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md), è possibile specificare solo una classe di base o interfaccia. Una classe non può ereditare da più di un elemento.  
  
     Una classe non può ereditare da un'altra classe con un livello di accesso più restrittivo. Ad esempio, un `Public` classe non può ereditare da un `Friend` classe.  
  
     Una classe non può ereditare da una classe annidata al suo interno.  
  
-   **Implementazione.** Se la classe Usa il [istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md), è necessario implementare tutti i membri definiti da ogni interfaccia specificata in `interfacenames`. Un'eccezione è reimplementazione di un membro di classe di base. Per altre informazioni, vedere "Reimplementazione" nella [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
-   **Proprietà predefinita.** Una classe può specificare al massimo una proprietà come relativo *predefiniti delle proprietà*. Per altre informazioni, vedere [predefinito](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Comportamento  
  
-   **Livello di accesso.** All'interno di una classe, è possibile dichiarare ogni membro con il proprio livello di accesso. Per impostazione predefinita i membri della classe [pubbliche](../../../visual-basic/language-reference/modifiers/public.md) accedere, ad eccezione delle variabili e costanti, quale per impostazione predefinita ai [privati](../../../visual-basic/language-reference/modifiers/private.md) accesso. Quando una classe, l'accesso è più limitato rispetto a uno dei relativi membri, il livello di accesso della classe ha la precedenza.  
  
-   **Ambito.** Una classe è l'ambito relativo dello spazio dei nomi, classe, struttura o modulo che lo contiene.  
  
     L'ambito di ogni membro della classe è l'intera classe.  
  
     **Ciclo di vita.** Visual Basic non supporta le classi statiche. L'equivalente funzionale di una classe statica viene fornito da un modulo. Per altre informazioni, vedere [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     I membri della classe hanno durate a seconda di come e dove vengono dichiarati. Per altre informazioni, vedere [durata in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   **Qualification.** Il codice all'esterno di una classe deve qualificare il nome di un membro con il nome di tale classe.  
  
     Se il codice all'interno di una classe annidata contiene un riferimento non qualificato a un elemento di programmazione, Visual Basic cerca prima della classe annidata, quindi nella classe che contiene e così via per l'elemento più esterno.  
  
## <a name="classes-and-modules"></a>Classi e moduli  
 Questi elementi presentano molte analogie, ma esistono alcune importanti differenze.  
  
-   **Terminology.** Le versioni precedenti di Visual Basic riconoscono due tipi di moduli: *classe moduli* (file CLS) e *moduli standard* (file con estensione BAS). La versione corrente chiama questi *classi* e *moduli*, rispettivamente.  
  
-   **Membri condivisi.** È possibile controllare se un membro di una classe è condivisa o membro di istanza.  
  
-   **Orientamento agli oggetti.** Le classi sono orientate a oggetti, ma non sono i moduli. È possibile creare uno o più istanze di una classe. Per altre informazioni, vedere [oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un `Class` istruzione per definire una classe e alcuni membri.  
  
 [!code-vb[VbVbalrStatements#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#62)]  
  
## <a name="see-also"></a>Vedere anche
- [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Strutture e classi](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md)
- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Durata degli oggetti: Come gli oggetti vengono creati ed eliminati](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Procedura: Usare una classe generica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
