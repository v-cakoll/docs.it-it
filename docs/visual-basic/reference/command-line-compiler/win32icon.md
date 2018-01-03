---
title: /win32icon
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4fc5210d2dcf30d9c4603b67b890c78510af1338
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="win32icon"></a>/win32icon
Inserisce un file ICO nel file di output. Il file ICO rappresenta il file di output in **Esplora File**.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`filename`|Il file ico da aggiungere al file di output. Racchiudere il nome del file tra virgolette ("") se contiene uno spazio.|  
  
## <a name="remarks"></a>Note  
 È possibile creare un file ico con il compilatore di risorse (RC) di Microsoft Windows. Il compilatore di risorse viene richiamato quando si compila un programma Visual C++. nel file RC, viene creato un file ico. Il `/win32icon` e `/win32resource` opzioni si escludono a vicenda.  
  
 Vedere [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) per fare riferimento un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse, o [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) per collegare un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse. Vedere [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) per importare un file con estensione res.  
  
|Per impostare /win32icon nell'IDE di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2.  Fare clic sulla scheda **Applicazione** .<br />3.  Modificare il valore di **icona** casella.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `In.vb` e allega un file ico, `Rf.ico`.  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
