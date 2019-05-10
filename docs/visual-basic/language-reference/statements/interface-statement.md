---
title: Istruzione Interface (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
ms.openlocfilehash: 42d0f86dd6561806701d17846bae6d88252ce46a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625492"
---
# <a name="interface-statement-visual-basic"></a>Istruzione Interface (Visual Basic)
Dichiara il nome di un'interfaccia e introduce le definizioni dei membri che comprende l'interfaccia.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] _  
Interface name [ ( Of typelist ) ]  
    [ Inherits interfacenames ]  
    [ [ modifiers ] Property membername ]  
    [ [ modifiers ] Function membername ]  
    [ [ modifiers ] Sub membername ]  
    [ [ modifiers ] Event membername ]  
    [ [ modifiers ] Interface membername ]  
    [ [ modifiers ] Class membername ]  
    [ [ modifiers ] Structure membername ]  
End Interface  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`attributelist`|Facoltativo. Visualizzare [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Facoltativo. Può essere uno dei seguenti:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protetto](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-  [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br/>- [Private Protected](../../language-reference/modifiers/private-protected.md)<br /><br /> Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Facoltativo. Visualizzare [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`name`|Obbligatorio. Nome di questa interfaccia. Vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Facoltativo. Specifica che si tratta di un'interfaccia generica.|  
|`typelist`|Obbligatorio se si usa la [di](../../../visual-basic/language-reference/statements/of-clause.md) (parola chiave). Elenco di parametri di tipo per questa interfaccia. Facoltativamente, ogni parametro di tipo può essere dichiarato variante mediante `In` e `Out` modificatori generici. Visualizzare [elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Facoltativo. Indica che questa interfaccia eredita gli attributi e membri di un'altra interfaccia o interfacce. Visualizzare [istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`interfacenames`|Obbligatorio se si usa il `Inherits` istruzione. I nomi delle interfacce da cui deriva questa interfaccia.|  
|`modifiers`|Facoltativo. Modificatori appropriati per il membro di interfaccia da definire.|  
|`Property`|Facoltativo. Definisce una proprietà che è un membro dell'interfaccia.|  
|`Function`|Facoltativo. Definisce un `Function` procedure che è un membro dell'interfaccia.|  
|`Sub`|Facoltativo. Definisce un `Sub` procedure che è un membro dell'interfaccia.|  
|`Event`|Facoltativo. Definisce un evento che è un membro dell'interfaccia.|  
|`Interface`|Facoltativo. Definisce un'interfaccia che viene nidificata all'interno di questa interfaccia. La definizione dell'interfaccia annidato deve terminare con un `End Interface` istruzione.|  
|`Class`|Facoltativo. Definisce una classe che è un membro dell'interfaccia. La definizione di classe di membro deve terminare con un `End Class` istruzione.|  
|`Structure`|Facoltativo. Definisce una struttura che è un membro dell'interfaccia. Definizione della struttura del membro deve terminare con un `End Structure` istruzione.|  
|`membername`|Obbligatorio per ogni proprietà, procedure, eventi, interfaccia, classe o struttura definita come un membro dell'interfaccia. Nome del membro.|  
|`End Interface`|Termina il `Interface` definizione.|  
  
## <a name="remarks"></a>Note  
 Un' *interfaccia* definisce un set di membri, ad esempio possano implementare le proprietà e le procedure, le classi e strutture. L'interfaccia definisce solo le firme dei membri e non i meccanismi interni.  
  
 Una classe o struttura implementa l'interfaccia fornendo il codice per tutti i membri definiti dall'interfaccia. Infine, quando l'applicazione crea un'istanza da tale classe o struttura, un oggetto esiste e viene eseguita in memoria. Per altre informazioni, vedere [oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) e [interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 È possibile usare `Interface` solo a livello di spazio dei nomi o modulo. Ciò significa che il *contesto della dichiarazione* per un'interfaccia deve essere un file di origine, lo spazio dei nomi, classe, struttura, modulo o dell'interfaccia e non può essere una routine o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Predefinito per le interfacce [Friend](../../../visual-basic/language-reference/modifiers/friend.md) accesso. È possibile modificare i livelli di accesso con i modificatori di accesso. Per altre informazioni, vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regole  
  
- **Annidamento delle interfacce.** È possibile definire un'interfaccia all'interno di altra. L'interfaccia esterna viene denominata la *contenente l'interfaccia*, e l'interfaccia interna viene chiamata una *interfaccia annidata*.  
  
- **Dichiarazione di membro.** Quando si dichiara una proprietà o routine come membro di un'interfaccia, si sta definendo solo il *firma* di tale proprietà o routine. Ciò include il tipo di elemento (proprietà o routine), i relativi parametri e tipi di parametro e il relativo tipo restituito. Per questo motivo, la definizione del membro utilizza solo una riga di codice le istruzioni di chiusura, ad esempio `End Function` o `End Property` non sono validi in un'interfaccia.  
  
     Al contrario, quando si definisce un'enumerazione o struttura, o una classe annidata o un'interfaccia, è necessario includere i relativi membri dati.  
  
- **Modificatori dei membri.** Non è possibile utilizzare tutti i modificatori di accesso quando si definiscono i membri del modulo, né è possibile specificare [Shared](../../../visual-basic/language-reference/modifiers/shared.md) o qualsiasi altro modificatore procedure tranne [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md). È possibile dichiarare qualsiasi membro con [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md), ed è possibile usare [predefinito](../../../visual-basic/language-reference/modifiers/default.md) quando si definisce una proprietà, nonché [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) oppure [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
- **Ereditarietà.** Se l'interfaccia utilizza il [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md), è possibile specificare uno o più interfacce di base. È possibile ereditare da due interfacce, anche se ognuno definisce un membro con lo stesso nome. Se in questo caso, il codice di implementazione deve usare la qualificazione di nomi per specificare quale membro che sta implementando.  
  
     Un'interfaccia non può ereditare da un'altra interfaccia con un livello di accesso più restrittivo. Ad esempio, un `Public` interfaccia non può ereditare da un `Friend` interfaccia.  
  
     Un'interfaccia non può ereditare da un'interfaccia annidata al suo interno.  
  
- **Implementazione.** Quando una classe Usa il [implementa](../../../visual-basic/language-reference/statements/implements-clause.md) istruzione per implementare questa interfaccia, deve implementare tutti i membri definiti all'interno dell'interfaccia. Inoltre, ogni firma nel codice di implementazione deve corrispondere esattamente alla firma corrispondente definita in questa interfaccia. Tuttavia, il nome del membro nel codice di implementazione non hanno corrisponda al nome di membro, come definito nell'interfaccia.  
  
     Quando una classe implementa una routine, non è designata come `Shared`.  
  
- **Proprietà predefinita.** Un'interfaccia è possibile specificare al massimo una proprietà come relativo *predefiniti delle proprietà*, che è possibile fare riferimento senza usare il nome della proprietà. Si specifica una proprietà di questo tipo dichiarando la variabile con il [predefinito](../../../visual-basic/language-reference/modifiers/default.md) modificatore.  
  
     Si noti che ciò significa che un'interfaccia può definire una proprietà predefinita solo se nessuno eredita.  
  
## <a name="behavior"></a>Comportamento  
  
- **Livello di accesso.** Tutti i membri di interfaccia dispongono implicitamente [pubblica](../../../visual-basic/language-reference/modifiers/public.md) accesso. È possibile usare il modificatore di accesso quando si definisce un membro. Tuttavia, una classe che implementa l'interfaccia può dichiarare un livello di accesso per ogni membro implementato.  
  
     Se si assegna un'istanza della classe a una variabile, il livello di accesso dei membri può dipendere dal fatto che il tipo di dati della variabile è l'interfaccia sottostante o alla classe che implementa. Questa condizione è illustrata nell'esempio seguente.  
  
     [!code-vb[VbVbalrStatements#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#39)]  
  
     Se si accede a membri della classe tramite `varAsInterface`, hanno tutti accesso pubblico. Tuttavia, se si accede ai membri attraverso `varAsClass`, il `Sub` procedure `doSomething` con accesso privato.  
  
- **Ambito.** Un'interfaccia è l'ambito relativo dello spazio dei nomi, classe, struttura o modulo.  
  
     L'ambito di ogni membro di interfaccia è l'intera interfaccia.  
  
- **Ciclo di vita.** Un'interfaccia non include una durata, né eseguire i relativi membri. Quando una classe implementa un'interfaccia e un oggetto viene creato come un'istanza di che (classe), l'oggetto ha una durata all'interno dell'applicazione in cui è in esecuzione. Per altre informazioni, vedere "Durata" nella [istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Interface` istruzione per definire un'interfaccia denominata `thisInterface`, che deve essere implementata con un `Property` istruzione e una `Function` istruzione.  
  
 [!code-vb[VbVbalrStatements#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#40)]  
  
 Si noti che il `Property` e `Function` istruzioni non introducono che terminano con i blocchi `End Property` e `End Function` all'interno dell'interfaccia. L'interfaccia definisce solo le firme dei relativi membri. La versione completa `Property` e `Function` blocchi vengono visualizzati in una classe che implementa `thisInterface`.  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md)
- [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Varianza nelle interfacce generiche](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
