---
title: Parola chiave enum (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: 634fbd846993d32ae529f87e96fd91857e5c1883
ms.sourcegitcommit: f9e38d31288fe5962e6be5b0cc286da633482873
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/27/2018
ms.locfileid: "37028279"
---
# <a name="enum-c-reference"></a>enum (Riferimenti per C#)

La parola chiave `enum` viene usata per dichiarare un'enumerazione, un tipo distinto costituito da un set di costanti denominate definite elenco degli enumeratori.  

In genere è preferibile definire un'enumerazione direttamente all'interno di uno spazio dei nomi in modo che tutte le classi nello spazio dei nomi possano accedervi con la stessa facilità. Tuttavia, un'enumerazione può anche essere annidata all'interno di una classe o di uno struct.

Per impostazione predefinita, il primo enumeratore ha un valore 0 e il valore di ogni enumeratore successivo viene incrementato di 1. Ad esempio, nell'enumerazione seguente `Sat` è `0`, `Sun` è `1`, `Mon` è `2`e così via.

```csharp
enum Day {Sat, Sun, Mon, Tue, Wed, Thu, Fri};
```

Gli enumeratori possono usare gli inizializzatori per sostituire i valori predefiniti, come illustrato nell'esempio seguente.

```csharp
enum Day {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

In questa enumerazione la sequenza di elementi viene forzata a iniziare da `1` anziché da `0`. Tuttavia, si consiglia di includere una costante con valore pari a 0. Per altre informazioni, vedere [Tipi di enumerazione](../../programming-guide/enumeration-types.md).

Ogni tipo di enumerazione ha un tipo sottostante, che può essere qualsiasi tipo integrale eccetto [char](char.md). Il tipo sottostante predefinito degli elementi dell'enumerazione è [int](int.md). Per dichiarare un'enumerazione di un altro tipo integrale, ad esempio [byte](byte.md), usare i due punti dopo l'identificatore seguiti dal tipo, come illustrato nell'esempio seguente.

```csharp
enum Day : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

I tipi approvati per un'enumerazione sono [byte](byte.md), [sbyte](sbyte.md), [short](short.md), [ushort](ushort.md), [int](int.md), [uint](uint.md), [long](long.md) o [ulong](ulong.md).

A una variabile di tipo `Day` può essere assegnato qualsiasi valore compreso nell'intervallo del tipo sottostante. I valori non sono limitati alle costanti denominate.

Il valore predefinito di un `enum E` è il valore prodotto dall'espressione `(E)0`.

> [!NOTE]
> Un enumeratore non può contenere spazi vuoti nel nome.

Il tipo sottostante specifica la quantità di spazio di archiviazione allocata per ogni enumeratore. Tuttavia, è necessario un cast esplicito per eseguire la conversione da un tipo `enum` a un tipo integrale. Ad esempio, l'istruzione seguente assegna l'enumeratore `Sun` a una variabile di tipo [int](int.md) usando un cast per convertire `enum` in `int`.

```csharp
int x = (int)Day.Sun;
```

Quando si applica <xref:System.FlagsAttribute?displayProperty=nameWithType> a un'enumerazione che contiene elementi che possono essere combinati con un'operazione `OR` bit per bit, l'attributo influisce sul comportamento di `enum` quando viene usato con alcuni strumenti. È possibile notare queste modifiche quando si usano strumenti come i metodi della classe <xref:System.Console> e l'analizzatore di espressioni. Vedere il terzo esempio.

## <a name="robust-programming"></a>Programmazione efficiente

Come per le altre costanti, tutti i riferimenti ai singoli valori di un'enumerazione vengono convertiti in valori letterali numerici in fase di compilazione. Questo può creare potenziali problemi relativi al controllo delle versioni come descritto in [Costanti](../../programming-guide/classes-and-structs/constants.md).

L'assegnazione di valori aggiuntivi alle nuove versioni delle enumerazioni o la modifica dei valori dei membri enum in una nuova versione può causare problemi per il codice sorgente dipendente. I valori enum spesso vengono usati nelle istruzioni [switch](switch.md) . Se sono stati aggiunti altri elementi al tipo `enum` , la sezione predefinita dell'istruzione switch può essere selezionata in modo imprevisto.

Se altri sviluppatori usano il codice, è opportuno fornire indicazioni su come dovrebbe rispondere il loro codice quando vengono aggiunti nuovi elementi a qualsiasi tipo `enum` .

## <a name="example"></a>Esempio

Nell'esempio seguente viene dichiarata un'enumerazione `Day`. Due enumeratori vengono convertiti esplicitamente in un valore integer e assegnati a variabili integer.

[!code-csharp[csrefKeywordsTypes#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#10)]

## <a name="example"></a>Esempio

Nell'esempio seguente l'opzione del tipo di base viene usata per dichiarare un `enum` i cui membri sono di tipo `long`. Si noti che, anche se il tipo sottostante dell'enumerazione è `long`, i membri dell'enumerazione non sono ancora stati convertiti esplicitamente nel tipo `long` con un cast.

[!code-csharp[csrefKeywordsTypes#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#11)]

## <a name="example"></a>Esempio

L'esempio di codice seguente illustra l'utilizzo e gli effetti dell'attributo <xref:System.FlagsAttribute?displayProperty=nameWithType> su una dichiarazione `enum` .

[!code-csharp[csrefKeywordsTypes#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#12)]

## <a name="comments"></a>Commenti

Se si rimuove `Flags`, l'esempio visualizza i valori seguenti:

`5`

`5`

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

[Riferimenti per C#](../index.md)  
[Tipi di enumerazione](../../programming-guide/enumeration-types.md)  
[Parole chiave di C#](index.md)  
[Tabella dei tipi integrali](integral-types-table.md)  
[Tabella dei tipi incorporati](built-in-types-table.md)  
[Tabella delle conversioni numeriche implicite](implicit-numeric-conversions-table.md)  
[Tabella delle conversioni numeriche esplicite](explicit-numeric-conversions-table.md)  
[Convenzioni di denominazione di enumerazione](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
