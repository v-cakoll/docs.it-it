---
title: 'Procedura: compilare un assembly a file singolo .NET Framework'
description: Informazioni su come creare un assembly su singolo file in .NET. Un assembly con un solo file può essere una libreria (. dll) destinata a .NET oppure un file eseguibile (exe).
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
dev_langs:
- csharp
- vb
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
ms.openlocfilehash: 482a973631e899b8d4bfc4640eef1ea26173605e
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104918"
---
# <a name="how-to-build-a-net-framework-single-file-assembly"></a>Procedura: compilare un assembly a file singolo .NET Framework

Un assembly su singolo file, che rappresenta il tipo di assembly più semplice, contiene le informazioni e l'implementazione relative al tipo, oltre al [manifesto dell'assembly](../../standard/assembly/manifest.md). È possibile usare i compilatori della riga di comando o Visual Studio per creare un assembly a file singolo destinato al .NET Framework. Per impostazione predefinita, il compilatore crea un file di assembly con estensione *exe* .

> [!NOTE]
> È possibile usare Visual Studio per C# e Visual Basic solo per creare assembly con un singolo file. Per creare assembly con più file, è necessario usare i compilatori della riga di comando o Visual C++.

Le procedure seguenti illustrano come creare assembly su singolo file usando i compilatori della riga di comando.

## <a name="create-an-assembly-with-an-exe-extension"></a>Creare un assembly con estensione exe

Al prompt dei comandi digitare il comando seguente:

\<*compiler command*> \<*module name*>

In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.

Nell'esempio seguente viene creato un assembly denominato *myCode.exe* da un modulo di codice denominato `myCode` .

```csharp
csc myCode.cs
```

```vb
vbc myCode.vb
```

## <a name="create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a>Creare un assembly con estensione exe e specificare il nome del file di output

Al prompt dei comandi digitare il comando seguente:

\<*compiler command*>**/out:** \<*file name*>\<*module name*>

In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice, *nome file* è il nome del file di output e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.

Nell'esempio seguente viene creato un assembly denominato *myAssembly.exe* da un modulo di codice denominato `myCode` .

```csharp
csc -out:myAssembly.exe myCode.cs
```

```vb
vbc -out:myAssembly.exe myCode.vb
```

## <a name="create-library-assemblies"></a>Creazione di assembly di librerie
 Un assembly di librerie è simile a una libreria di classi. L'assembly contiene tipi a cui altri assembly faranno riferimento, ma non ha alcun punto di ingresso per avviare l'esecuzione.

Per creare un assembly di librerie, digitare il comando seguente al prompt dei comandi:

\<*compiler command*>**-t:Library**\<*module name*>

In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice e *nome modulo* è il nome del modulo di codice da compilare nell'assembly. È possibile usare anche altre opzioni del compilatore, ad esempio l'opzione **-out:**.

Nell'esempio seguente viene creato un assembly di libreria denominato *myCodeAssembly.dll* da un modulo di codice denominato `myCode` .

```csharp
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```vb
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a>Vedere anche

- [Creare assembly](../../standard/assembly/create.md)
- [Assembly su più file](multifile-assemblies.md)
- [Procedura: Creare un assembly su più file](build-multifile-assembly.md)
- [Programmare con gli assembly](../../standard/assembly/index.md)
