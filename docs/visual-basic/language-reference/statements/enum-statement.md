---
title: Istruzione Enum
ms.date: 07/20/2015
f1_keywords:
- vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
ms.openlocfilehash: 48220fd1e88cf38e67db5dd3a2ad90638eb6b6df
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343707"
---
# <a name="enum-statement-visual-basic"></a>Istruzione Enum (Visual Basic)

Dichiara un'enumerazione e definisce i valori dei relativi membri.

## <a name="syntax"></a>Sintassi

```vb
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]
Enum enumerationname [ As datatype ]
   memberlist
End Enum
```

## <a name="parts"></a>Parti

- `attributelist`

  Facoltativa. Elenco degli attributi che si applicano a questa enumerazione. È necessario racchiudere l' [elenco degli attributi](../../../visual-basic/language-reference/statements/attribute-list.md) tra parentesi angolari ("`<`" e "`>`").

  L'attributo <xref:System.FlagsAttribute> indica che il valore di un'istanza dell'enumerazione può includere più membri di enumerazione e che ogni membro rappresenta un campo di bit nel valore di enumerazione.

- `accessmodifier`

  Facoltativa. Specifica il codice che può accedere a questa enumerazione. Può essere uno dei collegamenti seguenti:

  - [Public](../../../visual-basic/language-reference/modifiers/public.md)

  - [Protected](../../../visual-basic/language-reference/modifiers/protected.md)

  - [Friend](../../../visual-basic/language-reference/modifiers/friend.md)

  - [Private](../../../visual-basic/language-reference/modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

- `Shadows`

  Facoltativa. Specifica che questa enumerazione dichiara e nasconde un elemento di programmazione con nome identico o un set di elementi in overload in una classe base. È possibile specificare le [ombreggiature](../../../visual-basic/language-reference/modifiers/shadows.md) solo sull'enumerazione stessa, non su nessuno dei relativi membri.

- `enumerationname`

  Obbligatoria. Nome dell'enumerazione. Per informazioni sui nomi validi, vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

- `datatype`

  Facoltativa. Tipo di dati dell'enumerazione e di tutti i relativi membri.

- `memberlist`

  Obbligatoria. Elenco di costanti membro dichiarate in questa istruzione. Vengono visualizzati più membri nelle singole righe del codice sorgente.

  Ogni `member` presenta la sintassi e le parti seguenti: `[<attribute list>] member name [ = initializer ]`

  |Parte|Descrizione|
  |---|---|
  |`membername`|Obbligatoria. Nome del membro.|
  |`initializer`|Facoltativa. Espressione valutata in fase di compilazione e assegnata a questo membro.|

- `End` `Enum`

  Termina il blocco `Enum`.

## <a name="remarks"></a>Note

Se si dispone di un set di valori non modificabili logicamente correlati tra loro, è possibile definirli insieme in un'enumerazione. Che fornisce nomi significativi per l'enumerazione e i relativi membri, che sono più facili da ricordare rispetto ai relativi valori. È quindi possibile usare i membri di enumerazione in molte posizioni nel codice.

I vantaggi dell'utilizzo delle enumerazioni includono quanto segue:

- Riduce gli errori causati dalla trasposizione o dalla digitazione errata dei numeri.

- Semplifica la modifica dei valori in futuro.

- Semplifica la lettura del codice, il che significa che è meno probabile che vengano introdotti errori.

- Garantisce la compatibilità con le edizioni. Se si utilizzano le enumerazioni, è meno probabile che il codice abbia esito negativo se in futuro qualcuno modifica i valori corrispondenti ai nomi dei membri.

Un'enumerazione ha un nome, un tipo di dati sottostante e un set di membri. Ogni membro rappresenta una costante.

Un'enumerazione dichiarata a livello di classe, struttura, modulo o interfaccia, all'esterno di qualsiasi routine, è un' *enumerazione di membri*. È un membro della classe, struttura, modulo o interfaccia che lo dichiara.

È possibile accedere alle enumerazioni dei membri da qualsiasi posizione all'interno della classe, struttura, modulo o interfaccia. Il codice esterno a una classe, una struttura o un modulo deve qualificare il nome di un'enumerazione membro con il nome della classe, della struttura o del modulo. Per evitare di dover utilizzare nomi completi, è possibile aggiungere un'istruzione [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) al file di origine.

Un'enumerazione dichiarata a livello di spazio dei nomi, all'esterno di qualsiasi classe, struttura, modulo o interfaccia, è un membro dello spazio dei nomi in cui viene visualizzata.

Il *contesto di dichiarazione* per un'enumerazione deve essere un file di origine, uno spazio dei nomi, una classe, una struttura, un modulo o un'interfaccia e non può essere una routine. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).

È possibile applicare gli attributi a un'enumerazione nel suo complesso, ma non ai relativi membri singolarmente. Un attributo fornisce informazioni ai metadati dell'assembly.

## <a name="data-type"></a>Tipo di dati

L'istruzione `Enum` può dichiarare il tipo di dati di un'enumerazione. Ogni membro accetta il tipo di dati dell'enumerazione. È possibile specificare `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`o `UShort`.

Se non si specifica `datatype` per l'enumerazione, ogni membro accetta il tipo di dati del relativo `initializer`. Se si specificano sia `datatype` che `initializer`, il tipo di dati di `initializer` deve essere convertibile in `datatype`. Se non è presente né `datatype` né `initializer`, il tipo di dati predefinito è `Integer`.

## <a name="initializing-members"></a>Inizializzazione di membri

L'istruzione `Enum` può inizializzare il contenuto dei membri selezionati nel `memberlist`. Usare `initializer` per fornire un'espressione da assegnare al membro.

Se non si specifica `initializer` per un membro, Visual Basic inizializzarlo su zero (se è il primo `member` in `memberlist`) o su un valore maggiore di uno rispetto a quello del `member`immediatamente precedente.

L'espressione fornita in ogni `initializer` può essere costituita da qualsiasi combinazione di valori letterali, altre costanti già definite e membri di enumerazione già definiti, incluso un membro precedente di questa enumerazione. Per combinare tali elementi, è possibile utilizzare operatori aritmetici e logici.

Non è possibile usare variabili o funzioni in `initializer`. È tuttavia possibile usare parole chiave di conversione, ad esempio `CByte` e `CShort`. È inoltre possibile utilizzare `AscW` se viene chiamato con un argomento `String` o `Char` costante, dal momento che può essere valutato in fase di compilazione.

Le enumerazioni non possono avere valori a virgola mobile. Se a un membro viene assegnato un valore a virgola mobile e `Option Strict` è impostato su on, si verifica un errore del compilatore. Se `Option Strict` è impostata su off, il valore viene convertito automaticamente nel tipo di `Enum`.

Se il valore di un membro supera l'intervallo consentito per il tipo di dati sottostante o se si Inizializza un membro sul valore massimo consentito dal tipo di dati sottostante, il compilatore segnala un errore.

## <a name="modifiers"></a>Modificatori

Per impostazione predefinita, le enumerazioni di membri di classe, struttura, modulo e interfaccia sono di accesso pubblico. È possibile modificare i livelli di accesso con i modificatori di accesso. Per impostazione predefinita, le enumerazioni di membri dello spazio dei nomi sono Friend. È possibile modificare i livelli di accesso in pubblico, ma non in privato o protetto. Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

Tutti i membri di enumerazione hanno accesso pubblico e non è possibile usare alcun modificatore di accesso. Tuttavia, se l'enumerazione stessa ha un livello di accesso più limitato, il livello di accesso di enumerazione specificato avrà la precedenza.

Per impostazione predefinita, tutte le enumerazioni sono tipi e i rispettivi campi sono costanti. Pertanto, non è possibile usare le parole chiave `Shared`, `Static`e `ReadOnly` quando si dichiara un'enumerazione o i relativi membri.

## <a name="assigning-multiple-values"></a>Assegnazione di più valori

Le enumerazioni rappresentano in genere valori che si escludono a vicenda. Includendo l'attributo <xref:System.FlagsAttribute> nella dichiarazione di `Enum`, è invece possibile assegnare più valori a un'istanza dell'enumerazione. L'attributo <xref:System.FlagsAttribute> specifica che l'enumerazione deve essere considerata come un campo di bit, ovvero un set di flag. Queste sono denominate enumerazioni *bit per bit* .

Quando si dichiara un'enumerazione usando l'attributo <xref:System.FlagsAttribute>, è consigliabile usare le potenze di 2, ovvero 1, 2, 4, 8, 16 e così via, per i valori. Si consiglia inoltre che "None" sia il nome di un membro il cui valore è 0. Per altre linee guida, vedere <xref:System.FlagsAttribute> e <xref:System.Enum>.

## <a name="example"></a>Esempio

L'esempio seguente mostra come usare l'istruzione `Enum`. Si noti che il membro viene definito `EggSizeEnum.Medium`e non come `Medium`.

[!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]

## <a name="example"></a>Esempio

Il metodo nell'esempio seguente è esterno alla classe `Egg`. Pertanto, `EggSizeEnum` è completo come `Egg.EggSizeEnum`.

[!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene utilizzata l'istruzione `Enum` per definire un set correlato di valori costanti denominati. In questo caso, i valori sono i colori che è possibile scegliere per progettare moduli di immissione dati per un database.

[!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]

## <a name="example"></a>Esempio

Nell'esempio seguente vengono illustrati i valori che includono numeri positivi e negativi.

[!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene usata una clausola `As` per specificare il `datatype` di un'enumerazione.

[!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come utilizzare un'enumerazione bit per bit. È possibile assegnare più valori a un'istanza di un'enumerazione bit per bit. La dichiarazione `Enum` include l'attributo <xref:System.FlagsAttribute>, che indica che l'enumerazione può essere considerata come un set di flag.

[!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene iterata un'enumerazione. Usa il metodo <xref:System.Enum.GetNames%2A> per recuperare una matrice di nomi di membri dall'enumerazione e <xref:System.Enum.GetValues%2A> per recuperare una matrice di valori dei membri.

[!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)
- [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Costanti ed enumerazioni](../../../visual-basic/language-reference/constants-and-enumerations.md)
