---
title: /win32resource
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d839b1100b1ae76fbd4653ebc60c79db11b77685
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="win32resource"></a>/win32resource
Inserisce un file di risorse Win32 nel file di output.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/win32resource:filename  
```  
  
## <a name="arguments"></a>Argomenti  
 `filename`  
 Il nome del file di risorse da aggiungere al file di output. Racchiudere il nome del file tra virgolette ("") se contiene uno spazio.  
  
## <a name="remarks"></a>Note  
 È possibile creare un file di risorse Win32 con il compilatore di risorse (RC) di Microsoft Windows.  
  
 Una risorsa Win32 può contenere una versione o le informazioni di bitmap (icona) che consente di identificare l'applicazione in **Esplora File**. Se non si specifica `/win32resource`, il compilatore genera le informazioni sulla versione in base alla versione di assembly. Il `/win32resource` e `/win32icon` opzioni si escludono a vicenda.  
  
 Vedere [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) per fare riferimento un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse, o [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) per collegare un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse.  
  
> [!NOTE]
>  Il `/win32resource` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `In.vb` e allegare il file di risorse Win32, `Rf.res`:  
  
```  
vbc /win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
