---
title: 'Procedura: Compilare un assembly su singolo file'
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a73b2d8948c9a046fd77c02f1bcc87f5738105d9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303999"
---
# <a name="how-to-build-a-single-file-assembly"></a>Procedura: Compilare un assembly su singolo file

Un assembly su singolo file, che rappresenta il tipo di assembly più semplice, contiene le informazioni e l'implementazione relative al tipo, oltre al [manifesto dell'assembly](../../../docs/framework/app-domains/assembly-manifest.md). Per creare un assembly con un singolo file, è possibile usare i compilatori della riga di comando o Visual Studio. Per impostazione predefinita, il file di assembly creato dal compilatore ha l'estensione exe.

> [!NOTE]
> È possibile usare Visual Studio per C# e Visual Basic solo per creare assembly con un singolo file. Per creare assembly con più file, è necessario usare i compilatori della riga di comando o Visual C++.

Le procedure seguenti illustrano come creare assembly su singolo file usando i compilatori della riga di comando.

## <a name="to-create-an-assembly-with-an-exe-extension"></a>Per creare un assembly con estensione exe

1. Al prompt dei comandi digitare il seguente comando:

     \<*comando compilatore*> \<*nome modulo*>

     In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.

 L'esempio seguente crea un assembly denominato `myCode.exe` da un modulo di codice denominato `myCode`.

```console
csc myCode.cs
```

```console
vbc myCode.vb
```

### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a>Per creare un assembly con estensione exe e specificare il nome del file di output

1. Al prompt dei comandi digitare il seguente comando:

     \<*comando compilatore*> **/out:**\<*nome file*> \<*nome modulo*>

     In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice, *nome file* è il nome del file di output e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.

 L'esempio seguente crea un assembly denominato `myAssembly.exe` da un modulo di codice denominato `myCode`.

```console
csc -out:myAssembly.exe myCode.cs
```

```console
vbc -out:myAssembly.exe myCode.vb
```

## <a name="creating-library-assemblies"></a>Creazione di assembly di librerie
 Un assembly di librerie è simile a una libreria di classi. L'assembly contiene tipi a cui altri assembly faranno riferimento, ma non ha alcun punto di ingresso per avviare l'esecuzione.

### <a name="to-create-a-library-assembly"></a>Per creare un assembly di librerie

1. Al prompt dei comandi digitare il seguente comando:

     \<*comando compilatore*> **-t:library** \<*nome modulo*>

     In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice e *nome modulo* è il nome del modulo di codice da compilare nell'assembly. È possibile usare anche altre opzioni del compilatore, ad esempio l'opzione **-out:**.

 L'esempio seguente crea un assembly di librerie denominato `myCodeAssembly.dll` da un modulo di codice denominato `myCode`.

```console
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```console
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a>Vedere anche

- [Creazione degli assembly](../../../docs/framework/app-domains/create-assemblies.md)
- [Assembly su più file](../../../docs/framework/app-domains/multifile-assemblies.md)
- [Procedura: Compilare un assembly con più file](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [Programmazione con gli assembly](../../../docs/framework/app-domains/programming-with-assemblies.md)