---
title: Eccezioni di runtime in app .NET
ms.date: 03/30/2017
ms.assetid: 5f050181-8fdd-4a4e-9d16-f84c22a88a97
ms.openlocfilehash: 12df2ef7bf6e86a60dfa4c130f35969e72ac5211
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79180943"
---
# <a name="runtime-exceptions-in-net-native-apps"></a><span data-ttu-id="e6008-102">Eccezioni di runtime in app .NET</span><span class="sxs-lookup"><span data-stu-id="e6008-102">Runtime Exceptions in .NET Native Apps</span></span>
<span data-ttu-id="e6008-103">È importante testare le build di versione dell'app della piattaforma UWP (Universal Windows Platform) nelle rispettive piattaforme di destinazione, perché le configurazioni di tipo Debug e di tipo Versione sono completamente diverse.</span><span class="sxs-lookup"><span data-stu-id="e6008-103">It is important to test the release builds of your Universal Windows Platform app on their target platforms because the debug and release configurations are completely different.</span></span> <span data-ttu-id="e6008-104">Per impostazione predefinita, la configurazione di tipo Debug usa il runtime di .NET Core per compilare l'app, mentre quella di tipo Versione usa .NET Native per compilare l'app nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="e6008-104">By default, the debug configuration uses the .NET Core runtime to compile your app, but the release configuration uses .NET Native to compile your app to native code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e6008-105">Per informazioni sulla gestione delle eccezioni [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingInteropDataException](missinginteropdataexception-class-net-native.md)e [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) che possono verificarsi durante il test delle versioni di rilascio dell'app, vedere "passaggio 4: risolvere manualmente i metadati mancanti: nell'argomento [Introduzione](getting-started-with-net-native.md) , nonché informazioni di riferimento sui file di configurazione di [Reflection e .NET native](reflection-and-net-native.md) e di [Runtime (Rd. Xml)](runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="e6008-105">For information on dealing with the [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingInteropDataException](missinginteropdataexception-class-net-native.md), and [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exceptions that you may encounter when testing the release versions of your app, see "Step 4: Manually resolve missing metadata: in the [Getting Started](getting-started-with-net-native.md) topic, as well as [Reflection and .NET Native](reflection-and-net-native.md) and [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
## <a name="debug-and-release-builds"></a><span data-ttu-id="e6008-106">Build di tipo Debug e Versione</span><span class="sxs-lookup"><span data-stu-id="e6008-106">Debug and release builds</span></span>  
 <span data-ttu-id="e6008-107">La build di tipo Debug eseguita nel runtime .NET Core non è stata compilata nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="e6008-107">When the debug build executes against the .NET Core runtime, it has not been compiled to native code.</span></span> <span data-ttu-id="e6008-108">In questo modo tutti i servizi normalmente forniti dal runtime sono disponibili per l'app.</span><span class="sxs-lookup"><span data-stu-id="e6008-108">This makes all of the services ordinarily provided by the runtime available to your app.</span></span>  
  
 <span data-ttu-id="e6008-109">La build di versione viene invece compilata nel codice nativo per le rispettive piattaforme di destinazione, rimuove la maggior parte delle dipendenze da librerie e runtime esterni, oltre a ottimizzare notevolmente il codice garantendo prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="e6008-109">On the other hand, the release build compiles to native code for its target platforms, removes most dependencies on external runtimes and libraries, and heavily optimizes code for maximum performance.</span></span>  
  
 <span data-ttu-id="e6008-110">Quando si esegue il debug di build di tipo Versione compilate con .NET Native:</span><span class="sxs-lookup"><span data-stu-id="e6008-110">When you debug release builds that are compiled by using .NET Native:</span></span>  
  
- <span data-ttu-id="e6008-111">Si usa il motore di debug di .NET Native, che è diverso rispetto ai normali strumenti di debug di .NET.</span><span class="sxs-lookup"><span data-stu-id="e6008-111">You use the .NET Native debug engine, which is different from the normal .NET debugging tools.</span></span>  
  
- <span data-ttu-id="e6008-112">Le dimensioni del file eseguibile vengono ridotte il più possibile.</span><span class="sxs-lookup"><span data-stu-id="e6008-112">The size of your executable is reduced as much as possible.</span></span> <span data-ttu-id="e6008-113">Uno dei modi in cui .NET Native riesce a ridurre le dimensioni del file eseguibile consiste nel tagliare significativamente i messaggi di eccezione di runtime, come descritto in maggiore dettaglio nella sezione [Runtime exception messages](#Messages) .</span><span class="sxs-lookup"><span data-stu-id="e6008-113">One of the ways that .NET Native reduces the size of an executable is by significantly trimming runtime exception messages, a topic discussed in greater detail in the [Runtime exception messages](#Messages) section.</span></span>  
  
- <span data-ttu-id="e6008-114">Il codice viene notevolmente ottimizzato.</span><span class="sxs-lookup"><span data-stu-id="e6008-114">Your code is heavily optimized.</span></span> <span data-ttu-id="e6008-115">Questo significa che laddove possibile viene usato l'incorporamento,</span><span class="sxs-lookup"><span data-stu-id="e6008-115">This means that inlining is used whenever possible.</span></span> <span data-ttu-id="e6008-116">(Incorporamento sposta il codice dalle routine esterne alla routine chiamante).   Il fatto che .NET Native fornisca un runtime specializzato e implementi l'inlining aggressivo influiscono sullo stack di chiamate visualizzato durante il debug.</span><span class="sxs-lookup"><span data-stu-id="e6008-116">(Inlining moves code from external routines into the calling routine.)   The fact that .NET Native provides a specialized runtime and implements aggressive inlining  affects the call stack that is displayed when debugging.</span></span>  <span data-ttu-id="e6008-117">Per altre informazioni, vedere la sezione [Runtime call stack](#CallStack) .</span><span class="sxs-lookup"><span data-stu-id="e6008-117">For more information, see the [Runtime call stack](#CallStack) section.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6008-118">Per controllare se le build di tipo Debug e Versione sono compilate con la catena di strumenti .NET Native, selezionare o deselezionare la casella **Compilare con la catena di strumenti .NET Native** .</span><span class="sxs-lookup"><span data-stu-id="e6008-118">You can control whether the debug and release builds are compiled with the .NET Native tool chain by checking or unchecking the **Compile with .NET Native tool chain** box.</span></span>   <span data-ttu-id="e6008-119">Notare però che per la compilazione della versione di produzione dell'app, Windows Store userà sempre la catena di strumenti .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e6008-119">Note, however, that the Windows Store will always compile the production version of your app with the .NET Native tool chain.</span></span>  
  
<a name="Messages"></a>
## <a name="runtime-exception-messages"></a><span data-ttu-id="e6008-120">Runtime exception messages</span><span class="sxs-lookup"><span data-stu-id="e6008-120">Runtime exception messages</span></span>  
 <span data-ttu-id="e6008-121">Per ridurre al minimo le dimensioni dei file eseguibili delle applicazioni, .NET Native non include il testo completo dei messaggi di eccezione.</span><span class="sxs-lookup"><span data-stu-id="e6008-121">To minimize application executable size, .NET Native does not include the full text of exception messages.</span></span> <span data-ttu-id="e6008-122">Di conseguenza, è possibile che i messaggi delle eccezioni di runtime generate nelle build di tipo Versione non includano il testo completo,</span><span class="sxs-lookup"><span data-stu-id="e6008-122">As a result, runtime exceptions thrown in release builds may not display the full text of exception messages.</span></span> <span data-ttu-id="e6008-123">ma solo una sottostringa e un collegamento da aprire per visualizzare altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="e6008-123">Instead, the text may consist of a substring along with a link to follow for more information.</span></span> <span data-ttu-id="e6008-124">Le informazioni visualizzate sull'eccezione possono ad esempio essere simili a:</span><span class="sxs-lookup"><span data-stu-id="e6008-124">For example, the exception information may appear as:</span></span>  
  
```output
Exception thrown: '$16_System.AggregateException' in Unknown Module.  
  
Additional information: AggregateException_ctor_DefaultMessage  
  
If there is a handler for this exception, the program may be safely continued.  
```  
  
 <span data-ttu-id="e6008-125">Per visualizzare il messaggio di eccezione completo, eseguire la build di tipo Debug.</span><span class="sxs-lookup"><span data-stu-id="e6008-125">If you need the complete exception message,  run the debug build instead.</span></span> <span data-ttu-id="e6008-126">Ad esempio le informazioni sull'eccezione precedente della build di tipo Versione sono simili alle seguenti nella build di tipo Debug:</span><span class="sxs-lookup"><span data-stu-id="e6008-126">For example, the previous exception information  from the release build might appear as follows in the debug build:</span></span>  
  
```output
Exception thrown: 'System.AggregateException' in NativeApp.exe.  
  
Additional information: Value does not fall within the expected range.  
```  
  
<a name="CallStack"></a>
## <a name="runtime-call-stack"></a><span data-ttu-id="e6008-127">Runtime call stack</span><span class="sxs-lookup"><span data-stu-id="e6008-127">Runtime call stack</span></span>  
 <span data-ttu-id="e6008-128">A causa dell'incorporamento e di altre ottimizzazioni, lo stack di chiamate visualizzato da un'app compilata con la catena di strumenti .NET Native potrebbe risultare poco utile per identificare chiaramente il percorso di un'eccezione di runtime.</span><span class="sxs-lookup"><span data-stu-id="e6008-128">Because of inlining and other optimizations, the call stack displayed by an app compiled by the .NET Native tool chain may not help you to  clearly identify the path to a runtime exception.</span></span>  
  
 <span data-ttu-id="e6008-129">Per ottenere lo stack completo, eseguire la build di tipo Debug.</span><span class="sxs-lookup"><span data-stu-id="e6008-129">To get the full stack, run the debug build instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6008-130">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e6008-130">See also</span></span>

- [<span data-ttu-id="e6008-131">Debug di app universali di Windows .NET Native</span><span class="sxs-lookup"><span data-stu-id="e6008-131">Debugging .NET Native Windows Universal Apps</span></span>](https://devblogs.microsoft.com/devops/debugging-net-native-windows-universal-apps/)
- [<span data-ttu-id="e6008-132">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="e6008-132">Getting Started</span></span>](getting-started-with-net-native.md)
