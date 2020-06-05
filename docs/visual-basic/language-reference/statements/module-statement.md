---
title: Istruzione Module
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
ms.openlocfilehash: 24a27ba41f5ac889f2f2725a2852368a4292a6fb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404455"
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
Facoltativa. Vedere [elenco attributi](attribute-list.md).

`accessmodifier`  
Facoltativa. Può essere uno dei seguenti:

- [Pubblica](../modifiers/public.md)

- [Amico](../modifiers/friend.md)

Vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

`name`  
Obbligatorio. Nome del modulo. Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

`statements`  
Facoltativa. Istruzioni che definiscono le variabili, le proprietà, gli eventi, le procedure e i tipi annidati di questo modulo.

`End Module`  
Termina la `Module` definizione.

## <a name="remarks"></a>Commenti

Un' `Module` istruzione definisce un tipo di riferimento disponibile in tutto il relativo spazio dei nomi. Un *modulo* (talvolta denominato *modulo standard*) è simile a una classe ma con alcune importanti differenze. Ogni modulo dispone esattamente di un'istanza e non è necessario crearlo o assegnarlo a una variabile. I moduli non supportano l'ereditarietà né implementano le interfacce. Si noti che un modulo non è un *tipo* nel senso che una classe o una struttura è: non è possibile dichiarare un elemento di programmazione per avere il tipo di dati di un modulo.

È possibile usare `Module` solo a livello di spazio dei nomi. Ciò significa che il *contesto di dichiarazione* per un modulo deve essere un file di origine o uno spazio dei nomi e non può essere una classe, una struttura, un modulo, un'interfaccia, una routine o un blocco. Non è possibile annidare un modulo all'interno di un altro modulo o all'interno di qualsiasi tipo. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).

Un modulo ha la stessa durata del programma. Poiché i relativi membri sono tutti `Shared` , hanno anche durate uguali a quelle del programma.

Per impostazione predefinita, i moduli sono con accesso [Friend](../modifiers/friend.md) . È possibile modificare i livelli di accesso con i modificatori di accesso. Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

Tutti i membri di un modulo sono implicitamente `Shared` .

## <a name="classes-and-modules"></a>Classi e moduli

Questi elementi presentano molte analogie, ma esistono anche alcune differenze importanti.

- **Terminologia.** Le versioni precedenti di Visual Basic riconoscono due tipi di moduli: *moduli di classe* (file con estensione CLS) e *moduli standard* (file con estensione BAS). La versione corrente chiama queste *classi* e *moduli*, rispettivamente.

- **Membri condivisi.** È possibile controllare se un membro di una classe è un membro condiviso o di istanza.

- **Orientamento dell'oggetto.** Le classi sono orientate agli oggetti, ma i moduli non lo sono. È quindi possibile creare un'istanza di solo classi come oggetti. Per altre informazioni, vedere [oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md).

## <a name="rules"></a>Regole

- **Modificatori.** Tutti i membri del modulo sono [condivisi](../modifiers/shared.md)in modo implicito. Non è possibile usare la `Shared` parola chiave quando si dichiara un membro e non è possibile modificare lo stato condiviso di un membro.

- **Ereditarietà.** Un modulo non può ereditare da un tipo diverso <xref:System.Object> da, da cui tutti i moduli ereditano. In particolare, un modulo non può ereditare da un altro modulo.

  Non è possibile usare l' [istruzione Inherits](inherits-statement.md) in una definizione di modulo, anche per specificare <xref:System.Object> .

- **Proprietà predefinita.** Non è possibile definire proprietà predefinite in un modulo. Per ulteriori informazioni, vedere [default](../modifiers/default.md).

## <a name="behavior"></a>Comportamento

- **Livello di accesso.** All'interno di un modulo, è possibile dichiarare ogni membro con il proprio livello di accesso. Per impostazione predefinita, i membri del modulo hanno accesso [pubblico](../modifiers/public.md) , ad eccezione delle variabili e delle costanti, per impostazione predefinita l'accesso [privato](../modifiers/private.md) . Quando un modulo dispone di un accesso più limitato di uno dei relativi membri, il livello di accesso del modulo specificato ha la precedenza.

- **Ambito.** Un modulo è nell'ambito dello spazio dei nomi.

  L'ambito di ogni membro del modulo è l'intero modulo. Si noti che tutti i membri subiscono l' *innalzamento*di livello del tipo, che ne determina l'innalzamento di livello allo spazio dei nomi contenente il modulo. Per ulteriori informazioni, vedere [promozione del tipo](../../programming-guide/language-features/declared-elements/type-promotion.md).

- **Qualificazione.** È possibile avere più moduli in un progetto ed è possibile dichiarare membri con lo stesso nome in due o più moduli. Tuttavia, è necessario qualificare qualsiasi riferimento a tale membro con il nome del modulo appropriato se il riferimento è esterno al modulo. Per altre informazioni, vedere [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

## <a name="example"></a>Esempio

[!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]

## <a name="see-also"></a>Vedere anche

- [Istruzione Class](class-statement.md)
- [Istruzione Namespace](namespace-statement.md)
- [Istruzione Structure](structure-statement.md)
- [Istruzione Interface](interface-statement.md)
- [Property Statement](property-statement.md)
- [Promozione tipo](../../programming-guide/language-features/declared-elements/type-promotion.md)
