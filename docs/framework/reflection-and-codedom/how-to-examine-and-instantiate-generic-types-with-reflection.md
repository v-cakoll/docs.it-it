---
title: 'Procedura: Esaminare e creare istanze di tipi generici tramite reflection'
description: Vedere come esaminare e creare istanze di tipi generici con Reflection. Usare le proprietà IsGenericType, IsGenericParameter e GenericParameterPosition.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, generic types
- generics [.NET Framework], reflection
ms.assetid: f93b03b0-1778-43fc-bc6d-35983d210e74
ms.openlocfilehash: b57a0ed0c809da442dc9fcf202ad364060971f80
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865099"
---
# <a name="how-to-examine-and-instantiate-generic-types-with-reflection"></a>Procedura: Esaminare e creare istanze di tipi generici tramite reflection
Le informazioni sui tipi generici vengono ottenute esattamente come quelle relative ad altri tipi, ovvero esaminando un oggetto <xref:System.Type> che rappresenta il tipo generico. La differenza principale è data dal fatto che un tipo generico dispone di un elenco di oggetti <xref:System.Type> che rappresentano i relativi parametri di tipo generico. La prima procedura in questa sezione esamina i tipi generici.  
  
 È possibile creare un oggetto <xref:System.Type> che rappresenta un tipo costruito associando argomenti di tipo ai parametri di tipo di una definizione di tipo generico. Questo concetto è illustrato nella seconda procedura.  
  
### <a name="to-examine-a-generic-type-and-its-type-parameters"></a>Per esaminare un tipo generico e i relativi parametri di tipo  
  
1. Ottenere un'istanza di <xref:System.Type> che rappresenta il tipo generico. Nel codice seguente il tipo viene ottenuto usando l'operatore `typeof` C# (`GetType` in Visual Basic, `typeid` in Visual C++). Per informazioni su come ottenere un oggetto <xref:System.Type>, vedere l'argomento relativo alla classe <xref:System.Type>. Si noti che nella parte restante di questa procedura il tipo è contenuto in un parametro di metodo denominato `t`.  
  
     [!code-cpp[HowToGeneric#2](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#2)]
     [!code-csharp[HowToGeneric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#2)]
     [!code-vb[HowToGeneric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#2)]  
  
2. Usare la proprietà <xref:System.Type.IsGenericType%2A> per determinare se il tipo è generico e la proprietà <xref:System.Type.IsGenericTypeDefinition%2A> per determinare se il tipo è una definizione di tipo generico.  
  
     [!code-cpp[HowToGeneric#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#3)]
     [!code-csharp[HowToGeneric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#3)]
     [!code-vb[HowToGeneric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#3)]  
  
3. Ottenere una matrice contenente gli argomenti di tipo generico usando il metodo <xref:System.Type.GetGenericArguments%2A>.  
  
     [!code-cpp[HowToGeneric#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#4)]
     [!code-csharp[HowToGeneric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#4)]
     [!code-vb[HowToGeneric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#4)]  
  
4. Per ogni argomento di tipo, determinare se è un parametro di tipo, ad esempio in una definizione di tipo generico, oppure un tipo specificato per un parametro di tipo, ad esempio in un tipo costruito, usando la proprietà <xref:System.Type.IsGenericParameter%2A>.  
  
     [!code-cpp[HowToGeneric#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#5)]
     [!code-csharp[HowToGeneric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#5)]
     [!code-vb[HowToGeneric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#5)]  
  
5. Nell'ambito del sistema di tipi un parametro di tipo generico è rappresentato da un'istanza di <xref:System.Type>, esattamente come i tipi ordinari. Il codice seguente visualizza il nome e la posizione del parametro di un oggetto <xref:System.Type> che rappresenta un parametro di tipo generico. In questo contesto la posizione del parametro non è un'informazione rilevante, ma rappresenta un dato significativo per l'esame di un parametro di tipo usato come argomento di tipo di un altro tipo generico.  
  
     [!code-cpp[HowToGeneric#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#6)]
     [!code-csharp[HowToGeneric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#6)]
     [!code-vb[HowToGeneric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#6)]  
  
6. Individuare i vincoli del tipo base e dell'interfaccia di un parametro di tipo generico usando il metodo <xref:System.Type.GetGenericParameterConstraints%2A> per ottenere tutti i vincoli in una singola matrice. I vincoli non vengono necessariamente restituiti in un ordine specifico.  
  
     [!code-cpp[HowToGeneric#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#7)]
     [!code-csharp[HowToGeneric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#7)]
     [!code-vb[HowToGeneric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#7)]  
  
7. Usare la proprietà <xref:System.Type.GenericParameterAttributes%2A> per individuare i vincoli speciali applicati a un parametro di tipo, ad esempio quelli necessari perché il parametro sia un tipo di riferimento. La proprietà include anche valori che rappresentano la varianza, che è possibile nascondere come illustrato nel codice seguente.  
  
     [!code-cpp[HowToGeneric#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#8)]
     [!code-csharp[HowToGeneric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#8)]
     [!code-vb[HowToGeneric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#8)]  
  
8. Gli attributi di vincolo speciale sono flag e lo stesso flag (<xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>) non rappresenta né i vincoli speciali né covarianza e controvarianza. Per questa ragione, per eseguire il test di queste condizioni, è necessario usare la maschera appropriata. In questo case usare <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> per isolare i flag di vincolo speciale.  
  
     [!code-cpp[HowToGeneric#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#9)]
     [!code-csharp[HowToGeneric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#9)]
     [!code-vb[HowToGeneric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#9)]  
  
## <a name="constructing-an-instance-of-a-generic-type"></a>Costruzione di un'istanza di un tipo generico  
 Un tipo generico è analogo a un modello. Non è possibile crearne istanze, se non specificando i tipi reali associati ai relativi parametri di tipo generico. Per eseguire questa operazione in fase di esecuzione usando la reflection, è necessario usare il metodo <xref:System.Type.MakeGenericType%2A>.  
  
#### <a name="to-construct-an-instance-of-a-generic-type"></a>Per costruire un'istanza di un tipo generico  
  
1. Ottenere un oggetto <xref:System.Type> che rappresenta il tipo generico. Il codice seguente ottiene il tipo generico <xref:System.Collections.Generic.Dictionary%602> in due modi diversi: usando l'overload del metodo <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType> con una stringa che descrive il tipo e chiamando il metodo <xref:System.Type.GetGenericTypeDefinition%2A> nel tipo costruito `Dictionary\<String, Example>` (`Dictionary(Of String, Example)` in Visual Basic). Il metodo <xref:System.Type.MakeGenericType%2A> richiede una definizione di tipo generico.  
  
     [!code-cpp[HowToGeneric#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#10)]
     [!code-csharp[HowToGeneric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#10)]
     [!code-vb[HowToGeneric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#10)]  
  
2. Costruire una matrice di argomenti di tipo da sostituire ai parametri di tipo. La matrice deve contenere il numero corretto di oggetti <xref:System.Type> nello stesso ordine in cui sono visualizzati nell'elenco di parametri di tipo. In questo caso la chiave (il primo parametro di tipo) è di tipo <xref:System.String> e i valori nel dizionario sono istanze di una classe denominata `Example`.  
  
     [!code-cpp[HowToGeneric#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#11)]
     [!code-csharp[HowToGeneric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#11)]
     [!code-vb[HowToGeneric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#11)]  
  
3. Chiamare il metodo <xref:System.Type.MakeGenericType%2A> per associare gli argomenti di tipo ai parametri di tipo e costruire il tipo.  
  
     [!code-cpp[HowToGeneric#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#12)]
     [!code-csharp[HowToGeneric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#12)]
     [!code-vb[HowToGeneric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#12)]  
  
4. Usare l'overload del metodo <xref:System.Activator.CreateInstance%28System.Type%29> per creare un oggetto del tipo costruito. Il codice seguente archivia due istanze della classe `Example` nell'oggetto `Dictionary<String, Example>` risultante.  
  
     [!code-cpp[HowToGeneric#13](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#13)]
     [!code-csharp[HowToGeneric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#13)]
     [!code-vb[HowToGeneric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#13)]  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente definisce un metodo `DisplayGenericType` che consente di esaminare le definizioni di tipo generico e i tipi costruiti usati nel codice, nonché di visualizzare le relative informazioni. Il metodo `DisplayGenericType` illustra come usare le proprietà <xref:System.Type.IsGenericType%2A>, <xref:System.Type.IsGenericParameter%2A> e <xref:System.Type.GenericParameterPosition%2A> e il metodo <xref:System.Type.GetGenericArguments%2A>.  
  
 L'esempio definisce anche un metodo `DisplayGenericParameter` per esaminare un parametro di tipo generico e visualizzarne i vincoli.  
  
 L'esempio di codice definisce un insieme di tipi di test, contenente un tipo generico che indica i vincoli di parametro di tipo e illustra come visualizzare informazioni su questi tipi.  
  
 L'esempio costruisce un tipo dalla classe <xref:System.Collections.Generic.Dictionary%602> creando una matrice di argomenti di tipo e chiamando il metodo <xref:System.Type.MakeGenericType%2A>. Il programma confronta l'oggetto <xref:System.Type> costruito usando <xref:System.Type.MakeGenericType%2A> con un oggetto <xref:System.Type> ottenuto usando `typeof` (`GetType` in Visual Basic), dimostrando che i due oggetti sono equivalenti. Analogamente, il programma usa il metodo <xref:System.Type.GetGenericTypeDefinition%2A> per ottenere la definizione di tipo generico del tipo costruito e la confronta con l'oggetto <xref:System.Type> che rappresenta la classe <xref:System.Collections.Generic.Dictionary%602>.  
  
 [!code-cpp[HowToGeneric#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#1)]
 [!code-csharp[HowToGeneric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#1)]
 [!code-vb[HowToGeneric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#1)]  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Type>
- <xref:System.Reflection.MethodInfo>
- [Reflection e tipi generici](reflection-and-generic-types.md)
- [Visualizzazione delle informazioni sul tipo](viewing-type-information.md)
- [Generics](../../standard/generics/index.md)
