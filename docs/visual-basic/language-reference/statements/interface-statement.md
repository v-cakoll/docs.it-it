---
title: Istruzione Interface (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9418dc86ac6947ae951cb8fb757aed6e092a6668
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
|`attributelist`|Parametro facoltativo. Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Parametro facoltativo. Può essere uno dei seguenti:<br /><br /> -   [Pubblica](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protetto](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privato](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Parametro facoltativo. Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`name`|Obbligatorio. Nome di questa interfaccia. Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Parametro facoltativo. Specifica che si tratta di un'interfaccia generica.|  
|`typelist`|Obbligatorio se si usa il [di](../../../visual-basic/language-reference/statements/of-clause.md) (parola chiave). Elenco di parametri di tipo per questa interfaccia. Facoltativamente, ogni parametro di tipo può essere dichiarato variante mediante `In` e `Out` modificatori generici. Vedere [digitare elenco](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Parametro facoltativo. Indica che questa interfaccia eredita gli attributi e i membri di un altro o più interfacce. Vedere [istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`interfacenames`|Obbligatorio se si usa il `Inherits` istruzione. I nomi delle interfacce da cui deriva questa interfaccia.|  
|`modifiers`|Parametro facoltativo. Modificatori appropriati per il membro di interfaccia da definire.|  
|`Property`|Parametro facoltativo. Definisce una proprietà che è un membro dell'interfaccia.|  
|`Function`|Parametro facoltativo. Definisce un `Function` procedure che è un membro dell'interfaccia.|  
|`Sub`|Parametro facoltativo. Definisce un `Sub` procedure che è un membro dell'interfaccia.|  
|`Event`|Parametro facoltativo. Definisce un evento che è un membro dell'interfaccia.|  
|`Interface`|Parametro facoltativo. Definisce un'interfaccia che viene nidificata all'interno di questa interfaccia. La definizione di interfaccia annidata deve terminare con un `End Interface` istruzione.|  
|`Class`|Parametro facoltativo. Definisce una classe che è un membro dell'interfaccia. La definizione di classe di membro deve terminare con un `End Class` istruzione.|  
|`Structure`|Parametro facoltativo. Definisce una struttura che è un membro dell'interfaccia. La definizione della struttura membro deve terminare con un `End Structure` istruzione.|  
|`membername`|Obbligatorio per ogni proprietà, procedure, eventi, interfaccia, classe o struttura definita come un membro dell'interfaccia. Nome del membro.|  
|`End Interface`|Termina il `Interface` definizione.|  
  
## <a name="remarks"></a>Note  
 Un *interfaccia* definisce un set di membri, ad esempio proprietà e routine, che le classi e le strutture possono implementare. L'interfaccia definisce solo le firme dei membri e non i relativi processi interni.  
  
 Una classe o struttura implementa l'interfaccia fornendo il codice per ogni membro definito dall'interfaccia. Infine, quando l'applicazione crea un'istanza da tale classe o struttura, un oggetto esiste e viene eseguito in memoria. Per ulteriori informazioni, vedere [oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) e [interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 È possibile utilizzare `Interface` solo a livello di spazio dei nomi o modulo. Ciò significa che il *contesto della dichiarazione* per un'interfaccia deve essere un file di origine, lo spazio dei nomi, classe, struttura, modulo o interfaccia e non può essere una stored procedure o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Predefinito per le interfacce [Friend](../../../visual-basic/language-reference/modifiers/friend.md) accesso. È possibile regolare i livelli di accesso con i modificatori di accesso. Per ulteriori informazioni, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regole  
  
-   **Nidificazione delle interfacce.** È possibile definire un'interfaccia all'interno di altra. L'interfaccia esterna viene chiamato il *contenente interfaccia*, e l'interfaccia interna viene definita una *interfaccia annidata*.  
  
-   **Dichiarazione di membro.** Quando si dichiara una proprietà o routine come membro di un'interfaccia, si sta definendo solo il *firma* di quella proprietà o routine. Ciò include il tipo di elemento (proprietà o routine), i relativi parametri e tipi di parametro e il relativo tipo restituito. Per questo motivo, la definizione del membro utilizza solo una riga di codice e le istruzioni di chiusura, ad esempio `End Function` o `End Property` non sono validi in un'interfaccia.  
  
     Al contrario, quando si definisce un'enumerazione o struttura, o una classe annidata o un'interfaccia, è necessario includere i membri dati.  
  
-   **Modificatori di membro.** Non è possibile utilizzare i modificatori di accesso durante la definizione di membri del modulo, né specificare [Shared](../../../visual-basic/language-reference/modifiers/shared.md) o qualsiasi altro modificatore di routine, ad eccezione [overload](../../../visual-basic/language-reference/modifiers/overloads.md). È possibile dichiarare membri con [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md), ed è possibile utilizzare [predefinito](../../../visual-basic/language-reference/modifiers/default.md) quando si definisce una proprietà, così come [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) o [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   **Ereditarietà.** Se l'interfaccia Usa le [istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md), è possibile specificare uno o più interfacce di base. È possibile ereditare da due interfacce, anche se ciascuna di esse definisce un membro con lo stesso nome. Se si esegue questa operazione, il codice di implementazione deve utilizzare la qualificazione di nomi per specificare quale membro che sta implementando.  
  
     Un'interfaccia non può ereditare da un'altra interfaccia con un livello di accesso più restrittivo. Ad esempio, un `Public` interfaccia non può ereditare da un `Friend` interfaccia.  
  
     Un'interfaccia non può ereditare da un'interfaccia annidata al suo interno.  
  
-   **Implementazione.** Quando una classe utilizza il [implementa](../../../visual-basic/language-reference/statements/implements-clause.md) istruzione per implementare questa interfaccia deve implementare ogni membro definito all'interno dell'interfaccia. Inoltre, ogni firma nel codice di implementazione deve corrispondere esattamente la firma corrispondente definita in questa interfaccia. Tuttavia, non è necessario che il nome del membro nel codice di implementazione corrisponde al nome di membro, come definito nell'interfaccia.  
  
     Quando una classe implementa una routine, non è designata come `Shared`.  
  
-   **Proprietà predefinita.** Un'interfaccia può specificare al massimo una proprietà come relativo *proprietà predefinita*, che è possibile fare riferimento senza utilizzare il nome della proprietà. Questa proprietà è specificata mediante la dichiarazione con il [predefinito](../../../visual-basic/language-reference/modifiers/default.md) modificatore.  
  
     Notare che ciò significa che un'interfaccia può definire una proprietà predefinita solo se non eredita.  
  
## <a name="behavior"></a>Comportamento  
  
-   **Livello di accesso.** Tutti i membri di interfaccia sono implicitamente [pubblica](../../../visual-basic/language-reference/modifiers/public.md) accesso. È possibile usare qualsiasi altro modificatore di accesso quando si definisce un membro. Tuttavia, una classe che implementa l'interfaccia può dichiarare un livello di accesso per ogni membro implementato.  
  
     Se si assegna un'istanza della classe a una variabile, il livello di accesso dei relativi membri può dipendere se il tipo di dati della variabile è l'interfaccia sottostante o la classe di implementazione. Questa condizione è illustrata nell'esempio seguente.  
  
     [!code-vb[VbVbalrStatements#39](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_1.vb)]  
  
     Se si accede a membri della classe attraverso `varAsInterface`, hanno accesso pubblico. Tuttavia, se si accede ai membri tramite `varAsClass`, `Sub` procedura `doSomething` con accesso privato.  
  
-   **Ambito.** Un'interfaccia è nell'ambito in tutto il relativo spazio dei nomi, classe, struttura o modulo.  
  
     L'ambito di ogni membro di interfaccia è l'intera interfaccia.  
  
-   **Durata.** Un'interfaccia non include una durata, né eseguire i relativi membri. Quando una classe che implementa un'interfaccia e un oggetto viene creato come un'istanza di classe, l'oggetto ha una durata all'interno dell'applicazione in cui è in esecuzione. Per ulteriori informazioni, vedere "Durata" in [istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Interface` istruzione per definire un'interfaccia denominata `thisInterface`, che deve essere implementata con un `Property` istruzione e una `Function` istruzione.  
  
 [!code-vb[VbVbalrStatements#40](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_2.vb)]  
  
 Si noti che il `Property` e `Function` istruzioni non introducono blocchi che terminano con `End Property` e `End Function` all'interno dell'interfaccia. L'interfaccia definisce solo le firme dei relativi membri. La versione completa `Property` e `Function` blocchi vengono visualizzati in una classe che implementa `thisInterface`.  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Varianza nelle interfacce generiche](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
