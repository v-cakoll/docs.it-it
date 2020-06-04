---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 52ef0b991554c800dba4320b0c64c81ddd1b0ff4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414285"
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
  
## <a name="remarks"></a>Commenti  
 È possibile creare un file con estensione ico con il compilatore di risorse di Microsoft Windows (RC). Il compilatore di risorse viene richiamato quando si compila un programma di Visual C++; un file con estensione ICO viene creato dal file RC. Le opzioni `-win32icon` e `-win32resource` si escludono reciprocamente.  
  
 Vedere [-linkresource ((Visual Basic)](linkresource.md) per fare riferimento a un file di risorse .NET Framework o [-Resource (Visual Basic)](resource.md) per alleghire un file di risorse .NET Framework. Vedere [-win32resource (](win32resource.md) per importare un file con estensione res.  
  
|Per impostare-win32icon nell'IDE di Visual Studio|  
|---|  
|1. è stato selezionato un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**. <br />2. fare clic sulla scheda **applicazione** .<br />3. modificare il valore nella casella **icona** .|  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `In.vb` e connette un file con estensione ico `Rf.ico` .  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
