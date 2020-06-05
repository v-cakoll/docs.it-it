---
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 0934799853323110e73087ba6d8975c30f84d8f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387712"
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
 Il codice seguente viene compilato `T2.vb` senza fare riferimento alle librerie standard. Per rimuovere l'oggetto, è necessario impostare la `_MYTYPE` costante di compilazione condizionale sulla stringa "Empty" `My` .  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [-noconfig](noconfig.md)
- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
- [Personalizzazione degli oggetti disponibili in My](../../developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
