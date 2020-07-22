---
title: 'Procedura: Associare un delegato tramite reflection'
description: Vedere come associare un delegato tramite reflection in .NET. Connettere un metodo esistente a un evento ottenendo i tipi necessari tramite reflection.
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
ms.openlocfilehash: b5d93efd278a53a4e6382f2321918e58ead55899
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865086"
---
# <a name="how-to-hook-up-a-delegate-using-reflection"></a><span data-ttu-id="a5828-104">Procedura: Associare un delegato tramite reflection</span><span class="sxs-lookup"><span data-stu-id="a5828-104">How to: Hook Up a Delegate Using Reflection</span></span>
<span data-ttu-id="a5828-105">Quando viene usata la reflection per il caricamento e l'esecuzione di assembly, non è possibile usare le funzioni del linguaggio come l'operatore `+=` di C# o l'[istruzione AddHandler](../../visual-basic/language-reference/statements/addhandler-statement.md) di Visual Basic per associare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="a5828-105">When you use reflection to load and run assemblies, you cannot use language features like the C# `+=` operator or the Visual Basic [AddHandler statement](../../visual-basic/language-reference/statements/addhandler-statement.md) to hook up events.</span></span> <span data-ttu-id="a5828-106">Le procedure seguenti illustrano come associare un metodo esistente a un evento recuperando tutti i tipi necessari tramite reflection e come creare un metodo dinamico usando reflection emit e associarlo a un evento.</span><span class="sxs-lookup"><span data-stu-id="a5828-106">The following procedures show how to hook up an existing method to an event by getting all the necessary types through reflection, and how to create a dynamic method using reflection emit and hook it up to an event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5828-107">Per un metodo alternativo per associare un delegato per la gestione degli eventi, vedere l'esempio di codice per il metodo <xref:System.Reflection.EventInfo.AddEventHandler%2A> della classe <xref:System.Reflection.EventInfo>.</span><span class="sxs-lookup"><span data-stu-id="a5828-107">For another way to hook up an event-handling delegate, see the code example for the <xref:System.Reflection.EventInfo.AddEventHandler%2A> method of the <xref:System.Reflection.EventInfo> class.</span></span>  
  
### <a name="to-hook-up-a-delegate-using-reflection"></a><span data-ttu-id="a5828-108">Per associare un delegato tramite reflection</span><span class="sxs-lookup"><span data-stu-id="a5828-108">To hook up a delegate using reflection</span></span>  
  
1. <span data-ttu-id="a5828-109">Caricare un assembly contenente un tipo che genera eventi.</span><span class="sxs-lookup"><span data-stu-id="a5828-109">Load an assembly that contains a type that raises events.</span></span> <span data-ttu-id="a5828-110">Gli assembly vengono in genere caricati con il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a5828-110">Assemblies are usually loaded with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a5828-111">Per evitare che l'esempio diventi troppo complesso, viene usato un form derivato nell'assembly corrente, ovvero viene usato il metodo <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> per caricare l'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="a5828-111">To keep this example simple, a derived form in the current assembly is used, so the <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method is used to load the current assembly.</span></span>  
  
     [!code-cpp[HookUpDelegate#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#3)]
     [!code-csharp[HookUpDelegate#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#3)]
     [!code-vb[HookUpDelegate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#3)]  
  
2. <span data-ttu-id="a5828-112">Ottenere un oggetto <xref:System.Type> che rappresenta il tipo e creare un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="a5828-112">Get a <xref:System.Type> object representing the type, and create an instance of the type.</span></span> <span data-ttu-id="a5828-113">Nel codice seguente viene usato il metodo <xref:System.Activator.CreateInstance%28System.Type%29> perché il modulo ha un costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="a5828-113">The <xref:System.Activator.CreateInstance%28System.Type%29> method is used in the following code because the form has a parameterless constructor.</span></span> <span data-ttu-id="a5828-114">Se il tipo creato non ha un costruttore senza parametri, è possibile usare vari altri overload del metodo <xref:System.Activator.CreateInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5828-114">There are several other overloads of the <xref:System.Activator.CreateInstance%2A> method that you can use if the type you are creating does not have a parameterless constructor.</span></span> <span data-ttu-id="a5828-115">Affinché sembri che non sia disponibile alcuna informazione sull'assembly, la nuova istanza viene memorizzata come tipo <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="a5828-115">The new instance is stored as type <xref:System.Object> to maintain the fiction that nothing is known about the assembly.</span></span> <span data-ttu-id="a5828-116">Infatti, la reflection consente di ottenere i tipi in un assembly senza che sia necessario conoscerne i nomi in anticipo.</span><span class="sxs-lookup"><span data-stu-id="a5828-116">(Reflection allows you to get the types in an assembly without knowing their names in advance.)</span></span>  
  
     [!code-cpp[HookUpDelegate#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#4)]
     [!code-csharp[HookUpDelegate#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#4)]
     [!code-vb[HookUpDelegate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#4)]  
  
3. <span data-ttu-id="a5828-117">Ottenere un oggetto <xref:System.Reflection.EventInfo> che rappresenta l'evento e usare la proprietà <xref:System.Reflection.EventInfo.EventHandlerType%2A> per recuperare il tipo del delegato usato per la gestione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a5828-117">Get an <xref:System.Reflection.EventInfo> object representing the event, and use the <xref:System.Reflection.EventInfo.EventHandlerType%2A> property to get the type of delegate used to handle the event.</span></span> <span data-ttu-id="a5828-118">Nel codice seguente viene recuperato <xref:System.Reflection.EventInfo> per l'evento <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="a5828-118">In the following code, an <xref:System.Reflection.EventInfo> for the <xref:System.Windows.Forms.Control.Click> event is obtained.</span></span>  
  
     [!code-cpp[HookUpDelegate#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#5)]
     [!code-csharp[HookUpDelegate#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#5)]
     [!code-vb[HookUpDelegate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#5)]  
  
4. <span data-ttu-id="a5828-119">Ottenere un oggetto <xref:System.Reflection.MethodInfo> che rappresenta il metodo che gestisce l'evento.</span><span class="sxs-lookup"><span data-stu-id="a5828-119">Get a <xref:System.Reflection.MethodInfo> object representing the method that handles the event.</span></span> <span data-ttu-id="a5828-120">Nel codice del programma completo, riportato nella sezione Esempio più avanti in questo argomento è presente un metodo che corrisponde alla firma del delegato <xref:System.EventHandler> che gestisce l'evento <xref:System.Windows.Forms.Control.Click>, ma è anche possibile generare metodi dinamici in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a5828-120">The complete program code in the Example section later in this topic contains a method that matches the signature of the <xref:System.EventHandler> delegate, which handles the <xref:System.Windows.Forms.Control.Click> event, but you can also generate dynamic methods at run time.</span></span> <span data-ttu-id="a5828-121">Per informazioni dettagliate, vedere la procedura associata per generare un gestore eventi in fase di esecuzione tramite un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="a5828-121">For details, see the accompanying procedure, for generating an event handler at run time by using a dynamic method.</span></span>  
  
     [!code-cpp[HookUpDelegate#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#6)]
     [!code-csharp[HookUpDelegate#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#6)]
     [!code-vb[HookUpDelegate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#6)]  
  
5. <span data-ttu-id="a5828-122">Creare un'istanza del delegato usando il metodo <xref:System.Delegate.CreateDelegate%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5828-122">Create an instance of the delegate, using the <xref:System.Delegate.CreateDelegate%2A> method.</span></span> <span data-ttu-id="a5828-123">Poiché il metodo è statico (`Shared` in Visual Basic), è necessario specificare il tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="a5828-123">This method is static (`Shared` in Visual Basic), so the delegate type must be supplied.</span></span> <span data-ttu-id="a5828-124">Si consiglia di usare gli overload del metodo <xref:System.Delegate.CreateDelegate%2A> che accettano <xref:System.Reflection.MethodInfo>.</span><span class="sxs-lookup"><span data-stu-id="a5828-124">Using the overloads of <xref:System.Delegate.CreateDelegate%2A> that take a <xref:System.Reflection.MethodInfo> is recommended.</span></span>  
  
     [!code-cpp[HookUpDelegate#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#7)]
     [!code-csharp[HookUpDelegate#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#7)]
     [!code-vb[HookUpDelegate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#7)]  
  
6. <span data-ttu-id="a5828-125">Ottenere il metodo della funzione di accesso `add` e richiamarlo per associare l'evento.</span><span class="sxs-lookup"><span data-stu-id="a5828-125">Get the `add` accessor method and invoke it to hook up the event.</span></span> <span data-ttu-id="a5828-126">Tutti gli eventi hanno una funzione di accesso `add` e una funzione di accesso `remove` nascoste dalla sintassi dei linguaggi di alto livello.</span><span class="sxs-lookup"><span data-stu-id="a5828-126">All events have an `add` accessor and a `remove` accessor, which are hidden by the syntax of high-level languages.</span></span> <span data-ttu-id="a5828-127">Ad esempio, C# usa l'operatore `+=` per associare gli eventi e Visual Basic usa l'[istruzione AddHandler](../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a5828-127">For example, C# uses the `+=` operator to hook up events, and Visual Basic uses the [AddHandler statement](../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="a5828-128">Il codice seguente ottiene la funzione di accesso `add` dell'evento <xref:System.Windows.Forms.Control.Click> e la richiama con associazione tardiva passando l'istanza del delegato.</span><span class="sxs-lookup"><span data-stu-id="a5828-128">The following code gets the `add` accessor of the <xref:System.Windows.Forms.Control.Click> event and invokes it late-bound, passing in the delegate instance.</span></span> <span data-ttu-id="a5828-129">Gli argomenti devono essere passati come matrice.</span><span class="sxs-lookup"><span data-stu-id="a5828-129">The arguments must be passed as an array.</span></span>  
  
     [!code-cpp[HookUpDelegate#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#8)]
     [!code-csharp[HookUpDelegate#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#8)]
     [!code-vb[HookUpDelegate#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#8)]  
  
7. <span data-ttu-id="a5828-130">Verificare l'evento.</span><span class="sxs-lookup"><span data-stu-id="a5828-130">Test the event.</span></span> <span data-ttu-id="a5828-131">Il codice seguente illustra il form definito nell'esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="a5828-131">The following code shows the form defined in the code example.</span></span> <span data-ttu-id="a5828-132">Se si fa clic sul form, viene richiamato il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="a5828-132">Clicking the form invokes the event handler.</span></span>  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
<a name="procedureSection1"></a>
### <a name="to-generate-an-event-handler-at-run-time-by-using-a-dynamic-method"></a><span data-ttu-id="a5828-133">Per generare un gestore dell'evento in fase di esecuzione usando un metodo dinamico</span><span class="sxs-lookup"><span data-stu-id="a5828-133">To generate an event handler at run time by using a dynamic method</span></span>  
  
1. <span data-ttu-id="a5828-134">I metodi per la gestione degli eventi possono essere generati in fase di esecuzione usando metodi dinamici leggeri e reflection emit.</span><span class="sxs-lookup"><span data-stu-id="a5828-134">Event-handler methods can be generated at run time, using lightweight dynamic methods and reflection emit.</span></span> <span data-ttu-id="a5828-135">Per costruire un gestore dell'evento, sono necessari il tipo restituito e i tipi di parametro del delegato,</span><span class="sxs-lookup"><span data-stu-id="a5828-135">To construct an event handler, you need the return type and parameter types of the delegate.</span></span> <span data-ttu-id="a5828-136">che possono essere ottenuti esaminando il metodo `Invoke` del delegato.</span><span class="sxs-lookup"><span data-stu-id="a5828-136">These can be obtained by examining the delegate's `Invoke` method.</span></span> <span data-ttu-id="a5828-137">Il codice seguente usa i metodi `GetDelegateReturnType` e `GetDelegateParameterTypes` per ottenere queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="a5828-137">The following code uses the `GetDelegateReturnType` and `GetDelegateParameterTypes` methods to obtain this information.</span></span> <span data-ttu-id="a5828-138">Il codice per questi metodi è disponibile nella sezione Esempio più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="a5828-138">The code for these methods can be found in the Example section later in this topic.</span></span>  
  
     <span data-ttu-id="a5828-139">Poiché non è necessario assegnare un nome a <xref:System.Reflection.Emit.DynamicMethod>, è possibile usare la stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="a5828-139">It is not necessary to name a <xref:System.Reflection.Emit.DynamicMethod>, so the empty string can be used.</span></span> <span data-ttu-id="a5828-140">Nel codice seguente l'ultimo argomento associa il metodo dinamico al tipo corrente, concedendo al delegato l'accesso a tutti i membri pubblici e privati della classe `Example`.</span><span class="sxs-lookup"><span data-stu-id="a5828-140">In the following code, the last argument associates the dynamic method with the current type, giving the delegate access to all the public and private members of the `Example` class.</span></span>  
  
     [!code-cpp[HookUpDelegate#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#9)]
     [!code-csharp[HookUpDelegate#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#9)]
     [!code-vb[HookUpDelegate#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#9)]  
  
2. <span data-ttu-id="a5828-141">Generare il corpo di un metodo.</span><span class="sxs-lookup"><span data-stu-id="a5828-141">Generate a method body.</span></span> <span data-ttu-id="a5828-142">Il metodo carica una stringa, chiama l'overload del metodo <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> che accetta una stringa, estrae il valore restituito dallo stack perché il gestore non ha alcun tipo restituito e termina.</span><span class="sxs-lookup"><span data-stu-id="a5828-142">This method loads a string, calls the overload of the <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> method that takes a string, pops the return value off the stack (because the handler has no return type), and returns.</span></span> <span data-ttu-id="a5828-143">Per altre informazioni sulla creazione di metodi dinamici, vedere [Procedura: Definire ed eseguire metodi dinamici](how-to-define-and-execute-dynamic-methods.md).</span><span class="sxs-lookup"><span data-stu-id="a5828-143">To learn more about emitting dynamic methods, see [How to: Define and Execute Dynamic Methods](how-to-define-and-execute-dynamic-methods.md).</span></span>  
  
     [!code-cpp[HookUpDelegate#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#10)]
     [!code-csharp[HookUpDelegate#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#10)]
     [!code-vb[HookUpDelegate#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#10)]  
  
3. <span data-ttu-id="a5828-144">Completare il metodo dinamico chiamando il relativo metodo <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5828-144">Complete the dynamic method by calling its <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> method.</span></span> <span data-ttu-id="a5828-145">Usare la funzione di accesso `add` per aggiungere il delegato all'elenco di chiamate per l'evento.</span><span class="sxs-lookup"><span data-stu-id="a5828-145">Use the `add` accessor to add the delegate to the invocation list for the event.</span></span>  
  
     [!code-cpp[HookUpDelegate#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#11)]
     [!code-csharp[HookUpDelegate#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#11)]
     [!code-vb[HookUpDelegate#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#11)]  
  
4. <span data-ttu-id="a5828-146">Verificare l'evento.</span><span class="sxs-lookup"><span data-stu-id="a5828-146">Test the event.</span></span> <span data-ttu-id="a5828-147">Il codice seguente carica il form definito nell'esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="a5828-147">The following code loads the form defined in the code example.</span></span> <span data-ttu-id="a5828-148">Fare clic sul form per richiamare il gestore dell'evento predefinito e il gestore creato.</span><span class="sxs-lookup"><span data-stu-id="a5828-148">Clicking the form invokes both the predefined event handler and the emitted event handler.</span></span>  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="a5828-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="a5828-149">Example</span></span>  
 <span data-ttu-id="a5828-150">L'esempio di codice seguente illustra come associare un metodo esistente a un evento tramite reflection e come usare la classe <xref:System.Reflection.Emit.DynamicMethod> per creare un metodo in fase di esecuzione e associarlo a un evento.</span><span class="sxs-lookup"><span data-stu-id="a5828-150">The following code example shows how to hook up an existing method to an event using reflection, and also how to use the <xref:System.Reflection.Emit.DynamicMethod> class to emit a method at run time and hook it up to an event.</span></span>  
  
 [!code-cpp[HookUpDelegate#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#1)]
 [!code-csharp[HookUpDelegate#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#1)]
 [!code-vb[HookUpDelegate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a5828-151">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a5828-151">See also</span></span>

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Emit.DynamicMethod>
- <xref:System.Activator.CreateInstance%2A>
- <xref:System.Delegate.CreateDelegate%2A>
- [<span data-ttu-id="a5828-152">Procedura: Definire ed eseguire metodi dinamici</span><span class="sxs-lookup"><span data-stu-id="a5828-152">How to: Define and Execute Dynamic Methods</span></span>](how-to-define-and-execute-dynamic-methods.md)
- [<span data-ttu-id="a5828-153">Reflection</span><span class="sxs-lookup"><span data-stu-id="a5828-153">Reflection</span></span>](reflection.md)
