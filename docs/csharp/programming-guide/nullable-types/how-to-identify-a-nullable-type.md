---
title: 'Procedura: identificare un tipo nullable (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
caps.latest.revision: 7
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c9e05bfe8be45e5b71a8db06ce4f2502c5397fd4
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

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

