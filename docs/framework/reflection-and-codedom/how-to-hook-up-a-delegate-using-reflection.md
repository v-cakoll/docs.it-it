---
title: 'Procedura: associare un delegato tramite reflection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET Framework], adding event handlers with reflection
- reflection, adding event-handler delegates
- delegates [.NET Framework], adding event handlers with reflection
ms.assetid: 076ee62d-a964-449e-a447-c31b33518b81
ms.openlocfilehash: d748d9f8bdd0b4d831880548d4aceb1c77a0b0c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180509"
---
# <a name="how-to-hook-up-a-delegate-using-reflection"></a>Procedura: associare un delegato tramite reflection
Quando viene usata la reflection per il caricamento e l'esecuzione di assembly, non è possibile usare le funzioni del linguaggio come l'operatore `+=` di C# o l'[istruzione AddHandler](../../visual-basic/language-reference/statements/addhandler-statement.md) di Visual Basic per associare gli eventi. Le procedure seguenti illustrano come associare un metodo esistente a un evento recuperando tutti i tipi necessari tramite reflection e come creare un metodo dinamico usando reflection emit e associarlo a un evento.  
  
> [!NOTE]
> Per un metodo alternativo per associare un delegato per la gestione degli eventi, vedere l'esempio di codice per il metodo <xref:System.Reflection.EventInfo.AddEventHandler%2A> della classe <xref:System.Reflection.EventInfo>.  
  
### <a name="to-hook-up-a-delegate-using-reflection"></a>Per associare un delegato tramite reflection  
  
1. Caricare un assembly contenente un tipo che genera eventi. Gli assembly vengono in genere caricati con il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>. Per evitare che l'esempio diventi troppo complesso, viene usato un form derivato nell'assembly corrente, ovvero viene usato il metodo <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> per caricare l'assembly corrente.  
  
     [!code-cpp[HookUpDelegate#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#3)]
     [!code-csharp[HookUpDelegate#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#3)]
     [!code-vb[HookUpDelegate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#3)]  
  
2. Ottenere un oggetto <xref:System.Type> che rappresenta il tipo e creare un'istanza del tipo. Nel codice seguente viene usato il metodo <xref:System.Activator.CreateInstance%28System.Type%29> perché il modulo ha un costruttore senza parametri. Se il tipo creato non ha un costruttore senza parametri, è possibile usare vari altri overload del metodo <xref:System.Activator.CreateInstance%2A>. Affinché sembri che non sia disponibile alcuna informazione sull'assembly, la nuova istanza viene memorizzata come tipo <xref:System.Object>. Infatti, la reflection consente di ottenere i tipi in un assembly senza che sia necessario conoscerne i nomi in anticipo.  
  
     [!code-cpp[HookUpDelegate#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#4)]
     [!code-csharp[HookUpDelegate#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#4)]
     [!code-vb[HookUpDelegate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#4)]  
  
3. Ottenere un oggetto <xref:System.Reflection.EventInfo> che rappresenta l'evento e usare la proprietà <xref:System.Reflection.EventInfo.EventHandlerType%2A> per recuperare il tipo del delegato usato per la gestione dell'evento. Nel codice seguente viene recuperato <xref:System.Reflection.EventInfo> per l'evento <xref:System.Windows.Forms.Control.Click>.  
  
     [!code-cpp[HookUpDelegate#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#5)]
     [!code-csharp[HookUpDelegate#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#5)]
     [!code-vb[HookUpDelegate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#5)]  
  
4. Ottenere un oggetto <xref:System.Reflection.MethodInfo> che rappresenta il metodo che gestisce l'evento. Nel codice del programma completo, riportato nella sezione Esempio più avanti in questo argomento è presente un metodo che corrisponde alla firma del delegato <xref:System.EventHandler> che gestisce l'evento <xref:System.Windows.Forms.Control.Click>, ma è anche possibile generare metodi dinamici in fase di esecuzione. Per informazioni dettagliate, vedere la procedura associata per generare un gestore eventi in fase di esecuzione tramite un metodo dinamico.  
  
     [!code-cpp[HookUpDelegate#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#6)]
     [!code-csharp[HookUpDelegate#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#6)]
     [!code-vb[HookUpDelegate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#6)]  
  
5. Creare un'istanza del delegato usando il metodo <xref:System.Delegate.CreateDelegate%2A>. Poiché il metodo è statico (`Shared` in Visual Basic), è necessario specificare il tipo delegato. Si consiglia di usare gli overload del metodo <xref:System.Delegate.CreateDelegate%2A> che accettano <xref:System.Reflection.MethodInfo>.  
  
     [!code-cpp[HookUpDelegate#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#7)]
     [!code-csharp[HookUpDelegate#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#7)]
     [!code-vb[HookUpDelegate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#7)]  
  
6. Ottenere il metodo della funzione di accesso `add` e richiamarlo per associare l'evento. Tutti gli eventi hanno una funzione di accesso `add` e una funzione di accesso `remove` nascoste dalla sintassi dei linguaggi di alto livello. Ad esempio, C# usa l'operatore `+=` per associare gli eventi e Visual Basic usa l'[istruzione AddHandler](../../visual-basic/language-reference/statements/addhandler-statement.md). Il codice seguente ottiene la funzione di accesso `add` dell'evento <xref:System.Windows.Forms.Control.Click> e la richiama con associazione tardiva passando l'istanza del delegato. Gli argomenti devono essere passati come matrice.  
  
     [!code-cpp[HookUpDelegate#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#8)]
     [!code-csharp[HookUpDelegate#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#8)]
     [!code-vb[HookUpDelegate#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#8)]  
  
7. Verificare l'evento. Il codice seguente illustra il form definito nell'esempio di codice. Se si fa clic sul form, viene richiamato il gestore dell'evento.  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
<a name="procedureSection1"></a>
### <a name="to-generate-an-event-handler-at-run-time-by-using-a-dynamic-method"></a>Per generare un gestore dell'evento in fase di esecuzione usando un metodo dinamico  
  
1. I metodi per la gestione degli eventi possono essere generati in fase di esecuzione usando metodi dinamici leggeri e reflection emit. Per costruire un gestore dell'evento, sono necessari il tipo restituito e i tipi di parametro del delegato, che possono essere ottenuti esaminando il metodo `Invoke` del delegato. Il codice seguente usa i metodi `GetDelegateReturnType` e `GetDelegateParameterTypes` per ottenere queste informazioni. Il codice per questi metodi è disponibile nella sezione Esempio più avanti in questo argomento.  
  
     Poiché non è necessario assegnare un nome a <xref:System.Reflection.Emit.DynamicMethod>, è possibile usare la stringa vuota. Nel codice seguente l'ultimo argomento associa il metodo dinamico al tipo corrente, concedendo al delegato l'accesso a tutti i membri pubblici e privati della classe `Example`.  
  
     [!code-cpp[HookUpDelegate#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#9)]
     [!code-csharp[HookUpDelegate#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#9)]
     [!code-vb[HookUpDelegate#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#9)]  
  
2. Generare il corpo di un metodo. Il metodo carica una stringa, chiama l'overload del metodo <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> che accetta una stringa, estrae il valore restituito dallo stack perché il gestore non ha alcun tipo restituito e termina. Per altre informazioni sulla creazione di metodi dinamici, vedere [Procedura: Definire ed eseguire metodi dinamici](how-to-define-and-execute-dynamic-methods.md).  
  
     [!code-cpp[HookUpDelegate#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#10)]
     [!code-csharp[HookUpDelegate#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#10)]
     [!code-vb[HookUpDelegate#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#10)]  
  
3. Completare il metodo dinamico chiamando il relativo metodo <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>. Usare la funzione di accesso `add` per aggiungere il delegato all'elenco di chiamate per l'evento.  
  
     [!code-cpp[HookUpDelegate#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#11)]
     [!code-csharp[HookUpDelegate#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#11)]
     [!code-vb[HookUpDelegate#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#11)]  
  
4. Verificare l'evento. Il codice seguente carica il form definito nell'esempio di codice. Fare clic sul form per richiamare il gestore dell'evento predefinito e il gestore creato.  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente illustra come associare un metodo esistente a un evento tramite reflection e come usare la classe <xref:System.Reflection.Emit.DynamicMethod> per creare un metodo in fase di esecuzione e associarlo a un evento.  
  
 [!code-cpp[HookUpDelegate#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#1)]
 [!code-csharp[HookUpDelegate#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#1)]
 [!code-vb[HookUpDelegate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Emit.DynamicMethod>
- <xref:System.Activator.CreateInstance%2A>
- <xref:System.Delegate.CreateDelegate%2A>
- [Procedura: Definire ed eseguire metodi dinamici](how-to-define-and-execute-dynamic-methods.md)
- [Reflection](reflection.md)
