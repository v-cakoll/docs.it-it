---
title: Applicazioni a 64 bit
ms.date: 03/30/2017
helpviewer_keywords:
- applications [C++], 64-bit
- 64-bit applications [C++]
- 64-bit programming [C++]
ms.assetid: fd4026bc-2c3d-4b27-86dc-ec5e96018181
ms.openlocfilehash: 90e022d5643dc49ccc5b78d071b3b473c92f0670
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74429660"
---
# <a name="64-bit-applications"></a>Applicazioni a 64 bit
Quando si compila un'applicazione, è possibile specificare che deve essere eseguita in un sistema operativo Windows a 64 bit come applicazione nativa o in WOW64 (Windows a 32 bit in Windows a 64 bit). WOW64 è un ambiente di compatibilità che consente di eseguire in un sistema a 64 bit un'applicazione a 32 bit. WOW64 è incluso in tutte le versioni a 64 bit del sistema operativo Windows.  
  
## <a name="running-32-bit-vs-64-bit-applications-on-windows"></a>Confronto tra l'esecuzione di applicazioni a 32 bit e a 64 bit in Windows  
 Tutte le applicazioni basate su .NET Framework 1.0 o 1.1 sono considerate applicazioni a 32 bit in un sistema operativo a 64 bit e vengono sempre eseguite in WOW64 e in Common Language Runtime (CLR) a 32 bit. Le applicazioni a 32 bit basate su .NET Framework 4 o versioni successive vengono eseguite anche in WOW64 in sistemi a 64 bit.  
  
 Visual Studio installa la versione a 32 bit di CLR in un computer x86 e sia la versione a 32 bit che la versione a 64 bit appropriata di CLR in un computer Windows a 64 bit. Poiché Visual Studio è un'applicazione a 32 bit, quando viene installato in un sistema a 64 bit, viene eseguito in WOW64.  
  
> [!NOTE]
> Data la progettazione dell'emulazione x86 e del sottosistema WOW64 per la famiglia di processori Itanium, l'esecuzione delle applicazioni è limitata a un solo processore. Questi fattori riducono le prestazioni e la scalabilità delle applicazioni .NET Framework a 32 bit eseguite in sistemi basati su Itanium. Si consiglia di usare .NET Framework 4, che include il supporto a 64 bit nativo per sistemi basati su Itanium, per migliorare le prestazioni e la scalabilità.  
  
 Per impostazione predefinita, quando si esegue un'applicazione gestita a 64 bit in un sistema operativo Windows a 64 bit, non è possibile creare oggetti di più di 2 gigabyte (GB). Tuttavia, in .NET Framework 4.5 è possibile aumentare questo limite.  Per ulteriori informazioni, vedere [ \<l'elemento> gcAllowVeryLargeObjects](./configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md).  
  
 Molti assembly vengono eseguiti allo stesso modo sia su CLR a 32 bit che su CLR a 64 bit. Tuttavia, alcuni programmi possono comportarsi in modo diverso, a seconda della versione di CLR, se contengono uno o più dei seguenti elementi:  
  
- Strutture contenenti membri che cambiano dimensione in base alla piattaforma (ad esempio, tutti i tipi puntatore).  
  
- Operazioni aritmetiche che includono dimensioni costanti.  
  
- Dichiarazioni pInvoke o COM non corrette che usano `Int32` anziché `IntPtr` per gli handle.  
  
- Codice che esegue il cast di `IntPtr` a `Int32`.  
  
 Per altre informazioni su come eseguire il trasferimento di un'applicazione a 32 bit in modo che funzioni in CLR a 64 bit, vedere [Migrating 32-bit Managed Code to 64-bit](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973190(v=msdn.10)) (Migrazione del codice gestito da 32 bit a 64 bit).  
  
## <a name="general-64-bit-programming-information"></a>Informazioni generali sulla programmazione a 64 bit  
 Per informazioni generali sulla programmazione a 64 bit, vedere i seguenti documenti:  
  
- Nella documentazione di Windows SDK, vedere la sezione di [guida alla programmazione per Windows a 64 bit](/windows/win32/winprog64/programming-guide-for-64-bit-windows).  
  
- Per informazioni sul supporto di Visual Studio per la creazione di applicazioni a 64 bit, vedere [Supporto a 64 bit per IDE di Visual Studio](/visualstudio/ide/visual-studio-ide-64-bit-support).  
  
## <a name="compiler-support-for-creating-64-bit-applications"></a>Supporto dei compilatori per la creazione di applicazioni a 64 Bit  
 Per impostazione predefinita, quando si usa .NET Framework per compilare un'applicazione in un computer a 32 bit o a 64 bit, l'applicazione verrà eseguita in un computer a 64 bit come applicazione nativa (ovvero, non in WOW64). La tabella seguente elenca i documenti che illustrano come usare i compilatori di Visual Studio per creare applicazioni a 64 bit che verranno eseguite come native, in WOW64 o in entrambi i modi.  
  
|Compilatore|Opzione del compilatore|  
|--------------|---------------------|  
|Visual Basic|[-platform (Visual Basic)](../visual-basic/reference/command-line-compiler/platform.md)|  
|Visual C#|[-platform (opzioni del compilatore C](../csharp/language-reference/compiler-options/platform-compiler-option.md)|  
|Visual C++|È possibile creare applicazioni Microsoft Intermediate Language (MSIL) indipendenti dalla piattaforma usando **/clr:safe**. Per ulteriori informazioni, vedere [-clr (compilazione Common Language Runtime)](/cpp/build/reference/clr-common-language-runtime-compilation).<br /><br /> Visual C++ include un compilatore separato per ogni sistema operativo a 64 bit. Per altre informazioni sull'uso di Visual C++ per creare applicazioni native eseguibili in un sistema operativo Windows a 64 bit, vedere [Programmazione a 64 bit con Visual C++](/cpp/build/configuring-programs-for-64-bit-visual-cpp).|  
  
## <a name="determining-the-status-of-an-exe-file-or-dll-file"></a>Determinazione dello stato di un file EXE o di un file DLL  
 Per determinare se un file EXE o un file DLL deve essere eseguito solo su una piattaforma specifica o in WOW64, usare [CorFlags.exe (strumento di conversione CorFlags)](./tools/corflags-exe-corflags-conversion-tool.md) senza opzioni. È anche possibile usare CorFlags.exe per modificare lo stato della piattaforma di un file EXE o di un file DLL. Il numero di versione del runtime principale dell'intestazione CLR di un assembly di Visual Studio è impostato su 2, mentre quello secondario è impostato su 5. Le applicazioni con la versione di runtime secondaria impostata su 0 sono considerate applicazioni legacy e vengono sempre eseguite in WOW64.  
  
 Per eseguire query a livello di codice di un file EXE o DLL per determinare se deve essere eseguito solo su una piattaforma specifica o in WOW64, usare il metodo <xref:System.Reflection.Module.GetPEKind%2A?displayProperty=nameWithType>.
