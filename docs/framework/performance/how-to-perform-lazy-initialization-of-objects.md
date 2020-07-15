---
title: "Procedura: eseguire l'inizializzazione lenta di oggetti"
description: Vedere come eseguire l'inizializzazione differita di oggetti usando la classe System. Lazy <T> . L'inizializzazione differita indica che gli oggetti non vengono creati se non sono mai necessari.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lazy initialization in .NET, how to perform
ms.assetid: 8cd68620-dcc3-4f20-8835-c728a6820e71
ms.openlocfilehash: dbee0d8a5c3075ad7429feb92b87a566fdd35454
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309729"
---
# <a name="how-to-perform-lazy-initialization-of-objects"></a>Procedura: eseguire l'inizializzazione lenta di oggetti
La classe <xref:System.Lazy%601?displayProperty=nameWithType> semplifica le operazioni di inizializzazione differita e creazione di istanze di oggetti. L'inizializzazione di oggetti in modalità differita consente di evitare di doverli creare se non sono mai necessari oppure di posticiparne l'inizializzazione fino al primo accesso. Per altre informazioni, vedere [Inizializzazione differita](lazy-initialization.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra come inizializzare un valore con <xref:System.Lazy%601>. Partire dal presupposto che la variabile differita potrebbe non essere necessaria, a seconda che esista altro codice che imposta la variabile `someCondition` su true o false.  
  
```vb  
Dim someCondition As Boolean = False  
  
Sub Main()  
    'Initializing a value with a big computation, computed in parallel  
    Dim _data As Lazy(Of Integer) = New Lazy(Of Integer)(Function()  
                                                             Dim result =  
                                                                 ParallelEnumerable.Range(0, 1000).  
                                                                 Aggregate(Function(x, y)  
                                                                               Return x + y  
                                                                           End Function)  
                                                             Return result  
                                                         End Function)  
  
    '  do work that may or may not set someCondition to True  
    ' ...  
    '  Initialize the data only if needed  
    If someCondition = True Then  
  
        If (_data.Value > 100) Then  
  
            Console.WriteLine("Good data")  
        End If  
    End If  
End Sub  
```  
  
```csharp  
  static bool someCondition = false;
  //Initializing a value with a big computation, computed in parallel  
  Lazy<int> _data = new Lazy<int>(delegate  
  {  
      return ParallelEnumerable.Range(0, 1000).  
          Select(i => Compute(i)).Aggregate((x,y) => x + y);  
  }, LazyExecutionMode.EnsureSingleThreadSafeExecution);  
  
  // Do some work that may or may not set someCondition to true.  
  //  ...  
  // Initialize the data only if necessary  
  if (someCondition)  
  {  
    if (_data.Value > 100)  
      {  
          Console.WriteLine("Good data");  
      }  
  }  
```  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra come usare la classe <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> per inizializzare un tipo visibile solo per l'istanza dell'oggetto corrente nel thread corrente.  
  
 [!code-csharp[CDS#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds2.cs#13)]
 [!code-vb[CDS#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/lazyhowto.vb#13)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.LazyInitializer?displayProperty=nameWithType>
- [Inizializzazione differita](lazy-initialization.md)
