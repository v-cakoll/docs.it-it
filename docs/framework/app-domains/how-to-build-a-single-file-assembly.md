---
title: 'Procedura: compilare un assembly su singolo file'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bd9f2bab23fff1bbc4ebb521b167ac8031af3bc7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-build-a-single-file-assembly"></a>Procedura: compilare un assembly su singolo file
Un assembly su singolo file, che rappresenta il tipo di assembly più semplice, contiene le informazioni e l'implementazione relative al tipo, oltre al [manifesto dell'assembly](../../../docs/framework/app-domains/assembly-manifest.md). Per creare un assembly su singolo file, è possibile usare i compilatori della riga di comando o [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]. Per impostazione predefinita, il file di assembly creato dal compilatore ha l'estensione exe.  
  
> [!NOTE]
>  È possibile usare [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] per C# e Visual Basic solo per la creazione di assembly su singolo file. Per creare assembly su più file, è necessario usare i compilatori della riga di comando o [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] per Visual C++.  
  
 Le procedure seguenti illustrano come creare assembly su singolo file usando i compilatori della riga di comando.  
  
### <a name="to-create-an-assembly-with-an-exe-extension"></a>Per creare un assembly con estensione exe  
  
1.  Al prompt dei comandi digitare il seguente comando:  
  
     \<*comando compilatore*> \<*nome modulo*>  
  
     In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.  
  
 L'esempio seguente crea un assembly denominato `myCode.exe` da un modulo di codice denominato `myCode`.  
  
```csharp  
csc myCode.cs  
```  
  
```vb  
vbc myCode.vb  
```  
  
#### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a>Per creare un assembly con estensione exe e specificare il nome del file di output  
  
1.  Al prompt dei comandi digitare il seguente comando:  
  
     \<*comando compilatore*> **/out:**\<*nome file*> \<*nome modulo*>  
  
     In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice, *nome file* è il nome del file di output e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.  
  
 L'esempio seguente crea un assembly denominato `myAssembly.exe` da un modulo di codice denominato `myCode`.  
  
```csharp  
csc /out:myAssembly.exe myCode.cs  
```  
  
```vb  
vbc /out:myAssembly.exe myCode.vb  
```  
  
## <a name="creating-library-assemblies"></a>Creazione di assembly di librerie  
 Un assembly di librerie è simile a una libreria di classi. L'assembly contiene tipi a cui altri assembly faranno riferimento, ma non ha alcun punto di ingresso per avviare l'esecuzione.  
  
#### <a name="to-create-a-library-assembly"></a>Per creare un assembly di librerie  
  
1.  Al prompt dei comandi digitare il seguente comando:  
  
     \<*comando compilatore*> **/t:library** \<*nome modulo*>  
  
     In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice e *nome modulo* è il nome del modulo di codice da compilare nell'assembly. È possibile usare anche altre opzioni del compilatore, ad esempio l'opzione **/out:**.  
  
 L'esempio seguente crea un assembly di librerie denominato `myCodeAssembly.dll` da un modulo di codice denominato `myCode`.  
  
```csharp  
csc /out:myCodeLibrary.dll /t:library myCode.cs  
```  
  
```vb  
vbc /out:myCodeLibrary.dll /t:library myCode.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione degli assembly](../../../docs/framework/app-domains/create-assemblies.md)  
 [Assembly su più file](../../../docs/framework/app-domains/multifile-assemblies.md)  
 [Procedura: Compilare un assembly su più file](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [Programmazione con gli assembly](../../../docs/framework/app-domains/programming-with-assemblies.md)
