---
title: Elementi obsoleti nella libreria di classi .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- obsolete [.NET Framework]
- what's obsolete [.NET Framework]
- deprecated [.NET Framework]
ms.assetid: d356a43a-73df-4ae2-a457-b9628074c7cd
caps.latest.revision: 19
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7afe9496ca116ed0c330c4ff9e7c3a855249cf14
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="what39s-obsolete-in-the-net-framework-class-library"></a><span data-ttu-id="45485-102">Elementi obsoleti nella libreria di classi .NET Framework</span><span class="sxs-lookup"><span data-stu-id="45485-102">What&#39;s Obsolete in the .NET Framework Class Library</span></span>
<span data-ttu-id="45485-103">.NET Framework cambia nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="45485-103">The .NET Framework changes over time.</span></span> <span data-ttu-id="45485-104">In ogni nuova versione vengono aggiunti nuovi tipi e membri dei tipi che forniscono nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="45485-104">Each new version adds new types and type members that provide new functionality.</span></span> <span data-ttu-id="45485-105">Anche i tipi esistenti e i relativi membri cambiano nel tempo.</span><span class="sxs-lookup"><span data-stu-id="45485-105">Existing types and their members also change over time.</span></span> <span data-ttu-id="45485-106">Alcuni tipi, ad esempio, perdono di importanza in quanto la tecnologia che supportano viene sostituita da una nuova tecnologia, e alcuni metodi vengono sostituiti da altri più nuovi che sono più adatti o più completi in termini di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="45485-106">For example, some types become less important as the technology they support is replaced by a new technology, and some methods are superseded by newer methods that are either more convenient or more full-featured.</span></span>  
  
 <span data-ttu-id="45485-107">Sia in .NET Framework sia in Common Language Runtime si cerca di supportare la compatibilità con le versioni precedenti, grazie alla quale le applicazioni sviluppate con una versione di .NET Framework possono essere eseguite nella versione di .NET Framework successiva.</span><span class="sxs-lookup"><span data-stu-id="45485-107">The .NET Framework and the common language runtime strive to support backward compatibility (allowing applications that were developed with one version of the .NET Framework to run on the next version of the .NET Framework).</span></span> <span data-ttu-id="45485-108">Ciò rende difficile la semplice rimozione di un tipo o di un membro del tipo.</span><span class="sxs-lookup"><span data-stu-id="45485-108">This makes it difficult to simply remove a type or a type member.</span></span> <span data-ttu-id="45485-109">Per ovviare a questa difficoltà, si indica che un tipo o un membro del tipo non deve più essere usato contrassegnandolo come obsoleto o deprecato.</span><span class="sxs-lookup"><span data-stu-id="45485-109">Instead, the .NET Framework indicates that a type or a type member should no longer be used by marking it as obsolete or deprecated.</span></span> <span data-ttu-id="45485-110">La deprecazione di un tipo o di un membro ne implica il contrassegno, in modo che gli sviluppatori sappiano che verrà rimosso e abbiano il tempo di rispondere a tale rimozione.</span><span class="sxs-lookup"><span data-stu-id="45485-110">Deprecating a type or a member involves marking it so that developers are aware it will go away and have time to respond to its removal.</span></span> <span data-ttu-id="45485-111">Tuttavia, il codice esistente che usa il tipo o il membro continua a essere eseguito nella nuova versione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="45485-111">However, existing code that uses the type or member continues to run in the new version of the .NET Framework.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45485-112">Se applicati ai tipi e ai membri di .NET Framework, i termini *obsoleto* e *deprecato* hanno lo stesso significato.</span><span class="sxs-lookup"><span data-stu-id="45485-112">The terms *obsolete* and *deprecated* have the same meaning when applied to the types and members of the .NET Framework.</span></span>  
  
## <a name="the-obsoleteattribute-attribute"></a><span data-ttu-id="45485-113">Attributo ObsoleteAttribute</span><span class="sxs-lookup"><span data-stu-id="45485-113">The ObsoleteAttribute Attribute</span></span>  
 <span data-ttu-id="45485-114">.NET Framework indica che un tipo o un membro del tipo è obsoleto contrassegnandolo con l'attributo <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="45485-114">The .NET Framework indicates that a type or type member is obsolete by marking it with the <xref:System.ObsoleteAttribute> attribute.</span></span> <span data-ttu-id="45485-115">L'applicazione dell'attributo a un tipo o un membro indica che quel tipo o membro sarà rimosso nelle versioni future di .NET Framework, senza causare interruzioni nel codice compilato che lo usa.</span><span class="sxs-lookup"><span data-stu-id="45485-115">Applying the attribute to a type or member indicates that that type or member will be removed in some future version of the .NET Framework without breaking compiled code that uses that member.</span></span>  
  
 <span data-ttu-id="45485-116">Oltre a indicare che un tipo o un membro del tipo è obsoleto, <xref:System.ObsoleteAttribute> definisce il modo in cui il compilatore gestisce il codice sorgente che include quel tipo o membro.</span><span class="sxs-lookup"><span data-stu-id="45485-116">In addition to indicating that a type or a type member is obsolete, <xref:System.ObsoleteAttribute> defines how the compiler handles source code that includes that type or member.</span></span> <span data-ttu-id="45485-117">Il compilatore può compilare il codice generando però un messaggio di avviso oppure può considerare l'uso del tipo o membro come un errore.</span><span class="sxs-lookup"><span data-stu-id="45485-117">The compiler can compile the code but emit a warning message, or it can treat the use of the type or member as an error.</span></span> <span data-ttu-id="45485-118">Nel primo caso, il codice può essere compilato correttamente, ma un messaggio di avviso indica che il tipo o membro è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="45485-118">In the first case, the code can successfully compile, but a warning message indicates that the type or member is obsolete.</span></span> <span data-ttu-id="45485-119">Nel secondo caso, la compilazione non riesce.</span><span class="sxs-lookup"><span data-stu-id="45485-119">In the second case, compilation fails.</span></span>  
  
 <span data-ttu-id="45485-120">Anche se la compilazione produce un errore anziché un messaggio di avviso, <xref:System.ObsoleteAttribute> non influisce sul comportamento in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="45485-120">Even if compilation produces an error instead of a warning message, <xref:System.ObsoleteAttribute> does not affect run-time behavior.</span></span> <span data-ttu-id="45485-121">In altre parole, le applicazioni che usano il tipo o membro e che sono state compilate correttamente verranno sempre eseguite correttamente.</span><span class="sxs-lookup"><span data-stu-id="45485-121">That is, applications that use the type or member and that have compiled successfully will always run successfully.</span></span> <span data-ttu-id="45485-122">Soltanto il tentativo di ricompilare un'applicazione che usa il tipo o membro avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="45485-122">Only the attempt to recompile an application that uses the type or member fails.</span></span>  
  
## <a name="how-to-handle-obsolete-types-and-members"></a><span data-ttu-id="45485-123">Come gestire tipi e membri obsoleti</span><span class="sxs-lookup"><span data-stu-id="45485-123">How to Handle Obsolete Types and Members</span></span>  
 <span data-ttu-id="45485-124">Quando si aggiorna e si ricompila il codice esistente, l'uso di un tipo o membro obsoleto che genera un avviso del compilatore nell'applicazione è perfettamente accettabile.</span><span class="sxs-lookup"><span data-stu-id="45485-124">When you upgrade and recompile existing code, using an obsolete type or member that produces a compiler warning in your application is perfectly acceptable.</span></span> <span data-ttu-id="45485-125">Tuttavia, è consigliabile rivedere il messaggio di avviso del compilatore per stabilire se sia opportuno modificare il codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="45485-125">However, you should review the compiler warning message to determine whether you should change your application code.</span></span> <span data-ttu-id="45485-126">Se il messaggio non indica un'alternativa adatta, adottare una delle soluzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="45485-126">If the message does not point to a suitable alternative, you should do either of the following:</span></span>  
  
-   <span data-ttu-id="45485-127">Modificare il codice rimuovendo l'uso del tipo o membro, se possibile.</span><span class="sxs-lookup"><span data-stu-id="45485-127">Change your code by removing the use of the type or member, if possible.</span></span>  
  
     <span data-ttu-id="45485-128">-oppure-</span><span class="sxs-lookup"><span data-stu-id="45485-128">-or-</span></span>  
  
-   <span data-ttu-id="45485-129">Rivedere la documentazione di quest'area tecnologica per stabilire come rispondere a questa deprecazione.</span><span class="sxs-lookup"><span data-stu-id="45485-129">Review the documentation for this technology area to determine how to respond to the deprecation.</span></span>  
  
 <span data-ttu-id="45485-130">Si può scegliere di non ricompilare il codice esistente con una versione successiva di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="45485-130">You may choose not to recompile existing code against a later version of the .NET Framework.</span></span> <span data-ttu-id="45485-131">È possibile invece specificare la versione di .NET Framework con la quale eseguire il codice compilato esistente.</span><span class="sxs-lookup"><span data-stu-id="45485-131">Instead, you can specify the version of the .NET Framework against which your existing compiled code runs.</span></span> <span data-ttu-id="45485-132">Si supponga ad esempio di avere un'applicazione denominata app1.exe, compilata con [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)], e di voler eseguire l'applicazione in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45485-132">For example, suppose that you have an application named app1.exe that was compiled against the [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)], but you want the application to run against the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="45485-133">La procedura da adottare è la seguente:</span><span class="sxs-lookup"><span data-stu-id="45485-133">This requires the following steps:</span></span>  
  
1.  <span data-ttu-id="45485-134">Creare un file di configurazione per l'eseguibile principale e denominarlo *NomeApp*.exe.config, dove *NomeApp* è il nome dell'eseguibile dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="45485-134">Create a configuration file for your main executable and name it *appName*.exe.config, where *appName* is the name of the application executable.</span></span> <span data-ttu-id="45485-135">Nel caso dell'applicazione denominata app1.exe dell'esempio, il nome del file di configurazione da creare sarebbe app1.exe.config.</span><span class="sxs-lookup"><span data-stu-id="45485-135">For the application named app1.exe in our example, you would create a configuration file named app1.exe.config.</span></span>  
  
2.  <span data-ttu-id="45485-136">Aggiungere il codice seguente al file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="45485-136">Add the following to the configuration file.</span></span>  
  
    ```xml  
    <configuration>  
       <startup>   
          <supportedRuntime version="v4.0" />  
       </startup>  
    </configuration>  
    ```  
  
 <span data-ttu-id="45485-137">La tabella seguente elenca i valori di stringa che è possibile assegnare all'attributo `version` per scegliere come destinazione una versione di .NET Framework specifica.</span><span class="sxs-lookup"><span data-stu-id="45485-137">The following table lists the string values that you can assign to the `version` attribute to target a specific version of the .NET Framework.</span></span>  
  
|<span data-ttu-id="45485-138">Versione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="45485-138">.NET Framework version</span></span>|<span data-ttu-id="45485-139">Stringa `version`</span><span class="sxs-lookup"><span data-stu-id="45485-139">`version` string</span></span>|
|-|-|  
|<span data-ttu-id="45485-140">4.7</span><span class="sxs-lookup"><span data-stu-id="45485-140">4.7</span></span>|<span data-ttu-id="45485-141">v4.0</span><span class="sxs-lookup"><span data-stu-id="45485-141">v4.0</span></span>|  
|<span data-ttu-id="45485-142">4.6 (incluse 4.6.1 e 4.6.2)</span><span class="sxs-lookup"><span data-stu-id="45485-142">4.6 (including 4.6.1 and 4.6.2)</span></span>|<span data-ttu-id="45485-143">v4.0</span><span class="sxs-lookup"><span data-stu-id="45485-143">v4.0</span></span>|  
|<span data-ttu-id="45485-144">4.5 (incluse 4.5.1 e 4.5.2)</span><span class="sxs-lookup"><span data-stu-id="45485-144">4.5 (including 4.5.1 and 4.5.2)</span></span>|<span data-ttu-id="45485-145">v4.0</span><span class="sxs-lookup"><span data-stu-id="45485-145">v4.0</span></span>|  
|<span data-ttu-id="45485-146">4</span><span class="sxs-lookup"><span data-stu-id="45485-146">4</span></span>|<span data-ttu-id="45485-147">v4.0</span><span class="sxs-lookup"><span data-stu-id="45485-147">v4.0</span></span>|  
|<span data-ttu-id="45485-148">3.5</span><span class="sxs-lookup"><span data-stu-id="45485-148">3.5</span></span>|<span data-ttu-id="45485-149">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="45485-149">v2.0.50727</span></span>|  
|<span data-ttu-id="45485-150">2.0</span><span class="sxs-lookup"><span data-stu-id="45485-150">2.0</span></span>|<span data-ttu-id="45485-151">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="45485-151">v2.0.50727</span></span>|  
|<span data-ttu-id="45485-152">1.1</span><span class="sxs-lookup"><span data-stu-id="45485-152">1.1</span></span>|<span data-ttu-id="45485-153">v1.1.4322</span><span class="sxs-lookup"><span data-stu-id="45485-153">v1.1.4322</span></span>|  
|<span data-ttu-id="45485-154">1.0</span><span class="sxs-lookup"><span data-stu-id="45485-154">1.0</span></span>|<span data-ttu-id="45485-155">v1.0.3705</span><span class="sxs-lookup"><span data-stu-id="45485-155">v1.0.3705</span></span>|  
  
## <a name="obsolete-lists-for-the-net-framework-45-and-46"></a><span data-ttu-id="45485-156">Elenchi degli elementi obsoleti per .NET Framework 4.5 e 4.6</span><span class="sxs-lookup"><span data-stu-id="45485-156">Obsolete Lists for the .NET Framework 4.5 and 4.6</span></span>  
 [<span data-ttu-id="45485-157">Tipi obsoleti</span><span class="sxs-lookup"><span data-stu-id="45485-157">Obsolete Types</span></span>](../../../docs/framework/whats-new/obsolete-types.md)  
  
 [<span data-ttu-id="45485-158">Membri obsoleti</span><span class="sxs-lookup"><span data-stu-id="45485-158">Obsolete Members</span></span>](../../../docs/framework/whats-new/obsolete-members.md)  
  
## <a name="obsolete-lists-for-previous-versions"></a><span data-ttu-id="45485-159">Elenchi di elementi obsoleti per le versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="45485-159">Obsolete Lists for Previous Versions</span></span>  
 [<span data-ttu-id="45485-160">Tipi obsoleti in .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="45485-160">Obsolete Types in the .NET Framework 4</span></span>](http://go.microsoft.com/fwlink/?LinkId=224224)  
  
 [<span data-ttu-id="45485-161">Membri obsoleti in .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="45485-161">Obsolete Members in the .NET Framework 4</span></span>](http://go.microsoft.com/fwlink/?LinkId=224227)  
  
 [<span data-ttu-id="45485-162">Elenco degli elementi obsoleti di .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="45485-162">.NET Framework 3.5 Obsolete List</span></span>](http://go.microsoft.com/fwlink/?LinkId=163710)  
  
 [<span data-ttu-id="45485-163">Elenco degli elementi obsoleti di .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="45485-163">.NET Framework 2.0 Obsolete List</span></span>](http://go.microsoft.com/fwlink/?LinkID=125264)  
  
## <a name="see-also"></a><span data-ttu-id="45485-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45485-164">See Also</span></span>  
 [<span data-ttu-id="45485-165">Elemento \<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="45485-165">\<supportedRuntime> Element</span></span>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)

