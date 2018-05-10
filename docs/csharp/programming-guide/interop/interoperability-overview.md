---
title: Cenni preliminari sull'interoperabilità (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- COM interop
- C# language, interoperability
- C++ Interop
- interoperability, about interoperability
- platform invoke
ms.assetid: c025b2e0-2357-4c27-8461-118f0090aeff
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 51a92f89415fd3750d8d2e1880be0d9c2867600d
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="interoperability-overview-c-programming-guide"></a>Cenni preliminari sull'interoperabilità (Guida per programmatori C#)
In questo argomento vengono descritti i metodi per consentire l'interoperabilità tra il codice gestito C# e il codice non gestito.  
  
## <a name="platform-invoke"></a>Platform invoke  
 *Platform invoke* è un servizio che consente al codice gestito di chiamare funzioni non gestite implementate in librerie a collegamento dinamico (DLL), come quelle nell'API Microsoft Win32. Individua e richiama una funzione esportata ed esegue il marshalling degli argomenti (Integer, stringhe, matrici, strutture e così via) nel limite dell'interazione, in base alle necessità.  
  
 Per altre informazioni, vedere [Consuming Unmanaged DLL Functions](../../../framework/interop/consuming-unmanaged-dll-functions.md) (Uso di funzioni DLL non gestite) e [Procedura: Usare platform invoke per riprodurre un file audio](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md).  
  
> [!NOTE]
>  Il [Common Language Runtime](../../../standard/clr.md) (CLR) gestisce l'accesso alle risorse di sistema. La chiamata di codice non gestito esterno al CLR ignora questo meccanismo di sicurezza e presenta pertanto un rischio per la sicurezza. Ad esempio, il codice non gestito può chiamare direttamente le risorse nel codice non gestito, ignorando i meccanismi di sicurezza CLR. Per altre informazioni, vedere [Protezione di .NET Framework](https://technet.microsoft.com/en-us/security/).  
  
## <a name="c-interop"></a>interoperabilità C++  
 È possibile usare l'interoperabilità C++, nota anche come It Just Works (IJW), per eseguire il wrapping di una classe C++ nativa in modo che possa essere usata dal codice creato in C# o in un altro linguaggio .NET Framework. A tale scopo, scrivere codice C++ per eseguire il wrapping di un componente COM o DLL nativo. A differenza degli altri linguaggi .NET Framework, [!INCLUDE[vcprvc](~/includes/vcprvc-md.md)] offre un supporto all'interoperabilità che consente la presenza di codice gestito e non gestito nella stessa applicazione e perfino nello stesso file. Compilare quindi il codice C++ mediante l'opzione del compilatore **/clr** per produrre un assembly gestito. Infine, aggiungere un riferimento all'assembly nel progetto C# e usare gli oggetti con wrapping esattamente come si userebbero altre classi gestite.  
  
## <a name="exposing-com-components-to-c"></a>Esposizione di componenti COM a C#  
 È possibile usare un componente COM da un progetto C#. La procedura generale è la seguente:  
  
1.  Individuare un componente COM da usare e registrarlo. Usare regsvr32.exe per registrare o annullare la registrazione di una DLL COM.  
  
2.  Aggiungere al progetto un riferimento alla libreria dei componenti o dei tipi COM.  
  
     Quando si aggiunge il riferimento, Visual Studio usa [Tlbimp.exe (utilità di importazione della libreria dei tipi)](../../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), che accetta una libreria dei tipi come input, per generare un assembly di interoperabilità di .NET Framework. L'assembly, denominato anche Runtime Callable Wrapper (RCW), contiene le classi gestite e le interfacce che eseguono il wrapping delle classi e interfacce COM presenti nella libreria dei tipi. Visual Studio aggiunge al progetto un riferimento all'assembly generato.  
  
3.  Creare un'istanza di una classe definita nell'RCW. Essa, a sua volta, crea un'istanza dell'oggetto COM.  
  
4.  Usare l'oggetto allo stesso modo di altri oggetti gestiti. Quando l'oggetto viene recuperato da Garbage Collection, anche l'istanza dell'oggetto COM viene rilasciata dalla memoria.  
  
 Per altre informazioni, vedere [Esposizione di componenti COM a .NET Framework](../../../../docs/framework/interop/exposing-com-components.md).  
  
## <a name="exposing-c-to-com"></a>Esposizione di C# a COM  
 I client COM possono usare i tipi di C# che sono stati esposti in modo corretto. I passaggi di base per esporre tipi di C# sono i seguenti:  
  
1.  Aggiungere gli attributi di interoperabilità nel progetto C#.  
  
     È possibile rendere un assembly visibile a COM modificando le proprietà del progetto Visual C#. Per altre informazioni, vedere [Finestra di dialogo Informazioni assembly](/visualstudio/ide/reference/assembly-information-dialog-box).  
  
2.  Generare una libreria dei tipi COM e registrarla per l'uso di COM.  
  
     È possibile modificare le proprietà del progetto Visual C# per registrare automaticamente l'assembly C# per l'interoperabilità COM. Visual Studio usa [Regasm.exe (strumento di registrazione di assembly)](../../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md), tramite l'opzione della riga di comando `/tlb`, che accetta un assembly gestito come input, per generare una libreria dei tipi. Questa libreria dei tipi descrive i tipi `public` nell'assembly e aggiunge le voci del Registro di sistema in modo che i client COM possano creare classi gestite.  
  
 Per altre informazioni, vedere [Esposizione di componenti .NET Framework a COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md) e [Esempio di classe COM](../../../csharp/programming-guide/interop/example-com-class.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Improving Interop Performance (Miglioramento delle prestazioni di interoperabilità)](https://msdn.microsoft.com/library/ms998551.aspx)  
 [Introduction to Interoperability between COM and .NET (Introduzione all'interoperabilità tra COM e .NET)](https://msdn.microsoft.com/library/office/bb610378.aspx)  
 [Introduzione all'interoperabilità COM (Visual Basic)](../../../../docs/visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)  
 [Marshaling between Managed and Unmanaged Code (Marshalling tra codice gestito e non gestito)](../../../../docs/framework/interop/interop-marshaling.md)  
 [Interoperabilità con codice non gestito](../../../../docs/framework/interop/index.md)  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
