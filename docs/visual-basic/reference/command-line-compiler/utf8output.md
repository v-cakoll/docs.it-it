---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: adcb518cbe8397549c3ae3b3a8ca9f0ecf9dc38e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004662"
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)
Visualizza l'output del compilatore usando la codifica UTF-8.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 facoltativo. Il valore predefinito per questa opzione è `-utf8output-`, il che significa che l'output del compilatore non usa la codifica UTF-8. Specificare `-utf8output` equivale a specificare `-utf8output+`.  
  
## <a name="remarks"></a>Note  
 In alcune configurazioni internazionali, l'output del compilatore non può essere visualizzato correttamente nella console. In tali situazioni, utilizzare `-utf8output` e reindirizzare l'output del compilatore in un file.  
  
> [!NOTE]
> L'opzione `-utf8output` non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente compila `In.vb` e indica al compilatore di visualizzare l'output usando la codifica UTF-8.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
