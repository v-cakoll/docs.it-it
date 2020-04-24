---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 6b4b69d227c857442de6857fac023090b3698e81
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004638"
---
# <a name="-win32icon"></a>-win32icon
Inserisce un file con estensione ICO nel file di output. Il file ico rappresenta il file di output in **Esplora file**.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`filename`|File con estensione ico da aggiungere al file di output. Racchiudere il nome file tra virgolette ("") se contiene uno spazio.|  
  
## <a name="remarks"></a>Osservazioni  
 È possibile creare un file con estensione ico con il compilatore di risorse di Microsoft Windows (RC). Il compilatore di risorse viene richiamato quando si compila un programma di Visual C++; un file con estensione ICO viene creato dal file RC. Le opzioni `-win32icon` e `-win32resource` si escludono reciprocamente.  
  
 Vedere [-linkresource ((Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) per fare riferimento a un file di risorse .NET Framework o [-Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) per alleghire un file di risorse .NET Framework. Vedere [-win32resource (](../../../visual-basic/reference/command-line-compiler/win32resource.md) per importare un file con estensione res.  
  
|Per impostare-win32icon nell'IDE di Visual Studio|  
|---|  
|1. è stato selezionato un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2. fare clic sulla scheda **applicazione** .<br />3. modificare il valore nella casella **icona** .|  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `In.vb` e connette un file con estensione ico. `Rf.ico`  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>Vedi anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
