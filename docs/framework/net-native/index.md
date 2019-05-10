---
title: Compilazione di app con .NET Native
ms.date: 03/30/2017
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3c845cefad451c608f5c095e4941c3368dc9975
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650553"
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="77980-102">Compilazione di app con .NET Native</span><span class="sxs-lookup"><span data-stu-id="77980-102">Compiling Apps with .NET Native</span></span>
[!INCLUDE[net_native](../../../includes/net-native-md.md)] <span data-ttu-id="77980-103">è una tecnologia di precompilazione per la compilazione e distribuzione di App di Windows che è inclusa in Visual Studio 2015 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="77980-103">is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="77980-104">che compila automaticamente la versione finale delle app scritte in codice gestito (C# o Visual Basic) e destina .NET Framework e Windows 10 al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="77980-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>  
  
 <span data-ttu-id="77980-105">In genere, le applicazioni che usano .NET Framework vengono compilate in Microsoft Intermediate Language (IL).</span><span class="sxs-lookup"><span data-stu-id="77980-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="77980-106">In fase di esecuzione, il compilatore just-in-time (JIT) traduce IL in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="77980-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="77980-107">Al contrario, [!INCLUDE[net_native](../../../includes/net-native-md.md)] consente di compilare applicazioni Windows direttamente in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="77980-107">In contrast, [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiles Windows apps directly to native code.</span></span> <span data-ttu-id="77980-108">Per gli sviluppatori, questo significa che:</span><span class="sxs-lookup"><span data-stu-id="77980-108">For developers, this means:</span></span>  
  
- <span data-ttu-id="77980-109">Le app offrono le prestazioni del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="77980-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="77980-110">In genere, le prestazioni risulteranno superiori al codice che viene innanzitutto compilato a livello di integrità e quindi compilato in codice nativo tramite il compilatore JIT.</span><span class="sxs-lookup"><span data-stu-id="77980-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span> 
  
- <span data-ttu-id="77980-111">È possibile continuare a programmare in c# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="77980-111">You can continue to program in C# or Visual Basic.</span></span>  
  
- <span data-ttu-id="77980-112">È possibile continuare a sfruttare le risorse fornite da .NET Framework, tra cui la libreria di classi, gestione della memoria e Garbage Collection automatiche e la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="77980-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>  
  
 <span data-ttu-id="77980-113">Per gli utenti delle applicazioni, [!INCLUDE[net_native](../../../includes/net-native-md.md)] offre i seguenti vantaggi:</span><span class="sxs-lookup"><span data-stu-id="77980-113">For users of your apps, [!INCLUDE[net_native](../../../includes/net-native-md.md)] offers these advantages:</span></span>  
  
- <span data-ttu-id="77980-114">Tempi di esecuzione per la maggior parte delle App e gli scenari.</span><span class="sxs-lookup"><span data-stu-id="77980-114">Faster execution times for the majority of apps and scenarios.</span></span>
  
- <span data-ttu-id="77980-115">Tempi di avvio più rapidi per la maggior parte delle App e gli scenari.</span><span class="sxs-lookup"><span data-stu-id="77980-115">Faster startup times for the majority of apps and scenarios.</span></span> 
  
- <span data-ttu-id="77980-116">Basso costo di distribuzione e l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="77980-116">Low deployment and update costs.</span></span>  
  
- <span data-ttu-id="77980-117">Utilizzo memoria applicazione ottimizzata.</span><span class="sxs-lookup"><span data-stu-id="77980-117">Optimized app memory usage.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="77980-118">Per la maggior parte delle App e gli scenari, .NET Native offre tempi di avvio significativamente più veloce e prestazioni superiori rispetto a un'app compilata in linguaggio intermedio o di un'immagine NGEN.</span><span class="sxs-lookup"><span data-stu-id="77980-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="77980-119">Tuttavia, i risultati possono variare.</span><span class="sxs-lookup"><span data-stu-id="77980-119">However, your results may vary.</span></span> <span data-ttu-id="77980-120">Per assicurarsi che l'app ha tratto vantaggio dai miglioramenti delle prestazioni di .NET Native, è necessario confrontare le prestazioni con quello della versione non - .NET Native dell'app.</span><span class="sxs-lookup"><span data-stu-id="77980-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="77980-121">Per altre informazioni, vedere [panoramica delle sessioni di prestazioni](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span><span class="sxs-lookup"><span data-stu-id="77980-121">For more information, see [Performance Session Overview](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span></span>
 
<span data-ttu-id="77980-122">Ma [!INCLUDE[net_native](../../../includes/net-native-md.md)] prevede molto più di una semplice compilazione in codice nativo:</span><span class="sxs-lookup"><span data-stu-id="77980-122">But [!INCLUDE[net_native](../../../includes/net-native-md.md)] involves more than a compilation to native code.</span></span> <span data-ttu-id="77980-123">trasforma il modo in cui le applicazioni di .NET Framework vengono compilate ed eseguite.</span><span class="sxs-lookup"><span data-stu-id="77980-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="77980-124">In particolare:</span><span class="sxs-lookup"><span data-stu-id="77980-124">In particular:</span></span>  
  
- <span data-ttu-id="77980-125">Durante la precompilazione, le parti necessarie di .NET Framework vengono collegate staticamente nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="77980-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="77980-126">Ciò consente di eseguire l'applicazione con le librerie app-local di .NET Framework e di effettuare l'analisi globale per offrire prestazioni ottimali del compilatore.</span><span class="sxs-lookup"><span data-stu-id="77980-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="77980-127">Di conseguenza, l'avvio delle applicazioni sarà più rapido e coerente dopo l'aggiornamento di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="77980-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>  
  
- <span data-ttu-id="77980-128">Il [!INCLUDE[net_native](../../../includes/net-native-md.md)] runtime è ottimizzato per la precompilazione statica e nella maggior parte dei casi offre prestazioni superiori.</span><span class="sxs-lookup"><span data-stu-id="77980-128">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="77980-129">Allo stesso tempo, mantiene le funzionalità di reflection di base che gli sviluppatori troveranno estremamente produttive.</span><span class="sxs-lookup"><span data-stu-id="77980-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>  
  
- [!INCLUDE[net_native](../../../includes/net-native-md.md)] <span data-ttu-id="77980-130">usa lo stesso back-end del compilatore C++, che è ottimizzato per scenari di precompilazione statici.</span><span class="sxs-lookup"><span data-stu-id="77980-130">uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] <span data-ttu-id="77980-131">può offrire i vantaggi delle prestazioni di C++ agli sviluppatori di codice gestito perché usa strumenti identici o simili come C++ dietro le quinte, come illustrato in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="77980-131">is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>  
  
||[!INCLUDE[net_native](../../../includes/net-native-md.md)]|<span data-ttu-id="77980-132">C++</span><span class="sxs-lookup"><span data-stu-id="77980-132">C++</span></span>|  
|-|----------------------------------------------------------------|-----------|  
|<span data-ttu-id="77980-133">Librerie</span><span class="sxs-lookup"><span data-stu-id="77980-133">Libraries</span></span>|<span data-ttu-id="77980-134">.NET Framework + Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="77980-134">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="77980-135">Win32 + Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="77980-135">Win32 + Windows Runtime</span></span>|  
|<span data-ttu-id="77980-136">Compilatore</span><span class="sxs-lookup"><span data-stu-id="77980-136">Compiler</span></span>|<span data-ttu-id="77980-137">Compilatore di ottimizzazione UTC</span><span class="sxs-lookup"><span data-stu-id="77980-137">UTC optimizing compiler</span></span>|<span data-ttu-id="77980-138">Compilatore di ottimizzazione UTC</span><span class="sxs-lookup"><span data-stu-id="77980-138">UTC optimizing compiler</span></span>|  
|<span data-ttu-id="77980-139">Distribuito</span><span class="sxs-lookup"><span data-stu-id="77980-139">Deployed</span></span>|<span data-ttu-id="77980-140">File binari Ready to run</span><span class="sxs-lookup"><span data-stu-id="77980-140">Ready-to-run binaries</span></span>|<span data-ttu-id="77980-141">File binari Ready to run (ASM)</span><span class="sxs-lookup"><span data-stu-id="77980-141">Ready-to-run binaries (ASM)</span></span>|  
|<span data-ttu-id="77980-142">Runtime</span><span class="sxs-lookup"><span data-stu-id="77980-142">Runtime</span></span>|<span data-ttu-id="77980-143">MRT.dll (Runtime CLR minimo)</span><span class="sxs-lookup"><span data-stu-id="77980-143">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="77980-144">CRT.dll (C Runtime)</span><span class="sxs-lookup"><span data-stu-id="77980-144">CRT.dll (C Runtime)</span></span>|  
  
 <span data-ttu-id="77980-145">Per le app Windows per Windows 10, caricare i file binari per la compilazione con .NET Native in pacchetti di applicazioni (file APPX) in Windows Store.</span><span class="sxs-lookup"><span data-stu-id="77980-145">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77980-146">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="77980-146">In This Section</span></span>  
 <span data-ttu-id="77980-147">Per altre informazioni sullo sviluppo di applicazioni con la compilazione con .NET Native, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="77980-147">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>  
  
- [<span data-ttu-id="77980-148">Introduzione a compilazione codice .NET Native: La procedura dettagliata dell'esperienza per sviluppatori</span><span class="sxs-lookup"><span data-stu-id="77980-148">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
- <span data-ttu-id="77980-149">[Compilazione e .NET native:](../../../docs/framework/net-native/net-native-and-compilation.md) Modo in cui .NET Native compila il progetto in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="77980-149">[.NET Native and Compilation:](../../../docs/framework/net-native/net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>  
  
- [<span data-ttu-id="77980-150">Reflection e .NET Native</span><span class="sxs-lookup"><span data-stu-id="77980-150">Reflection and .NET Native</span></span>](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    - [<span data-ttu-id="77980-151">API basate sulla reflection</span><span class="sxs-lookup"><span data-stu-id="77980-151">APIs That Rely on Reflection</span></span>](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    - [<span data-ttu-id="77980-152">Riferimento all'API Reflection</span><span class="sxs-lookup"><span data-stu-id="77980-152">Reflection API Reference</span></span>](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    - [<span data-ttu-id="77980-153">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="77980-153">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
- <span data-ttu-id="77980-154">[Serialization and Metadata](../../../docs/framework/net-native/serialization-and-metadata.md) (Serializzazione e metadati)</span><span class="sxs-lookup"><span data-stu-id="77980-154">[Serialization and Metadata](../../../docs/framework/net-native/serialization-and-metadata.md)</span></span>  
  
- <span data-ttu-id="77980-155">[Migrating Your Windows Store App to .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md) (Migrazione dell'app di Windows Store a .NET Native)</span><span class="sxs-lookup"><span data-stu-id="77980-155">[Migrating Your Windows Store App to .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)</span></span>  
  
- [<span data-ttu-id="77980-156">Risoluzione dei problemi generale per .NET Native</span><span class="sxs-lookup"><span data-stu-id="77980-156">.NET Native General Troubleshooting</span></span>](../../../docs/framework/net-native/net-native-general-troubleshooting.md)
