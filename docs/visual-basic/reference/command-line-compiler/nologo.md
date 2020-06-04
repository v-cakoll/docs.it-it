---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: d1307603ebc06b4eb4c3786f1cd2fb432c0cf636
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360462"
---
# <a name="-nologo-visual-basic"></a>-nologo (Visual Basic)
Evita la visualizzazione del banner sul copyright e dei messaggi informativi durante la compilazione.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a>Osservazioni  
 Se si specifica `-nologo` , il compilatore non visualizza un banner sul copyright. Per impostazione predefinita, l'opzione `-nologo` non è attiva.  
  
> [!NOTE]
> L' `-nologo` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `T2.vb` e non visualizza un banner sul copyright.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
