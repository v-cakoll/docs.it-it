---
title: Istruzione Interface
ms.date: 05/12/2018
f1_keywords:
- vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
ms.openlocfilehash: 02d258084aaaa53dcc559cfaa0dec27556351037
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404486"
---
# <a name="interface-statement-visual-basic"></a>Istruzione Interface (Visual Basic)
Dichiara il nome di un'interfaccia e introduce le definizioni dei membri inclusi nell'interfaccia.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
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
|`attributelist`|Facoltativa. Vedere [elenco attributi](attribute-list.md).|  
|`accessmodifier`|Facoltativa. Può essere uno dei seguenti:<br /><br /> -   [Pubblico](../modifiers/public.md)<br />-   [Protetto](../modifiers/protected.md)<br />-   [Amico](../modifiers/friend.md)<br />-   [Privata](../modifiers/private.md)<br />-  [Amico protetto](../modifiers/protected-friend.md)<br/>- [Privato protetto](../modifiers/private-protected.md)<br /><br /> Vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Facoltativa. Vedere [Shadows](../modifiers/shadows.md).|  
|`name`|Obbligatorio. Nome di questa interfaccia. Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Facoltativa. Specifica che si tratta di un'interfaccia generica.|  
|`typelist`|Obbligatorio se si usa la parola chiave [of](of-clause.md) . Elenco di parametri di tipo per questa interfaccia. Facoltativamente, ogni parametro di tipo può essere dichiarato Variant usando `In` i `Out` modificatori generici e. Vedere [elenco dei tipi](type-list.md).|  
|`Inherits`|Facoltativa. Indica che questa interfaccia eredita gli attributi e i membri di un'altra interfaccia o di altre interfacce. Vedere [istruzione Inherits](inherits-statement.md).|  
|`interfacenames`|Obbligatorio se si usa l' `Inherits` istruzione. Nomi delle interfacce da cui deriva questa interfaccia.|  
|`modifiers`|Facoltativa. Modificatori appropriati per il membro di interfaccia definito.|  
|`Property`|Facoltativa. Definisce una proprietà che è un membro dell'interfaccia.|  
|`Function`|Facoltativa. Definisce una `Function` routine che è un membro dell'interfaccia.|  
|`Sub`|Facoltativa. Definisce una `Sub` routine che è un membro dell'interfaccia.|  
|`Event`|Facoltativa. Definisce un evento che è un membro dell'interfaccia.|  
|`Interface`|Facoltativa. Definisce un'interfaccia annidata all'interno di questa interfaccia. La definizione dell'interfaccia annidata deve terminare con un' `End Interface` istruzione.|  
|`Class`|Facoltativa. Definisce una classe che è un membro dell'interfaccia. La definizione della classe membro deve terminare con un' `End Class` istruzione.|  
|`Structure`|Facoltativa. Definisce una struttura che è un membro dell'interfaccia. La definizione della struttura del membro deve terminare con un' `End Structure` istruzione.|  
|`membername`|Obbligatorio per ogni proprietà, routine, evento, interfaccia, classe o struttura definita come membro dell'interfaccia. Nome del membro.|  
|`End Interface`|Termina la `Interface` definizione.|  
  
## <a name="remarks"></a>Commenti  
 Un' *interfaccia* definisce un set di membri, ad esempio proprietà e procedure, che possono essere implementate da classi e strutture. L'interfaccia definisce solo le firme dei membri e non i rispettivi meccanismi interni.  
  
 Una classe o una struttura implementa l'interfaccia fornendo il codice per ogni membro definito dall'interfaccia. Infine, quando l'applicazione crea un'istanza da tale classe o struttura, un oggetto esiste e viene eseguito in memoria. Per ulteriori informazioni, vedere [oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md) e [interfacce](../../programming-guide/language-features/interfaces/index.md).  
  
 È possibile usare `Interface` solo a livello di spazio dei nomi o di modulo. Ciò significa che il *contesto di dichiarazione* per un'interfaccia deve essere un file di origine, uno spazio dei nomi, una classe, una struttura, un modulo o un'interfaccia e non può essere una routine o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).  
  
 Per impostazione predefinita, le interfacce sono accessi [Friend](../modifiers/friend.md) . È possibile modificare i livelli di accesso con i modificatori di accesso. Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regole  
  
- **Annidamento di interfacce.** È possibile definire un'interfaccia in un'altra. L'interfaccia esterna viene chiamata *interfaccia contenitore*e l'interfaccia interna è chiamata *interfaccia nidificata*.  
  
- **Dichiarazione del membro.** Quando si dichiara una proprietà o una routine come membro di un'interfaccia, si definisce solo la *firma* della proprietà o della routine. Sono inclusi il tipo di elemento (proprietà o routine), i parametri e i tipi di parametro e il tipo restituito. Per questo motivo, nella definizione del membro viene utilizzata solo una riga di codice e le istruzioni che terminano, ad esempio `End Function` o, `End Property` non sono valide in un'interfaccia.  
  
     Al contrario, quando si definisce un'enumerazione o una struttura o una classe o un'interfaccia annidata, è necessario includere i relativi membri dati.  
  
- **Modificatori di membro.** Non è possibile usare alcun modificatore di accesso quando si definiscono i membri del modulo, né è possibile specificare un modificatore di routine [condiviso](../modifiers/shared.md) o qualsiasi, ad eccezione degli [Overload](../modifiers/overloads.md). È possibile dichiarare qualsiasi membro con [Shadows](../modifiers/shadows.md)ed è possibile utilizzare [default](../modifiers/default.md) quando si definisce una proprietà, nonché [ReadOnly](../modifiers/readonly.md) o [WriteOnly](../modifiers/writeonly.md).  
  
- **Ereditarietà.** Se l'interfaccia utilizza l' [istruzione Inherits](inherits-statement.md), è possibile specificare una o più interfacce di base. È possibile ereditare da due interfacce anche se ognuna definisce un membro con lo stesso nome. In tal caso, il codice di implementazione deve usare la qualificazione del nome per specificare il membro che sta implementando.  
  
     Un'interfaccia non può ereditare da un'altra interfaccia con un livello di accesso più restrittivo. Un'interfaccia, ad esempio, `Public` non può ereditare da un' `Friend` interfaccia.  
  
     Un'interfaccia non può ereditare da un'interfaccia annidata al suo interno.  
  
- **Implementazione.** Quando una classe utilizza l'istruzione [Implements](implements-clause.md) per implementare questa interfaccia, deve implementare tutti i membri definiti all'interno dell'interfaccia. Inoltre, ogni firma nel codice di implementazione deve corrispondere esattamente alla firma corrispondente definita in questa interfaccia. Tuttavia, il nome del membro nel codice di implementazione non deve corrispondere al nome del membro come definito nell'interfaccia.  
  
     Quando una classe implementa una routine, non può designare la procedura come `Shared` .  
  
- **Proprietà predefinita.** Un'interfaccia può specificare al massimo una proprietà come *proprietà predefinita*, a cui è possibile fare riferimento senza utilizzare il nome della proprietà. Per specificare tale proprietà, è necessario dichiararla con il modificatore [predefinito](../modifiers/default.md) .  
  
     Si noti che questo significa che un'interfaccia può definire una proprietà predefinita solo se eredita nessuno.  
  
## <a name="behavior"></a>Comportamento  
  
- **Livello di accesso.** Tutti i membri dell'interfaccia hanno in modo implicito l'accesso [pubblico](../modifiers/public.md) . Non è possibile usare alcun modificatore di accesso per la definizione di un membro. Tuttavia, una classe che implementa l'interfaccia può dichiarare un livello di accesso per ogni membro implementato.  
  
     Se si assegna un'istanza di classe a una variabile, il livello di accesso dei relativi membri può dipendere dal fatto che il tipo di dati della variabile sia l'interfaccia sottostante o la classe di implementazione. Questa condizione è illustrata nell'esempio seguente.  
  
     [!code-vb[VbVbalrStatements#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#39)]  
  
     Se si accede ai membri della classe tramite `varAsInterface` , tutti hanno accesso pubblico. Tuttavia, se si accede ai membri tramite `varAsClass` , la `Sub` procedura `doSomething` ha accesso privato.  
  
- **Ambito.** Un'interfaccia è nell'ambito di tutti i relativi spazi dei nomi, classe, struttura o modulo.  
  
     L'ambito di ogni membro di interfaccia è l'intera interfaccia.  
  
- **Vita.** Un'interfaccia non ha una durata, né i relativi membri. Quando una classe implementa un'interfaccia e un oggetto viene creato come un'istanza di tale classe, l'oggetto ha una durata all'interno dell'applicazione in cui è in esecuzione. Per ulteriori informazioni, vedere "Lifetime" nell' [istruzione Class](class-statement.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l' `Interface` istruzione per definire un'interfaccia denominata `thisInterface` , che deve essere implementata con un' `Property` istruzione e un' `Function` istruzione.  
  
 [!code-vb[VbVbalrStatements#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#40)]  
  
 Si noti che `Property` le `Function` istruzioni e non introducono blocchi che terminano con `End Property` e `End Function` all'interno dell'interfaccia. L'interfaccia definisce solo le firme dei relativi membri. I `Property` blocchi completi e `Function` vengono visualizzati in una classe che implementa `thisInterface` .  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce](../../programming-guide/language-features/interfaces/index.md)
- [Istruzione Class](class-statement.md)
- [Istruzione Module](module-statement.md)
- [Istruzione Structure](structure-statement.md)
- [Property Statement](property-statement.md)
- [Istruzione Function](function-statement.md)
- [Istruzione Sub](sub-statement.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Varianza nelle interfacce generiche](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [In](../modifiers/in-generic-modifier.md)
- [Out](../modifiers/out-generic-modifier.md)
