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
ms.openlocfilehash: ac128e257269ca301400bd8b294539d1ec836cab
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73038623"
---
# <a name="structure-statement"></a>Istruzione Structure

Dichiara il nome di una struttura e introduce la definizione delle variabili, delle proprietà, degli eventi e delle procedure incluse nella struttura.

## <a name="syntax"></a>Sintassi

```vb
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
|`attributelist`|Parametro facoltativo. Vedere [elenco attributi](attribute-list.md).|
|`accessmodifier`|Parametro facoltativo. Può essere uno dei seguenti:<br /><br /> -   [pubblico](../modifiers/public.md)<br />-   [protetto](../modifiers/protected.md)<br />-   [Friend](../modifiers/friend.md)<br />-   [privato](../modifiers/private.md)<br />- [Friend protetto](../modifiers/protected-friend.md)<br/>- [privato protetto](../modifiers/private-protected.md) <br /><br /> Vedere [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|
|`Shadows`|Parametro facoltativo. Vedere [Shadows](../modifiers/shadows.md).|
|`Partial`|Parametro facoltativo. Indica una definizione parziale della struttura. Vedere [parziale](../modifiers/partial.md).|
|`name`|Obbligatorio. Nome della struttura. Vedere [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`Of`|Parametro facoltativo. Specifica che si tratta di una struttura generica.|
|`typelist`|Obbligatorio se si usa la parola chiave [of](of-clause.md) . Elenco di parametri di tipo per questa struttura. Vedere [elenco dei tipi](type-list.md).|
|`Implements`|Parametro facoltativo. Indica che questa struttura implementa i membri di una o più interfacce. Vedere [istruzione Implements](implements-statement.md).|
|`interfacenames`|Obbligatorio se si usa l'istruzione `Implements`. Nomi delle interfacce implementate da questa struttura.|
|`datamemberdeclarations`|Obbligatorio. Zero o più istruzioni `Const`, `Dim`, `Enum` o `Event` che dichiarano *i membri dati* della struttura.|
|`methodmemberdeclarations`|Parametro facoltativo. Zero o più dichiarazioni di `Function`, `Operator`, `Property` o `Sub` procedure, che vengono utilizzate come *membri del metodo* della struttura.|
|`End Structure`|Obbligatorio. Termina la definizione di `Structure`.|

## <a name="remarks"></a>Note

L'istruzione `Structure` definisce un tipo di valore composto che è possibile personalizzare. Una *struttura* è una generalizzazione del tipo definito dall'utente (UDT) delle versioni precedenti di Visual Basic. Per altre informazioni, vedere [Structures](../../programming-guide/language-features/data-types/structures.md).

Le strutture supportano molte delle stesse funzionalità delle classi. Ad esempio, le strutture possono avere proprietà e procedure, possono implementare interfacce e possono avere costruttori con parametri. Tuttavia, esistono differenze significative tra le strutture e le classi in aree quali ereditarietà, dichiarazioni e utilizzo. Inoltre, le classi sono tipi di riferimento e le strutture sono tipi di valore. Per altre informazioni, vedere [strutture e classi](../../programming-guide/language-features/data-types/structures-and-classes.md).

È possibile usare `Structure` solo a livello di spazio dei nomi o di modulo. Ciò significa che il *contesto di dichiarazione* per una struttura deve essere un file di origine, uno spazio dei nomi, una classe, una struttura, un modulo o un'interfaccia e non può essere una routine o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).

Per impostazione predefinita, le strutture sono accessi [Friend](../modifiers/friend.md) . È possibile modificare i livelli di accesso con i modificatori di accesso. Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

## <a name="rules"></a>Regole

- **Annidamento.** È possibile definire una struttura in un'altra. La struttura esterna viene chiamata *struttura che lo contiene*e la struttura interna viene chiamata *struttura annidata*. Tuttavia, non è possibile accedere ai membri di una struttura annidata tramite la struttura che lo contiene. È invece necessario dichiarare una variabile del tipo di dati della struttura nidificata.

- **Dichiarazione del membro.** È necessario dichiarare ogni membro di una struttura. Un membro di struttura non può essere [protetto](../modifiers/protected.md) o `Protected Friend` perché nulla può ereditare da una struttura. La struttura, tuttavia, può essere `Protected` o `Protected Friend`.
  
     È possibile dichiarare zero o più variabili non condivise oppure eventi non condivisi o non personalizzati in una struttura. Non è possibile avere solo costanti, proprietà e procedure, anche se alcune di esse non sono condivise.

- **Inizializzazione.** Non è possibile inizializzare il valore di un membro dati non condiviso di una struttura come parte della relativa dichiarazione. È necessario inizializzare tale membro dati tramite un costruttore con parametri sulla struttura oppure assegnare un valore al membro dopo aver creato un'istanza della struttura.

- **Ereditarietà.** Una struttura non può ereditare da un tipo diverso da <xref:System.ValueType>, da cui ereditano tutte le strutture. In particolare, una struttura non può ereditare da un'altra.

     Non è possibile usare l' [istruzione Inherits](inherits-statement.md) in una definizione di struttura, neanche per specificare <xref:System.ValueType>.

- **Implementazione.** Se la struttura usa l' [istruzione Implements](implements-statement.md), è necessario implementare ogni membro definito da ogni interfaccia specificata in `interfacenames`.

- **Proprietà predefinita.** Una struttura può specificare al massimo una proprietà come *proprietà predefinita*, usando il modificatore [predefinito](../modifiers/default.md) . Per ulteriori informazioni, vedere [default](../modifiers/default.md).

## <a name="behavior"></a>Comportamento

- **Livello di accesso.** All'interno di una struttura, è possibile dichiarare ogni membro con il proprio livello di accesso. Per impostazione predefinita, tutti i membri della struttura sono con accesso [pubblico](../modifiers/public.md) . Si noti che se la struttura ha un livello di accesso più limitato, questo limita automaticamente l'accesso ai relativi membri, anche se si modificano i livelli di accesso con i modificatori di accesso.

- **Ambito.** Una struttura è nell'ambito di tutti gli spazi dei nomi, la classe, la struttura o il modulo che lo contiene.

     L'ambito di ogni membro della struttura è l'intera struttura.

- **Vita.** Una struttura non ha una durata. Ogni istanza di tale struttura ha invece una durata indipendente da tutte le altre istanze.

     Il ciclo di vita di un'istanza inizia quando viene creato da una nuova clausola di [operatore](../operators/new-operator.md) . Termina quando termina la durata della variabile che lo include.

     Non è possibile estendere la durata di un'istanza della struttura. Un modulo fornisce un'approssimazione alla funzionalità della struttura statica. Per ulteriori informazioni, vedere [istruzione Module](module-statement.md).

     I membri della struttura hanno durate a seconda della modalità e della posizione in cui vengono dichiarati. Per ulteriori informazioni, vedere "Lifetime" nell' [istruzione Class](class-statement.md).

- **Qualificazione.** Il codice esterno a una struttura deve qualificare il nome di un membro con il nome della struttura.

     Se il codice all'interno di una struttura annidata crea un riferimento non qualificato a un elemento di programmazione, Visual Basic cerca prima l'elemento nella struttura nidificata, quindi nella struttura che lo contiene e così via fino all'elemento contenitore più esterno. Per altre informazioni, vedere [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

- **Consumo di memoria.** Come per tutti i tipi di dati compositi, non è possibile calcolare in modo sicuro il consumo di memoria totale di una struttura aggiungendo le allocazioni di archiviazione nominale dei relativi membri. Inoltre, non è possibile presupporre in modo sicuro che l'ordine di archiviazione in memoria sia uguale all'ordine di dichiarazione. Se è necessario controllare il layout di archiviazione di una struttura, è possibile applicare l'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> all'istruzione `Structure`.

## <a name="example"></a>Esempio

Nell'esempio seguente viene utilizzata l'istruzione `Structure` per definire un set di dati correlati per un dipendente. Mostra l'uso dei membri `Public`, `Friend` e `Private` per riflettere la riservatezza degli elementi di dati. Vengono inoltre illustrati i membri della procedura, della proprietà e dell'evento.

[!code-vb[VbVbalrStatements#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#57)]

Per ulteriori informazioni sull'utilizzo di `Structure`s, vedere [variabile di struttura](../../programming-guide/language-features/data-types/structure-variables.md).

## <a name="see-also"></a>Vedere anche

- [Istruzione Class](class-statement.md)
- [Istruzione Interface](interface-statement.md)
- [Istruzione Module](module-statement.md)
- [Istruzione Dim](dim-statement.md)
- [Istruzione Const](const-statement.md)
- [Istruzione Enum](enum-statement.md)
- [Istruzione Event](event-statement.md)
- [Istruzione Operator](operator-statement.md)
- [Istruzione Property](property-statement.md)
- [Strutture e classi](../../programming-guide/language-features/data-types/structures-and-classes.md)
