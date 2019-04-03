---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: 44bc619c489fdff36f0b595f7d8934689b859adb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819437"
---
# <a name="-noconfig"></a>-noconfig
Specifica che il compilatore non deve automaticamente fare riferimento usati comunemente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] l'importazione o l'assembly la `System` e `Microsoft.VisualBasic` gli spazi dei nomi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a>Note  
 Il `-noconfig` opzione indica al compilatore di non eseguire la compilazione con il file Vbc. rsp, che si trova nella stessa directory del file Vbc.exe. Il file Vbc. rsp fa riferimento il diffuso [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] gli assembly e le importazioni il `System` e `Microsoft.VisualBasic` gli spazi dei nomi. Il compilatore fa riferimento in modo implicito all'assembly System. dll, a meno che il `-nostdlib` opzione specificata. Il `-nostdlib` opzione indica al compilatore di non eseguire la compilazione con Vbc. rsp o automaticamente fare riferimento all'assembly System. dll.  
  
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
