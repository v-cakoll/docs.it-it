---
title: Istruzione Class (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: df86ef0eec67d96f2f997dc5dac7ee2357c6362b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="class-statement-visual-basic"></a>Istruzione Class (Visual Basic)
Dichiara il nome di una classe e introduce la definizione di variabili, proprietà, eventi ed procedure che comprende la classe.  
  
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
|`attributelist`|Parametro facoltativo. Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Parametro facoltativo. Può essere uno dei seguenti:<br /><br /> -   [Pubblica](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protetto](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privato](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Parametro facoltativo. Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Parametro facoltativo. Vedere [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Parametro facoltativo. Vedere [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`Partial`|Parametro facoltativo. Indica una definizione parziale della classe. Vedere [parziale](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Obbligatorio. Nome di questa classe. Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Parametro facoltativo. Specifica che si tratta di una classe generica.|  
|`typelist`|Obbligatorio se si usa il [di](../../../visual-basic/language-reference/statements/of-clause.md) (parola chiave). Elenco di parametri di tipo per questa classe. Vedere [digitare elenco](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Parametro facoltativo. Indica che questa classe eredita i membri di un'altra classe. Vedere [istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Obbligatorio se si usa il `Inherits` istruzione. Il nome della classe da cui deriva questa classe.|  
|`Implements`|Parametro facoltativo. Indica che questa classe implementa i membri di una o più interfacce. Vedere [implementa istruzione](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Obbligatorio se si usa il `Implements` istruzione. I nomi delle interfacce di che questa classe implementa.|  
|`statements`|Parametro facoltativo. Istruzioni che definiscono i membri di questa classe.|  
|`End Class`|Obbligatorio. Termina il `Class` definizione.|  
  
## <a name="remarks"></a>Note  
 Oggetto `Class` istruzione definisce un nuovo tipo di dati. Oggetto *classe* è un blocco predefinito fondamentale per la programmazione orientata a oggetti (OOP). Per ulteriori informazioni, vedere [oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
 È possibile utilizzare `Class` solo a livello di spazio dei nomi o modulo. Ciò significa che il *contesto della dichiarazione* per una classe deve essere un file di origine, lo spazio dei nomi, classe, struttura, modulo o interfaccia e non può essere una stored procedure o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Ogni istanza di una classe ha una durata indipendente da tutte le altre istanze. Questa durata ha inizio quando viene creato da un [nuovo operatore](../../../visual-basic/language-reference/operators/new-operator.md) clausola o da una funzione, ad esempio <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>. Termina quando tutte le variabili che punta all'istanza sono state impostate su [nulla](../../../visual-basic/language-reference/nothing.md) o sulle istanze di altre classi.  
  
 Per impostazione predefinita a classi [Friend](../../../visual-basic/language-reference/modifiers/friend.md) accesso. È possibile regolare i livelli di accesso con i modificatori di accesso. Per ulteriori informazioni, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regole  
  
-   **La nidificazione.** È possibile definire una classe all'interno di altra. La classe esterna viene denominata la *contenente classe*, e la classe interna viene chiamata un *le classi annidate*.  
  
-   **Ereditarietà.** Se la classe utilizza il [istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md), è possibile specificare solo una classe di base o interfaccia. Una classe non può ereditare da più di un elemento.  
  
     Una classe non può ereditare da un'altra classe con un livello di accesso più restrittivo. Ad esempio, un `Public` classe non può ereditare da un `Friend` classe.  
  
     Una classe non può ereditare da una classe annidata al suo interno.  
  
-   **Implementazione.** Se la classe utilizza il [istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md), è necessario implementare ogni membro definito da ogni interfaccia specificata in `interfacenames`. Un'eccezione a questa è una nuove implementazione di un membro di classe di base. Per ulteriori informazioni, vedere "Nuove implementazione" in [implementa](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
-   **Proprietà predefinita.** Una classe possa specificare al massimo una proprietà come relativo *proprietà predefinita*. Per ulteriori informazioni, vedere [predefinito](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Comportamento  
  
-   **Livello di accesso.** All'interno di una classe, è possibile dichiarare ogni membro con il proprio livello di accesso. Per impostazione predefinita ai membri della classe [pubblica](../../../visual-basic/language-reference/modifiers/public.md) accedere, ad eccezione delle variabili e costanti, il valore predefinito per [privata](../../../visual-basic/language-reference/modifiers/private.md) accesso. Quando una classe ha più limitato l'accesso a uno dei relativi membri, il livello di accesso della classe ha la precedenza.  
  
-   **Ambito.** Una classe è l'ambito relativo spazio dei nomi, classe, struttura o modulo contenitore.  
  
     L'ambito di ogni membro della classe è l'intera classe.  
  
     **Durata.** Visual Basic non supporta le classi statiche. L'equivalente funzionale di una classe statica viene fornito da un modulo. Per ulteriori informazioni, vedere [istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     I membri di classe hanno durate a seconda di come e dove vengono dichiarate. Per ulteriori informazioni, vedere [durata in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   **Qualifica.** Codice esterno di una classe è necessario qualificare il nome di un membro con il nome di tale classe.  
  
     Se il codice all'interno di una classe annidata crea un riferimento non qualificato di un elemento di programmazione, Visual Basic cerca prima della classe annidata, quindi nella classe che contiene e così via per l'elemento più esterno.  
  
## <a name="classes-and-modules"></a>Classi e moduli  
 Questi elementi presentano molte analogie, ma esistono alcune importanti differenze.  
  
-   **Terminologia.** Due tipi di moduli di riconoscere le versioni precedenti di Visual Basic: *moduli di classe* (file CLS) e *moduli standard* (file BAS). La versione corrente chiama questi *classi* e *moduli*, rispettivamente.  
  
-   **Membri condivisi.** È possibile controllare se è un oggetto condiviso di un membro di una classe o membro di istanza.  
  
-   **Orientamento agli oggetti.** Classi sono orientata agli oggetti, ma non sono moduli. È possibile creare uno o più istanze di una classe. Per ulteriori informazioni, vedere [oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un `Class` istruzione per definire una classe e molti membri.  
  
 [!code-vb[VbVbalrStatements#62](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/class-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Strutture e classi](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Durata degli oggetti: come creare e distruggere oggetti](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Procedura: Usare una classe generica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
