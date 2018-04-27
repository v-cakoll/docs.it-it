---
title: Istruzione Module
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 51f8fd063449c072a69cdffd9f6ce2a96cc3f68c
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="module-statement"></a>Istruzione Module
Dichiara il nome di un modulo e introduce la definizione di variabili, proprietà, eventi ed procedure che comprende il modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a>Parti  
 `attributelist`  
 Facoltativo. Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Facoltativo. Può essere uno dei seguenti:  
  
-   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 Vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `name`  
 Obbligatorio. Nome di questo modulo. Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `statements`  
 Facoltativo. Istruzioni che definiscono le variabili, proprietà, eventi, procedure e tipi annidati di questo modulo.  
  
 `End Module`  
 Termina il `Module` definizione.  
  
## <a name="remarks"></a>Note  
 Oggetto `Module` istruzione definisce un tipo di riferimento disponibile in tutto lo spazio dei nomi. A *modulo* (detto anche un *modulo standard*) è simile a una classe, ma con alcune differenze importanti. Ogni modulo ha esattamente un'istanza e non devono essere creati o assegnati a una variabile. I moduli non supportano l'ereditarietà o implementare interfacce. Si noti che un modulo non è un *tipo* nel senso che è una classe o struttura, è possibile dichiarare un elemento di programmazione per il tipo di dati di un modulo.  
  
 È possibile utilizzare `Module` solo a livello di spazio dei nomi. Ciò significa che il *contesto della dichiarazione* per un modulo deve essere un file di origine o di spazio dei nomi e non può essere una classe, struttura, modulo, interfaccia, routine o blocco. È possibile nidificare un modulo all'interno di un altro modulo o all'interno di qualsiasi tipo. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Un modulo con la stessa durata del programma. Poiché i relativi membri sono tutti `Shared`, hanno anche una durata uguale a quella del programma.  
  
 Per impostazione predefinita i moduli [Friend](../../../visual-basic/language-reference/modifiers/friend.md) accesso. È possibile regolare i livelli di accesso con i modificatori di accesso. Per ulteriori informazioni, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Tutti i membri di un modulo sono implicitamente `Shared`.  
  
## <a name="classes-and-modules"></a>Classi e moduli  
 Questi elementi presentano molte analogie, ma esistono alcune importanti differenze.  
  
-   **Terminologia.** Due tipi di moduli di riconoscere le versioni precedenti di Visual Basic: *moduli di classe* (file CLS) e *moduli standard* (file BAS). La versione corrente chiama questi *classi* e *moduli*, rispettivamente.  
  
-   **Membri condivisi.** È possibile controllare se è un oggetto condiviso di un membro di una classe o membro di istanza.  
  
-   **Orientamento agli oggetti.** Classi sono orientata agli oggetti, ma non sono moduli. Pertanto sola classi possono essere implementate come oggetti. Per ulteriori informazioni, vedere [oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="rules"></a>Regole  
  
-   **Modificatori.** Tutti i membri del modulo sono implicitamente [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Non è possibile utilizzare il `Shared` (parola chiave) quando si dichiara un membro se non è possibile modificare lo stato condiviso tra i membri.  
  
-   **Ereditarietà.** Un modulo non può ereditare da qualsiasi tipo diverso da <xref:System.Object>, ereditare da tutti i moduli. In particolare, un modulo non può ereditare da un altro.  
  
     Non è possibile utilizzare il [istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md) nella definizione di un modulo, anche per specificare <xref:System.Object>.  
  
-   **Proprietà predefinita.** È possibile definire le proprietà predefinite in un modulo. Per ulteriori informazioni, vedere [predefinito](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Comportamento  
  
-   **Livello di accesso.** All'interno di un modulo, è possibile dichiarare ogni membro con il proprio livello di accesso. Per impostazione predefinita ai membri del modulo [pubblica](../../../visual-basic/language-reference/modifiers/public.md) accedere, ad eccezione delle variabili e costanti, il valore predefinito per [privata](../../../visual-basic/language-reference/modifiers/private.md) accesso. Quando un modulo ha più limitato l'accesso a uno dei relativi membri, il livello di accesso del modulo specificato ha la precedenza.  
  
-   **Ambito.** Un modulo è incluso nell'ambito dello spazio dei nomi.  
  
     L'ambito di ogni membro di modulo è l'intero modulo. Si noti che è possibile eseguire tutti i membri *promozione del tipo*, che comporta l'ambito da innalzare di livello allo spazio dei nomi che contiene il modulo. Per ulteriori informazioni, vedere [promozione tipo](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
-   **Qualifica.** È possibile più moduli in un progetto che è possibile dichiarare membri con lo stesso nome in due o più moduli. Tuttavia, è necessario qualificare ogni riferimento a tale membro con il nome del modulo appropriato se il riferimento si trova all'esterno del modulo. Per ulteriori informazioni, vedere [riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Istruzione Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Promozione tipo](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
