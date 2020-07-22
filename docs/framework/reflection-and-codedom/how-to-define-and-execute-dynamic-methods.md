---
title: 'Procedura: Definire ed eseguire metodi dinamici'
description: Vedere come definire ed eseguire metodi dinamici in .NET. Visualizzazione di esempi di un metodo dinamico semplice e di un metodo dinamico associato a un'istanza di una classe.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection emit, dynamic methods
- dynamic methods
ms.assetid: 07d08a99-62c5-4254-bce2-2a75e55a18ab
ms.openlocfilehash: 7c68be91deb59ea9439e81561f50b7cc40766a45
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865112"
---
# <a name="how-to-define-and-execute-dynamic-methods"></a>Procedura: Definire ed eseguire metodi dinamici
Le procedure seguenti illustrano come definire ed eseguire un metodo dinamico semplice e un metodo dinamico associato a un'istanza di una classe. Per altre informazioni sui metodi dinamici, vedere la classe <xref:System.Reflection.Emit.DynamicMethod> e [Scenari relativi a metodi dinamici della reflection emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sfk2s47t(v=vs.100)).  
  
### <a name="to-define-and-execute-a-dynamic-method"></a>Per definire ed eseguire un metodo dinamico  
  
1. Dichiarare un tipo delegato per l'esecuzione del metodo. È opportuno usare un delegato generico per ridurre al minimo il numero di tipi delegati da dichiarare. Il codice seguente dichiara due tipi delegati, uno dei quali generico, che possono essere usati per il metodo `SquareIt`.  
  
     [!code-cpp[DynamicMethodHowTo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#2)]
     [!code-csharp[DynamicMethodHowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#2)]
     [!code-vb[DynamicMethodHowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#2)]  
  
2. Creare una matrice che specifica i tipi di parametro per il metodo dinamico. In questo esempio poiché l'unico parametro è un `int` (`Integer` in Visual Basic), la matrice contiene un solo elemento.  
  
     [!code-cpp[DynamicMethodHowTo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#3)]
     [!code-csharp[DynamicMethodHowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#3)]
     [!code-vb[DynamicMethodHowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#3)]  
  
3. Creare un oggetto <xref:System.Reflection.Emit.DynamicMethod>. In questo esempio il metodo è denominato `SquareIt`.  
  
    > [!NOTE]
    > Non è necessario assegnare un nome ai metodi dinamici poiché non possono essere richiamati per nome. Più metodi dinamici possono avere lo stesso nome. Il nome viene tuttavia visualizzato negli stack delle chiamate e può risultare utile per il debug.  
  
     Il tipo del valore restituito è specificato come `long`. Il metodo è associato al modulo contenente la classe `Example` in cui è incluso il codice di esempio. È possibile specificare qualsiasi modulo caricato. Il metodo dinamico agisce come un metodo `static` a livello di modulo (`Shared` in Visual Basic).  
  
     [!code-cpp[DynamicMethodHowTo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#4)]
     [!code-csharp[DynamicMethodHowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#4)]
     [!code-vb[DynamicMethodHowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#4)]  
  
4. Creare il corpo del metodo. In questo esempio un oggetto <xref:System.Reflection.Emit.ILGenerator> viene usato per creare il codice Microsoft Intermediate Language (MSIL). In alternativa, è possibile usare un oggetto <xref:System.Reflection.Emit.DynamicILInfo> in combinazione con i generatori di codice non gestito per creare il corpo del metodo per un <xref:System.Reflection.Emit.DynamicMethod>.  
  
     In questo esempio il codice MSIL carica l'argomento (`int`) nello stack, lo converte in `long`, duplica `long` ed esegue la moltiplicazione tra i due numeri. In questo modo il risultato al quadrato rimane nello stack e il metodo termina.  
  
     [!code-cpp[DynamicMethodHowTo#5](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#5)]
     [!code-csharp[DynamicMethodHowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#5)]
     [!code-vb[DynamicMethodHowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#5)]  
  
5. Creare un'istanza del delegato dichiarato nel primo passaggio che rappresenta il metodo dinamico chiamando il metodo <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>. La creazione del delegato rende il metodo completo e qualsiasi successivo tentativo di modifica, ad esempio l'aggiunta di codice MSIL, verrà ignorato. Il codice seguente crea il delegato e lo richiama usando un delegato generico.  
  
     [!code-cpp[DynamicMethodHowTo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#6)]
     [!code-csharp[DynamicMethodHowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#6)]
     [!code-vb[DynamicMethodHowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#6)]  
  
### <a name="to-define-and-execute-a-dynamic-method-that-is-bound-to-an-object"></a>Per definire ed eseguire un metodo dinamico associato a un oggetto  
  
1. Dichiarare un tipo delegato per l'esecuzione del metodo. È opportuno usare un delegato generico per ridurre al minimo il numero di tipi delegati da dichiarare. Il codice seguente dichiara un tipo delegato generico che è possibile usare per eseguire qualsiasi metodo con un solo parametro e un valore restituito oppure un metodo con due parametri e un valore restituito se il delegato è associato a un oggetto.  
  
     [!code-cpp[DynamicMethodHowTo#12](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#12)]
     [!code-csharp[DynamicMethodHowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#12)]
     [!code-vb[DynamicMethodHowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#12)]  
  
2. Creare una matrice che specifica i tipi di parametro per il metodo dinamico. Se il delegato che rappresenta il metodo deve essere associato a un oggetto, il primo parametro deve corrispondere al tipo a cui è associato il delegato. In questo esempio sono presenti due parametri, uno di tipo `Example` e uno di tipo `int` (`Integer` in Visual Basic).  
  
     [!code-cpp[DynamicMethodHowTo#13](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#13)]
     [!code-csharp[DynamicMethodHowTo#13](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#13)]
     [!code-vb[DynamicMethodHowTo#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#13)]  
  
3. Creare un oggetto <xref:System.Reflection.Emit.DynamicMethod>. In questo esempio il metodo non ha nome. Il tipo del valore restituito è specificato come `int` (`Integer` in Visual Basic). Il metodo ha accesso ai membri privati e protetti della classe `Example`.  
  
     [!code-cpp[DynamicMethodHowTo#14](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#14)]
     [!code-csharp[DynamicMethodHowTo#14](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#14)]
     [!code-vb[DynamicMethodHowTo#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#14)]  
  
4. Creare il corpo del metodo. In questo esempio un oggetto <xref:System.Reflection.Emit.ILGenerator> viene usato per creare il codice Microsoft Intermediate Language (MSIL). In alternativa, è possibile usare un oggetto <xref:System.Reflection.Emit.DynamicILInfo> in combinazione con i generatori di codice non gestito per creare il corpo del metodo per un <xref:System.Reflection.Emit.DynamicMethod>.  
  
     In questo esempio il codice MSIL carica il primo argomento, un'istanza della classe `Example`, e usa l'argomento per caricare il valore di un campo di istanza privato di tipo `int`. Viene caricato il secondo argomento e viene eseguita la moltiplicazione tra i due numeri. Se il prodotto è maggiore di `int`, il valore viene troncato e i bit più significativi vengono ignorati. Il metodo termina lasciando il valore restituito nello stack.  
  
     [!code-cpp[DynamicMethodHowTo#15](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#15)]
     [!code-csharp[DynamicMethodHowTo#15](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#15)]
     [!code-vb[DynamicMethodHowTo#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#15)]  
  
5. Creare un'istanza del delegato dichiarato nel primo passaggio che rappresenta il metodo dinamico chiamando l'overload del metodo <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%28System.Type%2CSystem.Object%29>. La creazione del delegato rende il metodo completo e qualsiasi successivo tentativo di modifica, ad esempio l'aggiunta di codice MSIL, verrà ignorato.  
  
    > [!NOTE]
    > È possibile chiamare il metodo <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> più volte per creare delegati associati ad altre istanze del tipo di destinazione.  
  
     Il codice seguente associa il metodo a una nuova istanza della classe `Example` il cui campo di test privato è impostato su 42. In altri termini, ogni volta che viene richiamato il delegato, l'istanza di `Example` viene passata al primo parametro del metodo.  
  
     Viene usato il delegato `OneParameter` perché il primo parametro del metodo riceve sempre l'istanza di `Example`. Quando il delegato viene richiamato, sarà necessario solo il secondo parametro.  
  
     [!code-cpp[DynamicMethodHowTo#16](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#16)]
     [!code-csharp[DynamicMethodHowTo#16](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#16)]
     [!code-vb[DynamicMethodHowTo#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#16)]  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente illustra un metodo dinamico semplice e un metodo dinamico associato a un'istanza di una classe.  
  
 Il metodo dinamico semplice accetta un unico argomento, un intero a 32 bit, e ne restituisce il quadrato a 64 bit. Per richiamare il metodo, viene usato un delegato generico.  
  
 Il secondo metodo dinamico ha due parametri, uno di tipo `Example` e uno di tipo `int` (`Integer` in Visual Basic). Non appena viene creato, il metodo dinamico viene associato a un'istanza di `Example` usando un delegato generico che ha un unico argomento di tipo `int`. Il delegato non ha un argomento di tipo `Example` perché il primo parametro del metodo riceve sempre l'istanza associata di `Example`. Quando il delegato viene richiamato, viene specificato solo l'argomento `int`. Questo metodo dinamico accede a un campo privato della classe `Example` e restituisce il prodotto del campo privato e dell'argomento `int`.  
  
 L'esempio di codice definisce i delegati che possono essere usati per l'esecuzione dei metodi.  
  
 [!code-cpp[DynamicMethodHowTo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#1)]
 [!code-csharp[DynamicMethodHowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#1)]
 [!code-vb[DynamicMethodHowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Reflection.Emit.DynamicMethod>
- [Uso della reflection emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y322t50(v=vs.100))
- [Scenari relativi a metodi dinamici della reflection emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sfk2s47t(v=vs.100))
