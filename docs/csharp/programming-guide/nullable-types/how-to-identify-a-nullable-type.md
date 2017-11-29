---
title: 'Procedura: identificare un tipo nullable (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
caps.latest.revision: "7"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 610ed18308df02c5632361cd09ef94330dea598b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a>Procedura: identificare un tipo nullable (Guida per programmatori C#)
È possibile usare l'operatore [typeof](../../../csharp/language-reference/keywords/typeof.md) C# per creare un oggetto <xref:System.Type> che rappresenta un tipo nullable:  
  
```  
System.Type type = typeof(int?);  
```  
  
 È anche possibile usare le classi e i metodi dello spazio dei nomi <xref:System.Reflection> per generare oggetti <xref:System.Type> che rappresentano tipi nullable. Se tuttavia si prova a ottenere informazioni sul tipo dalle variabili nullable in fase di esecuzione usando il metodo <xref:System.Object.GetType%2A> o l'operatore `is`, il risultato è un oggetto <xref:System.Type> che rappresenta il tipo sottostante, non il tipo nullable stesso.  
  
 La chiamata di `GetType` su un tipo nullable causa l'esecuzione di un'operazione di conversione boxing quando il tipo viene convertito implicitamente in <xref:System.Object>. Pertanto, <xref:System.Object.GetType%2A> restituisce sempre un oggetto <xref:System.Type> che rappresenta il tipo sottostante, non il tipo nullable.  
  
```  
int? i = 5;  
Type t = i.GetType();  
Console.WriteLine(t.FullName); //"System.Int32"  
```  
  
 L'operatore C# [is](../../../csharp/language-reference/keywords/is.md) funziona anche sul tipo sottostante di un tipo nullable. Non è quindi possibile usare `is` per determinare se una variabile è un tipo nullable. L'esempio seguente mostra che l'operatore `is` tratta una variabile Nullable\<int> come tipo int.  
  
```  
static void Main(string[] args)  
{  
  int? i = 5;  
  if (i is int) // true  
    //…  
}  
```  
  
## <a name="example"></a>Esempio  
 Usare il codice seguente per determinare se un oggetto <xref:System.Type> rappresenta un tipo nullable. Tenere presente che questo codice restituisce sempre false se l'oggetto `Type` è stato restituito da una chiamata a <xref:System.Object.GetType%2A>, come illustrato in precedenza in questo argomento.  
  
```  
if (type.IsGenericType && type.GetGenericTypeDefinition() == typeof(Nullable<>)) {…}  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md)  
 [Conversione boxing dei tipi nullable](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)
