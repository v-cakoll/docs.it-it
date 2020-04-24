---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 03dc98c45a894304a67765c3e49cd19bbb089c8c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335439"
---
# <a name="-nologo-visual-basic"></a>-nologo (Visual Basic)
Evita la visualizzazione del banner sul copyright e dei messaggi informativi durante la compilazione.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a>Osservazioni  
 Se si specifica `-nologo`, il compilatore non visualizza un banner sul copyright. Per impostazione predefinita, l'opzione `-nologo` non è attiva.  
  
> [!NOTE]
> L' `-nologo` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `T2.vb` e non visualizza un banner sul copyright.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>Vedi anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
