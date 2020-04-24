---
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: db6b047f521d8ef44d2bd1b70b654a4233ebb1a7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347918"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
Fa in modo che il compilatore non faccia automaticamente riferimento alle librerie standard.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a>Osservazioni  
 L' `-nostdlib` opzione rimuove il riferimento automatico all'assembly System. dll e impedisce al compilatore di leggere il file Vbc. rsp. Il file Vbc. rsp, che si trova nella stessa directory del file Vbc. exe, fa riferimento agli assembly di .NET Framework di uso comune e importa `System` gli `Microsoft.VisualBasic` spazi dei nomi e.  
  
> [!NOTE]
> Viene sempre fatto riferimento agli assembly mscorlib. dll e Microsoft. VisualBasic. dll.  
  
> [!NOTE]
> L' `-nostdlib` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene compilato `T2.vb` senza fare riferimento alle librerie standard. Per rimuovere l' `My` oggetto `_MYTYPE` , è necessario impostare la costante di compilazione condizionale sulla stringa "Empty".  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Vedi anche

- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Personalizzazione degli oggetti disponibili in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
