---
title: Modificatore del parametro out - Riferimenti per C#
ms.date: 03/19/2020
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: c713aa929673e51e8e9986c536bae782121c7756
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249344"
---
# <a name="out-parameter-modifier-c-reference"></a>Modificatore del parametro out (Riferimenti per C#)
La parola chiave `out` fa sì che gli argomenti vengono passati per riferimento. Imposta il parametro formale come alias dell'argomento, che deve essere una variabile. In altre parole, qualsiasi operazione sul parametro viene eseguita sull'argomento. È come la parola chiave [ref](ref.md), con la differenza che `ref` richiede l'inizializzazione della variabile prima di essere passato. È anche come la parola chiave [in](in-parameter-modifier.md), con la differenza che `in` non consente al metodo chiamato di modificare il valore dell'argomento. Per usare un parametro `out`, la definizione del metodo e il metodo chiamante devono usare in modo esplicito la parola chiave `out`. Ad esempio:  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE]
> La parola chiave `out` può essere usata anche con un parametro di tipo generico per specificare che il parametro tipo è covariante. Per altre informazioni sull'uso della parola chiave `out` in questo contesto, vedere [out (Modificatore generico)](out-generic-modifier.md).
  
Le variabili passate come argomenti `out` non devono essere inizializzate prima di essere passate in una chiamata al metodo. È necessario tuttavia che il metodo chiamato assegni un valore prima della restituzione del metodo.  
  
Le parole chiave `in`, `ref` e `out` non sono considerate parte della firma del metodo ai fini della risoluzione dell'overload. Non è quindi possibile eseguirne l'overload se l'unica differenza è che un metodo accetta un argomento `ref` o `in` e l'altro un argomento `out`. Il codice seguente, ad esempio, non verrà compilato:  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
L'overload è consentito, tuttavia, se un metodo accetta un argomento `ref`, `in` o `out` e l'altro non ha alcuno di questi modificatori, come illustrato di seguito:  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

Il compilatore sceglie il miglior overload creando una corrispondenza tra i modificatori di parametro nel sito di chiamata e i modificatori di parametro utilizzati nella chiamata al metodo.

Le proprietà non sono variabili e quindi non possono essere passate come parametri `out`.
  
Non è possibile usare le parole chiave `in`, `ref` e `out` per i seguenti tipi di metodi:  
  
- Metodi asincroni definiti usando il modificatore [async](./async.md).  
  
- Metodi iteratori che includono un'istruzione [yield return](./yield.md) o `yield break`.  

Inoltre, i metodi di [estensione](../../programming-guide/classes-and-structs/extension-methods.md) hanno le seguenti restrizioni:

- Il `out` keywoard non può essere utilizzato sul primo argomento di un metodo di estensione.
- La `ref` parola chiave non può essere utilizzata sul primo argomento di un metodo di estensione quando l'argomento non è uno struct o un tipo generico non vincolato a essere uno struct.
- La `in` parola chiave non può essere utilizzata a meno che il primo argomento non sia uno struct. La `in` parola chiave non può essere utilizzata su qualsiasi tipo generico, anche quando vincolata a essere uno struct.

## <a name="declaring-out-parameters"></a>Dichiarazione di parametri `out`

La dichiarazione di un metodo con argomenti `out` è un classico espediente per restituire più valori. A partire da C# 7.0 è possibile usare le [tuple](../../tuples.md) per scenari analoghi. Nell'esempio seguente viene usato `out` per restituire tre variabili con una sola chiamata al metodo. Notare che il terzo argomento è assegnato a null. In questo modo i metodi restituiscono i valori facoltativamente.  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

## <a name="calling-a-method-with-an-out-argument"></a>Chiamata a un metodo con un argomento `out`

In C# 6 e nelle versioni precedenti è necessario dichiarare una variabile in un'istruzione separata prima di passarla come argomento `out`. L'esempio seguente dichiara una variabile denominata `number` prima che venga passata al metodo [Int32.TryParse3](xref:System.Int32.TryParse(System.String,System.Int32@)), che tenta di convertire una stringa in numero.

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

A partire da C# 7.0, è possibile dichiarare la variabile `out` nell'elenco degli argomenti della chiamata al metodo anziché in una dichiarazione di variabile separata. Il codice prodotto risulta più compatto e leggibile e viene impedita l'assegnazione accidentale di un valore alla variabile prima della chiamata al metodo. L'esempio seguente è uguale all'esempio precedente, ad eccezione del fatto che definisce la variabile `number` nella chiamata al metodo [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  

Nell'esempio precedente la variabile `number` è fortemente tipizzata come `int`. È anche possibile dichiarare una variabile locale tipizzata in modo implicito, come avviene nell'esempio seguente.

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  

## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida di riferimento a C](../index.md)
- [Guida alla programmazione in C](../../programming-guide/index.md)
- [Parole chiave di C](./index.md)
- [Parametri di metodo](./method-parameters.md)
