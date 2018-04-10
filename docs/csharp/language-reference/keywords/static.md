---
title: static (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c47f4a19843039c27ef9f1602581d1004fb8fd76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="static-c-reference"></a>static (Riferimenti per C#)
Usare il modificatore `static` per dichiarare un membro statico, che appartiene allo stesso tipo invece che a un oggetto specifico. Il modificatore `static` può essere usato con classi, campi, metodi, proprietà, operatori, eventi e costruttori, ma non con indicizzatori, finalizzatori o tipi diversi da classi. Per altre informazioni, vedere [Classi statiche e membri di classi statiche](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
## <a name="example"></a>Esempio  
 La classe seguente viene dichiarata come `static` e contiene solo metodi `static`:  
  
 [!code-csharp[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]  
  
 Una costante o una dichiarazione di tipo è implicitamente un membro statico.  
  
 Non è possibile fare riferimento a un membro statico tramite un'istanza. Al contrario, è possibile farvi riferimento tramite il nome del tipo. Si consideri ad esempio la classe seguente:  
  
 [!code-csharp[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]  
  
 Per fare riferimento al membro statico `x`, usare il nome completo `MyBaseC.MyStruct.x`, a meno che il membro non è accessibile dallo stesso ambito:  
  
```csharp  
Console.WriteLine(MyBaseC.MyStruct.x);  
```  
  
 Quando un'istanza di una classe contiene una copia separata di tutti i campi istanza della classe, è disponibile solo una copia di ogni campo statico.  
  
 Non è possibile usare [questo](../../../csharp/language-reference/keywords/this.md) per fare riferimento a funzioni di accesso di proprietà o metodi statici.  
  
 Se la parola chiave `static` viene applicata a una classe, tutti i membri della classe devono essere statici.  
  
 Le classi e le classi statiche possono disporre di costruttori statici. I costruttori statici vengono chiamati in un determinato momento tra l'avvio del programma e la creazione di un'istanza della classe.  
  
> [!NOTE]
>  La parola chiave `static` ha un uso più limitato rispetto a C++. Per un confronto con la parola chiave di C++, vedere [Classi di archiviazione (C++)](/cpp/cpp/storage-classes-cpp#static).
  
 Per illustrare i membri statici, si consideri una classe che rappresenta un dipendente della società. Si supponga che la classe contenga un metodo di conteggio dei dipendenti e un campo per memorizzare il numero dei dipendenti. Il metodo e il campo non appartengono a nessun dipendente dell'istanza. Appartengono invece alla classe aziendale. Pertanto, devono essere dichiarati come membri statici della classe.  
  
## <a name="example"></a>Esempio  
 Questo esempio legge il nome e l'ID di un nuovo dipendente, il contatore dipendente viene incrementato di uno e vengono visualizzate le informazioni per il nuovo dipendente e il nuovo numero di dipendenti. Per semplicità, questo programma legge il numero corrente di dipendenti dalla tastiera. In un'applicazione reale, queste informazioni devono essere lette da un file.  
  
 [!code-csharp[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]  
  
## <a name="example"></a>Esempio  
 Questo esempio mostra che anche se è possibile inizializzare un campo statico con un altro campo statico non ancora dichiarato, i risultati non saranno definiti fino a quando non si assegna in modo esplicito un valore al campo statico.  
  
 [!code-csharp[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../../../csharp/language-reference/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Parole chiave di C#](../../../csharp/language-reference/keywords/index.md)  
 [Modificatori](../../../csharp/language-reference/keywords/modifiers.md)  
 [Classi statiche e membri di classi statiche](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
