---
title: -utf8output
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 0a16cdc535de5ed0619bf080bb4637449b11cfef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403057"
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)
Visualizza l'output del compilatore usando la codifica UTF-8.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Facoltativa. Il valore predefinito per questa opzione è `-utf8output-` , il che significa che l'output del compilatore non usa la codifica UTF-8. Specificare `-utf8output` equivale a specificare `-utf8output+`.  
  
## <a name="remarks"></a>Commenti  
 In alcune configurazioni internazionali, l'output del compilatore non può essere visualizzato correttamente nella console. In tali situazioni, utilizzare `-utf8output` e reindirizzare l'output del compilatore in un file.  
  
> [!NOTE]
> L' `-utf8output` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `In.vb` e indirizza il compilatore per visualizzare l'output usando la codifica UTF-8.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
