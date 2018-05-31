---
title: -pathmap (opzioni del compilatore C#)
ms.date: 05/16/2018
f1_keywords:
- /pathmap
helpviewer_keywords:
- -pathmap compiler option [C#]
- pathmap compiler option [C#]
- /pathmap compiler option [C#]
ms.openlocfilehash: 36196ffea19cfde7ff5f830ea358d2bd83edf419
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2018
ms.locfileid: "34472814"
---
# <a name="-pathmap-c-compiler-options"></a>-pathmap (opzioni del compilatore C#)

L'opzione del compilatore **-pathmap** specifica come eseguire il mapping di percorsi fisici ai nomi di percorso di origine restituiti dal compilatore.

## <a name="syntax"></a>Sintassi

```console
-pathmap:path1=sourcePath1,path2=sourcePath2
```

## <a name="arguments"></a>Argomenti

 `path1` Percorso completo per i file di origine nell'ambiente corrente

 `sourcePath1` Percorso di origine con cui sostituire `path1` in tutti i file di output.

Per specificare più percorsi di origine mappati, separarli con una virgola.

## <a name="remarks"></a>Note

Il compilatore scrive il percorso di origine nell'output per i motivi seguenti:

1. Il percorso di origine viene sostituito per un argomento quando si applica <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> a un parametro facoltativo.
1. Il percorso di origine è incorporato in un file PDB.
1. Il percorso del file PDB è incorporato in un file PE (eseguibile portabile).

Questa opzione esegue il mapping di ogni percorso fisico nel computer in cui viene eseguito il compilatore in un percorso corrispondente che deve essere scritto nei file di output.

## <a name="example"></a>Esempio

Compilare `t.cs` nella directory **c:\\work\\tests** ed eseguire il mapping di tale directory a **\publish** nell'output:

```console
csc -pathmap:C:\work\tests=\publish t.cs
```

## <a name="see-also"></a>Vedere anche

 [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
