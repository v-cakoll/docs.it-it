---
title: Classi e metodi parziali - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
ms.openlocfilehash: 641c2e3adfb3dabaa300e94b203aa6c4c4b509d2
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628189"
---
# <a name="partial-classes-and-methods-c-programming-guide"></a>Classi e metodi parziali (Guida per programmatori C#)

È possibile suddividere la definizione di una [classe](../../language-reference/keywords/class.md) di uno [struct](../../language-reference/builtin-types/struct.md), di un'[interfaccia](../../language-reference/keywords/interface.md) o di un metodo tra due o più file di origine. Ogni file di origine contiene una sezione della definizione di tipo o metodo e tutte le parti vengono combinate al momento della compilazione dell'applicazione.

## <a name="partial-classes"></a>Classi parziali

La suddivisione della definizione di una classe è consigliabile in diverse situazioni:

- Quando si lavora su progetti di grandi dimensioni, la distribuzione di una classe in file distinti ne consente l'uso simultaneo da parte di più programmatori.

- Quando si usa un'origine generata automaticamente, è possibile aggiungere codice alla classe senza dover ricreare il file di origine. Visual Studio usa questo approccio per la creazione di Windows Form, codice wrapper di servizi Web e così via. È possibile creare codice che usa queste classi senza dover modificare il file creato da Visual Studio.

- Per suddividere la definizione di una classe, usare il modificatore della parola chiave [partial](../../language-reference/keywords/partial-type.md), come illustrato di seguito:

  [!code-csharp[csProgGuideObjects#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#26)]

La parola chiave `partial` indica che è possibile definire altre parti della classe, dello struct o dell'interfaccia nello spazio dei nomi. Tutte le parti devono usare la parola chiave `partial` ed essere disponibili in fase di compilazione in modo da formare il tipo finale. Tutte le parti devono anche avere lo stesso livello di accessibilità, ad esempio `public`, `private` e così via.

Se una parte viene dichiarata come astratta, l'intero tipo verrà considerato astratto. Se una parte viene dichiarata come sealed, l'intero tipo verrà considerato sealed. Se una parte dichiara un tipo base, l'intero tipo eredita la classe.

Tutte le parti che specificano una classe base devono concordare, tuttavia le parti che omettono una classe base ereditano comunque il tipo base. Le parti possono specificare interfacce di base differenti e il tipo finale implementa tutte le interfacce elencate da tutte le dichiarazioni parziali. Tutti i membri di classe, struttura o interfaccia dichiarati in una definizione parziale sono disponibili per tutte le altre parti. Il tipo finale rappresenta la combinazione di tutte le parti in fase di compilazione.

> [!NOTE]
> Il modificatore `partial` non è disponibile per le dichiarazioni di delegato o di enumerazione.

L'esempio seguente illustra che i tipi annidati possono essere parziali, anche se non lo è il tipo all'interno del quale sono annidati.

[!code-csharp[csProgGuideObjects#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#25)]

In fase di compilazione gli attributi delle definizioni di tipi parziali vengono uniti. Si considerino ad esempio le dichiarazioni seguenti:

[!code-csharp[csProgGuideObjects#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#23)]

Sono equivalenti alle dichiarazioni seguenti:

[!code-csharp[csProgGuideObjects#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#24)]

Gli elementi seguenti vengono uniti da tutte le definizioni di tipi parziali:

- XML (commenti)

- interfacce

- attributi di parametri di tipo generico

- attributi class

- membri

Si considerino ad esempio le dichiarazioni seguenti:

[!code-csharp[csProgGuideObjects#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#21)]

Sono equivalenti alle dichiarazioni seguenti:

[!code-csharp[csProgGuideObjects#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#22)]

### <a name="restrictions"></a>Restrizioni

Quando si usano le definizioni parziali di classi è necessario rispettare diverse regole:

- Tutte le definizioni di tipi parziali destinate a essere parti dello stesso tipo devono essere modificate con `partial`. Ad esempio, le dichiarazioni di classe seguenti generano un errore:

  [!code-csharp[csProgGuideObjects#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#20)]

- Il modificatore `partial` può essere specificato solo prima delle parole chiave `class`, `struct` o `interface`.

- I tipi parziali annidati sono consentiti nelle definizioni di tipi parziali, come illustrato nell'esempio seguente:

  [!code-csharp[csProgGuideObjects#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#19)]

- Tutte le definizioni di tipi parziali destinate a essere parti dello stesso tipo devono essere definite nello stesso assembly e nello stesso modulo (file con estensione exe o dll). Le definizioni parziali non possono estendersi su più moduli.

- Il nome della classe e i parametri di tipo generico devono corrispondere in tutte le definizioni di tipi parziali. I tipi generici possono essere parziali. In ogni dichiarazione parziale è necessario usare gli stessi nomi di parametri nello stesso ordine.

- Le parole chiave riportate di seguito sono facoltative in una definizione di tipi parziali. Tuttavia, se presenti in una definizione, tali parole chiave non possono essere in conflitto con quelle specificate in un'altra definizione parziale per lo stesso tipo:

  - [pubblico](../../language-reference/keywords/public.md)

  - [private](../../language-reference/keywords/private.md)

  - [protected](../../language-reference/keywords/protected.md)

  - [internal](../../language-reference/keywords/internal.md)

  - [abstract](../../language-reference/keywords/abstract.md)

  - [sealed](../../language-reference/keywords/sealed.md)

  - classi base

  - modificatore [new](../../language-reference/keywords/new-modifier.md) (parti annidate)

  - vincoli generici

Per altre informazioni, vedere [Vincoli sui parametri di tipo](../generics/constraints-on-type-parameters.md).

## <a name="example-1"></a>Esempio 1

### <a name="description"></a>Descrizione

Nell'esempio seguente i campi e il costruttore della classe `Coords` vengono dichiarati in una definizione parziale di classe, mentre il membro `PrintCoords` viene dichiarato in un'altra definizione parziale di classe.

### <a name="code"></a>Codice

[!code-csharp[csProgGuideObjects#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#17)]

## <a name="example-2"></a>Esempio 2

### <a name="description"></a>Descrizione

L'esempio seguente dimostra che è anche possibile sviluppare struct e interfacce parziali.

### <a name="code"></a>Codice

[!code-csharp[csProgGuideObjects#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#18)]

## <a name="partial-methods"></a>Metodi parziali

Una classe o uno struct parziale può contenere un metodo parziale. Una parte della classe contiene la firma del metodo. Un'implementazione facoltativa può essere definita nella stessa parte o in un'altra parte. Se l'implementazione non viene specificata, il metodo e tutte le chiamate al metodo vengono rimosse in fase di compilazione.

I metodi parziali consentono all'implementatore di una parte di una classe di definire un metodo, simile a un evento. L'implementatore dell'altra parte della classe può decidere se implementare il metodo o meno. Se il metodo non viene implementato, il compilatore rimuove la firma del metodo e tutte le chiamate al metodo. Le chiamate al metodo, inclusi eventuali risultati che derivassero dalla valutazione di argomenti nelle chiamate, non hanno alcun effetto in fase di esecuzione. Pertanto, il codice nella classe parziale può usare liberamente un metodo parziale, anche se non viene specificata l'implementazione. Non verranno generati errori in fase di compilazione o errori di runtime se il metodo viene chiamato ma non implementato.

I metodi parziali sono particolarmente utili per personalizzare il codice generato. Consentono di riservare un nome e una firma del metodo, in modo che il codice generato possa chiamare il metodo ma spetta allo sviluppatore decidere se implementare il metodo. Analogamente alle classi parziali, i metodi parziali consentono di usare il codice creato da un generatore di codice con il codice creato da un sviluppatore senza alcun costo in fase di esecuzione.

Una dichiarazione di metodo parziale è costituita da due parti: la definizione e l'implementazione, che possono trovarsi in parti separate di una classe parziale o nella stessa parte. Se non è presente la dichiarazione di implementazione, il compilatore ottimizza la dichiarazione di definizione e tutte le chiamate al metodo.

```csharp
// Definition in file1.cs
partial void onNameChanged();

// Implementation in file2.cs
partial void onNameChanged()
{
  // method body
}
```

- Le dichiarazioni di metodi parziali devono iniziare con la parola chiave contestuale [partial](../../language-reference/keywords/partial-type.md) e il metodo deve restituire [void](../../language-reference/builtin-types/void.md).

- I metodi parziali possono contenere il parametro [in](../../language-reference/keywords/in-parameter-modifier.md) o [ref](../../language-reference/keywords/ref.md) ma non il parametro [out](../../language-reference/keywords/out-parameter-modifier.md).

- I metodi parziali sono implicitamente [private](../../language-reference/keywords/private.md) e pertanto non possono essere [virtual](../../language-reference/keywords/virtual.md).

- I metodi parziali non possono essere [extern](../../language-reference/keywords/extern.md) perché la presenza del corpo determina se è in corso una definizione o un'implementazione.

- I metodi parziali possono contenere modificatori [static](../../language-reference/keywords/static.md) e [unsafe](../../language-reference/keywords/unsafe.md).

- I metodi parziali possono essere generici. I vincoli vengono inseriti nella dichiarazione di definizione del metodo parziale e possono essere ripetuti facoltativamente nella dichiarazione di implementazione. I nomi dei parametri e dei parametri di tipo non devono essere uguali nella dichiarazione di implementazione e in quella di definizione.

- È possibile creare un [delegato](../../language-reference/builtin-types/reference-types.md) di un metodo parziale che è stato definito e implementato, ma non di un metodo parziale che è stato solo definito.

## <a name="c-language-specification"></a>Specifica del linguaggio C#

Per altre informazioni, vedere [Tipi parziali](~/_csharplang/spec/classes.md#partial-types) in [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi](./classes.md)
- [Struct](./structs.md)
- [Interfacce](../interfaces/index.md)
- [partial (tipo)](../../language-reference/keywords/partial-type.md)
