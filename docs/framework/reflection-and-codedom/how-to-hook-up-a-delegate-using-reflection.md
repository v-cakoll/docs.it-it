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
# <a name="how-to-hook-up-a-delegate-using-reflection"></a><span data-ttu-id="4d8e9-102">Procedura: associare un delegato tramite reflection</span><span class="sxs-lookup"><span data-stu-id="4d8e9-102">How to: Hook Up a Delegate Using Reflection</span></span>
<span data-ttu-id="4d8e9-103">Quando viene usata la reflection per il caricamento e l'esecuzione di assembly, non è possibile usare le funzioni del linguaggio come l'operatore `+=` di C# o l'[istruzione AddHandler](../../visual-basic/language-reference/statements/addhandler-statement.md) di Visual Basic per associare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-103">When you use reflection to load and run assemblies, you cannot use language features like the C# `+=` operator or the Visual Basic [AddHandler statement](../../visual-basic/language-reference/statements/addhandler-statement.md) to hook up events.</span></span> <span data-ttu-id="4d8e9-104">Le procedure seguenti illustrano come associare un metodo esistente a un evento recuperando tutti i tipi necessari tramite reflection e come creare un metodo dinamico usando reflection emit e associarlo a un evento.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-104">The following procedures show how to hook up an existing method to an event by getting all the necessary types through reflection, and how to create a dynamic method using reflection emit and hook it up to an event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4d8e9-105">Per un metodo alternativo per associare un delegato per la gestione degli eventi, vedere l'esempio di codice per il metodo <xref:System.Reflection.EventInfo.AddEventHandler%2A> della classe <xref:System.Reflection.EventInfo>.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-105">For another way to hook up an event-handling delegate, see the code example for the <xref:System.Reflection.EventInfo.AddEventHandler%2A> method of the <xref:System.Reflection.EventInfo> class.</span></span>  
  
### <a name="to-hook-up-a-delegate-using-reflection"></a><span data-ttu-id="4d8e9-106">Per associare un delegato tramite reflection</span><span class="sxs-lookup"><span data-stu-id="4d8e9-106">To hook up a delegate using reflection</span></span>  
  
1. <span data-ttu-id="4d8e9-107">Caricare un assembly contenente un tipo che genera eventi.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-107">Load an assembly that contains a type that raises events.</span></span> <span data-ttu-id="4d8e9-108">Gli assembly vengono in genere caricati con il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-108">Assemblies are usually loaded with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4d8e9-109">Per evitare che l'esempio diventi troppo complesso, viene usato un form derivato nell'assembly corrente, ovvero viene usato il metodo <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> per caricare l'assembly corrente.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-109">To keep this example simple, a derived form in the current assembly is used, so the <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method is used to load the current assembly.</span></span>  
  
     [!code-cpp[HookUpDelegate#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#3)]
     [!code-csharp[HookUpDelegate#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#3)]
     [!code-vb[HookUpDelegate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#3)]  
  
2. <span data-ttu-id="4d8e9-110">Ottenere un oggetto <xref:System.Type> che rappresenta il tipo e creare un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-110">Get a <xref:System.Type> object representing the type, and create an instance of the type.</span></span> <span data-ttu-id="4d8e9-111">Nel codice seguente viene usato il metodo <xref:System.Activator.CreateInstance%28System.Type%29> perché il modulo ha un costruttore senza parametri.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-111">The <xref:System.Activator.CreateInstance%28System.Type%29> method is used in the following code because the form has a parameterless constructor.</span></span> <span data-ttu-id="4d8e9-112">Se il tipo creato non ha un costruttore senza parametri, è possibile usare vari altri overload del metodo <xref:System.Activator.CreateInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-112">There are several other overloads of the <xref:System.Activator.CreateInstance%2A> method that you can use if the type you are creating does not have a parameterless constructor.</span></span> <span data-ttu-id="4d8e9-113">Affinché sembri che non sia disponibile alcuna informazione sull'assembly, la nuova istanza viene memorizzata come tipo <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-113">The new instance is stored as type <xref:System.Object> to maintain the fiction that nothing is known about the assembly.</span></span> <span data-ttu-id="4d8e9-114">Infatti, la reflection consente di ottenere i tipi in un assembly senza che sia necessario conoscerne i nomi in anticipo.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-114">(Reflection allows you to get the types in an assembly without knowing their names in advance.)</span></span>  
  
     [!code-cpp[HookUpDelegate#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#4)]
     [!code-csharp[HookUpDelegate#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#4)]
     [!code-vb[HookUpDelegate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#4)]  
  
3. <span data-ttu-id="4d8e9-115">Ottenere un oggetto <xref:System.Reflection.EventInfo> che rappresenta l'evento e usare la proprietà <xref:System.Reflection.EventInfo.EventHandlerType%2A> per recuperare il tipo del delegato usato per la gestione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-115">Get an <xref:System.Reflection.EventInfo> object representing the event, and use the <xref:System.Reflection.EventInfo.EventHandlerType%2A> property to get the type of delegate used to handle the event.</span></span> <span data-ttu-id="4d8e9-116">Nel codice seguente viene recuperato <xref:System.Reflection.EventInfo> per l'evento <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-116">In the following code, an <xref:System.Reflection.EventInfo> for the <xref:System.Windows.Forms.Control.Click> event is obtained.</span></span>  
  
     [!code-cpp[HookUpDelegate#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#5)]
     [!code-csharp[HookUpDelegate#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#5)]
     [!code-vb[HookUpDelegate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#5)]  
  
4. <span data-ttu-id="4d8e9-117">Ottenere un oggetto <xref:System.Reflection.MethodInfo> che rappresenta il metodo che gestisce l'evento.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-117">Get a <xref:System.Reflection.MethodInfo> object representing the method that handles the event.</span></span> <span data-ttu-id="4d8e9-118">Nel codice del programma completo, riportato nella sezione Esempio più avanti in questo argomento è presente un metodo che corrisponde alla firma del delegato <xref:System.EventHandler> che gestisce l'evento <xref:System.Windows.Forms.Control.Click>, ma è anche possibile generare metodi dinamici in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-118">The complete program code in the Example section later in this topic contains a method that matches the signature of the <xref:System.EventHandler> delegate, which handles the <xref:System.Windows.Forms.Control.Click> event, but you can also generate dynamic methods at run time.</span></span> <span data-ttu-id="4d8e9-119">Per informazioni dettagliate, vedere la procedura associata per generare un gestore eventi in fase di esecuzione tramite un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-119">For details, see the accompanying procedure, for generating an event handler at run time by using a dynamic method.</span></span>  
  
     [!code-cpp[HookUpDelegate#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#6)]
     [!code-csharp[HookUpDelegate#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#6)]
     [!code-vb[HookUpDelegate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#6)]  
  
5. <span data-ttu-id="4d8e9-120">Creare un'istanza del delegato usando il metodo <xref:System.Delegate.CreateDelegate%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-120">Create an instance of the delegate, using the <xref:System.Delegate.CreateDelegate%2A> method.</span></span> <span data-ttu-id="4d8e9-121">Poiché il metodo è statico (`Shared` in Visual Basic), è necessario specificare il tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-121">This method is static (`Shared` in Visual Basic), so the delegate type must be supplied.</span></span> <span data-ttu-id="4d8e9-122">Si consiglia di usare gli overload del metodo <xref:System.Delegate.CreateDelegate%2A> che accettano <xref:System.Reflection.MethodInfo>.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-122">Using the overloads of <xref:System.Delegate.CreateDelegate%2A> that take a <xref:System.Reflection.MethodInfo> is recommended.</span></span>  
  
     [!code-cpp[HookUpDelegate#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#7)]
     [!code-csharp[HookUpDelegate#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#7)]
     [!code-vb[HookUpDelegate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#7)]  
  
6. <span data-ttu-id="4d8e9-123">Ottenere il metodo della funzione di accesso `add` e richiamarlo per associare l'evento.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-123">Get the `add` accessor method and invoke it to hook up the event.</span></span> <span data-ttu-id="4d8e9-124">Tutti gli eventi hanno una funzione di accesso `add` e una funzione di accesso `remove` nascoste dalla sintassi dei linguaggi di alto livello.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-124">All events have an `add` accessor and a `remove` accessor, which are hidden by the syntax of high-level languages.</span></span> <span data-ttu-id="4d8e9-125">Ad esempio, C# usa l'operatore `+=` per associare gli eventi e Visual Basic usa l'[istruzione AddHandler](../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4d8e9-125">For example, C# uses the `+=` operator to hook up events, and Visual Basic uses the [AddHandler statement](../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="4d8e9-126">Il codice seguente ottiene la funzione di accesso `add` dell'evento <xref:System.Windows.Forms.Control.Click> e la richiama con associazione tardiva passando l'istanza del delegato.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-126">The following code gets the `add` accessor of the <xref:System.Windows.Forms.Control.Click> event and invokes it late-bound, passing in the delegate instance.</span></span> <span data-ttu-id="4d8e9-127">Gli argomenti devono essere passati come matrice.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-127">The arguments must be passed as an array.</span></span>  
  
     [!code-cpp[HookUpDelegate#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#8)]
     [!code-csharp[HookUpDelegate#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#8)]
     [!code-vb[HookUpDelegate#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#8)]  
  
7. <span data-ttu-id="4d8e9-128">Verificare l'evento.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-128">Test the event.</span></span> <span data-ttu-id="4d8e9-129">Il codice seguente illustra il form definito nell'esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-129">The following code shows the form defined in the code example.</span></span> <span data-ttu-id="4d8e9-130">Se si fa clic sul form, viene richiamato il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-130">Clicking the form invokes the event handler.</span></span>  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
<a name="procedureSection1"></a>
### <a name="to-generate-an-event-handler-at-run-time-by-using-a-dynamic-method"></a><span data-ttu-id="4d8e9-131">Per generare un gestore dell'evento in fase di esecuzione usando un metodo dinamico</span><span class="sxs-lookup"><span data-stu-id="4d8e9-131">To generate an event handler at run time by using a dynamic method</span></span>  
  
1. <span data-ttu-id="4d8e9-132">I metodi per la gestione degli eventi possono essere generati in fase di esecuzione usando metodi dinamici leggeri e reflection emit.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-132">Event-handler methods can be generated at run time, using lightweight dynamic methods and reflection emit.</span></span> <span data-ttu-id="4d8e9-133">Per costruire un gestore dell'evento, sono necessari il tipo restituito e i tipi di parametro del delegato,</span><span class="sxs-lookup"><span data-stu-id="4d8e9-133">To construct an event handler, you need the return type and parameter types of the delegate.</span></span> <span data-ttu-id="4d8e9-134">che possono essere ottenuti esaminando il metodo `Invoke` del delegato.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-134">These can be obtained by examining the delegate's `Invoke` method.</span></span> <span data-ttu-id="4d8e9-135">Il codice seguente usa i metodi `GetDelegateReturnType` e `GetDelegateParameterTypes` per ottenere queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-135">The following code uses the `GetDelegateReturnType` and `GetDelegateParameterTypes` methods to obtain this information.</span></span> <span data-ttu-id="4d8e9-136">Il codice per questi metodi è disponibile nella sezione Esempio più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-136">The code for these methods can be found in the Example section later in this topic.</span></span>  
  
     <span data-ttu-id="4d8e9-137">Poiché non è necessario assegnare un nome a <xref:System.Reflection.Emit.DynamicMethod>, è possibile usare la stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-137">It is not necessary to name a <xref:System.Reflection.Emit.DynamicMethod>, so the empty string can be used.</span></span> <span data-ttu-id="4d8e9-138">Nel codice seguente l'ultimo argomento associa il metodo dinamico al tipo corrente, concedendo al delegato l'accesso a tutti i membri pubblici e privati della classe `Example`.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-138">In the following code, the last argument associates the dynamic method with the current type, giving the delegate access to all the public and private members of the `Example` class.</span></span>  
  
     [!code-cpp[HookUpDelegate#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#9)]
     [!code-csharp[HookUpDelegate#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#9)]
     [!code-vb[HookUpDelegate#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#9)]  
  
2. <span data-ttu-id="4d8e9-139">Generare il corpo di un metodo.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-139">Generate a method body.</span></span> <span data-ttu-id="4d8e9-140">Il metodo carica una stringa, chiama l'overload del metodo <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> che accetta una stringa, estrae il valore restituito dallo stack perché il gestore non ha alcun tipo restituito e termina.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-140">This method loads a string, calls the overload of the <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> method that takes a string, pops the return value off the stack (because the handler has no return type), and returns.</span></span> <span data-ttu-id="4d8e9-141">Per altre informazioni sulla creazione di metodi dinamici, vedere [Procedura: Definire ed eseguire metodi dinamici](how-to-define-and-execute-dynamic-methods.md).</span><span class="sxs-lookup"><span data-stu-id="4d8e9-141">To learn more about emitting dynamic methods, see [How to: Define and Execute Dynamic Methods](how-to-define-and-execute-dynamic-methods.md).</span></span>  
  
     [!code-cpp[HookUpDelegate#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#10)]
     [!code-csharp[HookUpDelegate#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#10)]
     [!code-vb[HookUpDelegate#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#10)]  
  
3. <span data-ttu-id="4d8e9-142">Completare il metodo dinamico chiamando il relativo metodo <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-142">Complete the dynamic method by calling its <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> method.</span></span> <span data-ttu-id="4d8e9-143">Usare la funzione di accesso `add` per aggiungere il delegato all'elenco di chiamate per l'evento.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-143">Use the `add` accessor to add the delegate to the invocation list for the event.</span></span>  
  
     [!code-cpp[HookUpDelegate#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#11)]
     [!code-csharp[HookUpDelegate#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#11)]
     [!code-vb[HookUpDelegate#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#11)]  
  
4. <span data-ttu-id="4d8e9-144">Verificare l'evento.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-144">Test the event.</span></span> <span data-ttu-id="4d8e9-145">Il codice seguente carica il form definito nell'esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-145">The following code loads the form defined in the code example.</span></span> <span data-ttu-id="4d8e9-146">Fare clic sul form per richiamare il gestore dell'evento predefinito e il gestore creato.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-146">Clicking the form invokes both the predefined event handler and the emitted event handler.</span></span>  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="4d8e9-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d8e9-147">Example</span></span>  
 <span data-ttu-id="4d8e9-148">L'esempio di codice seguente illustra come associare un metodo esistente a un evento tramite reflection e come usare la classe <xref:System.Reflection.Emit.DynamicMethod> per creare un metodo in fase di esecuzione e associarlo a un evento.</span><span class="sxs-lookup"><span data-stu-id="4d8e9-148">The following code example shows how to hook up an existing method to an event using reflection, and also how to use the <xref:System.Reflection.Emit.DynamicMethod> class to emit a method at run time and hook it up to an event.</span></span>  
  
 [!code-cpp[HookUpDelegate#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#1)]
 [!code-csharp[HookUpDelegate#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#1)]
 [!code-vb[HookUpDelegate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4d8e9-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d8e9-149">See also</span></span>

- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Emit.DynamicMethod>
- <xref:System.Activator.CreateInstance%2A>
- <xref:System.Delegate.CreateDelegate%2A>
- [<span data-ttu-id="4d8e9-150">Procedura: Definire ed eseguire metodi dinamici</span><span class="sxs-lookup"><span data-stu-id="4d8e9-150">How to: Define and Execute Dynamic Methods</span></span>](how-to-define-and-execute-dynamic-methods.md)
- [<span data-ttu-id="4d8e9-151">Reflection</span><span class="sxs-lookup"><span data-stu-id="4d8e9-151">Reflection</span></span>](reflection.md)
