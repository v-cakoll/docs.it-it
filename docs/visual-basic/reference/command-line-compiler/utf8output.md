---
title: /utf8output (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 23c7c308865a6b6afb07443a42090fff3d9e2efb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="utf8output-visual-basic"></a>/utf8output (Visual Basic)
Visualizza l'output del compilatore usando la codifica UTF-8.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/utf8output[+ | -]  
```  
  
## <a name="arguments"></a>Argomenti  
 `+` &#124; `-`  
 Parametro facoltativo. Il valore predefinito per questa opzione è `/utf8output-`, ovvero non verrà utilizzata la codifica UTF-8. Specifica di `/utf8output` è lo stesso effetto `/utf8output+`.  
  
## <a name="remarks"></a>Note  
 In alcune configurazioni internazionali, output del compilatore non può essere visualizzato correttamente nella console di. In tali situazioni, utilizzare `/utf8output` e reindirizzare l'output del compilatore in un file.  
  
> [!NOTE]
>  Il `/utf8output` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `In.vb` e indica al compilatore di visualizzare l'output utilizzando la codifica UTF-8.  
  
```  
vbc /utf8output in.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
