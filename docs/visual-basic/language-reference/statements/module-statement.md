---
title: Istruzione Module (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
ms.openlocfilehash: 08268fd473a3a916f41f2f46090e3245acda07dd
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513015"
---
# <a name="module-statement"></a>Istruzione Module
Dichiara il nome di un modulo e introduce la definizione di variabili, proprietà, eventi e procedure inclusi nel modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a>Parti  
 `attributelist`  
 facoltativo. Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 facoltativo. Può essere uno dei seguenti:  
  
- [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `name`  
 Richiesto. Nome del modulo. Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `statements`  
 facoltativo. Istruzioni che definiscono le variabili, le proprietà, gli eventi, le procedure e i tipi annidati di questo modulo.  
  
 `End Module`  
 Termina la `Module` definizione.  
  
## <a name="remarks"></a>Note  
 Un' `Module` istruzione definisce un tipo di riferimento disponibile in tutto il relativo spazio dei nomi. Un *modulo* (talvolta denominato *modulo standard*) è simile a una classe ma con alcune importanti differenze. Ogni modulo dispone esattamente di un'istanza e non è necessario crearlo o assegnarlo a una variabile. I moduli non supportano l'ereditarietà né implementano le interfacce. Si noti che un modulo non è un *tipo* nel senso che una classe o una struttura è: non è possibile dichiarare un elemento di programmazione per avere il tipo di dati di un modulo.  
  
 È possibile usare `Module` solo a livello di spazio dei nomi. Ciò significa che il *contesto di dichiarazione* per un modulo deve essere un file di origine o uno spazio dei nomi e non può essere una classe, una struttura, un modulo, un'interfaccia, una routine o un blocco. Non è possibile annidare un modulo all'interno di un altro modulo o all'interno di qualsiasi tipo. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Un modulo ha la stessa durata del programma. Poiché i relativi membri sono `Shared`tutti, hanno anche durate uguali a quelle del programma.  
  
 Per impostazione predefinita, i moduli sono con accesso [Friend](../../../visual-basic/language-reference/modifiers/friend.md) . È possibile modificare i livelli di accesso con i modificatori di accesso. Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Tutti i membri di un modulo sono implicitamente `Shared`.  
  
## <a name="classes-and-modules"></a>Classi e moduli  
 Questi elementi presentano molte analogie, ma esistono anche alcune differenze importanti.  
  
- **Terminologia.** Le versioni precedenti di Visual Basic riconoscono due tipi di moduli: *moduli di classe* (file con estensione CLS) e *moduli standard* (file con estensione BAS). La versione corrente chiama queste *classi* e *moduli*, rispettivamente.  
  
- **Membri condivisi.** È possibile controllare se un membro di una classe è un membro condiviso o di istanza.  
  
- **Orientamento dell'oggetto.** Le classi sono orientate agli oggetti, ma i moduli non lo sono. È quindi possibile creare un'istanza di solo classi come oggetti. Per altre informazioni, vedere [oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="rules"></a>Regole  
  
- **Modificatori.** Tutti i membri del modulo sono [condivisi](../../../visual-basic/language-reference/modifiers/shared.md)in modo implicito. Non è possibile usare `Shared` la parola chiave quando si dichiara un membro e non è possibile modificare lo stato condiviso di un membro.  
  
- **Ereditarietà.** Un modulo non può ereditare da un tipo <xref:System.Object>diverso da, da cui tutti i moduli ereditano. In particolare, un modulo non può ereditare da un altro modulo.  
  
     Non è possibile usare l' [istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md) in una definizione di modulo, anche <xref:System.Object>per specificare.  
  
- **Proprietà predefinita.** Non è possibile definire proprietà predefinite in un modulo. Per ulteriori informazioni, vedere [default](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Comportamento  
  
- **Livello di accesso.** All'interno di un modulo, è possibile dichiarare ogni membro con il proprio livello di accesso. Per impostazione predefinita, i membri del modulo hanno accesso [pubblico](../../../visual-basic/language-reference/modifiers/public.md) , ad eccezione delle variabili e delle costanti, per impostazione predefinita l'accesso [privato](../../../visual-basic/language-reference/modifiers/private.md) . Quando un modulo dispone di un accesso più limitato di uno dei relativi membri, il livello di accesso del modulo specificato ha la precedenza.  
  
- **Ambito.** Un modulo è nell'ambito dello spazio dei nomi.  
  
     L'ambito di ogni membro del modulo è l'intero modulo. Si noti che tutti i membri subiscono l'innalzamento di livello del *tipo*, che ne determina l'innalzamento di livello allo spazio dei nomi contenente il modulo. Per ulteriori informazioni, vedere [promozione del tipo](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
- **Qualificazione.** È possibile avere più moduli in un progetto ed è possibile dichiarare membri con lo stesso nome in due o più moduli. Tuttavia, è necessario qualificare qualsiasi riferimento a tale membro con il nome del modulo appropriato se il riferimento è esterno al modulo. Per altre informazioni, vedere [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Istruzione Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Promozione tipo](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
