---
title: Operatore new (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3c2b484b9872a54ce42520de77a723b9edb441a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="new-operator-c-reference"></a>Operatore new (Riferimenti per C#)
Usato per creare oggetti e richiamare costruttori. Ad esempio:  
  
```  
Class1 obj  = new Class1();  
```  
  
 Viene usato anche per creare istanze di tipi anonimi:  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 L'operatore `new` viene usato anche per richiamare il costruttore predefinito per i tipi di valore. Ad esempio:  
  
```  
int i = new int();  
```  
  
 Nell'istruzione precedente `i` viene inizializzato in `0`, ovvero il valore predefinito per il tipo `int`. L'istruzione ha lo stesso effetto dell'istruzione seguente:  
  
```  
int i = 0;  
```  
  
 Per un elenco completo dei valori predefiniti, vedere [Tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md).  
  
 È utile ricordare che è errato dichiarare un costruttore predefinito per uno [struct](../../../csharp/language-reference/keywords/struct.md) poiché ogni tipo di valore ha implicitamente un costruttore predefinito pubblico. È possibile dichiarare costruttori con parametri su un tipo struct per impostarne i valori iniziali, ma questa operazione è necessaria solo se sono richiesti valori diversi da quello predefinito.  
  
 Gli oggetti di tipo valore, ad esempio gli struct, vengono creati nello stack, mentre gli oggetti di tipo riferimento, ad esempio le classi, vengono creati nell'heap. Entrambi i tipi di oggetti vengono eliminati automaticamente in modo definitivo, mentre gli oggetti basati su tipi di valori vengono eliminati definitivamente quando escono dall'ambito di validità e quelli basati su tipi di riferimento vengono eliminati definitivamente in un momento non specificato dopo che è stato rimosso l'ultimo riferimento ad essi. Per i tipi di riferimento che usano risorse fisse, ad esempio grandi quantità di memoria, handle di file o connessioni di rete, può risultare preferibile adottare la finalizzazione deterministica per assicurarsi che l'oggetto venga eliminato definitivamente prima possibile. Per altre informazioni, vedere [Istruzione using](../../../csharp/language-reference/keywords/using-statement.md).  
  
 Non è possibile sottoporre l'operatore `new` a overload.  
  
 Se l'operatore `new` non riesce ad allocare memoria, genererà l'eccezione <xref:System.OutOfMemoryException>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono creati e inizializzati un oggetto `struct` e un oggetto classe usando l'operatore `new` e vengono quindi assegnati i valori. I valori predefiniti e assegnati sono visualizzati.  
  
 [!code-csharp[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]  
  
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
