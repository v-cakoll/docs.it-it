---
title: Caricamento e utilizzo dinamico dei tipi
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- late binding, about late binding
- early binding
- dynamically loading and using types
- implicit late binding
- reflection, dynamically using types
ms.assetid: db985bec-5942-40ec-b13a-771ae98623dc
ms.openlocfilehash: 940f334ec6a42c4d8da461d634051ff979b8f98d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130257"
---
# <a name="dynamically-loading-and-using-types"></a>Caricamento e utilizzo dinamico dei tipi
La reflection offre l'infrastruttura usata dai compilatori di linguaggi per implementare l'associazione tardiva implicita. L'associazione è il processo di individuazione della dichiarazione (ovvero l'implementazione) che corrisponde a un tipo specificato in modo univoco. Quando questo processo avviene in fase di esecuzione piuttosto che in fase di compilazione, esso viene chiamato associazione tardiva. Visual Basic consente di usare l'associazione tardiva implicita nel codice. Il compilatore Visual Basic chiama un metodo helper che usa la reflection per ottenere il tipo di oggetto. Gli argomenti passati al metodo helper determinano la chiamata, in fase di esecuzione, del metodo appropriato. Questi argomenti sono l'istanza (un oggetto) su cui richiamare il metodo, il nome del metodo richiamato (una stringa) e gli argomenti passati al metodo richiamato (una matrice di oggetti).  
  
 Nell'esempio seguente il compilatore Visual Basic usa la reflection in modo implicito per chiamare un metodo su un oggetto il cui tipo non è noto in fase di compilazione. Una classe **HelloWorld** dispone di un metodo **PrintHello** che stampa il testo "Hello World" concatenato con il testo passato al metodo **PrintHello**. Il metodo **PrintHello** chiamato in questo esempio è in realtà un <xref:System.Type.InvokeMember%2A?displayProperty=nameWithType>. Il codice Visual Basic consente di richiamare il metodo **PrintHello** come se il tipo dell'oggetto (helloObj) fosse noto in fase di compilazione (associazione anticipata) piuttosto che in fase di esecuzione (associazione tardiva).  
  
```vb
Module Hello  
    Sub Main()  
        ' Sets up the variable.  
        Dim helloObj As Object  
        ' Creates the object.  
        helloObj = new HelloWorld()  
        ' Invokes the print method as if it was early bound  
        ' even though it is really late bound.  
        helloObj.PrintHello("Visual Basic Late Bound")  
    End Sub  
End Module  
```  
  
## <a name="custom-binding"></a>Associazione personalizzata  
 Ai fini dell'associazione tardiva, oltre a essere usata in modo implicito dai compilatori, la reflection può essere usata in modo esplicito nel codice.  
  
 [Common Language Runtime](../../standard/clr.md) supporta più linguaggi di programmazione che seguono regole di associazione diverse. In caso di associazione anticipata, i generatori di codice possono controllare completamente questa associazione. Nell'associazione tardiva mediante reflection l'associazione deve essere invece controllata dall'associazione personalizzata. La classe <xref:System.Reflection.Binder> fornisce il controllo personalizzato sulla selezione e la chiamata dei membri.  
  
 Usando l'associazione personalizzata, è possibile caricare un assembly in fase di esecuzione, ottenere informazioni sui tipi in esso contenuti, specificare il tipo desiderato e quindi richiamarne i metodi o usarne i campi o le proprietà. Questa tecnica è utile se non si conosce il tipo di un oggetto in fase di compilazione, come avviene ad esempio quando il tipo di oggetto dipende dall'input dell'utente.  
  
 Nell'esempio seguente viene illustrato un semplice binder personalizzato che non offre la conversione del tipo di argomento. Il codice per `Simple_Type.dll` precede l'esempio principale. Assicurarsi di compilare `Simple_Type.dll` e di includere nel progetto un riferimento a esso durante la compilazione.  
  
 [!code-cpp[Conceptual.Types.Dynamic#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.Dynamic#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.Dynamic#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source1.vb#1)]  
  
### <a name="invokemember-and-createinstance"></a>InvokeMember e CreateInstance  
 Usare <xref:System.Type.InvokeMember%2A?displayProperty=nameWithType> per richiamare un membro di un tipo. I metodi **CreateInstance** di varie classi, ad esempio <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> e <xref:System.Reflection.Assembly.CreateInstance%2A?displayProperty=nameWithType>, sono forme speciali di **InvokeMember** che creano nuove istanze del tipo specificato. La classe **Binder** viene usata per la risoluzione dell'overload e la coercizione degli argomenti in questi metodi.  
  
 L'esempio seguente illustra le tre combinazioni possibili di coercizione degli argomenti (conversione del tipo) e selezione dei membri. Nel caso 1 non è necessaria la coercizione degli argomenti né la selezione dei membri. Nel caso 2 è necessaria solo la selezione dei membri. Nel caso 3 è necessaria solo la coercizione degli argomenti.  
  
 [!code-cpp[Conceptual.Types.Dynamic#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.dynamic/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.Dynamic#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.dynamic/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.Dynamic#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.dynamic/vb/source2.vb#2)]  
  
 La risoluzione dell'overload è necessaria quando vi sono più membri con lo stesso nome. I metodi <xref:System.Reflection.Binder.BindToMethod%2A?displayProperty=nameWithType> e <xref:System.Reflection.Binder.BindToField%2A?displayProperty=nameWithType> vengono usati per risolvere l'associazione su un singolo membro. **Binder.BindToMethod** offre anche la risoluzione delle proprietà mediante le funzioni di accesso alle proprietà **get** e **set**.  
  
 **BindToMethod** restituisce <xref:System.Reflection.MethodBase> da richiamare o un riferimento Null (**Nothing** in Visual Basic) se non è possibile effettuare la chiamata. **MethodBase** restituisce valori non necessariamente compresi tra quelli contenuti nel parametro *match*, sebbene questo sia il caso più frequente.  
  
 Quando sono presenti argomenti ByRef, è possibile che debbano essere restituiti al chiamante. Di conseguenza, **Binder** consentirà al client di eseguire il mapping della matrice di argomenti riportandola alla forma originale se **BindToMethod** ha modificato la matrice di argomenti. A questo scopo, è necessario garantire al chiamante che l'ordine degli argomenti resti inalterato. Quando gli argomenti vengono passati in base al nome, **Binder** riordina la matrice di argomenti, che rappresenta quanto viene visualizzato al chiamante. Per altre informazioni, vedere <xref:System.Reflection.Binder.ReorderArgumentArray%2A?displayProperty=nameWithType>.  
  
 Il set di membri disponibili è costituito dai membri definiti nel tipo o in qualsiasi tipo di base. Se si specifica <xref:System.Reflection.BindingFlags>, il set restituito comprenderà membri di qualsiasi accessibilità. Se **BindingFlags.NonPublic** non viene specificato, il binder dovrà applicare le regole di accessibilità. Quando si specifica il flag di associazione **Public** o **NonPublic** è necessario specificare anche il flag di associazione **Instance** o **Static**. In caso contrario non verrà restituito alcun membro.  
  
 Se vi è un solo membro con il nome specificato, non occorrerà alcun callback e l'associazione verrà effettuata su quel metodo. Nel caso 1 dell'esempio di codice viene illustrato questo punto: è disponibile un solo metodo **PrintBob**, quindi il callback non è necessario.  
  
 Se il set disponibile include più membri, tutti i metodi vengono passati a **BindToMethod** che seleziona il metodo appropriato e lo restituisce. Nel caso 2 dell'esempio di codice sono presenti due metodi denominati **PrintValue**. Il metodo appropriato viene selezionato dalla chiamata a **BindToMethod**.  
  
 <xref:System.Reflection.Binder.ChangeType%2A> esegue la coercizione degli argomenti (conversione del tipo) convertendo gli argomenti effettivi nel tipo di argomenti formali del metodo selezionato. **ChangeType** viene chiamato per ogni argomento anche se i tipi corrispondono esattamente.  
  
 Nel caso 3 dell'esempio di codice un argomento effettivo di tipo **String** con valore "5.5" viene passato a un metodo con un argomento formale di tipo **Double**. Affinché la chiamata abbia esito positivo, il valore di stringa "5.5" deve essere convertito in un valore Double. La conversione viene eseguita da **ChangeType**.  
  
 **ChangeType** esegue solo [coercizioni verso tipi più grandi](../../standard/base-types/type-conversion.md) o senza perdita di dati, come illustrato nella tabella seguente.  
  
|Tipo di origine|Tipo di destinazione|  
|-----------------|-----------------|  
|Qualsiasi tipo|Il relativo tipo di base|  
|Qualsiasi tipo|L'interfaccia implementata|  
|Char|UInt16, UInt32, Int32, UInt64, Int64, Single, Double|  
|Byte|Char, UInt16, Int16, UInt32, Int32, UInt64, Int64, Single, Double|  
|SByte|Int16, Int32, Int64, Single, Double|  
|UInt16|UInt32, Int32, UInt64, Int64, Single, Double|  
|Int16|Int32, Int64, Single, Double|  
|UInt32|UInt64, Int64, Single, Double|  
|Int32|Int64, Single, Double|  
|UInt64|Single, Double|  
|Int64|Single, Double|  
|Single|Double|  
|Tipo non di riferimento|Tipo di riferimento|  
  
 La classe <xref:System.Type> include metodi **Get** che usano i parametri di tipo **Binder** per risolvere i riferimenti su un membro specifico. <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType>, <xref:System.Type.GetMethod%2A?displayProperty=nameWithType> e <xref:System.Type.GetProperty%2A?displayProperty=nameWithType> cercano un membro specifico del tipo corrente fornendo informazioni sulla relativa firma. <xref:System.Reflection.Binder.SelectMethod%2A?displayProperty=nameWithType> e <xref:System.Reflection.Binder.SelectProperty%2A?displayProperty=nameWithType> vengono chiamati per selezionare le informazioni sulla firma dei metodi appropriati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Type.InvokeMember%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>
- [Visualizzazione delle informazioni sul tipo](viewing-type-information.md)
- [Conversione dei tipi nel .NET Framework](../../standard/base-types/type-conversion.md)
