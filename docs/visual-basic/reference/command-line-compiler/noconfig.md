---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: ee7cd1b8039a8d9312a8b058cc85c41ca536ed2b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401940"
---
# <a name="-noconfig"></a>-noconfig
Specifica che il compilatore non deve fare riferimento automaticamente agli assembly .NET Framework di uso comune o importare gli `System` `Microsoft.VisualBasic` spazi dei nomi e.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a>Osservazioni  
 L' `-noconfig` opzione indica al compilatore di non eseguire la compilazione con il file Vbc. rsp, che si trova nella stessa directory del file Vbc. exe. Il file Vbc. rsp fa riferimento agli assembly di .NET Framework di uso comune e importa gli `System` `Microsoft.VisualBasic` spazi dei nomi e. Il compilatore fa riferimento in modo implicito all'assembly System. dll, a meno che non `-nostdlib` venga specificata l'opzione. L' `-nostdlib` opzione indica al compilatore di non eseguire la compilazione con Vbc. rsp o di fare automaticamente riferimento all'assembly System. dll.  
  
> [!NOTE]
> Viene sempre fatto riferimento agli assembly mscorlib. dll e Microsoft. VisualBasic. dll.  
  
 È possibile modificare il file Vbc. rsp per specificare altre opzioni del compilatore da includere in ogni compilazione vbc. exe, tranne quando si specifica l' `-noconfig` opzione. Per ulteriori informazioni, vedere [@ (specificare il file di risposta)](specify-response-file.md).  
  
 Il compilatore elabora le opzioni passate al `vbc` comando per ultimo. Pertanto, qualsiasi opzione nella riga di comando esegue l'override dell'impostazione della stessa opzione nel file Vbc. rsp.  
  
> [!NOTE]
> L' `-noconfig` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="see-also"></a>Vedere anche

- [-nostdlib (Visual Basic)](nostdlib.md)
- [Compilatore della riga di comando di Visual Basic](index.md)
- [@ (Specifica di un file di risposta)](specify-response-file.md)
- [-Reference (Visual Basic)](reference.md)
