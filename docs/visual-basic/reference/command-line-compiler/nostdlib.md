---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3764409f13a00f6d8a050bfbdd0f59e537a5ded3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652718"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
Indica al compilatore di non riferimento automaticamente alle librerie standard.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a>Note  
 Il `-nostdlib` opzione rimuove il riferimento automatico all'assembly System. dll e impedisce al compilatore di leggere il file Vbc.rsp. Il file Vbc. rsp, che si trova nella stessa directory del file Vbc.exe, fa riferimento usati comunemente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] gli assembly e le importazioni il `System` e `Microsoft.VisualBasic` gli spazi dei nomi.  
  
> [!NOTE]
>  Gli assembly Mscorlib.dll e Microsoft.VisualBasic.dll vengono sempre fatto riferimento.  
  
> [!NOTE]
>  Il `-nostdlib` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `T2.vb` senza fare riferimento alle librerie standard. È necessario impostare il `_MYTYPE` costante di compilazione condizionale per la stringa "Empty" per rimuovere il `My` oggetto.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Personalizzazione degli oggetti disponibili in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
