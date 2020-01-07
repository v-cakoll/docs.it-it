---
title: Panoramica dell'interoperabilità - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- C# language, interoperability
- C++ Interop
- interoperability, about interoperability
- platform invoke
ms.assetid: c025b2e0-2357-4c27-8461-118f0090aeff
ms.openlocfilehash: 2e1b31817873324fd320a9dcbabaf5ef26fa7b74
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635184"
---
# <a name="interoperability-overview-c-programming-guide"></a>Cenni preliminari sull'interoperabilità (Guida per programmatori C#)
In questo argomento vengono descritti i metodi per consentire l'interoperabilità tra il codice gestito C# e il codice non gestito.  
  
## <a name="platform-invoke"></a>Platform invoke  
 *Platform invoke* è un servizio che consente al codice gestito di chiamare funzioni non gestite implementate in librerie di collegamento dinamico (DLL), come quelle nell'API Microsoft Windows. Individua e richiama una funzione esportata ed esegue il marshalling degli argomenti (Integer, stringhe, matrici, strutture e così via) nel limite dell'interazione, in base alle necessità.  
  
Per ulteriori informazioni, vedere Utilizzo di [funzioni dll non gestite](../../../framework/interop/consuming-unmanaged-dll-functions.md) e [come utilizzare Platform Invoke per riprodurre un file WAV](./how-to-use-platform-invoke-to-play-a-wave-file.md).
  
> [!NOTE]
> Il [Common Language Runtime](../../../standard/clr.md) (CLR) gestisce l'accesso alle risorse di sistema. La chiamata di codice non gestito esterno al CLR ignora questo meccanismo di sicurezza e presenta pertanto un rischio per la sicurezza. Ad esempio, il codice non gestito può chiamare direttamente le risorse nel codice non gestito, ignorando i meccanismi di sicurezza CLR. Per altre informazioni, vedere [Sicurezza in .NET](../../../standard/security/index.md).  
  
## <a name="c-interop"></a>interoperabilità C++  
 È possibile usare l'interoperabilità C++, nota anche come It Just Works (IJW), per eseguire il wrapping di una classe C++ nativa in modo che possa essere usata dal codice creato in C# o in un altro linguaggio .NET Framework. A tale scopo, scrivere codice C++ per eseguire il wrapping di un componente COM o DLL nativo. A differenza di altri linguaggi .NET Framework, Visual C++ offre un tipo di supporto per l'interoperabilità che permette la presenza di codice gestito e non gestito nella stessa applicazione e anche nello stesso file. Compilare quindi il codice C++ mediante l'opzione del compilatore **/clr** per produrre un assembly gestito. Infine, aggiungere un riferimento all'assembly nel progetto C# e usare gli oggetti con wrapping esattamente come si userebbero altre classi gestite.  
  
## <a name="exposing-com-components-to-c"></a>Esposizione di componenti COM a C\#
 È possibile usare un componente COM da un progetto C#. I passaggi principali sono i seguenti:  
  
1. Individuare un componente COM da usare e registrarlo. Usare regsvr32.exe per registrare o annullare la registrazione di una DLL COM.  
  
2. Aggiungere al progetto un riferimento alla libreria dei componenti o dei tipi COM.  
  
     Quando si aggiunge il riferimento, Visual Studio usa [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../../../framework/tools/tlbimp-exe-type-library-importer.md), che accetta una libreria dei tipi come input, per generare un assembly di interoperabilità di .NET Framework. L'assembly, denominato anche Runtime Callable Wrapper (RCW), contiene le classi gestite e le interfacce che eseguono il wrapping delle classi e interfacce COM presenti nella libreria dei tipi. Visual Studio aggiunge al progetto un riferimento all'assembly generato.  
  
3. Creare un'istanza di una classe definita nell'RCW. Essa, a sua volta, crea un'istanza dell'oggetto COM.  
  
4. Usare l'oggetto allo stesso modo di altri oggetti gestiti. Quando l'oggetto viene recuperato da Garbage Collection, anche l'istanza dell'oggetto COM viene rilasciata dalla memoria.  
  
 Per altre informazioni, vedere [Esposizione di componenti COM a .NET Framework](../../../framework/interop/exposing-com-components.md).  
  
## <a name="exposing-c-to-com"></a>Esposizione di C# a COM  
 I client COM possono usare i tipi di C# che sono stati esposti in modo corretto. I passaggi di base per esporre tipi di C# sono i seguenti:  
  
1. Aggiungere gli attributi di interoperabilità nel progetto C#.  
  
     È possibile rendere un assembly visibile a COM modificando le proprietà del progetto Visual C#. Per altre informazioni, vedere [Finestra di dialogo Informazioni assembly](/visualstudio/ide/reference/assembly-information-dialog-box).  
  
2. Generare una libreria dei tipi COM e registrarla per l'uso di COM.  
  
     È possibile modificare le proprietà del progetto Visual C# per registrare automaticamente l'assembly C# per l'interoperabilità COM. Visual Studio usa [Regasm.exe (strumento di registrazione di assembly)](../../../framework/tools/regasm-exe-assembly-registration-tool.md), tramite l'opzione della riga di comando `/tlb`, che accetta un assembly gestito come input, per generare una libreria dei tipi. Questa libreria dei tipi descrive i tipi `public` nell'assembly e aggiunge le voci del Registro di sistema in modo che i client COM possano creare classi gestite.  
  
 Per altre informazioni, vedere [Esposizione di componenti .NET Framework a COM](../../../framework/interop/exposing-dotnet-components-to-com.md) e [Esempio di classe COM](./example-com-class.md).  
  
## <a name="see-also"></a>Vedere anche

- [Improving Interop Performance (Miglioramento delle prestazioni di interoperabilità)](https://docs.microsoft.com/previous-versions/msp-n-p/ff647812%28v=pandp.10%29)
- [Introduction to Interoperability between COM and .NET (Introduzione all'interoperabilità tra COM e .NET)](/office/client-developer/outlook/pia/introduction-to-interoperability-between-com-and-net)
- [Introduzione all'interoperabilità COM (Visual Basic)](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
- [Marshaling between Managed and Unmanaged Code (Marshalling tra codice gestito e non gestito)](../../../framework/interop/interop-marshaling.md)
- [Interoperabilità con codice non gestito](../../../framework/interop/index.md)
- [Guida per programmatori C#](../index.md)
