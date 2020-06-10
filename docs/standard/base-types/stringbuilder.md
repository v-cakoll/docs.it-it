---
title: Uso della classe StringBuilder in .NET
description: Informazioni su come usare la classe StringBuilder in .NET. Utilizzare questa classe per modificare una stringa senza creare un nuovo oggetto.
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: b10d1c4579f10ca4fb84797ee67342825aaa9c32
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662940"
---
# <a name="using-the-stringbuilder-class-in-net"></a>Uso della classe StringBuilder in .NET
L'oggetto <xref:System.String> non è modificabile. Ogni volta che si usa uno dei metodi nella classe <xref:System.String?displayProperty=nameWithType>, si crea un nuovo oggetto stringa in memoria che richiede una nuova allocazione di spazio. In situazioni in cui è necessario modificare ripetutamente una stringa, il sovraccarico associato alla creazione di un nuovo oggetto <xref:System.String> può essere dispendioso. La classe <xref:System.Text.StringBuilder?displayProperty=nameWithType> può essere usata per modificare una stringa senza creare un nuovo oggetto. Ad esempio, l'uso della classe <xref:System.Text.StringBuilder> può migliorare le prestazioni quando si concatenano più stringhe in un ciclo.  
  
## <a name="importing-the-systemtext-namespace"></a>Importazione dello spazio dei nomi System.Type  
 La classe <xref:System.Text.StringBuilder> si trova nello spazio dei nomi <xref:System.Text>.  Per evitare di specificare il nome di tipo completo nel codice, è possibile importare lo spazio dei nomi <xref:System.Text>:  
  
 [!code-cpp[Conceptual.StringBuilder#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#11)]
 [!code-csharp[Conceptual.StringBuilder#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#11)]
 [!code-vb[Conceptual.StringBuilder#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#11)]  
  
## <a name="instantiating-a-stringbuilder-object"></a>Creazione di un'istanza di un oggetto StringBuilder  
 È possibile creare una nuova istanza della classe <xref:System.Text.StringBuilder> inizializzando la variabile con uno dei metodi del costruttore di overload, come illustrato nell'esempio seguente.  
  
 [!code-cpp[Conceptual.StringBuilder#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#1)]
 [!code-csharp[Conceptual.StringBuilder#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#1)]
 [!code-vb[Conceptual.StringBuilder#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#1)]  
  
## <a name="setting-the-capacity-and-length"></a>Impostazione di capacità e lunghezza  
 Anche se <xref:System.Text.StringBuilder> è un oggetto dinamico che consente di espandere il numero di caratteri nella stringa incapsulata, è possibile specificare un valore per il numero massimo di caratteri che può contenere. Questo valore rappresenta la capacità dell'oggetto e non deve essere confuso con la lunghezza della stringa contenuta dall'oggetto <xref:System.Text.StringBuilder>. Ad esempio, è possibile creare una nuova istanza della classe <xref:System.Text.StringBuilder> con la stringa "Hello", che ha una lunghezza pari a 5 caratteri, e specificare che l'oggetto ha una capacità massima di 25 caratteri. Quando si modifica la classe <xref:System.Text.StringBuilder>, le dimensioni non vengono riallocate automaticamente fino a quando non viene raggiunta la capacità specificata. In questo caso, il nuovo spazio viene allocato automaticamente e la capacità viene raddoppiata. È possibile specificare la capacità della classe <xref:System.Text.StringBuilder> usando uno dei costruttori di overload. L'esempio seguente specifica che l'oggetto `myStringBuilder` può essere espanso fino a un massimo di 25 spazi.  
  
 [!code-cpp[Conceptual.StringBuilder#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#2)]
 [!code-csharp[Conceptual.StringBuilder#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#2)]
 [!code-vb[Conceptual.StringBuilder#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#2)]  
  
 Inoltre, è possibile usare la proprietà <xref:System.Text.StringBuilder.Capacity%2A> di lettura/scrittura per impostare la lunghezza massima dell'oggetto. L'esempio seguente usa la proprietà **Capacity** per definire la lunghezza massima dell'oggetto.  
  
 [!code-cpp[Conceptual.StringBuilder#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#3)]
 [!code-csharp[Conceptual.StringBuilder#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#3)]
 [!code-vb[Conceptual.StringBuilder#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#3)]  
  
 Il metodo <xref:System.Text.StringBuilder.EnsureCapacity%2A> può essere usato per verificare la capacità dell'oggetto **StringBuilder** corrente. Se la capacità è maggiore del valore passato, non vengono apportate modifiche. Invece, se la capacità è minore del valore passato, la capacità corrente viene modificata in modo che corrisponda al valore passato.  
  
 La proprietà <xref:System.Text.StringBuilder.Length%2A> può essere anche visualizzata o impostata. Se si imposta la proprietà **Length** su un valore maggiore della proprietà **Capacity**, la proprietà **Capacity** viene impostata automaticamente sullo stesso valore della proprietà **Length**. L'impostazione della proprietà **Length** su un valore minore della lunghezza della stringa all'interno dell'oggetto **StringBuilder** corrente consente di abbreviare la stringa.  
  
## <a name="modifying-the-stringbuilder-string"></a>Modifica della stringa StringBuilder  
 La tabella seguente elenca i metodi che è possibile usare per modificare il contenuto di **StringBuilder**.  
  
|Nome metodo|Uso|  
|-----------------|---------|  
|<xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>|Aggiunge informazioni alla fine dell'oggetto **StringBuilder** corrente.|  
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|Sostituisce un identificatore di formato passato in una stringa con il testo formattato.|  
|<xref:System.Text.StringBuilder.Insert%2A?displayProperty=nameWithType>|Inserisce una stringa o un oggetto nell'indice specificato dell'oggetto **StringBuilder** corrente.|  
|<xref:System.Text.StringBuilder.Remove%2A?displayProperty=nameWithType>|Rimuove un numero specificato di caratteri dall'oggetto **StringBuilder** corrente.|  
|<xref:System.Text.StringBuilder.Replace%2A?displayProperty=nameWithType>|Sostituisce un determinato carattere nell'indice specificato.|  
  
### <a name="append"></a>Accoda  
 Il metodo **Append** può essere usato per aggiungere testo o una rappresentazione di stringa di un oggetto alla fine di una stringa rappresentata dall'oggetto **StringBuilder** corrente. Nell'esempio seguente viene inizializzato un oggetto **StringBuilder** su "Hello World" e quindi viene aggiunto il testo alla fine dell'oggetto. Lo spazio viene allocato automaticamente in base alle esigenze.  
  
 [!code-cpp[Conceptual.StringBuilder#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#4)]
 [!code-csharp[Conceptual.StringBuilder#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#4)]
 [!code-vb[Conceptual.StringBuilder#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#4)]  
  
### <a name="appendformat"></a>AppendFormat  
 Il metodo <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType> aggiunge il testo alla fine dell'oggetto <xref:System.Text.StringBuilder>. Supporta la funzionalità di formattazione composita (per altre informazioni, vedere [Formattazione composita](composite-formatting.md)) chiamando l'implementazione <xref:System.IFormattable> dell'oggetto o degli oggetti da formattare. Pertanto, accetta le stringhe di formato standard per i valori numerici, di data e ora e di enumerazione, le stringhe di formato personalizzato per i valori numerici e di data e ora e le stringhe di formato definite per i tipi personalizzati. Per informazioni sulla formattazione, vedere [formattazione dei tipi](formatting-types.md). È possibile usare questo metodo per personalizzare il formato delle variabili e aggiungere tali valori a un oggetto <xref:System.Text.StringBuilder> . L'esempio seguente usa il metodo <xref:System.Text.StringBuilder.AppendFormat%2A> per inserire un valore Integer formattato come valore di valuta alla fine di un oggetto <xref:System.Text.StringBuilder>.  
  
 [!code-cpp[Conceptual.StringBuilder#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#5)]
 [!code-csharp[Conceptual.StringBuilder#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#5)]
 [!code-vb[Conceptual.StringBuilder#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#5)]  
  
### <a name="insert"></a>Insert  
 Il metodo <xref:System.Text.StringBuilder.Insert%2A> aggiunge una stringa o un oggetto in una posizione specificata nell'oggetto <xref:System.Text.StringBuilder> corrente. L'esempio seguente usa questo metodo per inserire una parola nella sesta posizione di un oggetto <xref:System.Text.StringBuilder>.  
  
 [!code-cpp[Conceptual.StringBuilder#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#6)]
 [!code-csharp[Conceptual.StringBuilder#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#6)]
 [!code-vb[Conceptual.StringBuilder#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#6)]  
  
### <a name="remove"></a>Remove  
 È possibile usare il metodo **Remove** per rimuovere un numero specificato di caratteri dall'oggetto <xref:System.Text.StringBuilder> corrente, a partire dall'indice in base zero specificato. L'esempio seguente usa il metodo **Remove** per abbreviare un oggetto <xref:System.Text.StringBuilder>.  
  
 [!code-cpp[Conceptual.StringBuilder#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#7)]
 [!code-csharp[Conceptual.StringBuilder#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#7)]
 [!code-vb[Conceptual.StringBuilder#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#7)]  
  
### <a name="replace"></a>Replace  
 Il metodo **Replace** può essere usato per sostituire i caratteri all'interno dell'oggetto <xref:System.Text.StringBuilder> con un altro carattere specificato. L'esempio seguente usa il metodo **Replace** per cercare un oggetto <xref:System.Text.StringBuilder> per tutte le istanze del carattere punto esclamativo (!) e per sostituirle con il carattere punto interrogativo (?).  
  
 [!code-cpp[Conceptual.StringBuilder#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.StringBuilder/cpp/example.cpp#8)]
 [!code-csharp[Conceptual.StringBuilder#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/Example.cs#8)]
 [!code-vb[Conceptual.StringBuilder#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/Example.vb#8)]  
  
## <a name="converting-a-stringbuilder-object-to-a-string"></a>Conversione di un oggetto StringBuilder in una stringa  
 È necessario convertire l'oggetto <xref:System.Text.StringBuilder> in un oggetto <xref:System.String> prima di poter passare la stringa rappresentata dall'oggetto <xref:System.Text.StringBuilder> a un metodo che contiene un parametro <xref:System.String> o per visualizzarlo nell'interfaccia utente. Per eseguire la conversione, chiamare il metodo <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType>. Nell'esempio seguente vengono chiamati diversi metodi <xref:System.Text.StringBuilder> e quindi viene chiamato il metodo <xref:System.Text.StringBuilder.ToString?displayProperty=nameWithType> per visualizzare la stringa.  
  
 [!code-csharp[Conceptual.StringBuilder#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/tostringexample1.cs#10)]
 [!code-vb[Conceptual.StringBuilder#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/tostringexample1.vb#10)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Text.StringBuilder?displayProperty=nameWithType>
- [Operazioni di base sulle stringhe](basic-string-operations.md)
- [Formattazione di tipi](formatting-types.md)
