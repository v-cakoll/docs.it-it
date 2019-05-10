---
title: Eccezioni di runtime in app .NET
ms.date: 03/30/2017
ms.assetid: 5f050181-8fdd-4a4e-9d16-f84c22a88a97
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b682d4b43ece406ee320d6d4f96ed5cda5f17c3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650358"
---
# <a name="runtime-exceptions-in-net-native-apps"></a><span data-ttu-id="dd507-102">Eccezioni di runtime in app .NET</span><span class="sxs-lookup"><span data-stu-id="dd507-102">Runtime Exceptions in .NET Native Apps</span></span>
<span data-ttu-id="dd507-103">È importante testare le build di versione dell'app della piattaforma UWP (Universal Windows Platform) nelle rispettive piattaforme di destinazione, perché le configurazioni di tipo Debug e di tipo Versione sono completamente diverse.</span><span class="sxs-lookup"><span data-stu-id="dd507-103">It is important to test the release builds of your Universal Windows Platform app on their target platforms because the debug and release configurations are completely different.</span></span> <span data-ttu-id="dd507-104">Per impostazione predefinita, la configurazione di tipo Debug usa il runtime di .NET Core per compilare l'app, mentre quella di tipo Versione usa .NET Native per compilare l'app nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="dd507-104">By default, the debug configuration uses the .NET Core runtime to compile your app, but the release configuration uses .NET Native to compile your app to native code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dd507-105">Per informazioni sulla gestione con il [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md), e [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) le eccezioni che potrebbero si verifica durante il test delle versioni finali dell'app, vedere "passaggio 4: Risolvere manualmente i metadati mancanti: nel [Guida introduttiva](../../../docs/framework/net-native/getting-started-with-net-native.md) argomento, nonché [Reflection e .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md) e [direttive di Runtime (RD. XML) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="dd507-105">For information on dealing with the [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md), and [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exceptions that you may encounter when testing the release versions of your app, see  "Step 4: Manually resolve missing metadata: in the [Getting Started](../../../docs/framework/net-native/getting-started-with-net-native.md) topic, as well as [Reflection and .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md) and [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
## <a name="debug-and-release-builds"></a><span data-ttu-id="dd507-106">Build di tipo Debug e Versione</span><span class="sxs-lookup"><span data-stu-id="dd507-106">Debug and release builds</span></span>  
 <span data-ttu-id="dd507-107">La build di tipo Debug eseguita nel runtime .NET Core non è stata compilata nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="dd507-107">When the debug build executes against the .NET Core runtime, it has not been compiled to native code.</span></span> <span data-ttu-id="dd507-108">In questo modo tutti i servizi normalmente forniti dal runtime sono disponibili per l'app.</span><span class="sxs-lookup"><span data-stu-id="dd507-108">This makes all of the services ordinarily provided by the runtime available to your app.</span></span>  
  
 <span data-ttu-id="dd507-109">La build di versione viene invece compilata nel codice nativo per le rispettive piattaforme di destinazione, rimuove la maggior parte delle dipendenze da librerie e runtime esterni, oltre a ottimizzare notevolmente il codice garantendo prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="dd507-109">On the other hand, the release build compiles to native code for its target platforms, removes most dependencies on external runtimes and libraries, and heavily optimizes code for maximum performance.</span></span>  
  
 <span data-ttu-id="dd507-110">Quando si esegue il debug di build di tipo Versione compilate con .NET Native:</span><span class="sxs-lookup"><span data-stu-id="dd507-110">When you debug release builds that are compiled by using .NET Native:</span></span>  
  
- <span data-ttu-id="dd507-111">Si usa il motore di debug di .NET Native, che è diverso rispetto ai normali strumenti di debug di .NET.</span><span class="sxs-lookup"><span data-stu-id="dd507-111">You use the .NET Native debug engine, which is different from the normal .NET debugging tools.</span></span>  
  
- <span data-ttu-id="dd507-112">Le dimensioni del file eseguibile vengono ridotte il più possibile.</span><span class="sxs-lookup"><span data-stu-id="dd507-112">The size of your executable is reduced as much as possible.</span></span> <span data-ttu-id="dd507-113">Uno dei modi in cui .NET Native riesce a ridurre le dimensioni del file eseguibile consiste nel tagliare significativamente i messaggi di eccezione di runtime, come descritto in maggiore dettaglio nella sezione [Runtime exception messages](#Messages) .</span><span class="sxs-lookup"><span data-stu-id="dd507-113">One of the ways that .NET Native reduces the size of an executable is by significantly trimming runtime exception messages, a topic discussed in greater detail in the [Runtime exception messages](#Messages) section.</span></span>  
  
- <span data-ttu-id="dd507-114">Il codice viene notevolmente ottimizzato.</span><span class="sxs-lookup"><span data-stu-id="dd507-114">Your code is heavily optimized.</span></span> <span data-ttu-id="dd507-115">Questo significa che laddove possibile viene usato l'incorporamento,</span><span class="sxs-lookup"><span data-stu-id="dd507-115">This means that inlining is used whenever possible.</span></span> <span data-ttu-id="dd507-116">che sposta il codice dalle routine esterne in quella chiamante.   Il fatto che .NET Native fornisca un runtime specializzato e implementi massicciamente l'incorporamento influisce sullo stack di chiamate visualizzato durante il debug.</span><span class="sxs-lookup"><span data-stu-id="dd507-116">(Inlining moves code from external routines into the calling routine.)   The fact that .NET Native provides a specialized runtime and implements aggressive inlining  affects the call stack that is displayed when debugging.</span></span>  <span data-ttu-id="dd507-117">Per altre informazioni, vedere la sezione [Runtime call stack](#CallStack) .</span><span class="sxs-lookup"><span data-stu-id="dd507-117">For more information, see the [Runtime call stack](#CallStack) section.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd507-118">Per controllare se le build di tipo Debug e Versione sono compilate con la catena di strumenti .NET Native, selezionare o deselezionare la casella **Compilare con la catena di strumenti .NET Native** .</span><span class="sxs-lookup"><span data-stu-id="dd507-118">You can control whether the debug and release builds are compiled with the .NET Native tool chain by checking or unchecking the **Compile with .NET Native tool chain** box.</span></span>   <span data-ttu-id="dd507-119">Notare però che per la compilazione della versione di produzione dell'app, Windows Store userà sempre la catena di strumenti .NET Native.</span><span class="sxs-lookup"><span data-stu-id="dd507-119">Note, however, that the Windows Store will always compile the production version of your app with the .NET Native tool chain.</span></span>  
  
<a name="Messages"></a>   
## <a name="runtime-exception-messages"></a><span data-ttu-id="dd507-120">Runtime exception messages</span><span class="sxs-lookup"><span data-stu-id="dd507-120">Runtime exception messages</span></span>  
 <span data-ttu-id="dd507-121">Per ridurre al minimo le dimensioni dei file eseguibili delle applicazioni, .NET Native non include il testo completo dei messaggi di eccezione.</span><span class="sxs-lookup"><span data-stu-id="dd507-121">To minimize application executable size, .NET Native does not include the full text of exception messages.</span></span> <span data-ttu-id="dd507-122">Di conseguenza, è possibile che i messaggi delle eccezioni di runtime generate nelle build di tipo Versione non includano il testo completo,</span><span class="sxs-lookup"><span data-stu-id="dd507-122">As a result, runtime exceptions thrown in release builds may not display the full text of exception messages.</span></span> <span data-ttu-id="dd507-123">ma solo una sottostringa e un collegamento da aprire per visualizzare altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="dd507-123">Instead, the text may consist of a substring along with a link to follow for more information.</span></span> <span data-ttu-id="dd507-124">Le informazioni visualizzate sull'eccezione possono ad esempio essere simili a:</span><span class="sxs-lookup"><span data-stu-id="dd507-124">For example, the exception information may appear as:</span></span>  
  
```  
Exception thrown: '$16_System.AggregateException' in Unknown Module.  
  
Additional information: AggregateException_ctor_DefaultMessage  
  
If there is a handler for this exception, the program may be safely continued.  
```  
  
 <span data-ttu-id="dd507-125">Per visualizzare il messaggio di eccezione completo, eseguire la build di tipo Debug.</span><span class="sxs-lookup"><span data-stu-id="dd507-125">If you need the complete exception message,  run the debug build instead.</span></span> <span data-ttu-id="dd507-126">Ad esempio le informazioni sull'eccezione precedente della build di tipo Versione sono simili alle seguenti nella build di tipo Debug:</span><span class="sxs-lookup"><span data-stu-id="dd507-126">For example, the previous exception information  from the release build might appear as follows in the debug build:</span></span>  
  
```  
Exception thrown: 'System.AggregateException' in NativeApp.exe.  
  
Additional information: Value does not fall within the expected range.  
```  
  
<a name="CallStack"></a>   
## <a name="runtime-call-stack"></a><span data-ttu-id="dd507-127">Runtime call stack</span><span class="sxs-lookup"><span data-stu-id="dd507-127">Runtime call stack</span></span>  
 <span data-ttu-id="dd507-128">A causa dell'incorporamento e di altre ottimizzazioni, lo stack di chiamate visualizzato da un'app compilata con la catena di strumenti .NET Native potrebbe risultare poco utile per identificare chiaramente il percorso di un'eccezione di runtime.</span><span class="sxs-lookup"><span data-stu-id="dd507-128">Because of inlining and other optimizations, the call stack displayed by an app compiled by the .NET Native tool chain may not help you to  clearly identify the path to a runtime exception.</span></span>  
  
 <span data-ttu-id="dd507-129">Per ottenere lo stack completo, eseguire la build di tipo Debug.</span><span class="sxs-lookup"><span data-stu-id="dd507-129">To get the full stack, run the debug build instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd507-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd507-130">See also</span></span>

- [<span data-ttu-id="dd507-131">Debug di App universali di Windows nativa .NET</span><span class="sxs-lookup"><span data-stu-id="dd507-131">Debugging .NET Native Windows Universal Apps</span></span>](https://devblogs.microsoft.com/devops/debugging-net-native-windows-universal-apps/)
- [<span data-ttu-id="dd507-132">Introduzione</span><span class="sxs-lookup"><span data-stu-id="dd507-132">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)
