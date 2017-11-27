---
title: /optimize
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dead17435cd147bdcdf91bdc5b8e0aa651e9e9fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="optimize"></a>/optimize
Abilita o disabilita le ottimizzazioni del compilatore.  
  
## <a name="syntax"></a>Sintassi  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Argomenti  
  
|Termine|Definizione|  
|---|---|  
|`+` &#124; `-`|Parametro facoltativo. Il `/optimize-` opzione Disabilita le ottimizzazioni del compilatore. Il `/optimize+` opzione consente di abilitarle. Per impostazione predefinita, le ottimizzazioni sono disabilitate.|  
  
## <a name="remarks"></a>Note  
 Le ottimizzazioni del compilatore verificare il file di output più piccoli, più veloce e più efficiente. Tuttavia, poiché le ottimizzazioni comportano una riorganizzazione del codice nel file di output, `/optimize+` può rendere difficile il debug.  
  
 Tutti i moduli generati con `/target:module` per un assembly deve utilizzare lo stesso `/optimize` le impostazioni dell'assembly. Per ulteriori informazioni, vedere [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).  
  
 È possibile combinare la `/optimize` e `/debug` opzioni.  
  
|Per impostare /optimize nell'ambiente di sviluppo integrato di Visual Studio|  
|---|  
|1.  Selezionare un progetto in **Esplora soluzioni**. Scegliere **Proprietà** dal menu **Progetto**.<br />     Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Fare clic sulla scheda **Compila**.<br />3.  Fare clic su **Avanzate** .<br />4.  Modificare il **abilitare le ottimizzazioni** casella di controllo.|  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `T2.vb` e abilita le ottimizzazioni del compilatore.  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
