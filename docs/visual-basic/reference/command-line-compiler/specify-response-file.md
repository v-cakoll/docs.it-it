---
title: '@ (specificare il file di risposta) (Visual Basic)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: 6b993a6399eec4e203821109db153aadf246cbac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61639022"
---
# <a name="-specify-response-file-visual-basic"></a>@ (specificare il file di risposta) (Visual Basic)
Specifica un file che contiene le opzioni del compilatore e file di codice sorgente da compilare.  
  
## <a name="syntax"></a>Sintassi  
  
```  
@response_file  
```  
  
## <a name="arguments"></a>Argomenti  
 `response_file`  
 Obbligatorio. Un file che elenca le opzioni del compilatore o file del codice sorgente da compilare. Racchiudere il nome file racchiuso tra virgolette ("") se contiene uno spazio.  
  
## <a name="remarks"></a>Note  
 Il compilatore elabora le opzioni del compilatore e file del codice sorgente specificati in un file di risposta come se fossero stati specificati nella riga di comando.  
  
 Per specificare più di un file di risposta in una compilazione, specificare più opzioni di file di risposta, come illustrato di seguito.  
  
```  
@file1.rsp @file2.rsp  
```  
  
 Una risposta di file, più opzioni del compilatore e file del codice sorgente possono essere visualizzati in una sola riga. Specifica una singola opzione del compilatore deve essere visualizzato in una sola riga (non può estendersi su più righe). File di risposta possono contenere commenti che iniziano con la `#` simbolo.  
  
 È possibile combinare le opzioni specificate nella riga di comando con le opzioni specificate in uno o più file di risposta. Il compilatore elabora le opzioni di comando quando vengono rilevate. Di conseguenza, gli argomenti della riga di comando possono ignorare le opzioni elencate in precedenza nel file di risposta. Al contrario, le opzioni in un file di risposta ignorano le opzioni elencate in precedenza nella riga di comando o in altri file di risposta.  
  
 Visual Basic fornisce il file Vbc. rsp, che si trova nella stessa directory del file Vbc.exe. Tale file è incluso per impostazione predefinita, a meno che il `-noconfig` opzione viene utilizzata. Per altre informazioni, vedere [- noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).  
  
> [!NOTE]
>  Il `@` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Le righe seguenti provengono da un file di risposta di esempio.  
  
```console
# build the first output file  
-target:exe   
-out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come usare il `@` opzione con il file di risposta denominato `File1.rsp`.  
  
```console
vbc @file1.rsp  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
