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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac495e10be2ec1534dc9d9081aef369773d93e17
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933051"
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
  
 Visualizzare [- linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) per fare riferimento a un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse, o [-risorse (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) collegare un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse.  
  
> [!NOTE]
>  Il `-win32resource` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `In.vb` e allegare il file di risorse Win32, `Rf.res`:  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
