---
title: Utilizzo degli indicizzatori (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: 82de2841a74f58905d3089bb0b320e7501a77045
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="using-indexers-c-programming-guide"></a>Utilizzo degli indicizzatori (Guida per programmatori C#)
Gli indicizzatori sono una convenzione sintattica che consente di creare una [classe](../../../csharp/language-reference/keywords/class.md), uno [struct](../../../csharp/language-reference/keywords/struct.md) o un'[interfaccia](../../../csharp/language-reference/keywords/interface.md) a cui le applicazioni client possono accedere esattamente come a una matrice. Gli indicizzatori sono in genere implementati in tipi il cui scopo principale è incapsulare una raccolta o una matrice interna. Si supponga, ad esempio, di avere una classe denominata TempRecord che rappresenta la temperatura in gradi Farenheit registrata a 10 orari diversi in un periodo di 24 ore. La classe contiene una matrice denominata "temps" di tipo float per rappresentare le temperature e un oggetto <xref:System.DateTime> che rappresenta la data in cui sono state registrate le temperature. Implementando un indicizzatore in questa classe, i client possono accedere alle temperature in un'istanza di TempRecord come `float temp = tr[4]` anziché come `float temp = tr.temps[4]`. La notazione dell'indicizzatore non solo semplifica la sintassi per le applicazioni client, ma rende anche la classe e il relativo scopo più intuitivi per gli altri sviluppatori.  
  
 Per dichiarare un indicizzatore su una classe o uno struct, usare la parola chiave [this](../../../csharp/language-reference/keywords/this.md), come nell'esempio seguente:  
  
```  
public int this[int index]    // Indexer declaration  
{  
    // get and set accessors  
}  
```  
  
## <a name="remarks"></a>Note  
 Il tipo di un indicizzatore e dei relativi parametri deve essere accessibile almeno quanto l'indicizzatore. Per altre informazioni sui livelli di accessibilità, vedere [Modificatori di accesso](../../../csharp/language-reference/keywords/access-modifiers.md).  
  
 Per altre informazioni sull'uso degli indicizzatori con un'interfaccia, vedere [Indicizzatori nelle interfacce](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md).  
  
 La firma di un indicizzatore è costituita dal numero e dai tipi dei relativi parametri formali. Non include il tipo di indicizzatore o i nomi dei parametri formali. Se si dichiarano più indicizzatori nella stessa classe, gli indicizzatori devono avere firme diverse.  
  
 Il valore di un indicizzatore non è classificato come una variabile, pertanto non è possibile passare il valore di un indicizzatore come un parametro [ref](../../../csharp/language-reference/keywords/ref.md) o [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md).  
  
 Per fornire all'indicizzatore un nome utilizzabile da altri linguaggi, usare un attributo `name` nella dichiarazione. Ad esempio:  
  
```  
[System.Runtime.CompilerServices.IndexerName("TheItem")]  
public int this [int index]   // Indexer declaration  
{  
}  
```  
  
 Questo indicizzatore sarà denominato `TheItem`. Se non si specifica l'attributo name, il nome predefinito sarebbe `Item`.  
  
## <a name="example-1"></a>Esempio 1  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene illustrato come dichiarare un campo di matrice privata, `temps`, e un indicizzatore. L'indicizzatore consente l'accesso diretto all'istanza `tempRecord[i]`. In alternativa all'uso dell'indicizzatore, è possibile dichiarare la matrice come un membro [public](../../../csharp/language-reference/keywords/public.md) e accedere direttamente ai relativi membri, `tempRecord.temps[i]`.  
  
 Si noti che quando viene valutato l'accesso di un indicizzatore, ad esempio in un'istruzione `Console.Write`, viene richiamata la funzione di accesso [get](../../../csharp/language-reference/keywords/get.md). Pertanto, se non esiste alcuna funzione di accesso `get`, si verifica un errore in fase di compilazione.  
  
### <a name="code"></a>Codice  
 [!code-csharp[csProgGuideIndexers#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_1.cs)]  
  
## <a name="indexing-using-other-values"></a>Indicizzazione mediante altri valori  
 C# non limita il tipo di indice a integer. Può ad esempio essere utile usare una stringa con un indicizzatore. Un indicizzatore di questo tipo potrebbe essere implementato eseguendo la ricerca della stringa nella raccolta e restituendo il valore appropriato. Poiché è possibile eseguire l'overload delle funzioni di accesso, le versioni con la stringa e il tipo integer possono coesistere.  
  
## <a name="example-2"></a>Esempio 2  
  
### <a name="description"></a>Descrizione  
 In questo esempio, viene dichiarata una classe che archivia i giorni della settimana. Viene dichiarata una funzione di accesso `get` che accetta una stringa, il nome di un giorno, e restituisce l'intero corrispondente. Ad esempio, per domenica verrà restituito 0, per lunedì verrà restituito 1 e così via.  
  
### <a name="code"></a>Codice  
 [!code-csharp[csProgGuideIndexers#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-indexers_2.cs)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Esistono due modi principali per migliorare la sicurezza e l'affidabilità degli indicizzatori:  
  
-   Assicurarsi di incorporare qualche tipo di strategia di gestione degli errori per gestire la possibilità che il codice client passi un valore di indice non valido. Nel primo esempio riportato in questo argomento, la classe TempRecord fornisce una proprietà Length che consente al codice client di verificare l'input prima di passarlo all'indicizzatore. È anche possibile inserire il codice di gestione degli errori nell'indicizzatore stesso. Assicurarsi di documentare per gli utenti qualsiasi eccezione generata all'interno di una funzione di accesso dell'indicizzatore.  
  
-   Impostare l'accessibilità delle funzioni di accesso `get` e [set](../../../csharp/language-reference/keywords/set.md) in modo che siano quanto più restrittive possibile. Questo è particolarmente importante per la funzione di accesso `set`. Per altre informazioni, vedere [Limitazione dell'accessibilità delle funzioni di accesso](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Indicizzatori](../../../csharp/programming-guide/indexers/index.md)  
 [Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md)
