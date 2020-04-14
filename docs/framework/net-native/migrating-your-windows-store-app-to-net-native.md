---
title: Migrazione dell'app di Windows Store a .NET Native
ms.date: 03/30/2017
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
ms.openlocfilehash: 36f9ac4647b349ff379869f3415a5fb9e55228e3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81241945"
---
# <a name="migrate-your-windows-store-app-to-net-native"></a><span data-ttu-id="05feb-102">Eseguire la migrazione dell'app di Windows Store a .NET NativeMigrate Your Windows Store App to .NET Native</span><span class="sxs-lookup"><span data-stu-id="05feb-102">Migrate Your Windows Store App to .NET Native</span></span>

<span data-ttu-id="05feb-103">.NET Native fornisce la compilazione statica di app in Windows Store o nel computer dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="05feb-103">.NET Native provides static compilation of apps in the Windows Store or on the developer’s computer.</span></span> <span data-ttu-id="05feb-104">Ciò differisce dalla compilazione dinamica eseguita per applicazioni Windows Store dal compilatore just-in-time (JIT) o il [Native Image Generator (Ngen.exe)](../tools/ngen-exe-native-image-generator.md) sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="05feb-104">This differs from the dynamic compilation performed for Windows Store apps by the just-in-time (JIT) compiler or the [Native Image Generator (Ngen.exe)](../tools/ngen-exe-native-image-generator.md) on the device.</span></span> <span data-ttu-id="05feb-105">Nonostante le differenze, .NET Native tenta di mantenere la compatibilità con [.NET per le app](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29)di Windows Store.</span><span class="sxs-lookup"><span data-stu-id="05feb-105">Despite the differences, .NET Native tries to maintain compatibility with the [.NET for Windows Store apps](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29).</span></span> <span data-ttu-id="05feb-106">Per la maggior parte, gli elementi che funzionano in .NET per le app di Windows Store funzionano anche con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-106">For the most part, things that work on the .NET for Windows Store apps also work with .NET Native.</span></span>  <span data-ttu-id="05feb-107">Tuttavia, in alcuni casi, è possibile riscontrare differenze di comportamento.</span><span class="sxs-lookup"><span data-stu-id="05feb-107">However, in some cases, you may encounter behavioral changes.</span></span> <span data-ttu-id="05feb-108">Questo documento illustra queste differenze tra .NET standard per le app di Windows Store e .NET Native nelle aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="05feb-108">This document discusses these differences between the standard .NET for Windows Store apps and .NET Native in the following areas:</span></span>

- [<span data-ttu-id="05feb-109">Differenze generali di runtime</span><span class="sxs-lookup"><span data-stu-id="05feb-109">General runtime differences</span></span>](#Runtime)

- [<span data-ttu-id="05feb-110">Differenze di programmazione dinamica</span><span class="sxs-lookup"><span data-stu-id="05feb-110">Dynamic programming differences</span></span>](#Dynamic)

- [<span data-ttu-id="05feb-111">Altre differenze correlate alla reflection</span><span class="sxs-lookup"><span data-stu-id="05feb-111">Other reflection-related differences</span></span>](#Reflection)

- [<span data-ttu-id="05feb-112">Scenari e API non supportati</span><span class="sxs-lookup"><span data-stu-id="05feb-112">Unsupported scenarios and APIs</span></span>](#Unsupported)

- [<span data-ttu-id="05feb-113">Differenze di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="05feb-113">Visual Studio differences</span></span>](#VS)

<a name="Runtime"></a>

## <a name="general-runtime-differences"></a><span data-ttu-id="05feb-114">Differenze generali di runtime</span><span class="sxs-lookup"><span data-stu-id="05feb-114">General runtime differences</span></span>

- <span data-ttu-id="05feb-115">Le eccezioni, <xref:System.TypeLoadException>ad esempio , generate dal compilatore JIT quando un'app viene eseguita in Common Language Runtime (CLR) in genere generano errori in fase di compilazione durante l'elaborazione da parte di .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-115">Exceptions, such as <xref:System.TypeLoadException>, that are thrown by the JIT compiler when an app runs on the common language runtime (CLR) generally result in compile-time errors when processed by .NET Native.</span></span>

- <span data-ttu-id="05feb-116">Non chiamare il metodo <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> da un thread UI dell'app.</span><span class="sxs-lookup"><span data-stu-id="05feb-116">Don't call the <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> method from an app's UI thread.</span></span> <span data-ttu-id="05feb-117">Ciò può causare un deadlock in .NET Native.This can result in a deadlock on .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-117">This can result in a deadlock on .NET Native.</span></span>

- <span data-ttu-id="05feb-118">Non fare affidamento sull'ordine di chiamata del costruttore di classe statica.</span><span class="sxs-lookup"><span data-stu-id="05feb-118">Don't rely on static class constructor invocation ordering.</span></span> <span data-ttu-id="05feb-119">In .NET Native, l'ordine di chiamata è diverso dall'ordine nel runtime standard.</span><span class="sxs-lookup"><span data-stu-id="05feb-119">In .NET Native, the invocation order is different from the order on the standard runtime.</span></span> <span data-ttu-id="05feb-120">(anche con il runtime standard, non è consigliabile fare affidamento sull'ordine di esecuzione dei costruttori di classe statici).</span><span class="sxs-lookup"><span data-stu-id="05feb-120">(Even with the standard runtime, you shouldn't rely on the order of execution of static class constructors.)</span></span>

- <span data-ttu-id="05feb-121">Un ciclo infinito senza eseguire una chiamata (ad esempio, `while(true);`) su qualsiasi thread può comportare l'arresto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="05feb-121">Infinite looping without making a call (for example, `while(true);`) on any thread may bring the app to a halt.</span></span> <span data-ttu-id="05feb-122">Allo stesso modo, attese lunghe o infinite possono portare all'arresto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="05feb-122">Similarly, large or infinite waits may bring the app to a halt.</span></span>

- <span data-ttu-id="05feb-123">Alcuni cicli di inizializzazione generici non generano eccezioni in .NET Native.Certain generic initialization cycles don't throw exceptions in .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-123">Certain generic initialization cycles don't throw exceptions in .NET Native.</span></span> <span data-ttu-id="05feb-124">Ad esempio, il codice seguente genera un'eccezione <xref:System.TypeLoadException> sul CLR standard,</span><span class="sxs-lookup"><span data-stu-id="05feb-124">For example, the following code throws a <xref:System.TypeLoadException> exception on the standard CLR.</span></span> <span data-ttu-id="05feb-125">In .NET Native, non lo fa.</span><span class="sxs-lookup"><span data-stu-id="05feb-125">In .NET Native, it doesn't.</span></span>

  [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]

- <span data-ttu-id="05feb-126">In alcuni casi, .NET Native fornisce diverse implementazioni delle librerie di classi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05feb-126">In some cases, .NET Native provides different implementations of .NET Framework class libraries.</span></span> <span data-ttu-id="05feb-127">Un oggetto restituito da un metodo implementerà sempre i membri del tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="05feb-127">An object returned from a method will always implement the members of the returned type.</span></span> <span data-ttu-id="05feb-128">Tuttavia, poiché l'implementazione di supporto è diversa, potrebbe non essere possibile eseguire il cast per la stessa raccolta di tipi come su altre piattaforme di.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05feb-128">However, since its backing implementation is different, you may not be able to cast it to the same set of types as you could on other .NET Framework platforms.</span></span> <span data-ttu-id="05feb-129">Ad esempio, in alcuni casi, potrebbe non essere possibile eseguire il cast dell'oggetto di interfaccia <xref:System.Collections.Generic.IEnumerable%601> restituito da metodi quali <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> o <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> a `T[]`.</span><span class="sxs-lookup"><span data-stu-id="05feb-129">For example, in some cases, you may not be able to cast the <xref:System.Collections.Generic.IEnumerable%601> interface object returned by methods such as <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> or <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> to `T[]`.</span></span>

- <span data-ttu-id="05feb-130">La cache di WinInet non è abilitata per impostazione predefinita in .NET per le app di Windows Store, ma si trova in .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-130">The WinInet cache isn't enabled by default on .NET for Windows Store apps, but it is on .NET Native.</span></span> <span data-ttu-id="05feb-131">Questo migliora le prestazioni, ma ha implicazioni sul working set.</span><span class="sxs-lookup"><span data-stu-id="05feb-131">This improves performance but has working set implications.</span></span> <span data-ttu-id="05feb-132">Non è necessaria alcuna azione da parte dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="05feb-132">No developer action is necessary.</span></span>

<a name="Dynamic"></a>

## <a name="dynamic-programming-differences"></a><span data-ttu-id="05feb-133">Differenze di programmazione dinamica</span><span class="sxs-lookup"><span data-stu-id="05feb-133">Dynamic programming differences</span></span>

<span data-ttu-id="05feb-134">.NET Native collega in modo statico nel codice da .NET Framework per rendere l'app di codice locale per ottenere le massime prestazioni.</span><span class="sxs-lookup"><span data-stu-id="05feb-134">.NET Native statically links in code from the .NET Framework to make the code app-local for maximum performance.</span></span> <span data-ttu-id="05feb-135">Tuttavia, le dimensioni binarie devono rimanere ridotte, in modo da non consentire il passaggio dell'intero.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05feb-135">However, binary sizes have to remain small, so the entire .NET Framework can't be brought in.</span></span> <span data-ttu-id="05feb-136">Il compilatore .NET Native risolve questa limitazione utilizzando un riduttore di dipendenze che rimuove i riferimenti al codice inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="05feb-136">The .NET Native compiler resolves this limitation by using a dependency reducer that removes references to unused code.</span></span> <span data-ttu-id="05feb-137">Tuttavia, .NET Native potrebbe non gestire o generare alcune informazioni sul tipo e il codice quando tali informazioni non possono essere dedotte staticamente in fase di compilazione, ma vengono recuperate in modo dinamico in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="05feb-137">However, .NET Native might not maintain or generate some type information and code when that information can't be inferred statically at compile time, but instead is retrieved dynamically at runtime.</span></span>

<span data-ttu-id="05feb-138">.NET Native abilita la reflection e la programmazione dinamica.</span><span class="sxs-lookup"><span data-stu-id="05feb-138">.NET Native does enable reflection and dynamic programming.</span></span> <span data-ttu-id="05feb-139">Tuttavia, non tutti i tipi possono essere contrassegnati per la reflection, perché ciò rende eccessive le dimensioni del codice generato (soprattutto perché la reflection sulle API pubbliche in .NET Framework è supportata).</span><span class="sxs-lookup"><span data-stu-id="05feb-139">However, not all types can be marked for reflection, because this would make the generated code size too large (especially because reflecting on public APIs in the .NET Framework is supported).</span></span> <span data-ttu-id="05feb-140">Il compilatore .NET Native effettua scelte intelligenti su quali tipi devono supportare la reflection e mantiene i metadati e genera codice solo per tali tipi.</span><span class="sxs-lookup"><span data-stu-id="05feb-140">The .NET Native compiler makes smart choices about which types should support reflection, and it keeps the metadata and generates code only for those types.</span></span>

<span data-ttu-id="05feb-141">Ad esempio, il data binding richiede che un'applicazione possa eseguire il mapping dei nomi di proprietà alle funzioni.</span><span class="sxs-lookup"><span data-stu-id="05feb-141">For example, data binding requires an app to be able to map property names to functions.</span></span> <span data-ttu-id="05feb-142">In .NET per applicazioni Windows Store, Common Language Runtime usa automaticamente la reflection per fornire questa funzionalità per i tipi gestiti e i tipi nativi disponibili al pubblico.</span><span class="sxs-lookup"><span data-stu-id="05feb-142">In .NET for Windows Store apps, the common language runtime automatically uses reflection to provide this capability for managed types and publicly available native types.</span></span> <span data-ttu-id="05feb-143">In .NET Native, il compilatore include automaticamente i metadati per i tipi a cui si associano i dati.</span><span class="sxs-lookup"><span data-stu-id="05feb-143">In .NET Native, the compiler automatically includes metadata for types to which you bind data.</span></span>

<span data-ttu-id="05feb-144">Il compilatore .NET Native può inoltre <xref:System.Collections.Generic.List%601> gestire <xref:System.Collections.Generic.Dictionary%602>tipi generici di uso comune, ad esempio e , che funzionano senza richiedere alcun suggerimento o direttiva.</span><span class="sxs-lookup"><span data-stu-id="05feb-144">The .NET Native compiler can also handle commonly used generic types such as <xref:System.Collections.Generic.List%601> and <xref:System.Collections.Generic.Dictionary%602>, which work without requiring any hints or directives.</span></span> <span data-ttu-id="05feb-145">È supportata anche la parola chiave [dinamica](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) entro certi limiti.</span><span class="sxs-lookup"><span data-stu-id="05feb-145">The [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) keyword is also supported within certain limits.</span></span>

> [!NOTE]
> <span data-ttu-id="05feb-146">È necessario testare tutti i percorsi di codice dinamico accuratamente quando si esegue il porting dell'app in .NET Native.You should test all dynamic code paths thoroughly when porting your app to .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-146">You should test all dynamic code paths thoroughly when porting your app to .NET Native.</span></span>

<span data-ttu-id="05feb-147">La configurazione predefinita per .NET Native è sufficiente per la maggior parte degli sviluppatori, ma alcuni sviluppatori potrebbero voler ottimizzare le configurazioni utilizzando un file di direttive di runtime (con estensione rd.xml).</span><span class="sxs-lookup"><span data-stu-id="05feb-147">The default configuration for .NET Native is sufficient for most developers, but some developers might want to fine- tune their configurations by using a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="05feb-148">Inoltre, in alcuni casi, il compilatore nativo .NET non è in grado di determinare quali metadati devono essere disponibili per la reflection e si basa sui suggerimenti, in particolare nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="05feb-148">In addition, in some cases, the .NET Native compiler is unable to determine which metadata must be available for reflection and relies on hints, particularly in the following cases:</span></span>

- <span data-ttu-id="05feb-149">Alcuni costrutti come <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> e <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> non possono essere determinati staticamente.</span><span class="sxs-lookup"><span data-stu-id="05feb-149">Some constructs like <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> and <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> can't be determined statically.</span></span>

- <span data-ttu-id="05feb-150">Poiché il compilatore non può determinare le istanze create, un tipo generico di cui si vuole effettuare la reflection deve essere specificato dalle direttive di runtime.</span><span class="sxs-lookup"><span data-stu-id="05feb-150">Because the compiler can't determine the instantiations, a generic type that you want to reflect on has to be specified by runtime directives.</span></span> <span data-ttu-id="05feb-151">Ciò non solo perché è necessario includere tutto il codice, ma anche perché la reflection sui tipi può creare un ciclo infinito (ad esempio, quando un metodo generico viene richiamato su un tipo generico).</span><span class="sxs-lookup"><span data-stu-id="05feb-151">This isn't just because all code must be included, but because reflection on generic types can form an infinite cycle (for example, when a generic method is invoked on a generic type).</span></span>

> [!NOTE]
> <span data-ttu-id="05feb-152">Le direttive di runtime sono definite in un file nelle direttive di runtime (rd.xml).</span><span class="sxs-lookup"><span data-stu-id="05feb-152">Runtime directives are defined in a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="05feb-153">Per informazioni generali sull'uso di questo file, vedere [Introduzione](getting-started-with-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="05feb-153">For general information about using this file, see [Getting Started](getting-started-with-net-native.md).</span></span> <span data-ttu-id="05feb-154">Per informazioni sulle direttive di runtime, vedere [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="05feb-154">For information about the runtime directives, see [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span></span>

<span data-ttu-id="05feb-155">.NET Native include anche strumenti di profilatura che consentono allo sviluppatore di determinare quali tipi esterni al set predefinito devono supportare la reflection.</span><span class="sxs-lookup"><span data-stu-id="05feb-155">.NET Native also includes profiling tools that help the developer determine which types outside the default set should support reflection.</span></span>

<a name="Reflection"></a>

## <a name="other-reflection-related-differences"></a><span data-ttu-id="05feb-156">Altre differenze correlate alla reflection</span><span class="sxs-lookup"><span data-stu-id="05feb-156">Other reflection-related differences</span></span>

<span data-ttu-id="05feb-157">Esistono diverse altre differenze di comportamento correlate alla reflection tra .NET per le app di Windows Store e .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-157">There are a number of other individual reflection-related differences in behavior between the .NET for Windows Store apps and .NET Native.</span></span>

<span data-ttu-id="05feb-158">In .NET Native:</span><span class="sxs-lookup"><span data-stu-id="05feb-158">In .NET Native:</span></span>

- <span data-ttu-id="05feb-159">La reflection privata su tipi e membri della libreria di classi .NET Framework non è supportata.</span><span class="sxs-lookup"><span data-stu-id="05feb-159">Private reflection over types and members in the .NET Framework class library is not supported.</span></span> <span data-ttu-id="05feb-160">È tuttavia possibile riflettere sui propri tipi e membri privati, nonché sui tipi e membri nelle librerie di terze parti.</span><span class="sxs-lookup"><span data-stu-id="05feb-160">You can, however, reflect over your own private types and members, as well as types and members in third-party libraries.</span></span>

- <span data-ttu-id="05feb-161">La proprietà <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> restituisce correttamente `false` per un oggetto <xref:System.Reflection.ParameterInfo> che rappresenta un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="05feb-161">The <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> property correctly returns `false` for a <xref:System.Reflection.ParameterInfo> object that represents a return value.</span></span> <span data-ttu-id="05feb-162">In .NET per applicazioni Windows Store, restituisce `true`.</span><span class="sxs-lookup"><span data-stu-id="05feb-162">In the .NET for Windows Store apps, it returns `true`.</span></span> <span data-ttu-id="05feb-163">IL (Intermediate language) non supporta direttamente questa funzione, e quindi l'interpretazione viene lasciata al linguaggio.</span><span class="sxs-lookup"><span data-stu-id="05feb-163">Intermediate language (IL) doesn’t support this directly, and interpretation is left to the language.</span></span>

- <span data-ttu-id="05feb-164">I membri pubblici sulle strutture <xref:System.RuntimeFieldHandle> e <xref:System.RuntimeMethodHandle> non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="05feb-164">Public members on the <xref:System.RuntimeFieldHandle> and <xref:System.RuntimeMethodHandle> structures aren't supported.</span></span> <span data-ttu-id="05feb-165">Questi tipi sono supportati solo per LINQ, gli alberi delle espressioni e l'inizializzazione di matrice statica.</span><span class="sxs-lookup"><span data-stu-id="05feb-165">These types are supported only for LINQ, expression trees, and static array initialization.</span></span>

- <span data-ttu-id="05feb-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> e <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> includono membri nascosi in classi di base e perciò potrebbero essere sottoposti a override esplicito.</span><span class="sxs-lookup"><span data-stu-id="05feb-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> and <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> include hidden members in base classes and thus may be overridden without explicit overrides.</span></span> <span data-ttu-id="05feb-167">Ciò vale anche per gli altri metodi [RuntimeReflectionExtensions.GetRuntime\*](xref:System.Reflection.RuntimeReflectionExtensions) .</span><span class="sxs-lookup"><span data-stu-id="05feb-167">This is also true of other [RuntimeReflectionExtensions.GetRuntime\*](xref:System.Reflection.RuntimeReflectionExtensions) methods.</span></span>

- <span data-ttu-id="05feb-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> e <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> non hanno esito negativo quando si prova a creare determinate combinazioni (ad esempio, una matrice di ByRef).</span><span class="sxs-lookup"><span data-stu-id="05feb-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> and <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> don't fail when you try to create certain combinations (for example, an array of byrefs).</span></span>

- <span data-ttu-id="05feb-169">Non è possibile usare la reflection per richiamare i membri con parametri di puntatore.</span><span class="sxs-lookup"><span data-stu-id="05feb-169">You can't use reflection to invoke members that have pointer parameters.</span></span>

- <span data-ttu-id="05feb-170">Non è possibile usare la reflection per ottenere o impostare un campo del puntatore.</span><span class="sxs-lookup"><span data-stu-id="05feb-170">You can't use reflection to get or set a pointer field.</span></span>

- <span data-ttu-id="05feb-171">Quando il conteggio degli argomenti è errato e il tipo di uno <xref:System.ArgumentException> degli <xref:System.Reflection.TargetParameterCountException>argomenti non è corretto, .NET Native genera un'eccezione anziché un oggetto .</span><span class="sxs-lookup"><span data-stu-id="05feb-171">When the argument count is wrong and the type of one of the arguments is incorrect, .NET Native throws an <xref:System.ArgumentException> instead of a <xref:System.Reflection.TargetParameterCountException>.</span></span>

- <span data-ttu-id="05feb-172">In genere la serializzazione binaria delle eccezioni non è supportata.</span><span class="sxs-lookup"><span data-stu-id="05feb-172">Binary serialization of exceptions is generally not supported.</span></span> <span data-ttu-id="05feb-173">Di conseguenza, è possibile aggiungere gli oggetti non serializzabili al dizionario <xref:System.Exception.Data%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="05feb-173">As a result, non-serializable objects can be added to the <xref:System.Exception.Data%2A?displayProperty=nameWithType> dictionary.</span></span>

<a name="Unsupported"></a>

## <a name="unsupported-scenarios-and-apis"></a><span data-ttu-id="05feb-174">Scenari e API non supportati</span><span class="sxs-lookup"><span data-stu-id="05feb-174">Unsupported scenarios and APIs</span></span>

<span data-ttu-id="05feb-175">Nelle sezioni seguenti vengono elencati gli scenari e le API non supportati per lo sviluppo generale, l'interoperabilità e le tecnologie, ad esempio HTTPClient e Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="05feb-175">The following sections list unsupported scenarios and APIs for general development, interop, and technologies such as HTTPClient and Windows Communication Foundation (WCF):</span></span>

- [<span data-ttu-id="05feb-176">Sviluppo generale</span><span class="sxs-lookup"><span data-stu-id="05feb-176">General development</span></span>](#General)

- [<span data-ttu-id="05feb-177">HttpClient</span><span class="sxs-lookup"><span data-stu-id="05feb-177">HttpClient</span></span>](#HttpClient)

- [<span data-ttu-id="05feb-178">Interop</span><span class="sxs-lookup"><span data-stu-id="05feb-178">Interop</span></span>](#Interop)

- [<span data-ttu-id="05feb-179">API non supportate</span><span class="sxs-lookup"><span data-stu-id="05feb-179">Unsupported APIs</span></span>](#APIs)

<a name="General"></a>

### <a name="general-development-differences"></a><span data-ttu-id="05feb-180">Differenze generali per lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="05feb-180">General development differences</span></span>

<span data-ttu-id="05feb-181">**Tipi valore**</span><span class="sxs-lookup"><span data-stu-id="05feb-181">**Value types**</span></span>

- <span data-ttu-id="05feb-182">Se si esegue l'override dei metodi <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> e <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> per un tipo di valore, non chiamare le implementazioni della classe di base.</span><span class="sxs-lookup"><span data-stu-id="05feb-182">If you override the <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> and <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> methods for a value type, don't call the base class implementations.</span></span> <span data-ttu-id="05feb-183">In .NET per applicazioni Windows Store, questi metodi si basano sulla reflection.</span><span class="sxs-lookup"><span data-stu-id="05feb-183">In .NET for Windows Store apps, these methods rely on reflection.</span></span> <span data-ttu-id="05feb-184">In fase di compilazione, .NET Native genera un'implementazione che non si basa sulla reflection di runtime.</span><span class="sxs-lookup"><span data-stu-id="05feb-184">At compile time, .NET Native generates an implementation that doesn't rely on runtime reflection.</span></span> <span data-ttu-id="05feb-185">Ciò significa che se non si esegue l'override di questi due metodi, funzioneranno come previsto, perché .NET Native genera l'implementazione in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="05feb-185">This means that if you don't override these two methods, they will work as expected, because .NET Native generates the implementation at compile time.</span></span> <span data-ttu-id="05feb-186">Tuttavia, se si esegue l'override di questi metodi, ma si chiama l'implementazione della classe base verrà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="05feb-186">However, overriding these methods but calling the base class implementation results in an exception.</span></span>

- <span data-ttu-id="05feb-187">Non sono supportati i tipi di valore superiori a un megabyte.</span><span class="sxs-lookup"><span data-stu-id="05feb-187">Value types larger than one megabyte aren't supported.</span></span>

- <span data-ttu-id="05feb-188">I tipi di valore non possono avere un costruttore senza parametri in .NET Native.Value types can't have a parameterless constructor in .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-188">Value types can't have a parameterless constructor in .NET Native.</span></span> <span data-ttu-id="05feb-189">(C'è e Visual Basic proibiscono i costruttori senza parametri sui tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="05feb-189">(C# and Visual Basic prohibit parameterless constructors on value types.</span></span> <span data-ttu-id="05feb-190">Tuttavia, è possibile crearli in IL).</span><span class="sxs-lookup"><span data-stu-id="05feb-190">However, these can be created in IL.)</span></span>

<span data-ttu-id="05feb-191">**Matrici**</span><span class="sxs-lookup"><span data-stu-id="05feb-191">**Arrays**</span></span>

- <span data-ttu-id="05feb-192">Non sono supportate le matrici con limite inferiore diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="05feb-192">Arrays with a lower bound other than zero aren't supported.</span></span> <span data-ttu-id="05feb-193">Solitamente, queste matrici vengono create chiamando l'overload di <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="05feb-193">Typically, these arrays are created by calling the <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> overload.</span></span>

- <span data-ttu-id="05feb-194">Non è supportata la creazione dinamica di matrici multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="05feb-194">Dynamic creation of multidimensional arrays isn't supported.</span></span> <span data-ttu-id="05feb-195">Tali matrici vengono in genere creata dalla chiamata di un overload del metodo <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> che include un parametro `lengths` oppure dalla chiamata del metodo <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="05feb-195">Such arrays are typically created by calling an overload of the <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> method that includes a `lengths` parameter, or by calling the <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="05feb-196">Le matrici multidimensionali con quattro o più dimensioni non sono supportate; vale a dire il relativo valore della proprietà <xref:System.Array.Rank%2A?displayProperty=nameWithType> è 4 o superiore.</span><span class="sxs-lookup"><span data-stu-id="05feb-196">Multidimensional arrays that have four or more dimensions aren't supported; that is, their <xref:System.Array.Rank%2A?displayProperty=nameWithType> property value is four or greater.</span></span> <span data-ttu-id="05feb-197">Usare invece le [matrici irregolari](../../csharp/programming-guide/arrays/jagged-arrays.md) (una matrice di matrici).</span><span class="sxs-lookup"><span data-stu-id="05feb-197">Use [jagged arrays](../../csharp/programming-guide/arrays/jagged-arrays.md) (an array of arrays) instead.</span></span> <span data-ttu-id="05feb-198">Ad esempio, `array[x,y,z]` non è valido, mentre `array[x][y][z]` è valido.</span><span class="sxs-lookup"><span data-stu-id="05feb-198">For example, `array[x,y,z]` is invalid, but `array[x][y][z]` isn't.</span></span>

- <span data-ttu-id="05feb-199">La varianza per le matrici multidimensionali non è supportata e causa un'eccezione <xref:System.InvalidCastException> in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="05feb-199">Variance for multidimensional arrays isn't supported and causes an <xref:System.InvalidCastException> exception at run time.</span></span>

<span data-ttu-id="05feb-200">**Generics**</span><span class="sxs-lookup"><span data-stu-id="05feb-200">**Generics**</span></span>

- <span data-ttu-id="05feb-201">L'espansione di tipo generico infinito genera un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="05feb-201">Infinite generic type expansion results in a compiler error.</span></span> <span data-ttu-id="05feb-202">Ad esempio, questo codice non viene compilato:</span><span class="sxs-lookup"><span data-stu-id="05feb-202">For example, this code fails to compile:</span></span>

  [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]

<span data-ttu-id="05feb-203">**Puntatori**</span><span class="sxs-lookup"><span data-stu-id="05feb-203">**Pointers**</span></span>

- <span data-ttu-id="05feb-204">Le matrici di puntatori non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="05feb-204">Arrays of pointers aren't supported.</span></span>

- <span data-ttu-id="05feb-205">Non è possibile usare la reflection per ottenere o impostare un campo del puntatore.</span><span class="sxs-lookup"><span data-stu-id="05feb-205">You can't use reflection to get or set a pointer field.</span></span>

<span data-ttu-id="05feb-206">**Serializzazione**</span><span class="sxs-lookup"><span data-stu-id="05feb-206">**Serialization**</span></span>

<span data-ttu-id="05feb-207">L'attributo <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> non è supportato.</span><span class="sxs-lookup"><span data-stu-id="05feb-207">The <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> attribute isn't supported.</span></span> <span data-ttu-id="05feb-208">Usare piuttosto l'attributo <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> .</span><span class="sxs-lookup"><span data-stu-id="05feb-208">Use the <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> attribute instead.</span></span>

<span data-ttu-id="05feb-209">**Risorse**</span><span class="sxs-lookup"><span data-stu-id="05feb-209">**Resources**</span></span>

<span data-ttu-id="05feb-210">L'uso di risorse localizzate con la classe <xref:System.Diagnostics.Tracing.EventSource> non è supportato.</span><span class="sxs-lookup"><span data-stu-id="05feb-210">The use of localized resources with the <xref:System.Diagnostics.Tracing.EventSource> class isn't supported.</span></span> <span data-ttu-id="05feb-211">La proprietà <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> non definisce le risorse localizzate.</span><span class="sxs-lookup"><span data-stu-id="05feb-211">The <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> property doesn't define localized resources.</span></span>

<span data-ttu-id="05feb-212">**Delegati**</span><span class="sxs-lookup"><span data-stu-id="05feb-212">**Delegates**</span></span>

<span data-ttu-id="05feb-213">`Delegate.BeginInvoke` e `Delegate.EndInvoke` non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="05feb-213">`Delegate.BeginInvoke` and `Delegate.EndInvoke` aren't supported.</span></span>

<span data-ttu-id="05feb-214">**Varie API**</span><span class="sxs-lookup"><span data-stu-id="05feb-214">**Miscellaneous APIs**</span></span>

- <span data-ttu-id="05feb-215">La proprietà [TypeInfo.GUID](xref:System.Type.GUID) <xref:System.PlatformNotSupportedException> genera un'eccezione se un <xref:System.Runtime.InteropServices.GuidAttribute> attributo non viene applicato al tipo.</span><span class="sxs-lookup"><span data-stu-id="05feb-215">The [TypeInfo.GUID](xref:System.Type.GUID) property throws a <xref:System.PlatformNotSupportedException> exception if a <xref:System.Runtime.InteropServices.GuidAttribute> attribute isn't applied to the type.</span></span> <span data-ttu-id="05feb-216">Il GUID viene usato principalmente per il supporto COM.</span><span class="sxs-lookup"><span data-stu-id="05feb-216">The GUID is used primarily for COM support.</span></span>

- <span data-ttu-id="05feb-217">Il <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> metodo analizza correttamente le stringhe che contengono date brevi in .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-217">The <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> method correctly parses strings that contain short dates in .NET Native.</span></span> <span data-ttu-id="05feb-218">Tuttavia, non mantiene la compatibilità con le modifiche nell'analisi di data e ora descritte negli articoli della Microsoft Knowledge Base [KB2803771](https://support.microsoft.com/kb/2803771) e [KB2803755](https://support.microsoft.com/kb/2803755).</span><span class="sxs-lookup"><span data-stu-id="05feb-218">However, it doesn't maintain compatibility with the changes in date and time parsing described in the Microsoft Knowledge Base articles [KB2803771](https://support.microsoft.com/kb/2803771) and [KB2803755](https://support.microsoft.com/kb/2803755).</span></span>

- <span data-ttu-id="05feb-219"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType>`("E")` viene arrotondato correttamente in .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-219"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` is correctly rounded in .NET Native.</span></span> <span data-ttu-id="05feb-220">In alcune versioni di CLR, la stringa di risultato viene troncata anziché arrotondata.</span><span class="sxs-lookup"><span data-stu-id="05feb-220">In some versions of the CLR, the result string is truncated instead of rounded.</span></span>

<a name="HttpClient"></a>

### <a name="httpclient-differences"></a><span data-ttu-id="05feb-221">Differenze di HttpClient</span><span class="sxs-lookup"><span data-stu-id="05feb-221">HttpClient differences</span></span>

<span data-ttu-id="05feb-222"><xref:System.Net.Http.HttpClientHandler> In .NET Native, la classe usa internamente <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> WinINet <xref:System.Net.WebRequest> (tramite la classe) anziché le classi e <xref:System.Net.WebResponse> usate in .NET standard per le app di Windows Store.</span><span class="sxs-lookup"><span data-stu-id="05feb-222">In .NET Native, the <xref:System.Net.Http.HttpClientHandler> class internally uses WinINet (through the <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> class) instead of the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes used in the standard .NET for Windows Store apps.</span></span>  <span data-ttu-id="05feb-223">WinINet non supporta tutte le opzioni di configurazione supportate dalla classe <xref:System.Net.Http.HttpClientHandler> .</span><span class="sxs-lookup"><span data-stu-id="05feb-223">WinINet doesn't support all the configuration options that the <xref:System.Net.Http.HttpClientHandler> class supports.</span></span>  <span data-ttu-id="05feb-224">Di conseguenza:</span><span class="sxs-lookup"><span data-stu-id="05feb-224">As a result:</span></span>

- <span data-ttu-id="05feb-225">Alcune delle proprietà di <xref:System.Net.Http.HttpClientHandler> `false` funzionalità restituite in .NET Native, mentre restituiscono `true` .NET standard per le app di Windows Store.</span><span class="sxs-lookup"><span data-stu-id="05feb-225">Some of the capability properties on <xref:System.Net.Http.HttpClientHandler> return `false` on .NET Native, whereas they return `true` in the standard .NET for Windows Store apps.</span></span>

- <span data-ttu-id="05feb-226">Alcune delle funzioni `get` di accesso delle proprietà di configurazione restituiscono sempre un valore fisso in .NET Native diverso dal valore configurabile predefinito in .NET per le app di Windows Store.Some of the configuration property accessors always return a fixed value on .NET Native that is different than the default configurable value in .NET for Windows Store apps.</span><span class="sxs-lookup"><span data-stu-id="05feb-226">Some of the configuration property `get` accessors always return a fixed value on .NET Native that is different than the default configurable value in .NET for Windows Store apps.</span></span>

<span data-ttu-id="05feb-227">Nelle sottosezioni riportate di seguito sono descritte alcune differenze di comportamento aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="05feb-227">Some additional behavior differences are covered in the following subsections.</span></span>

<span data-ttu-id="05feb-228">**Proxy**</span><span class="sxs-lookup"><span data-stu-id="05feb-228">**Proxy**</span></span>

<span data-ttu-id="05feb-229">La <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> classe non supporta la configurazione o l'override del proxy in base alle richieste.</span><span class="sxs-lookup"><span data-stu-id="05feb-229">The <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> class doesn’t support configuring or overriding the proxy on a per-request basis.</span></span>  <span data-ttu-id="05feb-230">Ciò significa che tutte le richieste su .NET Native utilizzano il server <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> proxy configurato dal sistema o nessun server proxy, a seconda del valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="05feb-230">This means that all requests on .NET Native use the system-configured proxy server or no proxy server, depending on the value of the <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="05feb-231">In .NET per applicazioni Windows Store il server proxy viene definito dalla proprietà <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="05feb-231">In .NET for Windows Store apps, the proxy server is defined by the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="05feb-232">In .NET Native, <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> l'impostazione `null` di <xref:System.PlatformNotSupportedException> su un valore diverso da genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="05feb-232">On .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> to a value other than `null` throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="05feb-233">La <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> proprietà `false` restituisce .NET Native, mentre restituisce `true` in .NET Framework standard per le app di Windows Store.</span><span class="sxs-lookup"><span data-stu-id="05feb-233">The <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in the standard .NET Framework for Windows Store apps.</span></span>

<span data-ttu-id="05feb-234">**Reindirizzamento automatico**</span><span class="sxs-lookup"><span data-stu-id="05feb-234">**Automatic redirection**</span></span>

<span data-ttu-id="05feb-235">La <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> classe non consente la configurazione del numero massimo di reindirizzamenti automatici.</span><span class="sxs-lookup"><span data-stu-id="05feb-235">The <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> class doesn't allow the maximum number of automatic redirections to be configured.</span></span>  <span data-ttu-id="05feb-236">Il valore della proprietà <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> è 50 per impostazione predefinita in .NET per applicazioni Windows Store standard e può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="05feb-236">The value of the <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> property is 50 by default in the standard .NET for Windows Store apps and can be modified.</span></span> <span data-ttu-id="05feb-237">In .NET Native, il valore di questa proprietà è 10 <xref:System.PlatformNotSupportedException> e il tentativo di modificarlo genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="05feb-237">On .NET Native, the value of this property is 10, and trying to modify it throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="05feb-238">La <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> proprietà `false` restituisce .NET Native, mentre restituisce `true` .NET per le app di Windows Store.</span><span class="sxs-lookup"><span data-stu-id="05feb-238">The <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in .NET for Windows Store apps.</span></span>

<span data-ttu-id="05feb-239">**Decompressione automatica**</span><span class="sxs-lookup"><span data-stu-id="05feb-239">**Automatic decompression**</span></span>

<span data-ttu-id="05feb-240">.NET per applicazioni Windows Store consente di impostare la proprietà <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> su <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, sia <xref:System.Net.DecompressionMethods.Deflate> che <xref:System.Net.DecompressionMethods.GZip>o <xref:System.Net.DecompressionMethods.None>.</span><span class="sxs-lookup"><span data-stu-id="05feb-240">.NET for Windows Store apps allows you to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> property to <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="05feb-241">.NET Native supporta <xref:System.Net.DecompressionMethods.Deflate> solo <xref:System.Net.DecompressionMethods.GZip>con <xref:System.Net.DecompressionMethods.None>, o .</span><span class="sxs-lookup"><span data-stu-id="05feb-241">.NET Native only supports <xref:System.Net.DecompressionMethods.Deflate> together with <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="05feb-242">Provare a impostare la proprietà <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> su <xref:System.Net.DecompressionMethods.Deflate> o <xref:System.Net.DecompressionMethods.GZip> da soli comporta l'impostazione automatica su <xref:System.Net.DecompressionMethods.Deflate> e <xref:System.Net.DecompressionMethods.GZip>.</span><span class="sxs-lookup"><span data-stu-id="05feb-242">Trying to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> property to either <xref:System.Net.DecompressionMethods.Deflate> or <xref:System.Net.DecompressionMethods.GZip> alone silently sets it to both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>.</span></span>

<span data-ttu-id="05feb-243">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="05feb-243">**Cookies**</span></span>

<span data-ttu-id="05feb-244">La gestione dei cookie viene eseguita simultaneamente da <xref:System.Net.Http.HttpClient> e WinINet.</span><span class="sxs-lookup"><span data-stu-id="05feb-244">Cookie handling is performed simultaneously by <xref:System.Net.Http.HttpClient> and WinINet.</span></span>  <span data-ttu-id="05feb-245">I cookie di <xref:System.Net.CookieContainer> vengono combinati con i cookie nella cache dei cookie di WinINet.</span><span class="sxs-lookup"><span data-stu-id="05feb-245">Cookies from the <xref:System.Net.CookieContainer> are combined with cookies in the WinINet cookie cache.</span></span>  <span data-ttu-id="05feb-246">La rimozione di un cookie da <xref:System.Net.CookieContainer> impedisce a <xref:System.Net.Http.HttpClient> di inviarlo, ma se è già stato rilevato da WinINet, e i cookie non sono stati eliminati dall'utente, WinINet lo invia.</span><span class="sxs-lookup"><span data-stu-id="05feb-246">Removing a cookie from <xref:System.Net.CookieContainer> prevents <xref:System.Net.Http.HttpClient> from sending the cookie, but if the cookie was already seen by WinINet, and cookies weren't deleted by the user, WinINet sends it.</span></span>  <span data-ttu-id="05feb-247">Non è possibile rimuovere a livello di codice un cookie da WinINet usando le API <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>o <xref:System.Net.CookieContainer> .</span><span class="sxs-lookup"><span data-stu-id="05feb-247">It isn't possible to programmatically remove a cookie from WinINet by using the <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>, or <xref:System.Net.CookieContainer> API.</span></span>  <span data-ttu-id="05feb-248">L'impostazione della proprietà <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> su `false` fa solo sì che <xref:System.Net.Http.HttpClient> smetta di inviare cookie; WinINet potrebbe ancora includere i propri cookie nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="05feb-248">Setting the <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> property to `false` causes only <xref:System.Net.Http.HttpClient> to stop sending cookies; WinINet might still include its cookies in the request.</span></span>

<span data-ttu-id="05feb-249">**Credenziali**</span><span class="sxs-lookup"><span data-stu-id="05feb-249">**Credentials**</span></span>

<span data-ttu-id="05feb-250">In .NET per applicazioni Windows Store, le proprietà <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> e <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> funzionano in maniera indipendente.</span><span class="sxs-lookup"><span data-stu-id="05feb-250">In .NET for Windows Store apps, the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> properties work independently.</span></span>  <span data-ttu-id="05feb-251">Inoltre, la proprietà <xref:System.Net.Http.HttpClientHandler.Credentials%2A> accetta qualsiasi oggetto che implementa l'interfaccia <xref:System.Net.ICredentials> .</span><span class="sxs-lookup"><span data-stu-id="05feb-251">Additionally, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property accepts any object that implements the <xref:System.Net.ICredentials> interface.</span></span>  <span data-ttu-id="05feb-252">In .NET Native, <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> l'impostazione della proprietà su `true` fa sì che la <xref:System.Net.Http.HttpClientHandler.Credentials%2A> proprietà diventi `null`.</span><span class="sxs-lookup"><span data-stu-id="05feb-252">In .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> property to `true` causes the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property to become `null`.</span></span>  <span data-ttu-id="05feb-253">Inoltre, la proprietà <xref:System.Net.Http.HttpClientHandler.Credentials%2A> può essere impostata solo su `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>o un oggetto di tipo <xref:System.Net.NetworkCredential>.</span><span class="sxs-lookup"><span data-stu-id="05feb-253">In addition, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property can be set only to `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>, or an object of type <xref:System.Net.NetworkCredential>.</span></span>  <span data-ttu-id="05feb-254">L'assegnazione di qualsiasi altro oggetto <xref:System.Net.ICredentials> , il più popolare dei quali è <xref:System.Net.CredentialCache>, alla proprietà <xref:System.Net.Http.HttpClientHandler.Credentials%2A> genera una <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="05feb-254">Assigning any other <xref:System.Net.ICredentials> object, the most popular of which is <xref:System.Net.CredentialCache>, to the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property throws a <xref:System.PlatformNotSupportedException>.</span></span>

<span data-ttu-id="05feb-255">**Altre funzionalità non supportate o non configurabili**</span><span class="sxs-lookup"><span data-stu-id="05feb-255">**Other unsupported or unconfigurable features**</span></span>

<span data-ttu-id="05feb-256">In .NET Native:</span><span class="sxs-lookup"><span data-stu-id="05feb-256">In .NET Native:</span></span>

- <span data-ttu-id="05feb-257">Il valore della proprietà <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> è sempre <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span><span class="sxs-lookup"><span data-stu-id="05feb-257">The value of the <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> property is always <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span></span>  <span data-ttu-id="05feb-258">In .NET per applicazioni Windows Store, il valore predefinito è <xref:System.Net.Http.ClientCertificateOption.Manual>.</span><span class="sxs-lookup"><span data-stu-id="05feb-258">In .NET for Windows Store apps, the default is <xref:System.Net.Http.ClientCertificateOption.Manual>.</span></span>

- <span data-ttu-id="05feb-259">La proprietà <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> non è configurabile.</span><span class="sxs-lookup"><span data-stu-id="05feb-259">The <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> property isn't configurable.</span></span>

- <span data-ttu-id="05feb-260">La proprietà <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> è sempre `true`.</span><span class="sxs-lookup"><span data-stu-id="05feb-260">The <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> property is always `true`.</span></span>  <span data-ttu-id="05feb-261">In .NET per applicazioni Windows Store, il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="05feb-261">In .NET for Windows Store apps, the default is `false`.</span></span>

- <span data-ttu-id="05feb-262">L'intestazione `SetCookie2` nelle risposte verrà ignorata come obsoleta.</span><span class="sxs-lookup"><span data-stu-id="05feb-262">The `SetCookie2` header in responses is ignored as obsolete.</span></span>

<a name="Interop"></a>
### <a name="interop-differences"></a><span data-ttu-id="05feb-263">Differenze di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="05feb-263">Interop differences</span></span>
 <span data-ttu-id="05feb-264">**API deprecate**</span><span class="sxs-lookup"><span data-stu-id="05feb-264">**Deprecated APIs**</span></span>

 <span data-ttu-id="05feb-265">Una serie di API usate con minore frequenza per l'interoperabilità con codice gestito è stata deprecata.</span><span class="sxs-lookup"><span data-stu-id="05feb-265">A number of infrequently used APIs for interoperability with managed code have been deprecated.</span></span> <span data-ttu-id="05feb-266">Se utilizzate con .NET Native, queste <xref:System.NotImplementedException> API <xref:System.PlatformNotSupportedException> possono generare un'eccezione o generare un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="05feb-266">When used with .NET Native, these APIs may throw a <xref:System.NotImplementedException> or <xref:System.PlatformNotSupportedException> exception, or result in a compiler error.</span></span> <span data-ttu-id="05feb-267">In .NET per applicazioni Windows Store, queste API vengono contrassegnate come obsolete, anche se la chiamata genera un avviso del compilatore invece di un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="05feb-267">In .NET for Windows Store apps, these APIs are marked as obsolete, although calling them generates a compiler warning rather than a compiler error.</span></span>

 <span data-ttu-id="05feb-268">Le API deprecate `VARIANT` per il marshalling includono:Deprecated APIs for marshaling include:</span><span class="sxs-lookup"><span data-stu-id="05feb-268">Deprecated APIs for `VARIANT` marshaling include:</span></span>

- <xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VarEnum?displayProperty=nameWithType>

 <span data-ttu-id="05feb-269"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> è supportata, ma genera un'eccezione in alcuni scenari, ad esempio quando viene usata con [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) o varianti di ByRef.</span><span class="sxs-lookup"><span data-stu-id="05feb-269"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> is supported, but it throws an exception in some scenarios, such as when it is used with [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) or byref variants.</span></span>

 <span data-ttu-id="05feb-270">Le API deprecate per il supporto [di IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) includono:Deprecated APIs for IDispatch support include:</span><span class="sxs-lookup"><span data-stu-id="05feb-270">Deprecated APIs for [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) support include:</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>

<span data-ttu-id="05feb-271">Le API deprecate per gli eventi COM classici includono:Deprecated APIs for classic COM events include:</span><span class="sxs-lookup"><span data-stu-id="05feb-271">Deprecated APIs for classic COM events include:</span></span>

- <xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>

<span data-ttu-id="05feb-272">Le API deprecate <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> nell'interfaccia, che non è supportata in .NET Native, includono:Deprecated APIs in the interface, which isn't supported in .NET Native, include:</span><span class="sxs-lookup"><span data-stu-id="05feb-272">Deprecated APIs in the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface, which isn't supported in .NET Native, include:</span></span>

- <span data-ttu-id="05feb-273"><xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType>(tutti i membri)</span><span class="sxs-lookup"><span data-stu-id="05feb-273"><xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> (all members)</span></span>
- <span data-ttu-id="05feb-274"><xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType>(tutti i membri)</span><span class="sxs-lookup"><span data-stu-id="05feb-274"><xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType> (all members)</span></span>
- <span data-ttu-id="05feb-275"><xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType>(tutti i membri)</span><span class="sxs-lookup"><span data-stu-id="05feb-275"><xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType> (all members)</span></span>
- <xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=fullName>

<span data-ttu-id="05feb-276">Altre funzionalità di interoperabilità non supportate includono:Other unsupported interop features include:</span><span class="sxs-lookup"><span data-stu-id="05feb-276">Other unsupported interop features include:</span></span>

- <span data-ttu-id="05feb-277"><xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType>(tutti i membri)</span><span class="sxs-lookup"><span data-stu-id="05feb-277"><xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType> (all members)</span></span>
- <span data-ttu-id="05feb-278"><xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType>(tutti i membri)</span><span class="sxs-lookup"><span data-stu-id="05feb-278"><xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType> (all members)</span></span>
- <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.AsAny?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler?displayProperty=fullName>

 <span data-ttu-id="05feb-279">API di marshalling usate raramente:</span><span class="sxs-lookup"><span data-stu-id="05feb-279">Rarely used marshaling APIs:</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29?displayProperty=fullName>

 <span data-ttu-id="05feb-280">**Compatibilità platform invoke e interoperabilità COM**</span><span class="sxs-lookup"><span data-stu-id="05feb-280">**Platform invoke and COM interop compatibility**</span></span>

 <span data-ttu-id="05feb-281">La maggior parte degli scenari di platform invoke e di interoperabilità COM sono ancora supportati in .NET Native.Most platform invoke and COM interop scenarios are still supported in .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-281">Most platform invoke and COM interop scenarios are still supported in .NET Native.</span></span> <span data-ttu-id="05feb-282">In particolare, sono supportate tutte le API di interoperabilità con Windows Runtime (WinRT) e tutti i marshalling richiesti per Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="05feb-282">In particular, all interoperability with Windows Runtime (WinRT) APIs and all marshaling required for the Windows Runtime is supported.</span></span> <span data-ttu-id="05feb-283">Ciò include il supporto del marshalling per:</span><span class="sxs-lookup"><span data-stu-id="05feb-283">This includes marshaling support for:</span></span>

- <span data-ttu-id="05feb-284">Matrici (inclusa <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span><span class="sxs-lookup"><span data-stu-id="05feb-284">Arrays (including <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span></span>

- `BStr`

- <span data-ttu-id="05feb-285">Delegati</span><span class="sxs-lookup"><span data-stu-id="05feb-285">Delegates</span></span>

- <span data-ttu-id="05feb-286">Stringhe (Unicode, Ansi e HSTRING)</span><span class="sxs-lookup"><span data-stu-id="05feb-286">Strings (Unicode, Ansi, and HSTRING)</span></span>

- <span data-ttu-id="05feb-287">Struct (`byref` e `byval`)</span><span class="sxs-lookup"><span data-stu-id="05feb-287">Structs (`byref` and `byval`)</span></span>

- <span data-ttu-id="05feb-288">Unioni</span><span class="sxs-lookup"><span data-stu-id="05feb-288">Unions</span></span>

- <span data-ttu-id="05feb-289">Handle Win32</span><span class="sxs-lookup"><span data-stu-id="05feb-289">Win32 handles</span></span>

- <span data-ttu-id="05feb-290">Tutti i costrutti di WinRT</span><span class="sxs-lookup"><span data-stu-id="05feb-290">All WinRT constructs</span></span>

- <span data-ttu-id="05feb-291">Supporto parziale per il marshalling dei tipi variant.</span><span class="sxs-lookup"><span data-stu-id="05feb-291">Partial support for marshaling variant types.</span></span> <span data-ttu-id="05feb-292">Sono supportati gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="05feb-292">The following are supported:</span></span>

  - <xref:System.Boolean>

  - <xref:System.Byte>

  - <xref:System.Decimal>

  - <xref:System.Double>

  - <xref:System.Int16>

  - <xref:System.Int32>

  - <xref:System.Int64>

  - <xref:System.SByte>

  - <xref:System.Single>

  - <xref:System.UInt16>

  - <xref:System.UInt32>

  - <xref:System.UInt64>

  - `BStr`

  - [<span data-ttu-id="05feb-293">Iunknown</span><span class="sxs-lookup"><span data-stu-id="05feb-293">IUnknown</span></span>](/windows/desktop/api/unknwn/nn-unknwn-iunknown)

<span data-ttu-id="05feb-294">Tuttavia, .NET Native non supporta quanto segue:</span><span class="sxs-lookup"><span data-stu-id="05feb-294">However, .NET Native doesn't support the following:</span></span>

- <span data-ttu-id="05feb-295">Utilizzo degli eventi COM classici</span><span class="sxs-lookup"><span data-stu-id="05feb-295">Using classic COM events</span></span>

- <span data-ttu-id="05feb-296">Implementazione dell'interfaccia <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> su un tipo gestito</span><span class="sxs-lookup"><span data-stu-id="05feb-296">Implementing the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface on a managed type</span></span>

- <span data-ttu-id="05feb-297">Implementazione dell'interfaccia [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) su un tipo gestito tramite l'attributo <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="05feb-297">Implementing the [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) interface on a managed type through the <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> attribute.</span></span> <span data-ttu-id="05feb-298">Notare tuttavia che non è possibile chiamare oggetti COM tramite `IDispatch`e l'oggetto gestito non può implementare `IDispatch`.</span><span class="sxs-lookup"><span data-stu-id="05feb-298">However, note that you can't call COM objects through `IDispatch`, and your managed object can't implement `IDispatch`.</span></span>

<span data-ttu-id="05feb-299">L'uso della reflection per richiamare un metodo platform invoke non è supportato.</span><span class="sxs-lookup"><span data-stu-id="05feb-299">Using reflection to invoke a platform invoke method isn't supported.</span></span> <span data-ttu-id="05feb-300">È possibile aggirare questa limitazione eseguendo il wrapping della chiamata al metodo in un altro metodo e usando la reflection per chiamare invece il wrapper.</span><span class="sxs-lookup"><span data-stu-id="05feb-300">You can work around this limitation by wrapping the method call in another method and using reflection to call the wrapper instead.</span></span>

<a name="APIs"></a>

### <a name="other-differences-from-net-apis-for-windows-store-apps"></a><span data-ttu-id="05feb-301">Altre differenze rispetto alle API .NET per app di Windows Store</span><span class="sxs-lookup"><span data-stu-id="05feb-301">Other differences from .NET APIs for Windows Store apps</span></span>

<span data-ttu-id="05feb-302">In questa sezione sono elencate le API rimanenti che non sono supportate in .NET Native.This section lists the remaining APIs that aren't supported in .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-302">This section lists the remaining APIs that aren't supported in .NET Native.</span></span> <span data-ttu-id="05feb-303">Il set più grande di API non supportate è rappresentato dalle API di Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="05feb-303">The largest set of the unsupported APIs are Windows Communication Foundation (WCF) APIs.</span></span>

<span data-ttu-id="05feb-304">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span><span class="sxs-lookup"><span data-stu-id="05feb-304">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span></span>

<span data-ttu-id="05feb-305">I tipi <xref:System.ComponentModel.DataAnnotations> negli <xref:System.ComponentModel.DataAnnotations.Schema> spazi dei nomi e non sono supportati in .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-305">The types in the <xref:System.ComponentModel.DataAnnotations> and <xref:System.ComponentModel.DataAnnotations.Schema> namespaces aren't supported in .NET Native.</span></span> <span data-ttu-id="05feb-306">Sono inclusi i tipi seguenti presenti in .NET per le app di Windows Store per Windows 8:</span><span class="sxs-lookup"><span data-stu-id="05feb-306">These include the following types that are present in .NET for Windows Store apps for Windows 8:</span></span>

- <xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>
- <xref:System.ComponentModel.DataAnnotations.EditableAttribute>
- <xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>
- <xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=nameWithType>

 <span data-ttu-id="05feb-307">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="05feb-307">**Visual Basic**</span></span>

<span data-ttu-id="05feb-308">Visual Basic non è attualmente supportato in .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-308">Visual Basic isn't currently supported in .NET Native.</span></span> <span data-ttu-id="05feb-309">I tipi seguenti <xref:Microsoft.VisualBasic> <xref:Microsoft.VisualBasic.CompilerServices> negli spazi dei nomi e non sono disponibili in .NET Native:</span><span class="sxs-lookup"><span data-stu-id="05feb-309">The following types in the <xref:Microsoft.VisualBasic> and <xref:Microsoft.VisualBasic.CompilerServices> namespaces aren't available in .NET Native:</span></span>

- <xref:Microsoft.VisualBasic.CallType?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Constants?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=nameWithType>

<span data-ttu-id="05feb-310">**Contesto Reflection (spazio dei nomi System.Reflection.Context)**</span><span class="sxs-lookup"><span data-stu-id="05feb-310">**Reflection Context (System.Reflection.Context namespace)**</span></span>

<span data-ttu-id="05feb-311">La <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> classe non è supportata in .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-311">The <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> class isn't supported in .NET Native.</span></span>

<span data-ttu-id="05feb-312">**RTC (System.Net.Http.Rtc)**</span><span class="sxs-lookup"><span data-stu-id="05feb-312">**RTC (System.Net.Http.Rtc)**</span></span>

<span data-ttu-id="05feb-313">La `System.Net.Http.RtcRequestFactory` classe non è supportata in .NET Native.</span><span class="sxs-lookup"><span data-stu-id="05feb-313">The `System.Net.Http.RtcRequestFactory` class isn't supported in .NET Native.</span></span>

<span data-ttu-id="05feb-314">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span><span class="sxs-lookup"><span data-stu-id="05feb-314">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span></span>

<span data-ttu-id="05feb-315">I tipi negli [spazi dei nomi System.ServiceModel.](xref:System.ServiceModel)</span><span class="sxs-lookup"><span data-stu-id="05feb-315">The types in the [System.ServiceModel.\* namespaces](xref:System.ServiceModel) aren't supported in .NET Native.</span></span> <span data-ttu-id="05feb-316">Sono inclusi i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="05feb-316">These includes the following types:</span></span>

- <xref:System.ServiceModel.ActionNotSupportedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationState?displayProperty=nameWithType>
- <xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointAddress?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType>
- <xref:System.ServiceModel.EnvelopeVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.ExceptionDetail?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultCode?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultReason?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultReasonText?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpBindingBase?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpClientCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpTransportSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>
- <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtension%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtensionCollection%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.InvalidMessageContractException?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageHeader%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageHeaderException?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetHttpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetTcpSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContextScope?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationFormatStyle?displayProperty=nameWithType>
- <xref:System.ServiceModel.ProtocolException?displayProperty=nameWithType>
- <xref:System.ServiceModel.QuotaExceededException?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServerTooBusyException?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceActivationException?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpClientCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.TransferMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=nameWithType>
- <xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressHeader?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.FaultConverter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeader?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageProperties?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageState?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.RequestContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ClientCredentials?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.FaultDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDirection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.OperationDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.TrustVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=nameWithType>

### <a name="differences-in-serializers"></a><span data-ttu-id="05feb-317">Differenze nei serializzatori</span><span class="sxs-lookup"><span data-stu-id="05feb-317">Differences in serializers</span></span>

<span data-ttu-id="05feb-318">Le differenze riportate di seguito riguardano la serializzazione e la deserializzazione con le classi <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>e <xref:System.Xml.Serialization.XmlSerializer> :</span><span class="sxs-lookup"><span data-stu-id="05feb-318">The following differences concern serialization and deserialization with the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes:</span></span>

- <span data-ttu-id="05feb-319">In .NET <xref:System.Runtime.Serialization.DataContractSerializer> Native <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> e non riescono a serializzare o deserializzare una classe derivata con un membro della classe base il cui tipo non è un tipo di serializzazione radice.</span><span class="sxs-lookup"><span data-stu-id="05feb-319">In .NET Native, <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize or deserialize a derived class that has a base class member whose type isn't a root serialization type.</span></span> <span data-ttu-id="05feb-320">Ad esempio, nel codice seguente, il tentativo di serializzare o deserializzare `Y` genererà un errore:</span><span class="sxs-lookup"><span data-stu-id="05feb-320">For example, in the following code, trying to serialize or deserialize `Y` results in an error:</span></span>

  [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]

  <span data-ttu-id="05feb-321">Il tipo `InnerType` non è noto al serializzatore, perché i membri della classe base non vengono attraversati durante la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="05feb-321">Type `InnerType` isn't known to the serializer, because the members of the base class aren't traversed during serialization.</span></span>

- <span data-ttu-id="05feb-322"><xref:System.Runtime.Serialization.DataContractSerializer> e <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> non riescono a serializzare una classe o una struttura che implementa l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="05feb-322"><xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize a class or structure that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="05feb-323">Ad esempio, i seguenti tipi non riesco a serializzare o deserializzare:</span><span class="sxs-lookup"><span data-stu-id="05feb-323">For example, the following types fail to serialize or deserialize:</span></span>

- <span data-ttu-id="05feb-324"><xref:System.Xml.Serialization.XmlSerializer> non riesce a serializzare il valore dell'oggetto seguente, perché non conoscere il tipo esatto dell'oggetto da serializzare:</span><span class="sxs-lookup"><span data-stu-id="05feb-324"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize the following object value, because it doesn't know the exact type of the object to be serialized:</span></span>

- <span data-ttu-id="05feb-325"><xref:System.Xml.Serialization.XmlSerializer> non riesce a serializzare o deserializzare se il tipo di oggetto serializzato è <xref:System.Xml.XmlQualifiedName>.</span><span class="sxs-lookup"><span data-stu-id="05feb-325"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize or deserialize if the type of the serialized object is <xref:System.Xml.XmlQualifiedName>.</span></span>

- <span data-ttu-id="05feb-326">Tutti i serializzatori (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>e <xref:System.Xml.Serialization.XmlSerializer>) non riescono a generare un codice di serializzazione per il tipo <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> o per un tipo che contiene <xref:System.Xml.Linq.XElement>,</span><span class="sxs-lookup"><span data-stu-id="05feb-326">All serializers (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer>) fail to generate serialization code for type <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> or for a type that contains <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="05feb-327">visualizzando invece gli errori in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="05feb-327">They display build-time errors instead.</span></span>

- <span data-ttu-id="05feb-328">Il funzionamento corretto dei seguenti costruttori dei tipi di serializzazione non è garantito:</span><span class="sxs-lookup"><span data-stu-id="05feb-328">The following constructors of the serialization types aren't guaranteed to work as expected:</span></span>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29>

  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29>

- <span data-ttu-id="05feb-329"><xref:System.Xml.Serialization.XmlSerializer> non riesce a generare il codice per un tipo che ha metodi con uno qualsiasi dei seguenti attributi:</span><span class="sxs-lookup"><span data-stu-id="05feb-329"><xref:System.Xml.Serialization.XmlSerializer> fails to generate code for a type that has methods attributed with any of the following attributes:</span></span>

  - <xref:System.Runtime.Serialization.OnSerializingAttribute>

  - <xref:System.Runtime.Serialization.OnSerializedAttribute>

  - <xref:System.Runtime.Serialization.OnDeserializingAttribute>

  - <xref:System.Runtime.Serialization.OnDeserializedAttribute>

- <span data-ttu-id="05feb-330"><xref:System.Xml.Serialization.XmlSerializer> non soddisfa l'interfaccia di serializzazione personalizzata di <xref:System.Xml.Serialization.IXmlSerializable> .</span><span class="sxs-lookup"><span data-stu-id="05feb-330"><xref:System.Xml.Serialization.XmlSerializer> doesn't honor the <xref:System.Xml.Serialization.IXmlSerializable> custom serialization interface.</span></span> <span data-ttu-id="05feb-331">Se si ha una classe che implementa questa interfaccia, <xref:System.Xml.Serialization.XmlSerializer> considera il tipo come un oggetto Plain Old CLR Object (POCO) di CLR e ne serializza solo le proprietà pubbliche.</span><span class="sxs-lookup"><span data-stu-id="05feb-331">If you have a class that implements this interface, <xref:System.Xml.Serialization.XmlSerializer> considers the type a plain old CLR object (POCO) type and serializes only its public properties.</span></span>

- <span data-ttu-id="05feb-332">La serializzazione <xref:System.Exception> di un oggetto <xref:System.Runtime.Serialization.DataContractSerializer> semplice <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>non funziona bene con e .</span><span class="sxs-lookup"><span data-stu-id="05feb-332">Serializing a plain <xref:System.Exception> object doesn't work well with <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>

<a name="VS"></a>

## <a name="visual-studio-differences"></a><span data-ttu-id="05feb-333">Differenze di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="05feb-333">Visual Studio differences</span></span>

<span data-ttu-id="05feb-334">**Eccezioni e debug**</span><span class="sxs-lookup"><span data-stu-id="05feb-334">**Exceptions and debugging**</span></span>

<span data-ttu-id="05feb-335">Quando si eseguono app compilate utilizzando .NET Native nel debugger, le eccezioni first-chance sono abilitate per i tipi di eccezione seguenti:</span><span class="sxs-lookup"><span data-stu-id="05feb-335">When you're running apps compiled by using .NET Native in the debugger, first-chance exceptions are enabled for the following exception types:</span></span>

- <xref:System.MemberAccessException>

- <xref:System.TypeAccessException>

<span data-ttu-id="05feb-336">**Creazione di app**</span><span class="sxs-lookup"><span data-stu-id="05feb-336">**Building apps**</span></span>

<span data-ttu-id="05feb-337">Usare gli strumenti di compilazione x86 usati per impostazione predefinita da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="05feb-337">Use the x86 build tools that are used by default by Visual Studio.</span></span> <span data-ttu-id="05feb-338">Non è consigliabile usare gli strumenti di MSBuild AMD64, disponibili in C:\Program Files (x86)\MSBuild\12.0\bin\amd64, perché possono creare problemi di compilazione.</span><span class="sxs-lookup"><span data-stu-id="05feb-338">We don't recommend using the AMD64 MSBuild tools, which are found in C:\Program Files (x86)\MSBuild\12.0\bin\amd64; these may create build problems.</span></span>

<span data-ttu-id="05feb-339">**Profiler**</span><span class="sxs-lookup"><span data-stu-id="05feb-339">**Profilers**</span></span>

- <span data-ttu-id="05feb-340">Il profiler della CPU di Visual Studio e il profiler della memoria XAML non visualizzano Just My Code correttamente.</span><span class="sxs-lookup"><span data-stu-id="05feb-340">The Visual Studio CPU Profiler and XAML Memory Profiler don't display Just-My-Code correctly.</span></span>

- <span data-ttu-id="05feb-341">Il profiler della memoria di XAML non visualizza in modo accurato i dati di heap gestito.</span><span class="sxs-lookup"><span data-stu-id="05feb-341">The XAML Memory Profiler doesn't accurately display managed heap data.</span></span>

- <span data-ttu-id="05feb-342">Il profiler della CPU non identifica correttamente i moduli e consente di visualizzare i nomi di funzione con prefisso.</span><span class="sxs-lookup"><span data-stu-id="05feb-342">The CPU Profiler doesn't correctly identify modules, and displays prefixed function names.</span></span>

<span data-ttu-id="05feb-343">**Progetti di librerie unit test**</span><span class="sxs-lookup"><span data-stu-id="05feb-343">**Unit Test Library projects**</span></span>

<span data-ttu-id="05feb-344">L'abilitazione di .NET Native in una libreria di unit test per un progetto di app di Windows Store non è supportata e causa la mancata compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="05feb-344">Enabling .NET Native on a Unit Test Library for a Windows Store apps project isn't supported and causes the project to fail to build.</span></span>

## <a name="see-also"></a><span data-ttu-id="05feb-345">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05feb-345">See also</span></span>

- [<span data-ttu-id="05feb-346">Guida introduttiva</span><span class="sxs-lookup"><span data-stu-id="05feb-346">Getting Started</span></span>](getting-started-with-net-native.md)
- [<span data-ttu-id="05feb-347">Riferimento a file di configurazione di direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="05feb-347">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="05feb-348">Panoramica delle app di .NET Per Windows Store</span><span class="sxs-lookup"><span data-stu-id="05feb-348">.NET For Windows Store apps overview</span></span>](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29)
- [<span data-ttu-id="05feb-349">Supporto .NET Framework per applicazioni Windows Store e Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="05feb-349">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
