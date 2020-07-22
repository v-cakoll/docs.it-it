---
title: 'Procedura: Definire un tipo generico tramite reflection emit'
description: Vedere come definire un tipo generico tramite Reflection Emit. Creare un tipo generico con due parametri di tipo, applicare vincoli di classe, vincoli di interfaccia e altro ancora.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET Framework], reflection emit
- generics [.NET Framework], dynamic types
- reflection emit, generic types
ms.assetid: 07d5f01a-7b5b-40ea-9b15-f21561098fe4
ms.openlocfilehash: fe8fb731fd160ab87e5c65debf367a96bc0dea2a
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865125"
---
# <a name="how-to-define-a-generic-type-with-reflection-emit"></a>Procedura: Definire un tipo generico tramite reflection emit
Questo argomento illustra come creare un tipo generico semplice con due parametri di tipo, come applicare vincoli speciali, di classe e di interfaccia ai parametri di tipo e come creare membri che usano i parametri di tipo della classe come tipi di parametro o tipi restituiti.  
  
> [!IMPORTANT]
> Un metodo non può essere considerato generico solo perché appartiene a un tipo generico e ne usa i parametri di tipo. Per essere generico, un metodo deve avere un elenco specifico di parametri di tipo. La maggior parte dei metodi appartenenti a tipi generici non sono generici, come nell'esempio seguente. Per un esempio di creazione di un metodo generico, vedere [Procedura: Definire un metodo generico tramite reflection emit](how-to-define-a-generic-method-with-reflection-emit.md).  
  
### <a name="to-define-a-generic-type"></a>Per definire un tipo generico  
  
1. Definire un assembly dinamico denominato `GenericEmitExample1`. In questo esempio poiché l'assembly viene eseguito e salvato su disco, viene specificato <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndSave?displayProperty=nameWithType>.  
  
     [!code-cpp[EmitGenericType#2](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#2)]
     [!code-csharp[EmitGenericType#2](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#2)]
     [!code-vb[EmitGenericType#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#2)]  
  
2. Definire un modulo dinamico. Un assembly è composto da moduli eseguibili. Per un assembly a modulo singolo, il nome del modulo è lo stesso dell'assembly e il nome del file corrisponde a quello del modulo seguito da un'estensione.  
  
     [!code-cpp[EmitGenericType#3](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#3)]
     [!code-csharp[EmitGenericType#3](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#3)]
     [!code-vb[EmitGenericType#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#3)]  
  
3. Definire una classe. In questo esempio la classe è denominata `Sample`.  
  
     [!code-cpp[EmitGenericType#4](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#4)]
     [!code-csharp[EmitGenericType#4](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#4)]
     [!code-vb[EmitGenericType#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#4)]  
  
4. Definire i parametri di tipo generico di `Sample` passando una matrice di stringhe contenenti i nomi dei parametri al metodo <xref:System.Reflection.Emit.TypeBuilder.DefineGenericParameters%2A?displayProperty=nameWithType>. In questo modo la classe diventa un tipo generico. Il valore restituito è una matrice di oggetti <xref:System.Reflection.Emit.GenericTypeParameterBuilder> che rappresentano i parametri di tipo e che possono essere usati nel codice creato.  
  
     Nel codice seguente `Sample` diventa un tipo generico con parametri di tipo `TFirst` e `TSecond`. Per migliorare la leggibilità del codice, ogni oggetto <xref:System.Reflection.Emit.GenericTypeParameterBuilder> viene inserito in una variabile che ha lo stesso nome del parametro di tipo.  
  
     [!code-cpp[EmitGenericType#5](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#5)]
     [!code-csharp[EmitGenericType#5](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#5)]
     [!code-vb[EmitGenericType#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#5)]  
  
5. Aggiungere vincoli speciali ai parametri di tipo. In questo esempio il parametro di tipo `TFirst` è vincolato a tipi con costruttori senza parametri e a tipi di riferimento.  
  
     [!code-cpp[EmitGenericType#6](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#6)]
     [!code-csharp[EmitGenericType#6](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#6)]
     [!code-vb[EmitGenericType#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#6)]  
  
6. Facoltativamente, aggiungere vincoli di interfaccia e di classe ai parametri di tipo. In questo esempio il parametro di tipo `TFirst` è vincolato a tipi che derivano dalla classe di base rappresentata dall'oggetto <xref:System.Type> contenuto nella variabile `baseType` e che implementano le interfacce i cui tipi sono contenuti nelle variabili `interfaceA` e `interfaceB`. Per la dichiarazione e l'assegnazione di queste variabili, vedere l'esempio di codice.  
  
     [!code-cpp[EmitGenericType#7](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#7)]
     [!code-csharp[EmitGenericType#7](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#7)]
     [!code-vb[EmitGenericType#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#7)]  
  
7. Definire un campo. In questo esempio il tipo del campo è specificato dal parametro di tipo `TFirst`. Poiché <xref:System.Reflection.Emit.GenericTypeParameterBuilder> deriva da <xref:System.Type>, è possibile usare parametri di tipo generico ovunque sia consentito l'uso di un tipo.  
  
     [!code-cpp[EmitGenericType#21](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#21)]
     [!code-csharp[EmitGenericType#21](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#21)]
     [!code-vb[EmitGenericType#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#21)]  
  
8. Definire un metodo che usa i parametri di tipo del tipo generico. Si noti che questi tipi di metodi non sono generici, a meno che non abbiano specifici elenchi di parametri di tipo. Il codice seguente definisce un metodo `static` (`Shared` in Visual Basic) che accetta una matrice di `TFirst` e restituisce `List<TFirst>` (`List(Of TFirst)` in Visual Basic) contenente tutti gli elementi della matrice. Per definire questo metodo, è necessario creare il tipo `List<TFirst>` chiamando <xref:System.Type.MakeGenericType%2A> nella definizione di tipo generico `List<T>`. `T`Viene omesso quando si utilizza l' `typeof` operatore ( `GetType` in Visual Basic) per ottenere la definizione di tipo generico. Il tipo di parametro viene creato tramite il <xref:System.Type.MakeArrayType%2A> metodo.  
  
     [!code-cpp[EmitGenericType#22](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#22)]
     [!code-csharp[EmitGenericType#22](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#22)]
     [!code-vb[EmitGenericType#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#22)]  
  
9. Creare il corpo del metodo. Il corpo del metodo è costituito da tre codici operativi che caricano la matrice di input nello stack, chiamano il costruttore `List<TFirst>` che accetta `IEnumerable<TFirst>`, che esegue tutte le operazioni necessarie per l'inserimento degli elementi di input nell'elenco, e terminano lasciando il nuovo oggetto <xref:System.Collections.Generic.List%601> nello stack. Nella creazione di questo codice la difficoltà principale è rappresentata dal recupero del costruttore.  
  
     Poiché il metodo <xref:System.Type.GetConstructor%2A> non è supportato in <xref:System.Reflection.Emit.GenericTypeParameterBuilder>, non è possibile ottenere il costruttore di `List<TFirst>` in modo diretto. È innanzitutto necessario ottenere il costruttore della definizione di tipo generico `List<T>`, quindi chiamare un metodo che lo converta nel costruttore corrispondente di `List<TFirst>`.  
  
     Il costruttore usato per questo esempio di codice accetta `IEnumerable<T>`. Si noti tuttavia che, non trattandosi della definizione di tipo generico dell'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601>, è necessario sostituire il parametro di tipo `T` di `List<T>` per il parametro di tipo `T` di `IEnumerable<T>`. Per evitare che la presenza di parametri di tipo denominati `T` Questo è il motivo per cui in questo esempio di codice vengono usati i nomi `TFirst` e `TSecond` . Per ottenere il tipo dell'argomento del costruttore, iniziare con la definizione di tipo generico `IEnumerable<T>` e chiamare <xref:System.Type.MakeGenericType%2A> con il primo parametro di tipo generico di `List<T>` . L'elenco di argomenti del costruttore deve essere passato come matrice che, in questo caso, contiene un unico argomento.  
  
    > [!NOTE]
    > La definizione di tipo generico è espressa come `IEnumerable<>` quando viene usato l'operatore `typeof` in C# oppure come `IEnumerable(Of )` quando viene usato l'operatore `GetType` in Visual Basic.  
  
     A questo punto è possibile ottenere il costruttore di `List<T>` chiamando <xref:System.Type.GetConstructor%2A> nella definizione di tipo generico. Per convertire questo costruttore nel costruttore corrispondente di `List<TFirst>`, passare `List<TFirst>` e il costruttore da `List<T>` al metodo statico <xref:System.Reflection.Emit.TypeBuilder.GetConstructor%28System.Type%2CSystem.Reflection.ConstructorInfo%29?displayProperty=nameWithType>.  
  
     [!code-cpp[EmitGenericType#23](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#23)]
     [!code-csharp[EmitGenericType#23](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#23)]
     [!code-vb[EmitGenericType#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#23)]  
  
10. Creare il tipo e salvare il file.  
  
     [!code-cpp[EmitGenericType#8](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#8)]
     [!code-csharp[EmitGenericType#8](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#8)]
     [!code-vb[EmitGenericType#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#8)]  
  
11. Richiamare il metodo. Poiché `ExampleMethod` non è generico ma appartiene a un tipo generico, per ottenere un oggetto <xref:System.Reflection.MethodInfo> che possa essere richiamato, è necessario creare un tipo costruito dalla definizione di tipo per `Sample`. Il tipo costruito usa la classe `Example` che, essendo un tipo di riferimento e disponendo di un costruttore senza parametri predefinito, soddisfa i vincoli di `TFirst` e la classe `ExampleDerived` che soddisfa i vincoli di `TSecond`. (Il codice per `ExampleDerived` è disponibile nella sezione di codice di esempio). Questi due tipi vengono passati a <xref:System.Type.MakeGenericType%2A> per creare il tipo costruito. <xref:System.Reflection.MethodInfo> viene quindi ottenuto usando il metodo <xref:System.Type.GetMethod%2A>.  
  
     [!code-cpp[EmitGenericType#9](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#9)]
     [!code-csharp[EmitGenericType#9](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#9)]
     [!code-vb[EmitGenericType#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#9)]  
  
12. Il codice seguente crea una matrice di oggetti `Example`, inserisce la matrice in una matrice di tipo <xref:System.Object> che rappresenta gli argomenti del metodo da richiamare e le passa al metodo <xref:System.Reflection.MethodBase.Invoke%28System.Object%2CSystem.Object%5B%5D%29>. Il primo argomento del metodo <xref:System.Reflection.MethodBase.Invoke%2A> è un riferimento Null perché il metodo è `static`.  
  
     [!code-cpp[EmitGenericType#10](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#10)]
     [!code-csharp[EmitGenericType#10](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#10)]
     [!code-vb[EmitGenericType#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#10)]  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente definisce una classe denominata `Sample` insieme a una classe di base e a due interfacce. Il programma definisce due parametri di tipo generico per la classe `Sample`, trasformandola in un tipo generico. I parametri di tipo sono gli unici elementi in grado di rendere generico un tipo. Il programma segnala questa trasformazione visualizzando un messaggio di prova sia prima che dopo la definizione dei parametri di tipo.  
  
 Il parametro di tipo `TSecond` viene usato per dimostrare i vincoli di interfaccia e di classe tramite le interfacce e la classe di base, mentre il parametro di tipo `TFirst` viene usato per dimostrare i vincoli speciali.  
  
 L'esempio di codice definisce un campo e un metodo usando i parametri di tipo della classe per il tipo di campo e per il parametro e il tipo restituito del metodo.  
  
 Dopo aver creato la classe `Sample`, viene richiamato il metodo.  
  
 Il programma include un metodo che visualizza informazioni su un tipo generico e un metodo che visualizza i vincoli speciali in un parametro di tipo. Questi metodi vengono usati per visualizzare informazioni sulla classe `Sample` completata.  
  
 Il programma salva il modulo completato su disco come `GenericEmitExample1.dll` in modo che sia possibile aprirlo con [Ildasm.exe (Disassembler IL)](../tools/ildasm-exe-il-disassembler.md) ed esaminare il codice MSIL per la classe `Sample`.  
  
 [!code-cpp[EmitGenericType#1](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#1)]
 [!code-csharp[EmitGenericType#1](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#1)]
 [!code-vb[EmitGenericType#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Reflection.Emit.GenericTypeParameterBuilder>
- [Uso della reflection emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y322t50(v=vs.100))
- [Scenari relativi ad assembly dinamici della reflection emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tt9483fk(v=vs.100))
