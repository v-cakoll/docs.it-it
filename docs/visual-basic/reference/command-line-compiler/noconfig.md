---
title: /noconfig
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 94d13ccf0168027f4560b980c41e2a001ff503fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="noconfig"></a>/noconfig
Specifica che il compilatore non deve automaticamente fare riferimento usati comunemente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assembly o importazione di `System` e `Microsoft.VisualBasic` gli spazi dei nomi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/noconfig  
```  
  
## <a name="remarks"></a>Note  
 Il `/noconfig` opzione indica al compilatore di non eseguire la compilazione con tale file si trova nella stessa directory del file Vbc.exe. Il file Vbc.rsp fa riferimento a usati comunemente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assembly e le importazioni di `System` e `Microsoft.VisualBasic` gli spazi dei nomi. Il compilatore fa riferimento in modo implicito all'assembly System. dll, a meno che il `/nostdlib` è specificata l'opzione. Il `/nostdlib` opzione indica al compilatore di non eseguire la compilazione con Vbc.rsp o automaticamente riferimento all'assembly System. dll.  
  
> [!NOTE]
>  Gli assembly Mscorlib.dll e Microsoft.VisualBasic.dll vengono sempre fatto riferimento.  
  
 È possibile modificare il file Vbc.rsp per specificare ulteriori opzioni del compilatore che devono essere incluse in ogni compilazione Vbc.exe (tranne quando si specifica il `/noconfig` opzione). Per altre informazioni, vedere [@ (specifica di un file di risposta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 Il compilatore elabora le opzioni passate per il `vbc` ultimo comando. Pertanto, qualsiasi opzione della riga di comando sostituisce l'impostazione dell'opzione stesso in tale file.  
  
> [!NOTE]
>  Il `/noconfig` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="see-also"></a>Vedere anche  
 [/nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [@ (Specifica di un file di risposta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)  
 [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
