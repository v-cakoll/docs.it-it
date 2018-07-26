---
title: Operatore new (Riferimenti per C#)
ms.date: 03/15/2018
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 2ba3c574897ae5f1ec66e3810e23f0af74bd8872
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39243947"
---
# <a name="new-operator-c-reference"></a>Operatore new (Riferimenti per C#)
Usato per creare oggetti e richiamare costruttori. Ad esempio:  
  
```csharp
Class1 obj  = new Class1();  
```  
  
 Viene usato anche per creare istanze di tipi anonimi:  
  
```csharp
var query = from cust in customers  
            select new { Name = cust.Name, Address = cust.PrimaryAddress };  
```  
  
 L'operatore `new` viene usato anche per richiamare il costruttore predefinito per i tipi di valore. Ad esempio:  
  
```csharp
int i = new int();  
```  
  
 Nell'istruzione precedente `i` viene inizializzato in `0`, ovvero il valore predefinito per il tipo `int`. L'istruzione ha lo stesso effetto dell'istruzione seguente:  
  
```csharp
int i = 0;  
```  
  
 Per un elenco completo dei valori predefiniti, vedere [Tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).  
  
 È utile ricordare che è errato dichiarare un costruttore predefinito per uno [struct](../../../csharp/language-reference/keywords/struct.md) poiché ogni tipo di valore ha implicitamente un costruttore predefinito pubblico. È possibile dichiarare costruttori con parametri su un tipo struct per impostarne i valori iniziali, ma questa operazione è necessaria solo se sono richiesti valori diversi da quello predefinito.  
  
 Sia gli oggetti di tipo valore come gli struct che gli oggetti di tipo riferimento come le classi vengono eliminati automaticamente, ma gli oggetti di tipo valore vengono eliminati quando viene eliminato il loro contesto contenitore, mentre gli oggetti di tipo riferimento vengono eliminati da Garbage Collector in un momento non specificato dopo la rimozione dell'ultimo riferimento a essi relativo. Per i tipi che contengono risorse come ad esempio gli handle di file o le connessioni di rete, è consigliabile adottare la pulitura deterministica per garantire che le risorse contenute vengano rilasciate nel più breve tempo possibile. Per altre informazioni, vedere [Istruzione using](../../../csharp/language-reference/keywords/using-statement.md).  
  
 Non è possibile sottoporre l'operatore `new` a overload.  
  
 Se l'operatore `new` non riesce ad allocare memoria, genererà l'eccezione <xref:System.OutOfMemoryException>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono creati e inizializzati un oggetto `struct` e un oggetto classe usando l'operatore `new` e vengono quindi assegnati i valori. I valori predefiniti e assegnati sono visualizzati.  
  
 [!code-csharp[csrefKeywordsOperator#7](codesnippet/CSharp/new-operator_1.cs)]  
  
 Si noti che nell'esempio il valore predefinito di una stringa è `null` e, pertanto, non viene visualizzato.  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Parole chiave per gli operatori](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [new](../../../csharp/language-reference/keywords/new.md)  
 [Tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
