---
title: Istruzione Structure (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Structure
- Structure
helpviewer_keywords:
- user-defined types [Visual Basic], Structure statement
- compound data types [Visual Basic]
- Structure keyword [Visual Basic]
- Structure statement [Visual Basic]
- UDT (user-defined types)
- types [Visual Basic], user-defined
ms.assetid: 9bd1deea-2a89-4cdc-812c-6dcbb947c391
ms.openlocfilehash: 9377d889f56049720ab10439582300913f5cbb37
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416441"
---
# <a name="structure-statement"></a>Istruzione Structure
Dichiara il nome di una struttura e introduce la definizione delle variabili, proprietà, eventi e procedure che comprende la struttura.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Partial ] _  
Structure name [ ( Of typelist ) ]  
    [ Implements interfacenames ]  
    [ datamemberdeclarations ]  
    [ methodmemberdeclarations ]  
End Structure  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`attributelist`|Facoltativo. Visualizzare [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Facoltativo. Può essere uno dei seguenti:<br /><br /> -   [Pubblico](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protetto](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privato](../../../visual-basic/language-reference/modifiers/private.md)<br />- [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br/>- [Private Protected](../../language-reference/modifiers/private-protected.md) <br /><br /> Visualizzare [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Facoltativo. Visualizzare [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`Partial`|Facoltativo. Indica una definizione parziale della struttura. Visualizzare [parziale](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Obbligatorio. Nome della struttura. Visualizzare [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Facoltativo. Specifica che si tratta di una struttura generica.|  
|`typelist`|Obbligatorio se si usa la [di](../../../visual-basic/language-reference/statements/of-clause.md) (parola chiave). Elenco di parametri di tipo per questa struttura. Visualizzare [elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Implements`|Facoltativo. Indica che questa struttura implementa i membri di una o più interfacce. Visualizzare [implementa istruzione](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Obbligatorio se si usa il `Implements` istruzione. I nomi delle interfacce implementate questa struttura.|  
|`datamemberdeclarations`|Obbligatorio. Zero o più `Const`, `Dim`, `Enum`, o `Event` istruzioni di dichiarazione *membri dati* della struttura.|  
|`methodmemberdeclarations`|Facoltativo. Zero o più dichiarazioni di `Function`, `Operator`, `Property`, o `Sub` procedure che fungono da *metodo membri* della struttura.|  
|`End Structure`|Obbligatorio. Termina il `Structure` definizione.|  
  
## <a name="remarks"></a>Note  
 Il `Structure` istruzione definisce un tipo valore composito che è possibile personalizzare. Oggetto *struttura* è una generalizzazione del tipo definito dall'utente (UDT) di versioni precedenti di Visual Basic. Per altre informazioni, vedere [strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md).  
  
 Le strutture supportano molte delle stesse funzionalità di classi. Ad esempio, le strutture possono disporre di proprietà e routine, possono implementare interfacce e possono avere costruttori con parametri. Tuttavia, esistono differenze significative tra classi e strutture in aree quali ereditarietà, le dichiarazioni e utilizzo. Inoltre, le classi sono tipi riferimento e le strutture sono tipi valore. Per altre informazioni, vedere [classi e strutture](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 È possibile usare `Structure` solo a livello di spazio dei nomi o modulo. Ciò significa che il *contesto della dichiarazione* per una struttura deve essere un file di origine, lo spazio dei nomi, classe, struttura, modulo o dell'interfaccia e non può essere una routine o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Per impostazione predefinita le strutture [Friend](../../../visual-basic/language-reference/modifiers/friend.md) accesso. È possibile modificare i livelli di accesso con i modificatori di accesso. Per altre informazioni, vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regole  
  
-   **Annidamento.** È possibile definire una struttura all'interno di un altro. La struttura esterna viene definita la *contenente una struttura*, e la struttura interna è definita una *annidati struttura*. Tuttavia, è possibile accedere i membri di una struttura annidata della struttura che lo contiene. In alternativa, è necessario dichiarare una variabile del tipo di dati della struttura annidata.  
  
-   **Dichiarazione di membro.** È necessario dichiarare ogni membro di una struttura. Non può essere un membro della struttura [protetti](../../../visual-basic/language-reference/modifiers/protected.md) o `Protected Friend` perché non può ereditare da una struttura. La stessa struttura, tuttavia, può essere `Protected` o `Protected Friend`.  
  
     È possibile dichiarare zero o più variabili non condivise oppure eventi non condivisi o non personalizzati in una struttura. Non è possibile avere solo costanti, le proprietà e le procedure, anche se alcune di esse sono non condivise.  
  
-   **Inizializzazione.** Non è possibile inizializzare il valore di qualsiasi membro non condiviso dati di una struttura come parte della relativa dichiarazione. È necessario inizializzare un membro di dati tramite un costruttore con parametri in base alla struttura o assegnare un valore al membro dopo aver creato un'istanza della struttura.  
  
-   **Ereditarietà.** Una struttura non può ereditare da qualsiasi tipo diverso da <xref:System.ValueType>, da cui ereditano tutte le strutture. In particolare, una struttura non può ereditare da un altro.  
  
     Non è possibile usare la [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) in una definizione di struttura, anche per specificare <xref:System.ValueType>.  
  
-   **Implementazione.** Se la struttura viene utilizzata la [istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md), è necessario implementare tutti i membri definiti da ogni interfaccia specificata in `interfacenames`.  
  
-   **Proprietà predefinita.** Una struttura è possibile specificare al massimo una proprietà come relativo *proprietà predefinita*, usando la [predefinita](../../../visual-basic/language-reference/modifiers/default.md) modificatore. Per altre informazioni, vedere [predefinito](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Comportamento  
  
-   **Livello di accesso.** All'interno di una struttura, è possibile dichiarare ogni membro con il proprio livello di accesso. Per impostazione predefinita tutti i membri di struttura [pubblica](../../../visual-basic/language-reference/modifiers/public.md) accesso. Si noti che se la stessa struttura dispone di un livello di accesso più limitato, questo automaticamente limita l'accesso ai relativi membri, anche se si modificano i livelli di accesso con i modificatori di accesso.  
  
-   **Ambito.** Una struttura è l'ambito relativo dello spazio dei nomi, classe, struttura o modulo che lo contiene.  
  
     L'ambito di ogni membro della struttura è l'intera struttura.  
  
-   **Ciclo di vita.** Una struttura non include una durata. Piuttosto, ogni istanza di tale struttura ha una durata indipendente da tutte le altre istanze.  
  
     La durata di un'istanza inizia quando viene creato da un [operatore New](../../../visual-basic/language-reference/operators/new-operator.md) clausola. Termina quando la durata della variabile che contiene lo termina.  
  
     Non è possibile estendere la durata di un'istanza della struttura. Un'approssimazione alla funzionalità di struttura statica viene fornita da un modulo. Per altre informazioni, vedere [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     I membri di struttura hanno durate a seconda di come e dove vengono dichiarati. Per altre informazioni, vedere "Durata" nella [istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md).  
  
-   **Qualificazione.** Codice esterno a una struttura necessario qualificare il nome di un membro con il nome di tale struttura.  
  
     Se il codice all'interno di una struttura annidata contiene un riferimento non qualificato a un elemento di programmazione, Visual Basic cerca innanzitutto nella struttura annidata, quindi nella relativa struttura contenitore, e così via per l'elemento più esterno. Per altre informazioni, vedere [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
-   **Utilizzo di memoria.** Come con tutti i tipi di dati compositi, è possibile calcolare in modo sicuro il consumo di memoria totale di una struttura sommando le allocazioni di archiviazione nominale dei relativi membri. Inoltre, non è possibile tranquillamente presupporre che l'ordine di archiviazione in memoria è lo stesso l'ordine di dichiarazione. Se è necessario controllare il layout di archiviazione di una struttura, è possibile applicare il <xref:System.Runtime.InteropServices.StructLayoutAttribute> dell'attributo di `Structure` istruzione.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Structure` istruzione per definire un set di dati correlati per un dipendente. Viene illustrato l'utilizzo delle `Public`, `Friend`, e `Private` membri in modo da riflettere la riservatezza degli elementi di dati. Vengono inoltre visualizzati i membri di routine, proprietà ed eventi.  
  
 [!code-vb[VbVbalrStatements#57](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/structure-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)  
 [Istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Strutture e classi](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
