---
title: Utilizzo della classe StringBuilder in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Remove method
- strings [.NET Framework], capacities
- StringBuilder object
- Replace method
- AppendFormat method
- Append method
- Insert method
- strings [.NET Framework], StringBuilder object
ms.assetid: 5c14867c-9a99-45bc-ae7f-2686700d377a
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3a6c8f6dee9f2a1da6ed4a8219c1b4832464d9aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-stringbuilder-class-in-net"></a>Utilizzo della classe StringBuilder in .NET
Il <xref:System.String> oggetto non è modificabile. Ogni volta che si utilizza uno dei metodi di <xref:System.String?displayProperty=nameWithType> (classe), si crea un nuovo oggetto stringa in memoria, che richiede una nuova allocazione di spazio per il nuovo oggetto. In situazioni in cui è necessario modificare ripetutamente una stringa, il sovraccarico associato alla creazione di un nuovo <xref:System.String> oggetto può essere costoso. La <xref:System.Text.StringBuilder?displayProperty=nameWithType> classe può essere utilizzata quando si desidera modificare una stringa senza creare un nuovo oggetto. Ad esempio, usando la <xref:System.Text.StringBuilder> classe può migliorare le prestazioni quando si concatenano più stringhe in un ciclo.  
  
## <a name="importing-the-systemtext-namespace"></a>Importazione dello spazio dei nomi System.Type  
 Il <xref:System.Text.StringBuilder> classe è stata trovata nel <xref:System.Text> dello spazio dei nomi.  Per evitare di specificare un nome completo del tipo nel codice, è possibile importare il <xref:System.Text> dello spazio dei nomi:  
  
 [!code-cpp[Conceptual.StringBuilder#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#11)]
 [!code-csharp[Conceptual.StringBuilder#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#11)]
 [!code-vb[Conceptual.StringBuilder#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#11)]  
  
## <a name="instantiating-a-stringbuilder-object"></a>Creazione di un'istanza di un oggetto StringBuilder  
 È possibile creare una nuova istanza di <xref:System.Text.StringBuilder> classe inizializzando la variabile con uno dei metodi del costruttore di overload, come illustrato nell'esempio seguente.  
  
 [!code-cpp[Conceptual.StringBuilder#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#1)]
 [!code-csharp[Conceptual.StringBuilder#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#1)]
 [!code-vb[Conceptual.StringBuilder#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#1)]  
  
## <a name="setting-the-capacity-and-length"></a>Impostazione di capacità e lunghezza  
 Sebbene il <xref:System.Text.StringBuilder> è un oggetto dinamico che consente di espandere il numero di caratteri nella stringa incapsulata, è possibile specificare un valore per il numero massimo di caratteri che può contenere. Questo valore è la capacità dell'oggetto e non deve essere confuso con la lunghezza della stringa che corrente <xref:System.Text.StringBuilder> contiene. Ad esempio, è possibile creare una nuova istanza di <xref:System.Text.StringBuilder> classe con la stringa "Hello", che ha una lunghezza pari a 5 e si può specificare che l'oggetto ha una capacità massima di 25. Quando si modifica il <xref:System.Text.StringBuilder>, non le sue dimensioni stesso fino a quando non viene raggiunta la capacità. In questo caso, il nuovo spazio viene allocato automaticamente e la capacità viene raddoppiata. È possibile specificare la capacità del <xref:System.Text.StringBuilder> classe utilizzando uno dei costruttori di overload. L'esempio seguente specifica che l'oggetto `MyStringBuilder` può essere espanso fino a un massimo di 25 spazi.  
  
 [!code-cpp[Conceptual.StringBuilder#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#2)]
 [!code-csharp[Conceptual.StringBuilder#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#2)]
 [!code-vb[Conceptual.StringBuilder#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#2)]  
  
 Inoltre, è possibile utilizzare la lettura/scrittura <xref:System.Text.StringBuilder.Capacity%2A> proprietà per impostare la lunghezza massima dell'oggetto. L'esempio seguente usa la proprietà **Capacity** per definire la lunghezza massima dell'oggetto.  
  
 [!code-cpp[Conceptual.StringBuilder#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#3)]
 [!code-csharp[Conceptual.StringBuilder#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#3)]
 [!code-vb[Conceptual.StringBuilder#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#3)]  
  
 Il <xref:System.Text.StringBuilder.EnsureCapacity%2A> metodo può essere utilizzato per verificare la capacità dell'oggetto corrente **StringBuilder**. Se la capacità è maggiore del valore passato, non vengono apportate modifiche. Invece, se la capacità è minore del valore passato, la capacità corrente viene modificata in modo che corrisponda al valore passato.  
  
 Il <xref:System.Text.StringBuilder.Length%2A> proprietà può essere visualizzata o impostata. Se si imposta la proprietà **Length** su un valore maggiore della proprietà **Capacity**, la proprietà **Capacity** viene impostata automaticamente sullo stesso valore della proprietà **Length**. L'impostazione della proprietà **Length** su un valore minore della lunghezza della stringa all'interno dell'oggetto **StringBuilder** corrente consente di abbreviare la stringa.  
  
## <a name="modifying-the-stringbuilder-string"></a>Modifica della stringa StringBuilder  
 La tabella seguente elenca i metodi che è possibile usare per modificare il contenuto di **StringBuilder**.  
  
|Nome metodo|Uso|  
|-----------------|---------|  
|<xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>|Aggiunge informazioni alla fine dell'oggetto **StringBuilder** corrente.|  
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|Sostituisce un identificatore di formato passato in una stringa con il testo formattato.|  
|<xref:System.Text.StringBuilder.Insert%2A?displayProperty=nameWithType>|Inserisce una stringa o un oggetto nell'indice specificato dell'oggetto **StringBuilder** corrente.|  
|<xref:System.Text.StringBuilder.Remove%2A?displayProperty=nameWithType>|Rimuove un numero specificato di caratteri dall'oggetto **StringBuilder** corrente.|  
|<xref:System.Text.StringBuilder.Replace%2A?displayProperty=nameWithType>|Sostituisce un determinato carattere nell'indice specificato.|  
  
### <a name="append"></a>Aggiungi  
 Il **Append** metodo può essere utilizzato per aggiungere testo o una rappresentazione di stringa di un oggetto alla fine di una stringa rappresentata dall'oggetto corrente **StringBuilder**. Nell'esempio seguente viene inizializzato un oggetto **StringBuilder** su "Hello World" e quindi viene aggiunto il testo alla fine dell'oggetto. Lo spazio viene allocato automaticamente in base alle esigenze.  
  
 [!code-cpp[Conceptual.StringBuilder#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#4)]
 [!code-csharp[Conceptual.StringBuilder#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#4)]
 [!code-vb[Conceptual.StringBuilder#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#4)]  
  
### <a name="appendformat"></a>AppendFormat  
 Il <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType> aggiunge il testo alla fine del metodo di <xref:System.Text.StringBuilder> oggetto. Supporta la funzionalità di formattazione composita (per ulteriori informazioni, vedere [formattazione composita](../../../docs/standard/base-types/composite-formatting.md)) chiamando il <xref:System.IFormattable> implementazione dell'oggetto o gli oggetti da formattare. Pertanto, accetta le stringhe di formato standard per i valori numerici, di data e ora e di enumerazione, le stringhe di formato personalizzato per i valori numerici e di data e ora e le stringhe di formato definite per i tipi personalizzati. Per informazioni sulla formattazione, vedere [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md)). È possibile utilizzare questo metodo per personalizzare il formato delle variabili e aggiungere tali valori a un <xref:System.Text.StringBuilder>. L'esempio seguente usa il <xref:System.Text.StringBuilder.AppendFormat%2A> metodo per inserire un valore integer formattato come un valore di valuta alla fine di un <xref:System.Text.StringBuilder> oggetto.  
  
 [!code-cpp[Conceptual.StringBuilder#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#5)]
 [!code-csharp[Conceptual.StringBuilder#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#5)]
 [!code-vb[Conceptual.StringBuilder#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#5)]  
  
### <a name="insert"></a>INS  
 Il <xref:System.Text.StringBuilder.Insert%2A> metodo aggiunge una stringa o un oggetto in una posizione specificata nell'oggetto <xref:System.Text.StringBuilder> oggetto. L'esempio seguente usa questo metodo per inserire una parola nella sesta posizione di un <xref:System.Text.StringBuilder> oggetto.  
  
 [!code-cpp[Conceptual.StringBuilder#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#6)]
 [!code-csharp[Conceptual.StringBuilder#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#6)]
 [!code-vb[Conceptual.StringBuilder#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#6)]  
  
### <a name="remove"></a>Rimuovi  
 È possibile utilizzare il **rimuovere** metodo per rimuovere un numero specificato di caratteri dall'oggetto corrente <xref:System.Text.StringBuilder> oggetto, a partire dall'indice in base zero specificato. L'esempio seguente usa il **rimuovere** metodo per abbreviare un <xref:System.Text.StringBuilder> oggetto.  
  
 [!code-cpp[Conceptual.StringBuilder#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#7)]
 [!code-csharp[Conceptual.StringBuilder#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#7)]
 [!code-vb[Conceptual.StringBuilder#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#7)]  
  
### <a name="replace"></a>Sostituisci  
 Il **sostituire** metodo può essere utilizzato per sostituire i caratteri all'interno di <xref:System.Text.StringBuilder> oggetto con un altro carattere specificato. L'esempio seguente usa il **sostituire** metodo per cercare un <xref:System.Text.StringBuilder> dell'oggetto per tutte le istanze del punto esclamativo (!) di caratteri e sostituirli con il carattere punto interrogativo (?).  
  
 [!code-cpp[Conceptual.StringBuilder#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#8)]
 [!code-csharp[Conceptual.StringBuilder#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#8)]
 [!code-vb[Conceptual.StringBuilder#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#8)]  
  
## <a name="converting-a-stringbuilder-object-to-a-string"></a>Conversione di un oggetto StringBuilder in una stringa  
 È necessario convertire il <xref:System.Text.StringBuilder> l'oggetto in un <xref:System.String> oggetto prima di poter passare la stringa rappresentata dal <xref:System.Text.StringBuilder> oggetto a un metodo che presenta un <xref:System.String> parametro o per visualizzarlo nell'interfaccia utente. Eseguire questa conversione chiamando il <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> metodo. Nell'esempio seguente chiama un numero di <xref:System.Text.StringBuilder> metodi e quindi chiama il <xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType> metodo per visualizzare la stringa.  
  
 [!code-csharp[Conceptual.StringBuilder#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/tostringexample1.cs#10)]
 [!code-vb[Conceptual.StringBuilder#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/tostringexample1.vb#10)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Text.StringBuilder?displayProperty=nameWithType>  
 [Operazioni di base su stringhe](../../../docs/standard/base-types/basic-string-operations.md)  
 [Formattazione di tipi](../../../docs/standard/base-types/formatting-types.md)
