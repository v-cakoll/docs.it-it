---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 819505df2e7d5f93302f9ed601de856e36ed7124
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005409"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
Fa in modo che il compilatore non faccia automaticamente riferimento alle librerie standard.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a>Note  
 L'opzione `-nostdlib` rimuove il riferimento automatico all'assembly System. dll e impedisce al compilatore di leggere il file Vbc. rsp. Il file Vbc. rsp, che si trova nella stessa directory del file Vbc. exe, fa riferimento agli assembly di .NET Framework di uso comune e importa gli spazi dei nomi `System` e `Microsoft.VisualBasic`.  
  
> [!NOTE]
> Viene sempre fatto riferimento agli assembly mscorlib. dll e Microsoft. VisualBasic. dll.  
  
> [!NOTE]
> L'opzione `-nostdlib` non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `T2.vb` senza fare riferimento alle librerie standard. È necessario impostare la costante di compilazione condizionale `_MYTYPE` sulla stringa "Empty" per rimuovere l'oggetto `My`.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Personalizzazione degli oggetti disponibili in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
