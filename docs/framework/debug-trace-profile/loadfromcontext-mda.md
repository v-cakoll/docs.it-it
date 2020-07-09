---
title: MDA loadFromContext
description: Comprendere l'assistente al debug gestito di loadFromContext in .NET, che viene attivato se un assembly viene caricato nel contesto LoadFrom.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), LoadFrom context
- managed debugging assistants (MDAs), LoadFrom context
- LoadFrom context
- LoadFromContext MDA
ms.assetid: a9b14db1-d3a9-4150-a767-dcf3aea0071a
ms.openlocfilehash: 8d55268f2b2106dde4e488a6f0271fd3b17349da
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051649"
---
# <a name="loadfromcontext-mda"></a><span data-ttu-id="27a1e-103">MDA loadFromContext</span><span class="sxs-lookup"><span data-stu-id="27a1e-103">loadFromContext MDA</span></span>
<span data-ttu-id="27a1e-104">L'assistente al debug gestito `loadFromContext` viene attivato se viene caricato un assembly nel contesto `LoadFrom`.</span><span class="sxs-lookup"><span data-stu-id="27a1e-104">The `loadFromContext` managed debugging assistant (MDA) is activated if an assembly is loaded into the `LoadFrom` context.</span></span> <span data-ttu-id="27a1e-105">Questa situazione può verificarsi come risultato di una chiamata di <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> o di altri metodi simili.</span><span class="sxs-lookup"><span data-stu-id="27a1e-105">This situation can occur as a result of calling <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> or other similar methods.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="27a1e-106">Sintomi</span><span class="sxs-lookup"><span data-stu-id="27a1e-106">Symptoms</span></span>  
 <span data-ttu-id="27a1e-107">L'uso di alcuni metodi di caricamento può determinare il caricamento di un assembly nel contesto `LoadFrom`.</span><span class="sxs-lookup"><span data-stu-id="27a1e-107">The use of some loader methods can result in assemblies being loaded in the `LoadFrom` context.</span></span> <span data-ttu-id="27a1e-108">L'uso di questo contesto può provocare un comportamento imprevisto per la serializzazione, il cast e la risoluzione delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="27a1e-108">The use of this context can result in unexpected behavior for serialization, casting, and dependency resolution.</span></span> <span data-ttu-id="27a1e-109">In generale, per evitare problemi è preferibile che gli assembly vengano caricati nel contesto `Load`.</span><span class="sxs-lookup"><span data-stu-id="27a1e-109">In general, it is recommended that assemblies be loaded into the `Load` context to avoid these problems.</span></span> <span data-ttu-id="27a1e-110">Senza questo assistente al debug gestito, è difficile determinare il contesto in cui è stato caricato un assembly.</span><span class="sxs-lookup"><span data-stu-id="27a1e-110">It is difficult to determine which context an assembly has been loaded into without this MDA.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="27a1e-111">Causa</span><span class="sxs-lookup"><span data-stu-id="27a1e-111">Cause</span></span>  
 <span data-ttu-id="27a1e-112">In genere, un assembly viene caricato nel contesto `LoadFrom` se è stato caricato da un percorso esterno al contesto `Load`, ad esempio la Global Assembly Cache o la proprietà <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="27a1e-112">Generally, an assembly was loaded into the `LoadFrom` context if it was loaded from a path outside the `Load` context, such as the global assembly cache or the <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="27a1e-113">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="27a1e-113">Resolution</span></span>  
 <span data-ttu-id="27a1e-114">Configurare le applicazioni in modo che non siano più necessarie chiamate di <xref:System.Reflection.Assembly.LoadFrom%2A>.</span><span class="sxs-lookup"><span data-stu-id="27a1e-114">Configure applications such that <xref:System.Reflection.Assembly.LoadFrom%2A> calls are no longer needed.</span></span> <span data-ttu-id="27a1e-115">A questo scopo, è possibile usare le tecniche seguenti:</span><span class="sxs-lookup"><span data-stu-id="27a1e-115">You can use the following techniques for doing so:</span></span>  
  
- <span data-ttu-id="27a1e-116">Installare gli assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="27a1e-116">Install assemblies in the global assembly cache.</span></span>  
  
- <span data-ttu-id="27a1e-117">Inserire gli assembly nella directory <xref:System.AppDomainSetup.ApplicationBase%2A> per <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="27a1e-117">Place assemblies in the <xref:System.AppDomainSetup.ApplicationBase%2A> directory for the <xref:System.AppDomain>.</span></span> <span data-ttu-id="27a1e-118">Nel caso del dominio predefinito, la directory <xref:System.AppDomainSetup.ApplicationBase%2A> è quella che contiene il file eseguibile che ha avviato il processo.</span><span class="sxs-lookup"><span data-stu-id="27a1e-118">In the case of the default domain, the <xref:System.AppDomainSetup.ApplicationBase%2A> directory is the one that contains the executable file that started the process.</span></span> <span data-ttu-id="27a1e-119">In questo caso, può essere necessaria anche la creazione di un nuovo oggetto <xref:System.AppDomain> se non si vuole spostare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="27a1e-119">This might also require creating a new <xref:System.AppDomain> if it is not convenient to move the assembly.</span></span>  
  
- <span data-ttu-id="27a1e-120">Aggiungere un percorso di sondaggio al file di configurazione dell'applicazione (con estensione config) o ai domini dell'applicazione secondari se nelle directory figlio relative al file eseguibile sono presenti assembly dipendenti.</span><span class="sxs-lookup"><span data-stu-id="27a1e-120">Add a probing path to your application configuration (.config) file or to secondary  application domains if dependent assemblies are in child directories relative to the executable.</span></span>  
  
 <span data-ttu-id="27a1e-121">In ogni caso, il codice può essere modificato in modo da usare il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="27a1e-121">In each case, the code can be changed to use the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="27a1e-122">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="27a1e-122">Effect on the Runtime</span></span>  
 <span data-ttu-id="27a1e-123">L'assistente al debug gestito non ha alcun effetto su CLR</span><span class="sxs-lookup"><span data-stu-id="27a1e-123">The MDA does not have any effect on the CLR.</span></span> <span data-ttu-id="27a1e-124">e segnala il contesto usato come risultato di una richiesta di caricamento.</span><span class="sxs-lookup"><span data-stu-id="27a1e-124">It reports the context that was used as a result of a load request.</span></span>  
  
## <a name="output"></a><span data-ttu-id="27a1e-125">Output</span><span class="sxs-lookup"><span data-stu-id="27a1e-125">Output</span></span>  
 <span data-ttu-id="27a1e-126">L'assistente al debug gestito segnala che l'assembly è stato caricato nel contesto `LoadFrom`,</span><span class="sxs-lookup"><span data-stu-id="27a1e-126">The MDA reports that the assembly was loaded into the `LoadFrom` context.</span></span> <span data-ttu-id="27a1e-127">specifica il nome semplice dell'assembly e il percorso</span><span class="sxs-lookup"><span data-stu-id="27a1e-127">It specifies the simple name of the assembly and the path.</span></span> <span data-ttu-id="27a1e-128">e suggerisce anche le misure di prevenzione per evitare di usare il contesto `LoadFrom`.</span><span class="sxs-lookup"><span data-stu-id="27a1e-128">It also suggests mitigations to avoid using the `LoadFrom` context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="27a1e-129">Configurazione</span><span class="sxs-lookup"><span data-stu-id="27a1e-129">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <loadFromContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="27a1e-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="27a1e-130">Example</span></span>  
 <span data-ttu-id="27a1e-131">L'esempio di codice seguente mostra una situazione che può comportare l'attivazione dell'assistente al debug gestito:</span><span class="sxs-lookup"><span data-stu-id="27a1e-131">The following code example demonstrates a situation that can activate this MDA:</span></span>  
  
```csharp
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The following call caused the LoadFrom context to be used  
            // because the assembly is loaded using LoadFrom and the path is
            // located outside of the Load context probing path.
            Assembly.LoadFrom(@"C:\Text\Test.dll");  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="27a1e-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27a1e-132">See also</span></span>

- [<span data-ttu-id="27a1e-133">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="27a1e-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
