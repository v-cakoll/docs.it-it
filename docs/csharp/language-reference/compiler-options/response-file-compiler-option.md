---
title: '@ (opzioni del compilatore C#)'
ms.date: 07/20/2015
f1_keywords:
- '@'
helpviewer_keywords:
- response files, specifying for compilation [C#]
- '@ compiler option'
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
ms.openlocfilehash: d8e5c0ec148754c3e4cebfa32ad9f44a0bb0119e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70202905"
---
# <a name="-c-compiler-options"></a>@ (opzioni del compilatore C#)
L'opzione @ consente di specificare un file che contiene le opzioni del compilatore e i file di codice sorgente da compilare.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
@response_file  
```  
  
## <a name="arguments"></a>Argomenti  
 `response_file`  
 File che elenca le opzioni del compilatore o i file di codice sorgente da compilare.  
  
## <a name="remarks"></a>Osservazioni  
 Le opzioni del compilatore e i file di codice sorgente verranno elaborati dal compilatore come se fossero stati specificati nella riga di comando.  
  
 Per specificare più di un file di risposta in una compilazione, specificare più opzioni di file di risposta. Ad esempio:  
  
```console  
@file1.rsp @file2.rsp  
```  
  
 In un file di risposta, più opzioni del compilatore e file di codice sorgente possono essere contenuti in una sola riga. La specificazione di una singola opzione del compilatore deve essere contenuta in una sola riga (non può estendersi su più righe). I file di risposta possono contenere commenti che iniziano con il simbolo #.  
  
 Specificare le opzioni del compilatore da un file di risposta equivale a eseguire tali comandi dalla riga di comando. Per altre informazioni, vedere [Compilazione dalla riga di comando](./how-to-set-environment-variables-for-the-visual-studio-command-line.md).  
  
 Il compilatore elabora le opzioni di comando quando vengono rilevate. Di conseguenza, gli argomenti della riga di comando possono eseguire l'override di opzioni elencate in precedenza nei file di risposta. Viceversa, le opzioni in un file di risposta eseguiranno l'override delle opzioni elencate in precedenza nella riga di comando o in altri file di risposta.  
  
 In C# è disponibile il file csc.rsp, che si trova nella stessa directory del file csc.exe. Vedere [-noconfig](./noconfig-compiler-option.md) per ulteriori informazioni su csc.rsp.  
  
 Questa opzione del compilatore non può essere impostata nell'ambiente di sviluppo di Visual Studio, né modificata a livello di codice.  
  
## <a name="example"></a>Esempio  
 Di seguito sono riportate alcune righe da un file di risposta di esempio:  
  
```console  
# build the first output file  
-target:exe -out:MyExe.exe source1.cs source2.cs  
```  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
