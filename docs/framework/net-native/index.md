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
ms.openlocfilehash: 28b09bf07d831747be0006ffe1f1d8c5ac5171ce
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052637"
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="0a15c-102">Compilazione di app con .NET Native</span><span class="sxs-lookup"><span data-stu-id="0a15c-102">Compiling Apps with .NET Native</span></span>
<span data-ttu-id="0a15c-103">.NET native è una tecnologia di precompilazione per la compilazione e distribuzione di App di Windows che è inclusa in Visual Studio 2015 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="0a15c-103">.NET Native is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="0a15c-104">che compila automaticamente la versione finale delle app scritte in codice gestito (C# o Visual Basic) e destina .NET Framework e Windows 10 al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="0a15c-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>  
  
 <span data-ttu-id="0a15c-105">In genere, le applicazioni che usano .NET Framework vengono compilate in Microsoft Intermediate Language (IL).</span><span class="sxs-lookup"><span data-stu-id="0a15c-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="0a15c-106">In fase di esecuzione, il compilatore just-in-time (JIT) traduce IL in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="0a15c-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="0a15c-107">Al contrario, .NET Native compila le app Windows direttamente in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="0a15c-107">In contrast, .NET Native compiles Windows apps directly to native code.</span></span> <span data-ttu-id="0a15c-108">Per gli sviluppatori, questo significa che:</span><span class="sxs-lookup"><span data-stu-id="0a15c-108">For developers, this means:</span></span>  
  
- <span data-ttu-id="0a15c-109">Le app offrono le prestazioni del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="0a15c-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="0a15c-110">In genere, le prestazioni risulteranno superiori al codice che viene innanzitutto compilato a livello di integrità e quindi compilato in codice nativo tramite il compilatore JIT.</span><span class="sxs-lookup"><span data-stu-id="0a15c-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span> 
  
- <span data-ttu-id="0a15c-111">È possibile continuare a programmare in c# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0a15c-111">You can continue to program in C# or Visual Basic.</span></span>  
  
- <span data-ttu-id="0a15c-112">È possibile continuare a sfruttare le risorse fornite da .NET Framework, tra cui la libreria di classi, gestione della memoria e Garbage Collection automatiche e la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="0a15c-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>  
  
 <span data-ttu-id="0a15c-113">Per gli utenti delle app .NET nativa offre i seguenti vantaggi:</span><span class="sxs-lookup"><span data-stu-id="0a15c-113">For users of your apps, .NET Native offers these advantages:</span></span>  
  
- <span data-ttu-id="0a15c-114">Tempi di esecuzione per la maggior parte delle App e gli scenari.</span><span class="sxs-lookup"><span data-stu-id="0a15c-114">Faster execution times for the majority of apps and scenarios.</span></span>
  
- <span data-ttu-id="0a15c-115">Tempi di avvio più rapidi per la maggior parte delle App e gli scenari.</span><span class="sxs-lookup"><span data-stu-id="0a15c-115">Faster startup times for the majority of apps and scenarios.</span></span> 
  
- <span data-ttu-id="0a15c-116">Basso costo di distribuzione e l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0a15c-116">Low deployment and update costs.</span></span>  
  
- <span data-ttu-id="0a15c-117">Utilizzo memoria applicazione ottimizzata.</span><span class="sxs-lookup"><span data-stu-id="0a15c-117">Optimized app memory usage.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="0a15c-118">Per la maggior parte delle App e gli scenari, .NET Native offre tempi di avvio significativamente più veloce e prestazioni superiori rispetto a un'app compilata in linguaggio intermedio o di un'immagine NGEN.</span><span class="sxs-lookup"><span data-stu-id="0a15c-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="0a15c-119">Tuttavia, i risultati possono variare.</span><span class="sxs-lookup"><span data-stu-id="0a15c-119">However, your results may vary.</span></span> <span data-ttu-id="0a15c-120">Per assicurarsi che l'app ha tratto vantaggio dai miglioramenti delle prestazioni di .NET Native, è necessario confrontare le prestazioni con quello della versione non - .NET Native dell'app.</span><span class="sxs-lookup"><span data-stu-id="0a15c-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="0a15c-121">Per altre informazioni, vedere [panoramica delle sessioni di prestazioni](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span><span class="sxs-lookup"><span data-stu-id="0a15c-121">For more information, see [Performance Session Overview](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span></span>
 
<span data-ttu-id="0a15c-122">Ma prevede più di una compilazione in codice nativo .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0a15c-122">But .NET Native involves more than a compilation to native code.</span></span> <span data-ttu-id="0a15c-123">trasforma il modo in cui le applicazioni di .NET Framework vengono compilate ed eseguite.</span><span class="sxs-lookup"><span data-stu-id="0a15c-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="0a15c-124">In particolare:</span><span class="sxs-lookup"><span data-stu-id="0a15c-124">In particular:</span></span>  
  
- <span data-ttu-id="0a15c-125">Durante la precompilazione, le parti necessarie di .NET Framework vengono collegate staticamente nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0a15c-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="0a15c-126">Ciò consente di eseguire l'applicazione con le librerie app-local di .NET Framework e di effettuare l'analisi globale per offrire prestazioni ottimali del compilatore.</span><span class="sxs-lookup"><span data-stu-id="0a15c-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="0a15c-127">Di conseguenza, l'avvio delle applicazioni sarà più rapido e coerente dopo l'aggiornamento di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0a15c-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>  
  
- <span data-ttu-id="0a15c-128">Il runtime di .NET Native è ottimizzato per la precompilazione statica e nella maggior parte dei casi offre prestazioni superiori.</span><span class="sxs-lookup"><span data-stu-id="0a15c-128">The .NET Native runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="0a15c-129">Allo stesso tempo, mantiene le funzionalità di reflection di base che gli sviluppatori troveranno estremamente produttive.</span><span class="sxs-lookup"><span data-stu-id="0a15c-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>  
  
- <span data-ttu-id="0a15c-130">.NET native Usa il back-end stesso come il C++ compilatore, che è ottimizzato per scenari di precompilazione statici.</span><span class="sxs-lookup"><span data-stu-id="0a15c-130">.NET Native uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>  
  
 <span data-ttu-id="0a15c-131">.NET native è in grado di offrire i vantaggi delle prestazioni di C++ gestire gli sviluppatori di codice perché Usa gli strumenti identici o simili come C++ dietro le quinte, come illustrato in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="0a15c-131">.NET Native is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>  
  
||<span data-ttu-id="0a15c-132">.NET Native</span><span class="sxs-lookup"><span data-stu-id="0a15c-132">.NET Native</span></span>|<span data-ttu-id="0a15c-133">C++</span><span class="sxs-lookup"><span data-stu-id="0a15c-133">C++</span></span>|  
|-|----------------------------------------------------------------|-----------|  
|<span data-ttu-id="0a15c-134">Librerie</span><span class="sxs-lookup"><span data-stu-id="0a15c-134">Libraries</span></span>|<span data-ttu-id="0a15c-135">.NET Framework + Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="0a15c-135">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="0a15c-136">Win32 + Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="0a15c-136">Win32 + Windows Runtime</span></span>|  
|<span data-ttu-id="0a15c-137">Compilatore</span><span class="sxs-lookup"><span data-stu-id="0a15c-137">Compiler</span></span>|<span data-ttu-id="0a15c-138">Compilatore di ottimizzazione UTC</span><span class="sxs-lookup"><span data-stu-id="0a15c-138">UTC optimizing compiler</span></span>|<span data-ttu-id="0a15c-139">Compilatore di ottimizzazione UTC</span><span class="sxs-lookup"><span data-stu-id="0a15c-139">UTC optimizing compiler</span></span>|  
|<span data-ttu-id="0a15c-140">Distribuito</span><span class="sxs-lookup"><span data-stu-id="0a15c-140">Deployed</span></span>|<span data-ttu-id="0a15c-141">File binari Ready to run</span><span class="sxs-lookup"><span data-stu-id="0a15c-141">Ready-to-run binaries</span></span>|<span data-ttu-id="0a15c-142">File binari Ready to run (ASM)</span><span class="sxs-lookup"><span data-stu-id="0a15c-142">Ready-to-run binaries (ASM)</span></span>|  
|<span data-ttu-id="0a15c-143">Runtime</span><span class="sxs-lookup"><span data-stu-id="0a15c-143">Runtime</span></span>|<span data-ttu-id="0a15c-144">MRT.dll (Runtime CLR minimo)</span><span class="sxs-lookup"><span data-stu-id="0a15c-144">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="0a15c-145">CRT.dll (C Runtime)</span><span class="sxs-lookup"><span data-stu-id="0a15c-145">CRT.dll (C Runtime)</span></span>|  
  
 <span data-ttu-id="0a15c-146">Per le app Windows per Windows 10, caricare i file binari per la compilazione con .NET Native in pacchetti di applicazioni (file APPX) in Windows Store.</span><span class="sxs-lookup"><span data-stu-id="0a15c-146">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a15c-147">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="0a15c-147">In This Section</span></span>  
 <span data-ttu-id="0a15c-148">Per altre informazioni sullo sviluppo di applicazioni con la compilazione con .NET Native, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="0a15c-148">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>  
  
- [<span data-ttu-id="0a15c-149">Introduzione a compilazione codice .NET Native: La procedura dettagliata dell'esperienza per sviluppatori</span><span class="sxs-lookup"><span data-stu-id="0a15c-149">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
- <span data-ttu-id="0a15c-150">[Compilazione e .NET native:](../../../docs/framework/net-native/net-native-and-compilation.md) Modo in cui .NET Native compila il progetto in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="0a15c-150">[.NET Native and Compilation:](../../../docs/framework/net-native/net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>  
  
- [<span data-ttu-id="0a15c-151">Reflection e .NET Native</span><span class="sxs-lookup"><span data-stu-id="0a15c-151">Reflection and .NET Native</span></span>](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    - [<span data-ttu-id="0a15c-152">API basate sulla reflection</span><span class="sxs-lookup"><span data-stu-id="0a15c-152">APIs That Rely on Reflection</span></span>](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    - [<span data-ttu-id="0a15c-153">Riferimento all'API Reflection</span><span class="sxs-lookup"><span data-stu-id="0a15c-153">Reflection API Reference</span></span>](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    - [<span data-ttu-id="0a15c-154">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="0a15c-154">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
- <span data-ttu-id="0a15c-155">[Serialization and Metadata](../../../docs/framework/net-native/serialization-and-metadata.md) (Serializzazione e metadati)</span><span class="sxs-lookup"><span data-stu-id="0a15c-155">[Serialization and Metadata](../../../docs/framework/net-native/serialization-and-metadata.md)</span></span>  
  
- <span data-ttu-id="0a15c-156">[Migrating Your Windows Store App to .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md) (Migrazione dell'app di Windows Store a .NET Native)</span><span class="sxs-lookup"><span data-stu-id="0a15c-156">[Migrating Your Windows Store App to .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)</span></span>  
  
- [<span data-ttu-id="0a15c-157">Risoluzione dei problemi generale per .NET Native</span><span class="sxs-lookup"><span data-stu-id="0a15c-157">.NET Native General Troubleshooting</span></span>](../../../docs/framework/net-native/net-native-general-troubleshooting.md)
