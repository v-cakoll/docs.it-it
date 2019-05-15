---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: b707899c845b6b08e008fe229497f682c930044a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65588855"
---
# <a name="-noconfig"></a>-noconfig
Specifica che il compilatore deve automaticamente riferimento agli assembly .NET Framework comunemente usati o importare la `System` e `Microsoft.VisualBasic` gli spazi dei nomi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a>Note  
 Il `-noconfig` opzione indica al compilatore di non eseguire la compilazione con il file Vbc. rsp, che si trova nella stessa directory del file Vbc.exe. Il file Vbc. rsp fa riferimento all'assembly di .NET Framework comunemente utilizzati e Importa il `System` e `Microsoft.VisualBasic` gli spazi dei nomi. Il compilatore fa riferimento in modo implicito all'assembly System. dll, a meno che il `-nostdlib` opzione specificata. Il `-nostdlib` opzione indica al compilatore di non eseguire la compilazione con Vbc. rsp o automaticamente fare riferimento all'assembly System. dll.  
  
> [!NOTE]
>  Gli assembly mscorlib. dll e VisualBasic vengono sempre fatto riferimento.  
  
 È possibile modificare il file Vbc. per specificare altre opzioni del compilatore che devono essere incluse in ogni compilazione Vbc.exe (tranne quando si specifica il `-noconfig` opzione). Per altre informazioni, vedere [@ (specifica di un file di risposta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 Il compilatore elabora le opzioni passate al `vbc` ultimo comando. Pertanto, qualsiasi opzione nella riga di comando sostituisce l'impostazione dell'opzione stesso nel file Vbc. rsp.  
  
> [!NOTE]
>  Il `-noconfig` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="see-also"></a>Vedere anche

- [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [@ (Specifica di un file di risposta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [-riferimenti (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
