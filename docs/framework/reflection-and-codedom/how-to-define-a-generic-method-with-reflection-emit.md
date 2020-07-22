---
title: 'Procedura: Definire un metodo generico tramite reflection emit'
description: Definire un metodo generico con Reflection Emit. Un esempio crea un metodo generico con due parametri di tipo. Un secondo esempio Mostra come creare il corpo del metodo.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generics [.NET Framework], reflection emit
- reflection emit, generic methods
- generics [.NET Framework], dynamic types
ms.assetid: 93892fa4-90b3-4ec4-b147-4bec9880de2b
ms.openlocfilehash: 3b85fb480e5862daa3b2800f75392adbe92348f2
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865138"
---
# <a name="how-to-define-a-generic-method-with-reflection-emit"></a>Procedura: Definire un metodo generico tramite reflection emit

La prima procedura illustra come creare un metodo generico semplice con due parametri di tipo e come applicare a questi ultimi vincoli speciali, di interfaccia e di classe.

La seconda procedura illustra come creare il corpo del metodo e usare i parametri di tipo del metodo generico per creare istanze di tipi generici e chiamare i relativi metodi.

La terza procedura illustra come richiamare il metodo generico.

> [!IMPORTANT]
> Un metodo non può essere considerato generico solo perché appartiene a un tipo generico e ne usa i parametri di tipo. Per essere generico, un metodo deve avere un elenco specifico di parametri di tipo. Un metodo generico può appartenere a un tipo non generico, come nell'esempio seguente. Per un esempio di metodo non generico incluso in un tipo generico, vedere [Procedura: Definire un tipo generico tramite reflection emit](how-to-define-a-generic-type-with-reflection-emit.md).

### <a name="to-define-a-generic-method"></a>Per definire un metodo generico

1. Prima di iniziare, può essere utile esaminare un metodo generico scritto con un linguaggio di alto livello. Il codice seguente è incluso nel codice di esempio di questo argomento insieme al codice usato per chiamare il metodo generico. Il metodo ha due parametri di tipo, `TInput` e `TOutput`, il secondo dei quali deve essere un tipo di riferimento (`class`), deve avere un costruttore senza parametri (`new`) e deve implementare `ICollection(Of TInput)` (`ICollection<TInput>` in C#). Questo vincolo di interfaccia garantisce la possibilità di usare il metodo <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType> per aggiungere elementi all'insieme `TOutput` creato dal metodo. Il metodo ha un unico parametro formale, `input`, che è una matrice di `TInput`. Il metodo crea un insieme di tipo `TOutput` e copia gli elementi di `input` nell'insieme.

    [!code-csharp[GenericMethodHowTo#20](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#20)]
    [!code-vb[GenericMethodHowTo#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#20)]

2. Definire un assembly dinamico e un modulo dinamico per contenere il tipo a cui appartiene il metodo generico. In questo caso l'assembly ha un unico modulo denominato `DemoMethodBuilder1` il cui nome corrisponde a quello dell'assembly seguito da un'estensione. In questo esempio l'assembly viene salvato su disco e anche eseguito, pertanto è specificato <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndSave?displayProperty=nameWithType>. È possibile usare lo strumento [Ildasm.exe (IL Disassembler)](../tools/ildasm-exe-il-disassembler.md) per esaminare DemoMethodBuilder1.dll ed eseguirne un confronto con il codice Microsoft Intermediate Language (MSIL) relativo al metodo illustrato nel primo passaggio 1.

    [!code-csharp[GenericMethodHowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#2)]
    [!code-vb[GenericMethodHowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#2)]

3. Definire il tipo che a cui appartiene il metodo generico. Il tipo non deve essere necessariamente generico. Un metodo generico può infatti appartenere a un tipo generico o non generico. In questo esempio il tipo è una classe, non è generico ed è denominato `DemoType`.

    [!code-csharp[GenericMethodHowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#3)]
    [!code-vb[GenericMethodHowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#3)]

4. Definire il metodo generico. Se i tipi dei parametri formali di un metodo generico sono specificati dai parametri di tipo generico di tale metodo, usare l'overload del metodo <xref:System.Reflection.Emit.TypeBuilder.DefineMethod%28System.String%2CSystem.Reflection.MethodAttributes%29> per definire il metodo. I parametri di tipo generico del metodo non sono ancora definiti e non è pertanto possibile specificare i tipi dei parametri formali del metodo nella chiamata a <xref:System.Reflection.Emit.TypeBuilder.DefineMethod%2A>. In questo esempio il metodo è denominato `Factory`, è pubblico e `static` (`Shared` in Visual Basic).

    [!code-csharp[GenericMethodHowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#4)]
    [!code-vb[GenericMethodHowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#4)]

5. Definire i parametri di tipo generico di `DemoMethod` passando una matrice di stringhe contenenti i nomi dei parametri al metodo <xref:System.Reflection.Emit.MethodBuilder.DefineGenericParameters%2A?displayProperty=nameWithType>. In questo modo si ottiene un metodo generico. Il codice seguente trasforma `Factory` in un metodo generico con i parametri di tipo `TInput` e `TOutput`. Per migliorare la leggibilità del codice, vengono create variabili con questi nomi per contenere gli oggetti <xref:System.Reflection.Emit.GenericTypeParameterBuilder> che rappresentano i due parametri di tipo.

    [!code-csharp[GenericMethodHowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#5)]
    [!code-vb[GenericMethodHowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#5)]

6. Facoltativamente, aggiungere vincoli speciali ai parametri di tipo. I vincoli speciali vengono aggiunti usando il metodo <xref:System.Reflection.Emit.GenericTypeParameterBuilder.SetGenericParameterAttributes%2A>. In questo esempio `TOutput` deve essere un tipo di riferimento e deve avere un costruttore senza parametri.

    [!code-csharp[GenericMethodHowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#6)]
    [!code-vb[GenericMethodHowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#6)]

7. Facoltativamente, aggiungere vincoli di interfaccia e di classe ai parametri di tipo. In questo esempio il parametro di tipo `TOutput` è vincolato a tipi che implementano l'interfaccia `ICollection(Of TInput)` (`ICollection<TInput>` in C#). Questo vincolo garantisce la possibilità di usare il metodo <xref:System.Collections.Generic.ICollection%601.Add%2A> per l'aggiunta di elementi.

    [!code-csharp[GenericMethodHowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#7)]
    [!code-vb[GenericMethodHowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#7)]

8. Definire i parametri formali del metodo usando il metodo <xref:System.Reflection.Emit.MethodBuilder.SetParameters%2A>. In questo esempio il metodo `Factory` ha un unico parametro, una matrice di `TInput`. Il tipo viene creato chiamando il metodo <xref:System.Type.MakeArrayType%2A> in <xref:System.Reflection.Emit.GenericTypeParameterBuilder> che rappresenta `TInput`. L'argomento di <xref:System.Reflection.Emit.MethodBuilder.SetParameters%2A> è una matrice di oggetti <xref:System.Type>.

    [!code-csharp[GenericMethodHowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#8)]
    [!code-vb[GenericMethodHowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#8)]

9. Definire il tipo restituito per il metodo usando il metodo <xref:System.Reflection.Emit.MethodBuilder.SetReturnType%2A>. In questo esempio viene restituita un'istanza di `TOutput`.

    [!code-csharp[GenericMethodHowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#9)]
    [!code-vb[GenericMethodHowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#9)]

10. Creare il corpo del metodo usando <xref:System.Reflection.Emit.ILGenerator>. Per informazioni dettagliate, vedere la procedura associata per creare il corpo del metodo.

    > [!IMPORTANT]
    > Quando si creano chiamate a metodi di tipi generici e gli argomenti di tipo di questi ultimi sono parametri di tipo del metodo generico, è necessario usare gli overload dei metodi `static`<xref:System.Reflection.Emit.TypeBuilder.GetConstructor%28System.Type%2CSystem.Reflection.ConstructorInfo%29>, <xref:System.Reflection.Emit.TypeBuilder.GetMethod%28System.Type%2CSystem.Reflection.MethodInfo%29> e <xref:System.Reflection.Emit.TypeBuilder.GetField%28System.Type%2CSystem.Reflection.FieldInfo%29> della classe <xref:System.Reflection.Emit.TypeBuilder> per ottenere i formati costruiti dei metodi. Questo concetto è illustrato nella procedura associata per la creazione del corpo del metodo.

11. Completare il tipo contenente il metodo e salvare l'assembly. Nella procedura associata per richiamare il metodo generico vengono indicati due modi per richiamare il metodo completato.

    [!code-csharp[GenericMethodHowTo#14](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#14)]
    [!code-vb[GenericMethodHowTo#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#14)]

<a name="procedureSection1"></a>

### <a name="to-emit-the-method-body"></a>Per creare il corpo del metodo

1. Ottenere un generatore di codice e dichiarare le variabili locali e le etichette. Per dichiarare le variabili locali viene usato il metodo <xref:System.Reflection.Emit.ILGenerator.DeclareLocal%2A>. Il metodo `Factory` ha quattro variabili locali: `retVal` per contenere il nuovo oggetto `TOutput` restituito dal metodo, `ic` per contenere `TOutput` quando ne viene eseguito il cast in `ICollection(Of TInput)` (`ICollection<TInput>` in C#), `input` per contenere la matrice di input di oggetti `TInput` e `index` scorrere la matrice. Il metodo ha anche due etichette, una per l'ingresso nel ciclo (`enterLoop`) e una per l'inizio del ciclo (`loopAgain`), definite usando il metodo <xref:System.Reflection.Emit.ILGenerator.DefineLabel%2A>.

    La prima operazione eseguita dal metodo consiste nel caricare il relativo argomento mediante il codice operativo <xref:System.Reflection.Emit.OpCodes.Ldarg_0> e nel memorizzarlo nella variabile locale `input` mediante il codice operativo <xref:System.Reflection.Emit.OpCodes.Stloc_S>.

    [!code-csharp[GenericMethodHowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#10)]
    [!code-vb[GenericMethodHowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#10)]

2. Creare il codice per generare un'istanza di `TOutput`, usando l'overload di metodo generico del metodo <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>. Per usare questo overload è necessario che il tipo specificato abbia un costruttore senza parametri. Per questo motivo questo vincolo viene aggiunto a `TOutput`. Creare il metodo generico costruito passando `TOutput` a <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>. Dopo aver creato il codice per la chiamata al metodo, creare il codice per memorizzarlo nella variabile locale `retVal` usando <xref:System.Reflection.Emit.OpCodes.Stloc_S>

    [!code-csharp[GenericMethodHowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#11)]
    [!code-vb[GenericMethodHowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#11)]

3. Creare il codice per eseguire il cast del nuovo oggetto `TOutput` in `ICollection(Of TInput)` e memorizzarlo nella variabile locale `ic`.

    [!code-csharp[GenericMethodHowTo#31](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#31)]
    [!code-vb[GenericMethodHowTo#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#31)]

4. Ottenere un oggetto <xref:System.Reflection.MethodInfo> che rappresenta il metodo <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType>. Poiché il metodo opera su `ICollection(Of TInput)` (`ICollection<TInput>` in C#), è necessario ottenere il metodo `Add` specifico per il tipo costruito. Non è possibile usare il metodo <xref:System.Type.GetMethod%2A> per ottenere <xref:System.Reflection.MethodInfo> direttamente da `icollOfTInput`, perché <xref:System.Type.GetMethod%2A> non è supportato su un tipo costruito con un oggetto <xref:System.Reflection.Emit.GenericTypeParameterBuilder>. Chiamare invece <xref:System.Type.GetMethod%2A> su `icoll`, che contiene la definizione di tipo generico per l'interfaccia generica <xref:System.Collections.Generic.ICollection%601>. Usare quindi il metodo <xref:System.Reflection.Emit.TypeBuilder.GetMethod%28System.Type%2CSystem.Reflection.MethodInfo%29>`static` per produrre l'oggetto <xref:System.Reflection.MethodInfo> per il tipo costruito. Questo concetto è illustrato nel codice riportato di seguito.

    [!code-csharp[GenericMethodHowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#12)]
    [!code-vb[GenericMethodHowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#12)]

5. Creare il codice per inizializzare la variabile `index` caricando un intero 0 a 32 bit e memorizzandolo nella variabile. Creare il codice per la creazione del ramo dell'etichetta `enterLoop`. Poiché si trova all'interno del ciclo, l'etichetta non è ancora contrassegnata. Il codice per il ciclo verrà creato nel passaggio successivo.

    [!code-csharp[GenericMethodHowTo#32](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#32)]
    [!code-vb[GenericMethodHowTo#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#32)]

6. Creare il codice per il ciclo. Il primo passaggio consiste nel contrassegnare l'inizio del ciclo chiamando <xref:System.Reflection.Emit.ILGenerator.MarkLabel%2A> con l'etichetta `loopAgain`. Le istruzioni per la creazione di un ramo che usano l'etichetta passeranno a questo punto del codice. Il passaggio successivo prevede l'inserimento nello stack dell'oggetto `TOutput` di cui è stato eseguito il cast in `ICollection(Of TInput)`. Questa operazione non deve essere eseguita immediatamente, ma deve comunque essere prevista per la chiamata al metodo `Add`. Dopo l'inserimento della matrice di input nello stack è necessario inserire la variabile `index` contenente l'indice corrente nella matrice. Il codice operativo <xref:System.Reflection.Emit.OpCodes.Ldelem> estrae l'indice e la matrice dallo stack e inserisce l'elemento della matrice indicizzata nello stack. A questo punto lo stack è pronto per la chiamata al metodo <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType> che estrae l'insieme e il nuovo elemento dallo stack e aggiunge il secondo al primo.

    La parte del codice rimanente nel ciclo incrementa l'indice e verifica se il ciclo è terminato: l'indice e un intero 1 a 32 bit vengono inseriti nello stack e aggiunti tramite addizione, lasciando la somma risultante nello stack; la somma viene archiviata in `index`. Per impostare questo punto come punto di ingresso per il ciclo, viene chiamato il metodo <xref:System.Reflection.Emit.ILGenerator.MarkLabel%2A>. L'indice viene nuovamente caricato. La matrice di input viene inserita nello stack e viene creato <xref:System.Reflection.Emit.OpCodes.Ldlen> per ottenere la relativa lunghezza. Per eseguire il confronto tra l'indice e la lunghezza, ora presenti nello stack, viene creato <xref:System.Reflection.Emit.OpCodes.Clt>. Se l'indice è minore della lunghezza, <xref:System.Reflection.Emit.OpCodes.Brtrue_S> torna all'inizio del ciclo.

    [!code-csharp[GenericMethodHowTo#13](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#13)]
    [!code-vb[GenericMethodHowTo#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#13)]

7. Creare il codice per inserire l'oggetto `TOutput` nello stack e uscire dal metodo. Entrambe le variabili locali `retVal` e `ic` contengono riferimenti al nuovo `TOutput`; `ic` viene usato solo per accedere al metodo <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=nameWithType>.

    [!code-csharp[GenericMethodHowTo#33](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#33)]
    [!code-vb[GenericMethodHowTo#33](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#33)]

<a name="procedureSection2"></a>

### <a name="to-invoke-the-generic-method"></a>Per richiamare il metodo generico

1. `Factory` è una definizione di metodo generico. Per richiamarla, è necessario assegnare tipi ai parametri di tipo generico. A questo scopo, usare il metodo <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>. Il codice seguente crea un metodo generico costruito, specificando <xref:System.String> per `TInput` e `List(Of String)` (`List<string>` in C#) per `TOutput`, e visualizza una rappresentazione in formato stringa del metodo.

    [!code-csharp[GenericMethodHowTo#21](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#21)]
    [!code-vb[GenericMethodHowTo#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#21)]

2. Per richiamare il metodo con associazione tardiva, usare il metodo <xref:System.Reflection.MethodBase.Invoke%2A>. Il codice seguente crea una matrice di <xref:System.Object>, contenente come unico elemento una matrice di stringhe, e passa la matrice come elenco di argomenti per il metodo generico. Il primo parametro di <xref:System.Reflection.MethodBase.Invoke%2A> è un riferimento Null perché il metodo è `static`. Viene eseguito il cast del valore restituito in `List(Of String)` e viene visualizzato il primo elemento.

    [!code-csharp[GenericMethodHowTo#22](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#22)]
    [!code-vb[GenericMethodHowTo#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#22)]

3. Per richiamare il metodo usando un delegato, è necessario avere un delegato che corrisponda alla firma del metodo generico costruito. Un modo semplice per eseguire questa operazione consiste nel creare un delegato generico. Il codice seguente crea un'istanza del delegato generico `D` definito nel codice di esempio usando l'overload del metodo <xref:System.Delegate.CreateDelegate%28System.Type%2CSystem.Reflection.MethodInfo%29?displayProperty=nameWithType> e richiama il delegato. I delegati offrono migliori prestazioni rispetto alle chiamate con associazione tardiva.

    [!code-csharp[GenericMethodHowTo#23](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#23)]
    [!code-vb[GenericMethodHowTo#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#23)]

4. Il metodo creato può essere chiamato anche da un programma che fa riferimento all'assembly salvato.

## <a name="example"></a>Esempio

L'esempio di codice seguente crea il tipo non generico `DemoType` con il metodo generico `Factory`. Il metodo ha due parametri di tipo generico, ovvero `TInput` per specificare un tipo di input e `TOutput` per specificare un tipo di output. Al parametro di tipo `TOutput` sono applicati vincoli affinché implementi `ICollection<TInput>` (`ICollection(Of TInput)` in Visual Basic), sia un tipo di riferimento e abbia un costruttore senza parametri.

Il metodo ha un unico parametro formale che è una matrice di `TInput`. Il metodo restituisce un'istanza di `TOutput` che contiene gli elementi della matrice di input. `TOutput` può essere qualsiasi tipo di insieme generico che implementa l'interfaccia generica <xref:System.Collections.Generic.ICollection%601>.

Quando il codice viene eseguito, l'assembly dinamico viene salvato come DemoGenericMethod1.dll e può essere esaminato mediante lo strumento [Ildasm.exe (Disassembler IL)](../tools/ildasm-exe-il-disassembler.md).

> [!NOTE]
> Per acquisire familiarità con le procedure per la creazione di codice, si consiglia di scrivere un programma Visual Basic, C# o Visual C++ che esegua l'attività che si tenta di creare e usare il disassembler per esaminare il codice MSIL prodotto dal compilatore.

L'esempio di codice include il codice sorgente equivalente al metodo creato. Il metodo creato viene richiamato con associazione tardiva e anche tramite un delegato generico dichiarato nell'esempio di codice.

[!code-csharp[GenericMethodHowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#1)]
[!code-vb[GenericMethodHowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#1)]

## <a name="see-also"></a>Vedi anche

- <xref:System.Reflection.Emit.MethodBuilder>
- [Procedura: Definire un tipo generico tramite reflection emit](how-to-define-a-generic-type-with-reflection-emit.md)
