---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: c57ed1699d110959e9faf3dc3d43bcc200851c1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005441"
---
# <a name="-noconfig"></a>-noconfig
Specifica che il compilatore non deve fare riferimento automaticamente agli assembly .NET Framework di uso comune o importare gli spazi dei nomi `System` e `Microsoft.VisualBasic`.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a>Note  
 L'opzione `-noconfig` indica al compilatore di non eseguire la compilazione con il file Vbc. rsp, che si trova nella stessa directory del file Vbc. exe. Il file Vbc. rsp fa riferimento agli assembly .NET Framework di uso comune e importa gli spazi dei nomi `System` e `Microsoft.VisualBasic`. Il compilatore fa riferimento in modo implicito all'assembly System. dll, a meno che non venga specificata l'opzione `-nostdlib`. L'opzione `-nostdlib` indica al compilatore di non eseguire la compilazione con Vbc. rsp o di fare automaticamente riferimento all'assembly System. dll.  
  
> [!NOTE]
> Viene sempre fatto riferimento agli assembly mscorlib. dll e Microsoft. VisualBasic. dll.  
  
 È possibile modificare il file Vbc. rsp per specificare altre opzioni del compilatore da includere in ogni compilazione vbc. exe, tranne quando si specifica l'opzione `-noconfig`. Per altre informazioni, vedere [@ (specifica di un file di risposta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 Il compilatore elabora le opzioni passate al comando `vbc` per ultimo. Pertanto, qualsiasi opzione nella riga di comando esegue l'override dell'impostazione della stessa opzione nel file Vbc. rsp.  
  
> [!NOTE]
> L'opzione `-noconfig` non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="see-also"></a>Vedere anche

- [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [@ (Specifica di un file di risposta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
