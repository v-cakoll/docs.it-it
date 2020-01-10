---
title: Uso di indicizzatori - Guida per programmatori C#
ms.date: 10/03/2018
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: bf290681395460bec10be45c4eaa1f165e453caf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75702896"
---
# <a name="using-indexers-c-programming-guide"></a>Uso di indicizzatori (Guida per programmatori C#)

Gli indicizzatori sono una convenzione sintattica che consente di creare una [classe](../../language-reference/keywords/class.md), uno [struct](../../language-reference/keywords/struct.md) o un'[interfaccia](../../language-reference/keywords/interface.md) a cui le applicazioni client possono accedere esattamente come a una matrice. Gli indicizzatori sono in genere implementati in tipi il cui scopo principale è incapsulare una raccolta o una matrice interna. Si supponga, ad esempio, una classe `TempRecord` che rappresenta la temperatura in gradi Fahrenheit registrata in 10 momenti diversi in un periodo di 24 ore. La classe contiene una matrice `temps` di tipo `float[]` per archiviare i valori di temperatura. Implementando un indicizzatore in questa classe, i client possono accedere alle temperature in un'istanza `TempRecord` come `float temp = tr[4]` invece che come `float temp = tr.temps[4]`. La notazione dell'indicizzatore non solo semplifica la sintassi per le applicazioni client, ma rende anche la classe e il relativo scopo più intuitivi per gli altri sviluppatori.  
  
Per dichiarare un indicizzatore in una classe o uno struct, usare la parola chiave [this](../../language-reference/keywords/this.md), come nell'esempio seguente:

```csharp
public int this[int index]    // Indexer declaration  
{  
    // get and set accessors  
}  
```

## <a name="remarks"></a>Note

Il tipo di un indicizzatore e dei relativi parametri deve essere accessibile almeno quanto l'indicizzatore. Per altre informazioni sui livelli di accessibilità, vedere [Modificatori di accesso](../../language-reference/keywords/access-modifiers.md).  
  
 Per altre informazioni sull'uso degli indicizzatori con un'interfaccia, vedere [Indicizzatori nelle interfacce](./indexers-in-interfaces.md).  
  
 La firma di un indicizzatore è costituita dal numero e dai tipi dei relativi parametri formali. Non include il tipo di indicizzatore o i nomi dei parametri formali. Se si dichiarano più indicizzatori nella stessa classe, gli indicizzatori devono avere firme diverse.  
  
 Il valore di un indicizzatore non è classificato come una variabile, pertanto non è possibile passare il valore di un indicizzatore come un parametro [ref](../../language-reference/keywords/ref.md) o [out](../../language-reference/keywords/out-parameter-modifier.md).  
  
 Per fornire all'indicizzatore un nome che possa essere usato da altri linguaggi, usare <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, come nell'esempio seguente:  

```csharp
[System.Runtime.CompilerServices.IndexerName("TheItem")]  
public int this[int index]   // Indexer declaration  
{
    // get and set accessors  
}  
```

Questo indicizzatore sarà denominato `TheItem`. Se non si specifica l'attributo name, il nome predefinito sarebbe `Item`.  
  
## <a name="example-1"></a>Esempio 1  
  
Nell'esempio seguente viene illustrato come dichiarare un campo di matrice privata, `temps`, e un indicizzatore. L'indicizzatore consente l'accesso diretto all'istanza `tempRecord[i]`. In alternativa all'uso dell'indicizzatore, è possibile dichiarare la matrice come un membro [public](../../language-reference/keywords/public.md) e accedere direttamente ai relativi membri, `tempRecord.temps[i]`.  
  
 Si noti che quando viene valutato l'accesso di un indicizzatore, ad esempio in un'istruzione `Console.Write`, viene richiamata la funzione di accesso [get](../../language-reference/keywords/get.md). Pertanto, se non esiste alcuna funzione di accesso `get`, si verifica un errore in fase di compilazione.  
  
 [!code-csharp[csProgGuideIndexers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#1)]  
  
## <a name="indexing-using-other-values"></a>Indicizzazione tramite altri valori

C# non limita il tipo del parametro dell'indicizzatore a Integer. Può ad esempio essere utile usare una stringa con un indicizzatore. Un indicizzatore di questo tipo potrebbe essere implementato eseguendo la ricerca della stringa nella raccolta e restituendo il valore appropriato. Poiché è possibile eseguire l'overload delle funzioni di accesso, le versioni con la stringa e il tipo integer possono coesistere.  
  
## <a name="example-2"></a>Esempio 2  
  
L'esempio seguente dichiara una classe che archivia i giorni della settimana. Una funzione di accesso `get` accetta una stringa e il nome di un giorno e restituisce l'intero corrispondente. Ad esempio, "Domenica" restituisce 0, "Lunedì" restituisce 1 e così via.  
  
 [!code-csharp[csProgGuideIndexers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#2)]  
  
## <a name="robust-programming"></a>Programmazione efficiente

 Esistono due modi principali per migliorare la sicurezza e l'affidabilità degli indicizzatori:  
  
- Assicurarsi di incorporare qualche tipo di strategia di gestione degli errori per gestire la possibilità che il codice client passi un valore di indice non valido. Nel primo esempio riportato in questo argomento, la classe TempRecord fornisce una proprietà Length che consente al codice client di verificare l'input prima di passarlo all'indicizzatore. È anche possibile inserire il codice di gestione degli errori nell'indicizzatore stesso. Assicurarsi di documentare per gli utenti qualsiasi eccezione generata all'interno di una funzione di accesso dell'indicizzatore.  
  
- Impostare l'accessibilità delle funzioni di accesso [get](../../language-reference/keywords/get.md) e [set](../../language-reference/keywords/set.md) in modo che siano quanto più restrittive possibile. Questo è particolarmente importante per la funzione di accesso `set`. Per altre informazioni, vedere [Limitazione dell'accessibilità delle funzioni di accesso](../classes-and-structs/restricting-accessor-accessibility.md).  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Indicizzatori](./index.md)
- [Proprietà](../classes-and-structs/properties.md)
