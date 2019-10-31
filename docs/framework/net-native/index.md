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
ms.openlocfilehash: 1f176e81905fe68c6d740a13240fe814659a7a59
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128380"
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="07c26-102">Compilazione di app con .NET Native</span><span class="sxs-lookup"><span data-stu-id="07c26-102">Compiling Apps with .NET Native</span></span>

<span data-ttu-id="07c26-103">.NET Native è una tecnologia di precompilazione per la compilazione e la distribuzione di app di Windows incluse in Visual Studio 2015 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="07c26-103">.NET Native is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="07c26-104">che compila automaticamente la versione finale delle app scritte in codice gestito (C# o Visual Basic) e destina .NET Framework e Windows 10 al codice nativo.</span><span class="sxs-lookup"><span data-stu-id="07c26-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>

<span data-ttu-id="07c26-105">In genere, le applicazioni che usano .NET Framework vengono compilate in Microsoft Intermediate Language (IL).</span><span class="sxs-lookup"><span data-stu-id="07c26-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="07c26-106">In fase di esecuzione, il compilatore just-in-time (JIT) traduce IL in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="07c26-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="07c26-107">Al contrario, .NET Native compila le app di Windows direttamente nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="07c26-107">In contrast, .NET Native compiles Windows apps directly to native code.</span></span> <span data-ttu-id="07c26-108">Per gli sviluppatori, questo significa che:</span><span class="sxs-lookup"><span data-stu-id="07c26-108">For developers, this means:</span></span>

- <span data-ttu-id="07c26-109">Le app offrono le prestazioni del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="07c26-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="07c26-110">In genere, le prestazioni saranno superiori a quelle del codice prima compilato in IL e quindi compilate in codice nativo dal compilatore JIT.</span><span class="sxs-lookup"><span data-stu-id="07c26-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span>

- <span data-ttu-id="07c26-111">È possibile continuare a programmare in c# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="07c26-111">You can continue to program in C# or Visual Basic.</span></span>

- <span data-ttu-id="07c26-112">È possibile continuare a sfruttare le risorse fornite da .NET Framework, tra cui la libreria di classi, gestione della memoria e Garbage Collection automatiche e la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="07c26-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>

<span data-ttu-id="07c26-113">Per gli utenti delle app, .NET Native offre i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="07c26-113">For users of your apps, .NET Native offers these advantages:</span></span>

- <span data-ttu-id="07c26-114">Tempi di esecuzione più rapidi per la maggior parte delle app e degli scenari.</span><span class="sxs-lookup"><span data-stu-id="07c26-114">Faster execution times for the majority of apps and scenarios.</span></span>

- <span data-ttu-id="07c26-115">Tempi di avvio più rapidi per la maggior parte delle app e degli scenari.</span><span class="sxs-lookup"><span data-stu-id="07c26-115">Faster startup times for the majority of apps and scenarios.</span></span>

- <span data-ttu-id="07c26-116">Riduzione dei costi di distribuzione e aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="07c26-116">Low deployment and update costs.</span></span>

- <span data-ttu-id="07c26-117">Utilizzo ottimizzato della memoria dell'app.</span><span class="sxs-lookup"><span data-stu-id="07c26-117">Optimized app memory usage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07c26-118">Per la maggior parte delle app e degli scenari, .NET Native offre tempi di avvio notevolmente più veloci e prestazioni superiori rispetto a un'app compilata con IL o a un'immagine NGEN.</span><span class="sxs-lookup"><span data-stu-id="07c26-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="07c26-119">Tuttavia, i risultati possono variare.</span><span class="sxs-lookup"><span data-stu-id="07c26-119">However, your results may vary.</span></span> <span data-ttu-id="07c26-120">Per assicurarsi che l'app abbia tratto vantaggio dai miglioramenti apportati alle prestazioni di .NET Native, è necessario confrontarne le prestazioni con quella della versione nativa di non-.NET dell'app.</span><span class="sxs-lookup"><span data-stu-id="07c26-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="07c26-121">Per ulteriori informazioni, vedere [Cenni preliminari sulle sessioni di prestazioni](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span><span class="sxs-lookup"><span data-stu-id="07c26-121">For more information, see [Performance Session Overview](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span></span>

<span data-ttu-id="07c26-122">Tuttavia .NET Native implica più di una compilazione in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="07c26-122">But .NET Native involves more than a compilation to native code.</span></span> <span data-ttu-id="07c26-123">trasforma il modo in cui le applicazioni di .NET Framework vengono compilate ed eseguite.</span><span class="sxs-lookup"><span data-stu-id="07c26-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="07c26-124">In particolare:</span><span class="sxs-lookup"><span data-stu-id="07c26-124">In particular:</span></span>

- <span data-ttu-id="07c26-125">Durante la precompilazione, le parti necessarie di .NET Framework vengono collegate staticamente nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="07c26-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="07c26-126">Ciò consente di eseguire l'applicazione con le librerie app-local di .NET Framework e di effettuare l'analisi globale per offrire prestazioni ottimali del compilatore.</span><span class="sxs-lookup"><span data-stu-id="07c26-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="07c26-127">Di conseguenza, l'avvio delle applicazioni sarà più rapido e coerente dopo l'aggiornamento di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="07c26-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>

- <span data-ttu-id="07c26-128">Il runtime di .NET Native è ottimizzato per la precompilazione statica e nella maggior parte dei casi offre prestazioni superiori.</span><span class="sxs-lookup"><span data-stu-id="07c26-128">The .NET Native runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="07c26-129">Allo stesso tempo, mantiene le funzionalità di reflection di base che gli sviluppatori troveranno estremamente produttive.</span><span class="sxs-lookup"><span data-stu-id="07c26-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>

- <span data-ttu-id="07c26-130">.NET Native usa lo stesso back-end del C++ compilatore, ottimizzato per scenari di precompilazione statici.</span><span class="sxs-lookup"><span data-stu-id="07c26-130">.NET Native uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>

<span data-ttu-id="07c26-131">.NET Native è in grado di sfruttare i vantaggi delle C++ prestazioni di per gli sviluppatori di codice gestito, perché usa gli stessi C++ strumenti o simili di quelli usati sotto la cappa, come illustrato in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="07c26-131">.NET Native is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>

||<span data-ttu-id="07c26-132">.NET Native</span><span class="sxs-lookup"><span data-stu-id="07c26-132">.NET Native</span></span>|<span data-ttu-id="07c26-133">C++</span><span class="sxs-lookup"><span data-stu-id="07c26-133">C++</span></span>|
|-|----------------------------------------------------------------|-----------|
|<span data-ttu-id="07c26-134">Librerie</span><span class="sxs-lookup"><span data-stu-id="07c26-134">Libraries</span></span>|<span data-ttu-id="07c26-135">.NET Framework + Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="07c26-135">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="07c26-136">Win32 + Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="07c26-136">Win32 + Windows Runtime</span></span>|
|<span data-ttu-id="07c26-137">Compilatore</span><span class="sxs-lookup"><span data-stu-id="07c26-137">Compiler</span></span>|<span data-ttu-id="07c26-138">Compilatore di ottimizzazione UTC</span><span class="sxs-lookup"><span data-stu-id="07c26-138">UTC optimizing compiler</span></span>|<span data-ttu-id="07c26-139">Compilatore di ottimizzazione UTC</span><span class="sxs-lookup"><span data-stu-id="07c26-139">UTC optimizing compiler</span></span>|
|<span data-ttu-id="07c26-140">Distribuito</span><span class="sxs-lookup"><span data-stu-id="07c26-140">Deployed</span></span>|<span data-ttu-id="07c26-141">File binari Ready to run</span><span class="sxs-lookup"><span data-stu-id="07c26-141">Ready-to-run binaries</span></span>|<span data-ttu-id="07c26-142">File binari Ready to run (ASM)</span><span class="sxs-lookup"><span data-stu-id="07c26-142">Ready-to-run binaries (ASM)</span></span>|
|<span data-ttu-id="07c26-143">Runtime</span><span class="sxs-lookup"><span data-stu-id="07c26-143">Runtime</span></span>|<span data-ttu-id="07c26-144">MRT.dll (Runtime CLR minimo)</span><span class="sxs-lookup"><span data-stu-id="07c26-144">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="07c26-145">CRT.dll (C Runtime)</span><span class="sxs-lookup"><span data-stu-id="07c26-145">CRT.dll (C Runtime)</span></span>|

<span data-ttu-id="07c26-146">Per le app Windows per Windows 10, caricare i file binari per la compilazione con .NET Native in pacchetti di applicazioni (file APPX) in Windows Store.</span><span class="sxs-lookup"><span data-stu-id="07c26-146">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="07c26-147">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="07c26-147">In This Section</span></span>

<span data-ttu-id="07c26-148">Per altre informazioni sullo sviluppo di applicazioni con la compilazione con .NET Native, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="07c26-148">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>

- [<span data-ttu-id="07c26-149">Introduzione alla compilazione con .NET Native: procedura dettagliata dell'esperienza di sviluppatore</span><span class="sxs-lookup"><span data-stu-id="07c26-149">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](getting-started-with-net-native.md)

- <span data-ttu-id="07c26-150">[Compilazione e .NET Native:](net-native-and-compilation.md) compilazione di un progetto in codice nativo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="07c26-150">[.NET Native and Compilation:](net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>

- [<span data-ttu-id="07c26-151">Reflection e .NET Native</span><span class="sxs-lookup"><span data-stu-id="07c26-151">Reflection and .NET Native</span></span>](reflection-and-net-native.md)

  - [<span data-ttu-id="07c26-152">API basate sulla reflection</span><span class="sxs-lookup"><span data-stu-id="07c26-152">APIs That Rely on Reflection</span></span>](apis-that-rely-on-reflection.md)

  - [<span data-ttu-id="07c26-153">Riferimento all'API Reflection</span><span class="sxs-lookup"><span data-stu-id="07c26-153">Reflection API Reference</span></span>](net-native-reflection-api-reference.md)

  - [<span data-ttu-id="07c26-154">Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="07c26-154">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)

- [<span data-ttu-id="07c26-155">Serializzazione e metadati</span><span class="sxs-lookup"><span data-stu-id="07c26-155">Serialization and Metadata</span></span>](serialization-and-metadata.md)

- <span data-ttu-id="07c26-156">[Migrating Your Windows Store App to .NET Native](migrating-your-windows-store-app-to-net-native.md) (Migrazione dell'app di Windows Store a .NET Native)</span><span class="sxs-lookup"><span data-stu-id="07c26-156">[Migrating Your Windows Store App to .NET Native](migrating-your-windows-store-app-to-net-native.md)</span></span>

- [<span data-ttu-id="07c26-157">Risoluzione dei problemi generale per .NET Native</span><span class="sxs-lookup"><span data-stu-id="07c26-157">.NET Native General Troubleshooting</span></span>](net-native-general-troubleshooting.md)
