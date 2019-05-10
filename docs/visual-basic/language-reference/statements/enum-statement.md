---
title: Istruzione Enum (Visual Basic)
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
ms.openlocfilehash: 0a761c39b51a8d71919a84cbbbf6739fc1f5bcea
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754623"
---
# <a name="enum-statement-visual-basic"></a>Istruzione Enum (Visual Basic)

Dichiara un'enumerazione e definisce i valori dei relativi membri.

## <a name="syntax"></a>Sintassi

```
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]
Enum enumerationname [ As datatype ]
   memberlist
End Enum
```

## <a name="parts"></a>Parti

- `attributelist`

  Facoltativo. Elenco di attributi che si applicano a questa enumerazione. È necessario racchiudere il [elenco di attributi](../../../visual-basic/language-reference/statements/attribute-list.md) parentesi angolari ("`<`"e"`>`").

  Il <xref:System.FlagsAttribute> attributo indica che il valore di un'istanza dell'enumerazione può includere più membri dell'enumerazione e che ogni membro rappresenta un campo di bit nel valore di enumerazione.

- `accessmodifier`

  Facoltativo. Specifica il codice può accedere a questa enumerazione. Può essere uno dei seguenti:

  - [Public](../../../visual-basic/language-reference/modifiers/public.md)

  - [Protected](../../../visual-basic/language-reference/modifiers/protected.md)

  - [Friend](../../../visual-basic/language-reference/modifiers/friend.md)

  - [Private](../../../visual-basic/language-reference/modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

- `Shadows`

  Facoltativo. Specifica che questa enumerazione ridichiara e nasconde un elemento di programmazione omonimo o un set di elementi in overload, una classe di base. È possibile specificare [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) solo sull'enumerazione stessa, non sui relativi membri.

- `enumerationname`

  Obbligatorio. Nome dell'enumerazione. Per informazioni sui nomi validi, vedere [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

- `datatype`

  Facoltativo. Tipo di dati di enumerazione e tutti i relativi membri.

- `memberlist`

  Obbligatorio. Elenco di costanti di membro dichiarate in questa istruzione. Più membri vengono visualizzati su righe di codice sorgente singoli.

  Ogni `member` ha la sintassi e le parti seguenti: `[<attribute list>] member name [ = initializer ]`

  |Parte|Descrizione|
  |---|---|
  |`membername`|Obbligatorio. Nome del membro.|
  |`initializer`|Facoltativo. Espressione che viene valutata in fase di compilazione e assegnato a questo membro.|

- `End` `Enum`

  Termina il blocco `Enum`.

## <a name="remarks"></a>Note

Se si dispone di un set di valori costanti che sono correlate logicamente tra loro, è possibile definirli insieme in un'enumerazione. Ciò fornisce nomi significativi per l'enumerazione e i relativi membri, che sono più facili da ricordare rispetto ai relativi valori. È quindi possibile usare i membri dell'enumerazione in molte posizioni nel codice.

I vantaggi dell'uso di enumerazioni includono quanto segue:

- Consente di ridurre gli errori causati da trasporre o errata digitazione numeri.

- Semplifica modificare i valori in futuro.

- Rende il codice più leggibile, ciò significa che è meno probabile che verranno introdotti errori.

- Assicura la compatibilità. Se si utilizzano le enumerazioni, il codice è meno probabile che se in futuro un utente modifica i valori corrispondenti ai nomi dei membri.

Un'enumerazione ha un nome, tipo di dati sottostante e un set di membri. Ogni membro rappresenta una costante.

Un'enumerazione dichiarata nella classe, struttura, modulo o a livello di interfaccia, all'esterno di qualsiasi routine è una *enumerazione membro*. È un membro della classe, struttura, modulo o dell'interfaccia che lo dichiara.

Le enumerazioni dei membri sono accessibili da ovunque la classe, struttura, modulo o interfaccia. Codice esterno di una classe, struttura o un modulo necessario qualificare il nome di un'enumerazione di membri con il nome di tale classe, struttura o modulo. È possibile evitare la necessità di utilizzare nomi pienamente qualificati mediante l'aggiunta di un [importazioni](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) istruzione nel file di origine.

Un'enumerazione dichiarata a livello di spazio dei nomi, all'esterno di qualsiasi classe, struttura, modulo o interfaccia, è un membro dello spazio dei nomi in cui è presente.

Il *contesto della dichiarazione* per un'enumerazione deve essere un file di origine, lo spazio dei nomi, classe, struttura, modulo o interfaccia e non può essere una procedura. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).

È possibile applicare attributi a un'enumerazione nel suo complesso, ma non ai relativi membri singolarmente. Un attributo fornisce informazioni per i metadati dell'assembly.

## <a name="data-type"></a>Tipo di dati

Il `Enum` istruzione può dichiarare il tipo di dati di un'enumerazione. Ogni membro accetta il tipo di dati dell'enumerazione. È possibile specificare `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, o `UShort`.

Se non si specifica `datatype` per l'enumerazione, ogni membro accetta il tipo di dati relativo `initializer`. Se si specificano entrambe `datatype` e `initializer`, il tipo di dati `initializer` deve essere convertibile in `datatype`. Se nessuno di essi `datatype` né `initializer` è presente, il valore predefinito è di tipo di dati `Integer`.

## <a name="initializing-members"></a>L'inizializzazione dei membri

Il `Enum` istruzione possibile inizializzare il contenuto dei membri selezionati in `memberlist`. Si utilizza `initializer` per fornire un'espressione da assegnare al membro.

Se non si specifica `initializer` per un membro, oggetto visivo viene inizializzato su zero (se è il primo `member` nelle `memberlist`), o su un valore maggiore di uno rispetto a quello di immediatamente precedente `member`.

L'espressione fornita in ciascun `initializer` può essere qualsiasi combinazione di valori letterali, altre costanti che sono già definite e membri di enumerazione che sono già definiti, tra cui un membro precedente di questa enumerazione. È possibile utilizzare gli operatori logici e aritmetici per combinare tali elementi.

È possibile usare le variabili o funzioni in `initializer`. Tuttavia, è possibile utilizzare parole chiave di conversione, ad esempio `CByte` e `CShort`. È anche possibile usare `AscW` se viene chiamata con una costante `String` o `Char` argomento, dal momento che possono essere valutati in fase di compilazione.

Le enumerazioni non possono avere valori a virgola mobile. Se un membro viene assegnato un valore a virgola mobile e `Option Strict` è impostata su on, si verifica un errore del compilatore. Se `Option Strict` è disattivata, il valore viene convertito automaticamente nel `Enum` tipo.

Se il valore di un membro supera l'intervallo consentito per il tipo di dati sottostante o se si inizializza un membro del valore massimo consentito dal tipo di dati sottostante, il compilatore segnala un errore.

## <a name="modifiers"></a>Modificatori

Classe, struttura, modulo e predefinito di enumerazioni membro di interfaccia per l'accesso pubblico. È possibile modificare i livelli di accesso con i modificatori di accesso. Namespace membro enumerazioni per impostazione predefinita l'accesso friend. È possibile modificare i livelli di accesso pubblico, ma non a privati o protetti. Per altre informazioni, vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

Tutti i membri di enumerazione hanno l'accesso pubblico e non è possibile utilizzare tutti i modificatori di accesso su di essi. Tuttavia, se l'enumerazione dispone di un livello di accesso più limitato, il livello di accesso enumerazione specificata ha la precedenza.

Per impostazione predefinita, tutte le enumerazioni sono tipi e i relativi campi sono costanti. Di conseguenza il `Shared`, `Static`, e `ReadOnly` parole chiave non possono essere usate quando si dichiara un'enumerazione o i relativi membri.

## <a name="assigning-multiple-values"></a>Assegnazione di più valori

Enumerazioni rappresentano in genere valori si escludono a vicenda. Includendo il <xref:System.FlagsAttribute> attributo la `Enum` dichiarazione, si possono invece assegnare più valori a un'istanza dell'enumerazione. Il <xref:System.FlagsAttribute> attributo specifica che l'enumerazione vengono considerati come un campo di bit, vale a dire, un set di flag. Questi sono denominati *bit per bit* enumerazioni.

Quando si dichiara un'enumerazione utilizzando il <xref:System.FlagsAttribute> attributo, è consigliabile usare potenze di 2, ovvero, 1, 2, 4, 8, 16 e così via, per i valori. È inoltre consigliabile che "None" sia il nome di un membro il cui valore è 0. Per altre indicazioni, vedere <xref:System.FlagsAttribute> e <xref:System.Enum>.

## <a name="example"></a>Esempio

L'esempio seguente mostra come usare l'istruzione `Enum`. Si noti che il membro è detta `EggSizeEnum.Medium`e non come `Medium`.

[!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]

## <a name="example"></a>Esempio

Nell'esempio seguente il metodo non è compreso il `Egg` classe. Pertanto `EggSizeEnum` è un nome completo come `Egg.EggSizeEnum`.

[!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]

## <a name="example"></a>Esempio

L'esempio seguente usa il `Enum` istruzione per definire un set correlato di denominato valori costanti. In questo caso, i valori sono i colori, che è possibile scegliere di progettare il form di immissione di dati per un database.

[!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]

## <a name="example"></a>Esempio

Nell'esempio seguente mostra i valori che includono numeri positivi e negativi.

[!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]

## <a name="example"></a>Esempio

Nell'esempio seguente, un' `As` clausola viene utilizzata per specificare il `datatype` di un'enumerazione.

[!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come utilizzare un'enumerazione bit per bit. Più valori possono essere assegnati a un'istanza di un'enumerazione bit per bit. Il `Enum` dichiarazione include il <xref:System.FlagsAttribute> attributo, che indica che l'enumerazione può essere considerato come un set di flag.

[!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]

## <a name="example"></a>Esempio

Nell'esempio seguente esegue l'iterazione attraverso un'enumerazione. Usa il <xref:System.Enum.GetNames%2A> metodo per recuperare una matrice di nomi dei membri dell'enumerazione e <xref:System.Enum.GetValues%2A> per recuperare una matrice dei valori del membro.

[!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md)
- [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Costanti ed enumerazioni](../../../visual-basic/language-reference/constants-and-enumerations.md)
