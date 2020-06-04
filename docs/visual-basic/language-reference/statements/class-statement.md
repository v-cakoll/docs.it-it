---
title: Istruzione Class
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
ms.openlocfilehash: bdb73772dfe0e6d49d89a4ef006b1bceac14c8ee
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397155"
---
# <a name="class-statement-visual-basic"></a>Istruzione Class (Visual Basic)
Dichiara il nome di una classe e introduce la definizione di variabili, proprietà, eventi e routine inclusi nella classe.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
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
|`attributelist`|Facoltativa. Vedere [elenco attributi](attribute-list.md).|  
|`accessmodifier`|Facoltativa. Può essere uno dei seguenti:<br /><br /> -   [Pubblico](../modifiers/public.md)<br />-   [Protetto](../modifiers/protected.md)<br />-   [Amico](../modifiers/friend.md)<br />-   [Privata](../modifiers/private.md)<br />-   [Amico protetto](../modifiers/protected-friend.md)<br />- [Privato protetto](../modifiers/private-protected.md)<br/><br/> Vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Facoltativa. Vedere [Shadows](../modifiers/shadows.md).|  
|`MustInherit`|Facoltativa. Vedere [MustInherit](../modifiers/mustinherit.md).|  
|`NotInheritable`|Facoltativa. Vedere [NotInheritable](../modifiers/notinheritable.md).|  
|`Partial`|Facoltativa. Indica una definizione parziale della classe. Vedere [parziale](../modifiers/partial.md).|  
|`name`|Obbligatorio. Nome di questa classe. Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Facoltativa. Specifica che si tratta di una classe generica.|  
|`typelist`|Obbligatorio se si usa la parola chiave [of](of-clause.md) . Elenco di parametri di tipo per questa classe. Vedere [elenco dei tipi](type-list.md).|  
|`Inherits`|Facoltativa. Indica che questa classe eredita i membri di un'altra classe. Vedere [istruzione Inherits](inherits-statement.md).|  
|`classname`|Obbligatorio se si usa l' `Inherits` istruzione. Nome della classe da cui deriva questa classe.|  
|`Implements`|Facoltativa. Indica che questa classe implementa i membri di una o più interfacce. Vedere [istruzione Implements](implements-statement.md).|  
|`interfacenames`|Obbligatorio se si usa l' `Implements` istruzione. Nomi delle interfacce implementate da questa classe.|  
|`statements`|Facoltativa. Istruzioni che definiscono i membri di questa classe.|  
|`End Class`|Obbligatorio. Termina la `Class` definizione.|  
  
## <a name="remarks"></a>Commenti  
 Un' `Class` istruzione definisce un nuovo tipo di dati. Una *classe* è un blocco predefinito fondamentale della programmazione orientata a oggetti (OOP). Per altre informazioni, vedere [oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md).  
  
 È possibile usare `Class` solo a livello di spazio dei nomi o di modulo. Ciò significa che il *contesto di dichiarazione* per una classe deve essere un file di origine, uno spazio dei nomi, una classe, una struttura, un modulo o un'interfaccia e non può essere una routine o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).  
  
 Ogni istanza di una classe ha una durata indipendente da tutte le altre istanze. Questa durata inizia quando viene creata da una [nuova clausola operator](../operators/new-operator.md) o da una funzione come <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A> . Termina quando tutte le variabili che puntano all'istanza sono state impostate su [Nothing](../nothing.md) o su istanze di altre classi.  
  
 Per impostazione predefinita, le classi accedono a [Friend](../modifiers/friend.md) . È possibile modificare i livelli di accesso con i modificatori di accesso. Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regole  
  
- **Annidamento.** È possibile definire una classe all'interno di un'altra. La classe esterna viene chiamata *classe che la contiene*e la classe interna è chiamata *classe annidata*.  
  
- **Ereditarietà.** Se la classe utilizza l' [istruzione Inherits](inherits-statement.md), è possibile specificare solo una classe o un'interfaccia di base. Una classe non può ereditare da più di un elemento.  
  
     Una classe non può ereditare da un'altra classe con un livello di accesso più restrittivo. Una classe, ad esempio, `Public` non può ereditare da una `Friend` classe.  
  
     Una classe non può ereditare da una classe annidata al suo interno.  
  
- **Implementazione.** Se la classe utilizza l' [istruzione Implements](implements-statement.md), è necessario implementare ogni membro definito da ogni interfaccia specificata in `interfacenames` . Un'eccezione a questa operazione è la riimplementazione di un membro della classe base. Per ulteriori informazioni, vedere la sezione relativa alla riimplementazione in [Implements](implements-clause.md).  
  
- **Proprietà predefinita.** Una classe può specificare al massimo una proprietà come *proprietà predefinita*. Per ulteriori informazioni, vedere [default](../modifiers/default.md).  
  
## <a name="behavior"></a>Comportamento  
  
- **Livello di accesso.** All'interno di una classe, è possibile dichiarare ogni membro con il proprio livello di accesso. I membri della classe hanno per impostazione predefinita l'accesso [pubblico](../modifiers/public.md) , eccetto le variabili e le costanti, per impostazione predefinita l'accesso [privato](../modifiers/private.md) . Quando una classe dispone di un accesso più limitato di uno dei relativi membri, il livello di accesso della classe ha la precedenza.  
  
- **Ambito.** Una classe è nell'ambito di tutti gli spazi dei nomi, la classe, la struttura o il modulo che lo contiene.  
  
     L'ambito di ogni membro della classe è l'intera classe.  
  
     **Vita.** Visual Basic non supporta classi statiche. L'equivalente funzionale di una classe statica viene fornito da un modulo. Per ulteriori informazioni, vedere [istruzione Module](module-statement.md).  
  
     I membri della classe hanno durate a seconda della modalità e della posizione in cui vengono dichiarati. Per ulteriori informazioni, vedere [Lifetime in Visual Basic](../../programming-guide/language-features/declared-elements/lifetime.md).  
  
- **Qualificazione.** Il codice esterno a una classe deve qualificare il nome di un membro con il nome della classe.  
  
     Se il codice all'interno di una classe annidata crea un riferimento non qualificato a un elemento di programmazione, Visual Basic cerca prima l'elemento nella classe annidata, quindi nella classe che lo contiene e così via fino all'elemento contenitore più esterno.  
  
## <a name="classes-and-modules"></a>Classi e moduli  
 Questi elementi presentano molte analogie, ma esistono anche alcune differenze importanti.  
  
- **Terminologia.** Le versioni precedenti di Visual Basic riconoscono due tipi di moduli: *moduli di classe* (file con estensione CLS) e *moduli standard* (file con estensione BAS). La versione corrente chiama queste *classi* e *moduli*, rispettivamente.  
  
- **Membri condivisi.** È possibile controllare se un membro di una classe è un membro condiviso o di istanza.  
  
- **Orientamento dell'oggetto.** Le classi sono orientate agli oggetti, ma i moduli non lo sono. È possibile creare una o più istanze di una classe. Per altre informazioni, vedere [oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata un' `Class` istruzione per definire una classe e diversi membri.  
  
 [!code-vb[VbVbalrStatements#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#62)]  
  
## <a name="see-also"></a>Vedere anche

- [Oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md)
- [Strutture e classi](../../programming-guide/language-features/data-types/structures-and-classes.md)
- [Istruzione Interface](interface-statement.md)
- [Istruzione Module](module-statement.md)
- [Property Statement](property-statement.md)
- [Durata degli oggetti: come creare e distruggere oggetti](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Procedura: Usare una classe generica](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
