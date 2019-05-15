---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
ms.openlocfilehash: d8f9c9aac87fd71b61a5413386582ae660efd903
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593081"
---
# <a name="-win32resource"></a>-win32resource
Inserisce un file di risorse Win32 nel file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a>Argomenti  
 `filename`  
 Il nome del file di risorse da aggiungere al file di output. Racchiudere il nome file racchiuso tra virgolette ("") se contiene uno spazio.  
  
## <a name="remarks"></a>Note  
 È possibile creare un file di risorse Win32 con il compilatore di risorse (RC) di Microsoft Windows.  
  
 Una risorsa Win32 può contenere versione o le informazioni di bitmap (icona) che consente di identificare l'applicazione in **Esplora File**. Se non si specifica `-win32resource`, il compilatore genera le informazioni sulla versione in base alla versione dell'assembly. Il `-win32resource` e `-win32icon` opzioni si escludono a vicenda.  
  
 Visualizzare [- linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) per fare riferimento a un file di risorse .NET Framework, o [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) per allegare un file di risorse .NET Framework.  
  
> [!NOTE]
>  Il `-win32resource` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `In.vb` e allegare il file di risorse Win32, `Rf.res`:  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
