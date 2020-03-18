---
title: -noconfig (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
ms.openlocfilehash: 2d6d0c52be2306292224d7831f8818c6f865f2f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602744"
---
# <a name="-noconfig-c-compiler-options"></a>-noconfig (opzioni del compilatore C#)
L'opzione **-noconfig** indica al compilatore di non eseguire la compilazione con il file csc.rsp, che si trova in e viene caricato dalla stessa directory del file csc.exe.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a>Osservazioni  
 Il file csc.rsp fa riferimento a tutti gli assembly forniti con .NET Framework. I riferimenti effettivi inclusi nell'ambiente di sviluppo di Visual Studio .NET dipendono dal tipo di progetto.  
  
 È possibile modificare il file csc.rsp e specificare opzioni del compilatore aggiuntive che devono essere incluse in ogni compilazione dalla riga di comando con csc.exe (ad eccezione dell'opzione **-noconfig).**  
  
 Le opzioni passate al comando **csc** verranno elaborate nel compilatore per ultime. Le opzioni della riga di comando eseguiranno pertanto l'override delle impostazioni relative alle stesse opzioni nel file csc.rsp.  
  
 Se non si desidera che il compilatore cerchi e utilizzi le impostazioni nel file csc.rsp, specificare **-noconfig**.  
  
 Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
