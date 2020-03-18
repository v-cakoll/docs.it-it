---
title: -addmodule (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
ms.openlocfilehash: 148a63c37cfbc4c60448adccde10947e91e22bb9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970180"
---
# <a name="-addmodule-c-compiler-options"></a>-addmodule (opzioni del compilatore C#)
Questa opzione aggiunge un modulo creato con l'opzione target:module nella compilazione in corso.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a>Argomenti  
 `file`, `file2`  
 Un file di output che contiene i metadati. Il file non può contenere un manifesto dell'assembly. Per importare più di un file, separare i nomi dei file con una virgola o con un punto e virgola.  
  
## <a name="remarks"></a>Osservazioni  
 In fase di esecuzione tutti i moduli aggiunti con **-addmodule** devono essere nella stessa directory del file di output. Ovvero, è possibile specificare un modulo in una directory in fase di compilazione, ma il modulo deve essere nella directory dell'applicazione in fase di esecuzione. Se il modulo non è nella directory dell'applicazione in fase di esecuzione, verrà restituita un'eccezione <xref:System.TypeLoadException>.  
  
 `file` non può contenere un assembly. Ad esempio, se il file di output è stato creato con [-target:module](./target-module-compiler-option.md), i relativi metadati possono essere importati con **-addmodule**.  
  
 Se il file di output è stato creato con un'opzione **-target** diversa da **-target:module**, i relativi metadati non possono essere importati con l'opzione **-addmodule**, ma possono essere impostati con l'opzione [-reference](./reference-compiler-option.md).  
  
 L'opzione del compilatore non è disponibile in Visual Studio. Un progetto non può fare riferimento a un modulo. Inoltre, l'opzione del compilatore non può essere modificata a livello di codice.  
  
## <a name="example"></a>Esempio  
 Compilare un file di origine `input.cs` e aggiungere i metadati da `metad1.netmodule` e `metad2.netmodule` per creare `out.exe`:  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
- [Assiemi multifile](../../../framework/app-domains/multifile-assemblies.md)
- [Procedura: Compilare un assembly su più file](../../../framework/app-domains/build-multifile-assembly.md)
