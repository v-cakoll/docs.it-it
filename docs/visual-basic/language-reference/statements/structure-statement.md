---
title: Istruzione Structure
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
ms.openlocfilehash: 6fdc4f1d2fbd40689c76a15a5a35b25522138be6
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2018
---
# <a name="structure-statement"></a>Istruzione Structure
Dichiara il nome di una struttura e introduce la definizione di variabili, proprietà, eventi ed procedure che comprende la struttura.  
  
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
|`attributelist`|Facoltativo. Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Facoltativo. Può essere uno dei seguenti:<br /><br /> -   [Pubblica](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protetto](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privato](../../../visual-basic/language-reference/modifiers/private.md)<br />- [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br/>- [Protetto privato](../../language-reference/modifiers/private-protected.md) <br /><br /> Vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Facoltativo. Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`Partial`|Facoltativo. Indica una definizione parziale della struttura. Vedere [parziale](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Obbligatorio. Nome della struttura. Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Facoltativo. Specifica che si tratta di una struttura generica.|  
|`typelist`|Obbligatorio se si usa il [di](../../../visual-basic/language-reference/statements/of-clause.md) (parola chiave). Elenco di parametri di tipo per questa struttura. Vedere [digitare elenco](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Implements`|Facoltativo. Indica che questa struttura implementa i membri di una o più interfacce. Vedere [implementa istruzione](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Obbligatorio se si usa il `Implements` istruzione. I nomi delle interfacce implementate questa struttura.|  
|`datamemberdeclarations`|Obbligatorio. Zero o più `Const`, `Dim`, `Enum`, o `Event` istruzioni di dichiarazione *membri dati* della struttura.|  
|`methodmemberdeclarations`|Facoltativo. Zero o più dichiarazioni di `Function`, `Operator`, `Property`, o `Sub` procedure che fungono da *membri metodo* della struttura.|  
|`End Structure`|Obbligatorio. Termina il `Structure` definizione.|  
  
## <a name="remarks"></a>Note  
 Il `Structure` istruzione definisce un tipo di valore composito che è possibile personalizzare. Oggetto *struttura* è una generalizzazione del tipo definito dall'utente (UDT) di versioni precedenti di Visual Basic. Per ulteriori informazioni, vedere [strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md).  
  
 Strutture supportano molte delle stesse funzionalità di classi. Ad esempio, le strutture possono disporre di proprietà e routine, possono implementare interfacce e possono disporre di costruttori parametrizzati. Tuttavia, esistono differenze significative tra strutture e classi in aree quali ereditarietà, le dichiarazioni e utilizzo. Inoltre, le classi sono tipi di riferimento e le strutture sono tipi di valore. Per ulteriori informazioni, vedere [strutture e classi](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 È possibile utilizzare `Structure` solo a livello di spazio dei nomi o modulo. Ciò significa che il *contesto della dichiarazione* per una struttura deve essere un file di origine, lo spazio dei nomi, classe, struttura, modulo o interfaccia e non può essere una stored procedure o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Per impostazione predefinita le strutture [Friend](../../../visual-basic/language-reference/modifiers/friend.md) accesso. È possibile regolare i livelli di accesso con i modificatori di accesso. Per ulteriori informazioni, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regole  
  
-   **La nidificazione.** È possibile definire una struttura all'interno di un altro. Struttura esterna viene definita la *contenente una struttura*, e la struttura interna viene definita una *annidati struttura*. Tuttavia, è possibile accedere i membri di una struttura nidificata attraverso la struttura contenente. In alternativa, è necessario dichiarare una variabile del tipo di dati della struttura annidata.  
  
-   **Dichiarazione di membro.** È necessario dichiarare ogni membro di una struttura. Non può essere un membro di struttura [Protected](../../../visual-basic/language-reference/modifiers/protected.md) o `Protected Friend` perché non può ereditare da una struttura. La stessa struttura, tuttavia, può essere `Protected` o `Protected Friend`.  
  
     È possibile dichiarare zero o più variabili non condivise oppure eventi non condivisi o non personalizzati in una struttura. È possibile avere solo costanti, proprietà e routine, anche se alcuni di essi sono non condivisi.  
  
-   **inizializzazione.** Non è possibile inizializzare il valore di un membro dati non condivisi di una struttura come parte della relativa dichiarazione. È necessario inizializzare un membro di dati tramite un costruttore con parametri in base alla struttura o assegnare un valore per il membro dopo aver creato un'istanza della struttura.  
  
-   **Ereditarietà.** Una struttura non può ereditare da qualsiasi tipo diverso da <xref:System.ValueType>, dalla quale ereditano tutte le strutture. In particolare, una struttura non può ereditare da un altro.  
  
     Non è possibile utilizzare il [istruzione Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md) nella definizione di una struttura, anche per specificare <xref:System.ValueType>.  
  
-   **Implementazione.** Se la struttura utilizza il [istruzione Implements](../../../visual-basic/language-reference/statements/implements-statement.md), è necessario implementare ogni membro definito da ogni interfaccia specificata in `interfacenames`.  
  
-   **Proprietà predefinita.** Una struttura è possibile specificare al massimo una proprietà come relativo *proprietà predefinita*, usando il [predefinito](../../../visual-basic/language-reference/modifiers/default.md) modificatore. Per ulteriori informazioni, vedere [predefinito](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Comportamento  
  
-   **Livello di accesso.** All'interno di una struttura, è possibile dichiarare ogni membro con il proprio livello di accesso. Per impostazione predefinita tutti i membri di struttura [pubblica](../../../visual-basic/language-reference/modifiers/public.md) accesso. Si noti che se la stessa struttura dispone di un livello di accesso più limitato, questo automaticamente limita l'accesso ai relativi membri, anche se non è regolare i livelli di accesso con i modificatori di accesso.  
  
-   **Ambito.** Una struttura è l'ambito relativo spazio dei nomi, classe, struttura o modulo contenitore.  
  
     L'ambito di ogni membro di struttura è l'intera struttura.  
  
-   **Durata.** Una struttura non include una durata. Invece, ogni istanza di tale struttura ha una durata indipendente da tutte le altre istanze.  
  
     La durata di un'istanza inizia quando viene creato da un [nuovo operatore](../../../visual-basic/language-reference/operators/new-operator.md) clausola. Termina la durata della variabile che contiene la fine.  
  
     È possibile estendere la durata di un'istanza della struttura. Un'approssimazione alla funzionalità di struttura statica viene fornita da un modulo. Per ulteriori informazioni, vedere [istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Membri di struttura hanno durate a seconda di come e dove vengono dichiarate. Per ulteriori informazioni, vedere "Durata" in [istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md).  
  
-   **Qualifica.** Codice di fuori di una struttura è necessario qualificare il nome di un membro con il nome della struttura.  
  
     Se il codice all'interno di una struttura nidificata fa riferimento non qualificato di un elemento di programmazione, Visual Basic cerca innanzitutto nella struttura nidificata, quindi nella sua struttura contenente, e così via per l'elemento più esterno. Per ulteriori informazioni, vedere [riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
-   **Utilizzo di memoria.** Come con tutti i tipi di dati compositi, è possibile calcolare in modo sicuro il consumo di memoria totale di una struttura sommando le allocazioni di memoria nominali dei relativi membri. Inoltre, non è possibile presupporre che l'ordine di archiviazione in memoria è identico all'ordine di dichiarazione. Se è necessario controllare il layout di archiviazione di una struttura, è possibile applicare il <xref:System.Runtime.InteropServices.StructLayoutAttribute> attributo la `Structure` istruzione.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Structure` istruzione per definire un set di dati correlati per un dipendente. Viene illustrato l'utilizzo di `Public`, `Friend`, e `Private` membri per riflettere la riservatezza degli elementi di dati. Viene inoltre i membri di routine, proprietà ed eventi.  
  
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
