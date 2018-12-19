---
title: dynamic - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- dynamic_CSharpKeyword
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
ms.openlocfilehash: 7ac9c04da277af6a03a6a8994763451146adefc8
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243309"
---
# <a name="dynamic-c-reference"></a>dynamic (Riferimenti per C#)

`dynamic` abilita le operazioni in cui il tipo appare per ignorare il controllo del tipo in fase di compilazione. Queste operazioni vengono risolte in fase di esecuzione. Il tipo `dynamic` semplifica l'accesso alle API COM, ad esempio le API di automazione di Office, e anche ad API dinamiche come le librerie di IronPython e al modello DOM (Document Object Model) HTML.

Il tipo `dynamic` si comporta come tipo `object` nella maggior parte dei casi. Tuttavia, le operazioni che contengono espressioni di tipo `dynamic` non vengono risolte o il tipo non viene verificato dal compilatore. Il compilatore raggruppa le informazioni sull'operazione e tali informazioni successivamente vengono usate per valutare l'operazione in fase di esecuzione. Come parte del processo, le variabili di tipo `dynamic` vengono compilate in variabili di tipo `object`. Di conseguenza, il tipo `dynamic` esiste solo in fase di compilazione, non in fase di esecuzione.

Nell'esempio seguente vengono messe a confronto una variabile di tipo `dynamic` e una variabile di tipo `object`. Per verificare il tipo di ogni variabile in fase di compilazione, posizionare il puntatore del mouse su `dyn` o `obj` nelle istruzioni `WriteLine`. IntelliSense visualizza **dynamic** per `dyn` e **object** per `obj`.

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

Le istruzioni `WriteLine` visualizzano i tipi in fase di esecuzione di `dyn` e `obj`. A questo punto, entrambe hanno lo stesso tipo, un numero intero. Viene generato l'output seguente:

`System.Int32`

`System.Int32`

Per vedere la differenza tra `dyn` e `obj` in fase di compilazione, aggiungere le due righe seguenti tra le dichiarazioni e le istruzioni `WriteLine` dell'esempio precedente.

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 Viene segnalato un errore del compilatore per il tentativo di aggiunta di un numero intero e di un oggetto nell'espressione `obj + 3`. Tuttavia non vengono segnalati errori per `dyn + 3`. L'espressione che contiene `dyn` non viene controllata in fase di compilazione perché il tipo di `dyn` è `dynamic`.

## <a name="context"></a>Contesto

La parola chiave `dynamic` può apparire direttamente o come componente di un tipo costruito nelle situazioni seguenti:

- Nelle dichiarazioni, come tipo di proprietà, campo, indicizzatore, parametro, valore restituito, variabile locale o vincolo di tipo. La definizione di classe seguente usa `dynamic` in molte dichiarazioni diverse.

    [!code-csharp[csrefKeywordsTypes#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#22)]

- Nelle conversioni di tipo esplicito, ad esempio il tipo di destinazione di una conversione.

    [!code-csharp[csrefKeywordsTypes#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#23)]

- In qualsiasi contesto in cui i tipi vengono usati come valori, ad esempio sul lato destro di un operatore `is` o un operatore `as`, o come argomento di `typeof` come parte di un tipo costruito. Ad esempio, `dynamic` può essere usato nelle espressioni seguenti.

    [!code-csharp[csrefKeywordsTypes#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#24)]

## <a name="example"></a>Esempio

Nell'esempio seguente viene usato `dynamic` in diverse dichiarazioni. Il metodo `Main` confronta anche il controllo dei tipi in fase di compilazione con il controllo dei tipi in fase di esecuzione.

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

Per altre informazioni ed esempi, vedere [Uso del tipo dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Dynamic.ExpandoObject?displayProperty=nameWithType>  
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>  
- [Uso del tipo dinamico](../../../csharp/programming-guide/types/using-type-dynamic.md)  
- [object](../../../csharp/language-reference/keywords/object.md)  
- [is](../../../csharp/language-reference/keywords/is.md)  
- [as](../../../csharp/language-reference/keywords/as.md)  
- [typeof](../../../csharp/language-reference/keywords/typeof.md)  
- [Procedura: Eseguire il cast sicuro con i criteri di ricerca e gli operatori as e is](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)  
- [Procedura dettagliata: Creazione e uso di oggetti dinamici](../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
