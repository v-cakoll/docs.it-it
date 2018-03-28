---
title: ref (Riferimenti per C#)
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 63f984f4004cfce9694e7e7405ec2477bc370731
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2018
---
# <a name="ref-c-reference"></a>ref (Riferimenti per C#)

La parola chiave `ref` indica un valore che viene passato per riferimento. Viene usata in tre contesti diversi: 

- Nella firma di un metodo e in una chiamata al metodo, per passare un argomento a un metodo per riferimento. Per altre informazioni, vedere [Passaggio di un argomento per riferimento](#passing-an-argument-by-reference).

- Nella firma di un metodo, per restituire un valore al chiamante per riferimento. Per altre informazioni, vedere [Valori restituiti di riferimento](#reference-return-values).

- Nel corpo di un membro, per indicare che un valore restituito di riferimento è archiviato in locale come un riferimento che il chiamante intende modificare o, in generale, che una variabile locale accede a un altro valore per riferimento. Per altre informazioni, vedere [Variabili locali ref](#ref-locals).

## <a name="passing-an-argument-by-reference"></a>Passaggio di un argomento per riferimento

Quando viene usata nell'elenco di parametri di un metodo, la parola chiave `ref` indica che un argomento viene passato per riferimento, non per valore. L'effetto del passaggio per riferimento è che qualsiasi modifica all'argomento nel metodo chiamato viene riflessa nel metodo di chiamata. Ad esempio, se il chiamante passa un'espressione variabile locale o un'espressione di accesso dell'elemento della matrice e il metodo chiamato sostituisce l'oggetto a cui fa riferimento il parametro ref, l'elemento della matrice o la variabile locale del chiamante fa riferimento al nuovo oggetto quando viene restituito il risultato del metodo.

> [!NOTE]
>  Non confondere il concetto di passaggio per riferimento con il concetto di tipi di riferimento. I due concetti non sono uguali. Un parametro di metodo può essere modificato da `ref` che si tratti di un tipo di valore o di un tipo di riferimento. Non viene eseguito il boxing di un tipo di valore quando viene passato per riferimento.  

Per usare un parametro `ref`, la definizione del metodo e il metodo chiamante devono usare in modo esplicito la parola chiave `ref`, come illustrato nell'esempio seguente.  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

Un argomento passato a un parametro `ref` o `in` deve essere inizializzato prima di essere passato. Questo comportamento è diverso dai parametri [out](out-parameter-modifier.md), i cui argomenti non devono essere inizializzati in modo esplicito prima di essere passati.

I membri di una classe non possono avere firme che differiscono solo per `ref`, `in` o `out`. Un errore del compilatore si verifica se l'unica differenza tra due membri di un tipo è che uno di essi ha un parametro `ref` e l'altro ha un parametro `out` o `in`. Il codice seguente, ad esempio, non viene compilato.  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
È tuttavia possibile eseguire l'overload dei metodi quando un metodo ha un parametro `ref`, `in` o `out` e l'altro ha un parametro di valore, come illustrato nell'esempio seguente.
  
[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 In altre situazioni che richiedono la firma corrispondente, ad esempio nascondere o sottoporre a override, `in`, `ref` e `out` fanno parte della firma e non sono corrispondenti tra loro.  
  
 Le proprietà non sono variabili. Sono metodi e non possono essere passate ai parametri `ref`.  
  
 Per informazioni su come passare le matrici, vedere [Passaggio di matrici usando ref e out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 Non è possibile usare le parole chiave `ref`, `in` e `out` per i seguenti tipi di metodi:  
  
- Metodi asincroni definiti usando il modificatore [async](../../../csharp/language-reference/keywords/async.md).  
- Metodi iteratori che includono un'istruzione [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.  

## <a name="passing-an-argument-by-reference-an-example"></a>Passaggio di un argomento per riferimento: un esempio

Negli esempi precedenti vengono passati tipi valore per riferimento. È anche possibile usare la parola chiave `ref` per passare tipi riferimento per riferimento. Il passaggio di un tipo riferimento per riferimento consente al metodo chiamato di sostituire l'oggetto a cui fa riferimento il parametro per riferimento nel chiamante. Il percorso di archiviazione dell'oggetto viene passato al metodo come valore del parametro referenziato. Se si modifica il valore nella posizione di archiviazione del parametro (in modo che punti a un nuovo oggetto), è anche possibile modificare il percorso di archiviazione a cui fa riferimento il chiamante. Nell'esempio seguente viene passata un'istanza di un tipo di riferimento come parametro `ref`.   
  
[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

Per altre informazioni su come passare i tipi di riferimento per valore e per riferimento, vedere [Passaggio di parametri di tipi di riferimento](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).
  
## <a name="reference-return-values"></a>Valori restituiti di riferimento

I valori restituiti di riferimento (o valori restituiti ref) sono i valori che un metodo restituisce per riferimento al chiamante. In altre parole, il chiamante può modificare il valore restituito da un metodo e tale modifica viene riflessa nello stato dell'oggetto che contiene il metodo. 

Un valore restituito di riferimento viene definito mediante la parola chiave `ref`:

- Nella firma del metodo. Ad esempio, la firma del metodo seguente indica che il metodo `GetCurrentPrice` restituisce un valore <xref:System.Decimal> per riferimento.

   ```csharp
   public ref decimal GetCurrentValue()
   ``` 
- Tra il token `return` e la variabile restituita in un'istruzione `return` nel metodo. Ad esempio:
 
   ```csharp
   return ref DecimalArray[0];
   ``` 

Affinché il chiamante modifichi lo stato dell'oggetto, il valore restituito di riferimento deve essere archiviato in una variabile definita in modo esplicito come [variabile locale ref](#ref-locals). 

Per un esempio, vedere [Esempio di valori restituiti e variabili locali ref](#a-ref-returns-and-ref-locals-example)

## <a name="ref-locals"></a>Variabili locali ref

Una variabile locale ref viene usata per fare riferimento ai valori restituiti mediante `return ref`.  Una variabile locale ref deve essere inizializzata e assegnata a un valore restituito ref. Tutte le modifiche apportate al valore della variabile locale ref vengono riflesse nello stato dell'oggetto di cui metodo ha restituito il valore per riferimento.

Per definire una variabile locale ref, usare la parola chiave `ref` prima della dichiarazione di variabile, nonché immediatamente prima della chiamata al metodo che restituisce il valore per riferimento. 

Ad esempio, l'istruzione seguente definisce un valore di variabile locale ref restituito da un metodo denominato `GetEstimatedValue`:

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

È possibile accedere a un valore per riferimento nello stesso modo. In alcuni casi, l'accesso a un valore per riferimento migliora le prestazioni evitando un'operazione di copia potenzialmente dispendiosa. L'istruzione seguente, ad esempio, spiega come sia possibile definire un valore locale di riferimento usato per fare riferimento a un valore.

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

Si noti che nei due esempi la parola chiave `ref` deve essere usata in entrambe le posizioni. In caso contrario, il compilatore genera l'errore CS8172, "Non è possibile inizializzare una variabile per riferimento con un valore". 
 
## <a name="a-ref-returns-and-ref-locals-example"></a>Esempio di valori restituiti e variabili locali ref

Nell'esempio seguente viene definita una classe `Book` che ha due campi <xref:System.String>, `Title` e `Author`. Definisce inoltre una classe `BookCollection` che include una matrice privata di oggetti `Book`. I singoli oggetti book vengono restituiti per riferimento chiamando il relativo metodo `GetBookByTitle`.

[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

Quando il chiamante archivia il valore restituito dal metodo `GetBookByTitle` come una variabile locale ref, le modifiche apportate al valore restituito dal chiamante vengono riflesse nell'oggetto `BookCollection`, come illustrato nell'esempio seguente.

[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Passaggio di parametri](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)  
 [Parametri dei metodi](../../../csharp/language-reference/keywords/method-parameters.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)
