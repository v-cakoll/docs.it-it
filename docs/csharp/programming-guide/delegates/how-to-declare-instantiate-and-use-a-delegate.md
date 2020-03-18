---
title: Come dichiarare, creare un'istanza e usare un delegato - Guida per programmatori C
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], declaring and instantiating
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
ms.openlocfilehash: 7ac1d736e19c4dcf1c8408db944505c399762778
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712364"
---
# <a name="how-to-declare-instantiate-and-use-a-delegate-c-programming-guide"></a>Come dichiarare, creare un'istanza e usare un delegato (Guida per programmatori C
In C# 1.0 e versioni successive i delegati possono essere dichiarati come illustrato nell'esempio seguente.  
  
 [!code-csharp[csProgGuideDelegates#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#13)]  
  
 [!code-csharp[csProgGuideDelegates#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#14)]  
  
 In C# 2.0 è disponibile un metodo più semplice per scrivere la dichiarazione precedente, come illustrato nell'esempio seguente.  
  
 [!code-csharp[csProgGuideDelegates#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#32)]  
  
 In C# 2.0 e versioni successive, è anche possibile usare un metodo anonimo per dichiarare e inizializzare un [delegato](../../language-reference/builtin-types/reference-types.md), come illustrato nell'esempio seguente.  
  
 [!code-csharp[csProgGuideDelegates#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#15)]  
  
 In C# 3.0 e versioni successive, è inoltre possibile dichiarare i delegati e crearne un'istanza usando un'espressione lambda, come illustrato nell'esempio seguente.  
  
 [!code-csharp[csProgGuideDelegates#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#31)]  
  
 Per ulteriori informazioni, vedere [Espressioni lambda](../statements-expressions-operators/lambda-expressions.md).  
  
 Nell'esempio che segue viene illustrato come dichiarare un delegato, crearne un'istanza e usarlo. La classe `BookDB` incapsula il database di una libreria che gestisce un database di volumi. Espone un metodo, `ProcessPaperbackBooks`, che ricerca tutti i tascabili all'interno del database e chiama un delegato per ognuno di essi. Il tipo `delegate` usato viene denominato `ProcessBookDelegate`. La classe `Test` usa questa classe per stampare i titoli e il prezzo medio dei tascabili.  
  
 L'uso dei delegati consente la separazione ottimale delle funzionalità tra il database della libreria e il codice client. Il codice client non contiene alcuna informazione sulle modalità di archiviazione dei libri o sul meccanismo che consente al codice di individuare i tascabili. Il codice della libreria non contiene alcuna informazione sull'elaborazione effettuata sui tascabili individuati.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideDelegates#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#12)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
  
- Dichiarazione di un delegato.  
  
     L'istruzione seguente dichiara un nuovo tipo di delegato.  
  
     [!code-csharp[csProgGuideDelegates#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#16)]  
  
     Ogni tipo delegato descrive il numero e il tipo degli argomenti e il tipo di valore restituito dai metodi in esso incapsulati. Ogni volta che è necessario un nuovo set di tipi di argomento o un nuovo tipo di valore restituito, è necessario dichiarare un nuovo tipo di delegato.  
  
- Creazione di un'istanza di un delegato.  
  
     Dopo aver dichiarato un tipo delegato, è necessario creare un oggetto delegato e associarlo a un determinato metodo. Nell'esempio precedente questa operazione viene eseguita passando il metodo `PrintTitle` al metodo `ProcessPaperbackBooks`, come illustrato nell'esempio seguente:  
  
     [!code-csharp[csProgGuideDelegates#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#17)]  
  
     In questo modo viene creato un nuovo oggetto delegato associato al metodo [statico](../../language-reference/keywords/static.md)`Test.PrintTitle`. Analogamente, il metodo non statico `AddBookToTotal` dell'oggetto `totaller` viene passato come illustrato nell'esempio seguente:  
  
     [!code-csharp[csProgGuideDelegates#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#18)]  
  
     In entrambi i casi, al metodo `ProcessPaperbackBooks` viene passato un nuovo oggetto delegato.  
  
     Dopo la creazione di un delegato, il metodo ad esso associato non viene mai modificato, poiché gli oggetti delegati non sono modificabili.  
  
- Chiamata a un delegato.  
  
     Una volta creato, un oggetto delegato viene in genere passato a un altro codice che chiamerà il delegato. Per la chiamata di un oggetto delegato viene usato il nome dell'oggetto stesso, seguito dagli argomenti, racchiusi tra parentesi, che devono essere passati al delegato. Di seguito viene riportato un esempio di chiamata a un delegato:  
  
     [!code-csharp[csProgGuideDelegates#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#19)]  
  
     Un delegato può essere chiamato in modo sincrono, come in questo esempio, oppure in modo asincrono usando i metodi `BeginInvoke` e `EndInvoke`.  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Events](../events/index.md)
- [Delegati](./index.md)
