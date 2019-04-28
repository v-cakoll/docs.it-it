---
title: MDA loadFromContext
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), LoadFrom context
- managed debugging assistants (MDAs), LoadFrom context
- LoadFrom context
- LoadFromContext MDA
ms.assetid: a9b14db1-d3a9-4150-a767-dcf3aea0071a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 01b2cf06a5ab921f5ae89da4856e8164b6f57db5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754258"
---
# <a name="loadfromcontext-mda"></a><span data-ttu-id="d48a3-102">MDA loadFromContext</span><span class="sxs-lookup"><span data-stu-id="d48a3-102">loadFromContext MDA</span></span>
<span data-ttu-id="d48a3-103">L'assistente al debug gestito `loadFromContext` viene attivato se viene caricato un assembly nel contesto `LoadFrom`.</span><span class="sxs-lookup"><span data-stu-id="d48a3-103">The `loadFromContext` managed debugging assistant (MDA) is activated if an assembly is loaded into the `LoadFrom` context.</span></span> <span data-ttu-id="d48a3-104">Questa situazione può verificarsi come risultato di una chiamata di <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> o di altri metodi simili.</span><span class="sxs-lookup"><span data-stu-id="d48a3-104">This situation can occur as a result of calling <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> or other similar methods.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="d48a3-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="d48a3-105">Symptoms</span></span>  
 <span data-ttu-id="d48a3-106">L'uso di alcuni metodi di caricamento può determinare il caricamento di un assembly nel contesto `LoadFrom`.</span><span class="sxs-lookup"><span data-stu-id="d48a3-106">The use of some loader methods can result in assemblies being loaded in the `LoadFrom` context.</span></span> <span data-ttu-id="d48a3-107">L'uso di questo contesto può provocare un comportamento imprevisto per la serializzazione, il cast e la risoluzione delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="d48a3-107">The use of this context can result in unexpected behavior for serialization, casting, and dependency resolution.</span></span> <span data-ttu-id="d48a3-108">In generale, per evitare problemi è preferibile che gli assembly vengano caricati nel contesto `Load`.</span><span class="sxs-lookup"><span data-stu-id="d48a3-108">In general, it is recommended that assemblies be loaded into the `Load` context to avoid these problems.</span></span> <span data-ttu-id="d48a3-109">Senza questo assistente al debug gestito, è difficile determinare il contesto in cui è stato caricato un assembly.</span><span class="sxs-lookup"><span data-stu-id="d48a3-109">It is difficult to determine which context an assembly has been loaded into without this MDA.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="d48a3-110">Causa</span><span class="sxs-lookup"><span data-stu-id="d48a3-110">Cause</span></span>  
 <span data-ttu-id="d48a3-111">In genere, un assembly viene caricato nel contesto `LoadFrom` se è stato caricato da un percorso esterno al contesto `Load`, ad esempio la Global Assembly Cache o la proprietà <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d48a3-111">Generally, an assembly was loaded into the `LoadFrom` context if it was loaded from a path outside the `Load` context, such as the global assembly cache or the <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="d48a3-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="d48a3-112">Resolution</span></span>  
 <span data-ttu-id="d48a3-113">Configurare le applicazioni in modo che non siano più necessarie chiamate di <xref:System.Reflection.Assembly.LoadFrom%2A>.</span><span class="sxs-lookup"><span data-stu-id="d48a3-113">Configure applications such that <xref:System.Reflection.Assembly.LoadFrom%2A> calls are no longer needed.</span></span> <span data-ttu-id="d48a3-114">A questo scopo, è possibile usare le tecniche seguenti:</span><span class="sxs-lookup"><span data-stu-id="d48a3-114">You can use the following techniques for doing so:</span></span>  
  
- <span data-ttu-id="d48a3-115">Installare gli assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="d48a3-115">Install assemblies in the global assembly cache.</span></span>  
  
- <span data-ttu-id="d48a3-116">Inserire gli assembly nella directory <xref:System.AppDomainSetup.ApplicationBase%2A> per <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="d48a3-116">Place assemblies in the <xref:System.AppDomainSetup.ApplicationBase%2A> directory for the <xref:System.AppDomain>.</span></span> <span data-ttu-id="d48a3-117">Nel caso del dominio predefinito, la directory <xref:System.AppDomainSetup.ApplicationBase%2A> è quella che contiene il file eseguibile che ha avviato il processo.</span><span class="sxs-lookup"><span data-stu-id="d48a3-117">In the case of the default domain, the <xref:System.AppDomainSetup.ApplicationBase%2A> directory is the one that contains the executable file that started the process.</span></span> <span data-ttu-id="d48a3-118">In questo caso, può essere necessaria anche la creazione di un nuovo oggetto <xref:System.AppDomain> se non si vuole spostare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="d48a3-118">This might also require creating a new <xref:System.AppDomain> if it is not convenient to move the assembly.</span></span>  
  
- <span data-ttu-id="d48a3-119">Aggiungere un percorso di sondaggio al file di configurazione dell'applicazione (con estensione config) o ai domini dell'applicazione secondari se nelle directory figlio relative al file eseguibile sono presenti assembly dipendenti.</span><span class="sxs-lookup"><span data-stu-id="d48a3-119">Add a probing path to your application configuration (.config) file or to secondary  application domains if dependent assemblies are in child directories relative to the executable.</span></span>  
  
 <span data-ttu-id="d48a3-120">In ogni caso, il codice può essere modificato in modo da usare il metodo <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d48a3-120">In each case, the code can be changed to use the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d48a3-121">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="d48a3-121">Effect on the Runtime</span></span>  
 <span data-ttu-id="d48a3-122">L'assistente al debug gestito non ha alcun effetto su CLR</span><span class="sxs-lookup"><span data-stu-id="d48a3-122">The MDA does not have any effect on the CLR.</span></span> <span data-ttu-id="d48a3-123">e segnala il contesto usato come risultato di una richiesta di caricamento.</span><span class="sxs-lookup"><span data-stu-id="d48a3-123">It reports the context that was used as a result of a load request.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d48a3-124">Output</span><span class="sxs-lookup"><span data-stu-id="d48a3-124">Output</span></span>  
 <span data-ttu-id="d48a3-125">L'assistente al debug gestito segnala che l'assembly è stato caricato nel contesto `LoadFrom`,</span><span class="sxs-lookup"><span data-stu-id="d48a3-125">The MDA reports that the assembly was loaded into the `LoadFrom` context.</span></span> <span data-ttu-id="d48a3-126">specifica il nome semplice dell'assembly e il percorso</span><span class="sxs-lookup"><span data-stu-id="d48a3-126">It specifies the simple name of the assembly and the path.</span></span> <span data-ttu-id="d48a3-127">e suggerisce anche le misure di prevenzione per evitare di usare il contesto `LoadFrom`.</span><span class="sxs-lookup"><span data-stu-id="d48a3-127">It also suggests mitigations to avoid using the `LoadFrom` context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d48a3-128">Configurazione</span><span class="sxs-lookup"><span data-stu-id="d48a3-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <loadFromContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="d48a3-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="d48a3-129">Example</span></span>  
 <span data-ttu-id="d48a3-130">L'esempio di codice seguente mostra una situazione che può comportare l'attivazione dell'assistente al debug gestito:</span><span class="sxs-lookup"><span data-stu-id="d48a3-130">The following code example demonstrates a situation that can activate this MDA:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d48a3-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d48a3-131">See also</span></span>

- [<span data-ttu-id="d48a3-132">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="d48a3-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
